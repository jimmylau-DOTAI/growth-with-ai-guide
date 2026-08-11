# AI 一遇資料不足就繼續猜？Skill 要先寫好 exception ladder，令它知道何時停

很多人寫 AI Skill 時，只寫「正常情況」：讀材料、分析、交 output。真正工作卻很少每次都正常。資料可能少了一份、來源可能互相矛盾、規則可能不通過、工具可能中斷，或者下一步忽然牽涉到對外 action、正本資料或權限。

如果 Skill 只寫「遇到問題請小心處理」，AI 通常仍然會想完成任務：它補一個看似合理的答案、重試到狀態愈來愈亂，或把應交給人的判斷偷偷做掉。結果不只是 output 不準，而是 reviewer 根本看不出它在哪一步猜了、哪一版仍可信、下一步誰應接手。

Jimmy 的判斷是：一份可交接的 Skill 不只要寫「怎樣做對」，還要寫「缺了、衝突了、失敗了或不該做時，應留低甚麼 state、由誰決定、在哪裡停」。exception ladder 就是把這些例外變成共同工作語言，讓 AI 可以安全地交出未完成狀態，而不是扮成已完成。

| 例外狀態 | 它出現的原因 | AI 要留下甚麼 | 下一步由誰做 |
| --- | --- | --- | --- |
| Needs input | 指定材料或必要欄位不足 | 欠缺項目清單 | 提供材料的人 |
| Needs approval | 來源衝突、範圍不清、責任要改變 | 分歧與選項 note | Named owner |
| Revise once | 已知格式／規則不通過 | Diff 與檢查結果 | AI 按明確規則修一次 |
| Failed safe | 工具中斷、狀態不明、不能可信重跑 | 已完成部分與錯誤 state | Operator／owner |
| Human release | 要外發、覆寫、付款、改權限 | Draft 與 review request | 人類 release owner |

## AI 遇到例外仍繼續猜，為甚麼比「做得慢」更危險？

AI 被要求完成一項工作時，通常很擅長把空白補成看起來順的答案。對文字草稿，這種傾向可能只是要多改一次；但對有來源、資料、狀態或外部 action 的工作，猜錯會把未確認內容混進可採用 output，甚至令下一個人以為流程已經安全完成。

例如一條 internal briefing workflow 指定要讀三份公開文章。若少了一份，AI 可以選擇明確標記「欠哪個 URL」，也可以自己用相似搜尋結果補一篇。前者保留了可追溯性；後者雖然交到一份看似完整的 brief，但它已經暗中改了任務和證據基礎。

**Jimmy 的結論：** AI 能夠停下並說清楚未完成甚麼，不是能力不足；這正是一條可靠 Skill 比「一路補到底」更可用的地方。

當例外發生時，先分辨它屬於哪一類：

| 你看見的情況 | 不應做的反應 | 較可靠的反應 |
| --- | --- | --- |
| 欠資料 | 用記憶或搜索結果硬補 | 列出缺項，標成 needs input |
| 兩個說法矛盾 | AI 自己挑一邊當事實 | 保留兩邊與原始位置，要求 approval |
| 格式不合格 | 順手重寫整個任務 | 只按已知 check revise once |
| 工具出錯 | 無限重跑或覆寫舊 output | 留 failed-safe state，讓人判斷重跑 |
| 要對外／改正本 | 直接執行，事後再通知 | 停在 human release，交 draft review |

這個分類令錯誤有名字、有去處；不必每次只靠「再試一次」或「叫 AI 小心」處理。

## Exception ladder 的五個狀態怎樣令 AI 和 reviewer 都知道下一步？

例外管理的目的不是把每一個小問題升級成危機，也不是令 AI 每一步都卡住等待。目的只是把不同責任放回不同狀態：資料不足由提供資料的人補、範圍或立場衝突由 owner 判斷、固定格式錯誤才容許 AI 依規則修正、外部 action 必須由有權的人 release。

當 status 名稱和 artifact 固定，reviewer 不必重新閱讀整段 chat 去猜發生甚麼。看見 `needs-input` 就知道要補材料；看見 `failed-safe` 就知道不能把半成品當結果；看見 `human-release` 就知道內容或變更尚未對外發生。這些都是可交接 workflow 的基本可讀 state。

**Jimmy 的結論：** Exception ladder 不是技術術語清單，而是讓工作不會在例外時失去 owner 的責任地圖；每個狀態都要說清「留下甚麼、誰接手、尚未做甚麼」。

可直接把五個狀態寫進 Skill：

1. **Needs input**：列明任務缺少的 input，暫停，不創作替代資料。
2. **Needs approval**：列出衝突、選項、影響，等待指定 owner 決定。
3. **Revise once**：只修正已寫清楚的 schema、格式或 quality check，輸出 diff。
4. **Failed safe**：保留成功部分、失敗位置、錯誤訊息和最後可信版本，不盲重跑。
5. **Human release**：只交草稿／變更預覽；任何外發、覆寫、付款、權限改動都停在人手批准前。

如果一個例外不能被放進任何狀態，這不是叫 AI 自由發揮的理由，而是提醒你這條 Skill 尚未寫清楚 scope 或責任。

## AI Skill 的 exception artifact 要寫到甚麼程度，人才可以安全接手？

一句「出錯了」幫不到下一位 owner；同樣地，一段很長的錯誤 log 也未必能讓人快速判斷。好的 exception artifact 要在很短時間內說清楚：原本要做甚麼、實際到了哪一步、問題是甚麼、AI 已做過甚麼、它刻意沒有做甚麼、需要誰決定甚麼。

這個 artifact 不必包含全部原始資料或私人內容。對公開安全／internal draft workflow 而言，保留指定來源名稱、欄位、狀態、選項和下一步已足夠；對敏感工作則應只保留必要 metadata，避免為了方便 review 而擴大資料曝光。

**Jimmy 的結論：** Exception artifact 的完成線不是記錄得很詳細，而是另一個人不用靠猜，也不用打開所有私有資料，就知道可否繼續、要補甚麼、應否停止。

一張最小 exception receipt 可以有這六欄：

| 欄位 | 要寫甚麼 |
| --- | --- |
| 任務與 run ID | 本次原本要處理哪一個工作單位 |
| 已完成部分 | 哪些 input 已讀、哪些 output 已生成 |
| 例外狀態 | needs input／approval／revise once／failed safe／human release |
| 證據或檢查 | 哪個欄位、來源或 check 觸發例外 |
| 未做 action | 它刻意沒有發送、覆寫、推測或擴大讀取甚麼 |
| 下一位與下一步 | 指定 owner 要補、選、review 或重跑甚麼 |

有了這份 receipt，AI 不再只是「成功／失敗」二元狀態，而是交出一個讓團隊可以管理的過渡狀態。

## Approval 放在哪些 AI action 前，才不會每一步都停死？

很多人擔心加 approval 會令 workflow 太慢，於是把所有判斷交給 AI；另一個極端則是每一個小修正都要求真人按一次掣，最後沒有人願意用。兩者的問題都是沒有區分「固定、低風險的修正」和「改變責任、外部狀態或不可回退結果的 action」。

一個合理的原則是：如果 action 只是在預先定義範圍內修正可回退草稿，並有清楚 schema／check，AI 可以 revise once；如果它會公開發送、覆寫正本、花費資源、改權限、接觸敏感資料，或把不確定內容當成事實，就應停在 owner approval。這不是不信任 AI，而是把責任放回正確位置。

**Jimmy 的結論：** Approval 不是「凡事問人」，而是用在會改變風險、責任或外部世界的分水嶺；其餘固定、可回退的工作才值得讓 AI 節省時間。

可用這個判斷表決定是否要停：

| Action | 一般處理方式 | 原因 |
| --- | --- | --- |
| 補回缺失格式、依 schema 改欄位 | 可 revise once | 範圍清楚、可 review、容易回退 |
| 把公開資料整理成 internal draft | 可做，但標記不確定 | output 仍在受控 review 內 |
| 選擇矛盾說法、改核心主張 | needs approval | 需要人承擔判斷與語境 |
| 發 email、排程社交內容、覆寫正本 | human release | 改變外部狀態，後果較高 |
| 改付款、權限、客戶／CRM 資料 | human release 或不在 scope | 敏感、通常不可只靠 AI 判斷 |

如果不確定 action 屬於哪一格，預設停下來並交 draft。先慢一格，通常比事後追回一個已發出的錯誤更快。

## 用一個 AI research brief 試跑 exception ladder，會怎樣發生？

假設一條低風險 workflow 每週把三篇已批准的公開文章整理成一份 internal research brief。它只可讀指定 URL，輸出只會放到一個草稿位置；任何對外發佈或關鍵結論都由內容 owner review。這種小任務足夠測試 exception ladder，亦不需要接 CRM、客戶資料或自動發佈。

當其中一篇 URL 失效，AI 的目的不是「想辦法生一份完整 brief」，而是交回一份正確的 `needs-input` receipt。當兩篇文章的主張不同，它應交 `needs-approval` note；當少了原始連結欄位，才可以在不改研究問題下 `revise-once`。這些狀態讓 owner 看見 workflow 有沒有真的守住界線。

**Jimmy 的結論：** 例外試跑的價值，不在於一次都沒出錯，而在於每次出錯都能留下可用的 state，讓你知道下一輪要補 input、補規則，還是根本縮小 scope。

這是一次可以安全驗收的 run：

| 發生甚麼 | AI 應留下甚麼 | 它絕對不應做甚麼 |
| --- | --- | --- |
| 少一篇指定來源 | `needs-input` 欠缺清單 | 用搜尋結果偷換來源 |
| 來源彼此矛盾 | `needs-approval` 兩邊摘要與原始連結 | 自己挑一邊寫成結論 |
| 漏必需欄位 | `revise-once` diff 和 check 結果 | 偷偷改變 brief 範圍 |
| 讀取中斷 | `failed-safe` 已讀項目與錯誤 state | 無限重試，覆蓋舊結果 |
| Owner 想發布 brief | `human-release` draft | 自行排程或發送 |

跑完後，檢查的不是「Agent 有冇做完」，而是每種例外有沒有去到正確 owner、留下正確 artifact、守住未做 action。

## 想為第一份 Skill 加 exception ladder，最安全的開始是甚麼？

不用由最重要、最高風險的 workflow 開始。挑一件低風險、只交 draft、你已做過幾次的重複工作，例如整理指定公開資料、把已批准筆記轉成 outline，或檢查一份不會直接覆寫正本的格式。這些工作足夠讓你看見資料不足、格式不合格和狀態中斷等真例外。

第一輪也不用寫盡所有可能。先從你真實見過的三個例外開始，為每一個寫 status、artifact、下一位 owner、可否 revise once、必停 action。下一次再遇到新例外，才決定它應加入 ladder、變成 quality check，還是代表整條工作 scope 要收窄。

**Jimmy 的結論：** Exception ladder 的第一步不是做一個全自動 Agent，而是令一條小 Skill 在不確定時懂得安全停下，並讓人可以接回工作。

可以立即做這五步：

1. 選一條只交 draft、可回退的重複工作。
2. 寫下三個真正遇過的例外，不要先幻想所有風險。
3. 為每個例外指定 status、receipt、owner 和未做 action。
4. 只讓 AI 按清楚 schema revise once；其餘判斷或外部 action 全部停下。
5. 跑一次用公開或 synthetic input 的 test，review receipt 後才補規則。

暫時不要因為寫好 exception ladder 就接 CRM、付款、客戶資料、正本覆寫或自動外發工具；它只證明你較能處理已知例外，不代表 workflow 已安全或 autonomous。若你未寫過完整 Skill，可先讀 [Skill 其實是一份工作合約](./4-23-skill-is-a-work-contract.md)；想把重複錯變成可重跑檢查，可讀 [最小 regression pack](./4-10-minimum-regression-pack.md)，需要另一個人或 AI 幫你核對時則讀 [設計獨立 review](./4-18-independent-review.md)。

← [返回 AI Builder](../README.md) · [按問題瀏覽](../../../README.md)
