# AI 話做完時點樣先收貨：用一張 run receipt 看清交付、檢查、未知和下一步

當 Codex、Agent、Skill 或一條 AI workflow 顯示 done，很容易令人以為工作已完成。其實它通常只代表某次執行停止了：可能出了一份檔案、回覆了一段文字、或跑完一些工具。它未必代表 output 已被核對、未知已處理、範圍沒有越界，更不代表已發佈、已寫入系統、已證明有效。

若團隊只靠「done」、screenshot 或 AI 自己的說法交接，下一位 reviewer 要重新猜這次做過甚麼、用了哪些材料、哪裡仍不確定。久而久之，AI workflow 的 evidence 很難累積：每次都像重新開始，大家也難以判斷應 accept、revise 還是 stop。

Jimmy 的看法是：run receipt 是一張只記本輪工作的最小收貨證據。它不取代 work card，也不是 value／ROI report；它讓人知道本次 scope、approved input、artifact、checks、unknown 和 owner decision，令「AI 說 done」變成人能負責的下一個決定。

AI run receipt · AI agent · AI workflow · review · acceptance · unknown · owner · evidence

| 一張 run receipt 要記 | 它回答甚麼 | 為何重要 |
|---|---|---|
| Scope | 本輪只做／不做甚麼？ | 不把 run 當無限權限 |
| Approved input | 只讀過哪些類別？ | 可回看資料邊界 |
| Artifact | 交了甚麼位置／版本？ | 不是一句 done |
| Checks | 已核對甚麼？ | 可知道品質最低線 |
| Unknown／exception | 哪些未驗、缺資料、要停？ | 不讓不確定藏起來 |
| Owner decision | 誰 accept／revise／stop？ | AI 不可自行批准 |

## AI 說 done 點解還未算完成：執行停止不等於人已收貨

AI 完成一輪任務後，可能交了一份 draft、改了一個檔案或提出一組建議。這些是有用的 artifact，但仍需要有人判斷它是否符合當初 scope、是否只使用 approved input、是否有遺漏或越界。若沒有這一層，團隊很容易把「可 review」誤讀成「可以直接用」。

這個分別在高風險工作特別重要：外發、寫入 CRM、付款、刪除、公開設定和 production action，都不能因為 AI 說 done 就自動成立。即使低風險 internal draft，也應有清楚 status，讓下一位知道現在是 ready-for-review、revise 還是 stop，而不是留下含糊的完成感。

**Jimmy 的結論：** AI 的 done 是 execution status；人的 accept／revise／stop 才是工作 status。run receipt 正是把兩者分開的工具。

| AI 顯示甚麼 | 它真正代表 | 尚未代表甚麼 |
|---|---|---|
| Task completed | 這輪 action 已停止 | artifact 已被 owner 接受 |
| File created | 有一份交付候選 | 內容正確／可公開 |
| Tests passed | 某些檢查通過 | 所有業務風險消失 |
| Draft ready | 可交 reviewer 看 | 可以外發／寫 production |
| Agent replied | 有一份建議 | 人已作最終決定 |

若目前沒有 reviewer，也請把 status 留在 ready-for-review，而不是自行升級成 approved。誠實 status 能保護後續的人，也保護你的 evidence。

## Run receipt、work card 和 value proof card 有咩分別：三張卡回答三種問題

三種卡都會留下 evidence，容易被混在一起。work card 是長期設計：這個 AI 幫手負責甚麼工作、可讀甚麼、交甚麼 artifact、誰 review、何時停。run receipt 是一次執行：今次實際做了甚麼、出了甚麼、檢查了甚麼、還欠甚麼。value proof card 則是多次 run 之後：看到了甚麼可比較變化，值不值得 retain、revise、stop 或 scale。

若跳過 run receipt，value proof card 很容易只剩「好像快了」；若沒有 work card，receipt 又難知道本輪有沒有越界。三張卡不是文書負擔，而是對應 workflow 的不同時間尺度：設計、執行、決策。

**Jimmy 的結論：** 不要用一張卡承擔所有事。work card 定責任，run receipt 定本輪收貨，value proof card 定多輪價值；分開後每一個判斷才清楚。

| 你想回答的問題 | 用哪一張卡 | 何時寫 |
|---|---|---|
| AI 幫手長期負責甚麼？ | work card | 開始／改 workflow 時 |
| 它今次交了甚麼，可否收貨？ | run receipt | 每次重要 run 後 |
| 多次 run 有沒有看到價值？ | value proof card | 有足夠比較 evidence 後 |
| 這次可否直接外發？ | owner approval，不是卡本身 | 高風險 action 前 |

如果你剛剛做完一次 AI run，先寫 receipt；不要急著寫成公開 case study 或 ROI。先讓本輪 evidence 能被另一人看懂。

## Run receipt 怎樣寫 scope 和 input：只記接手所需證據，不複製私人材料

receipt 的第一格是 scope：本輪只做甚麼、不做甚麼。這看似簡單，卻能防止「整理三篇公開文章」在交接時被誤讀成「已完成完整研究」或「可直接對外發佈」。第二格是 approved input 類別，目的不是把每段原文、raw chat 或私人 asset 複製進去，而是讓 reviewer 知道資料邊界。

例如可以寫：本輪只將三個已批准 URL 整理成 internal draft；不新增事實、不讀 private drive、不寫對外貼文。這足夠令下一位知道這一輪是甚麼，也避免把客戶、CRM、合約、credentials、付款、私人筆記或 production data 為了「證明」而留在 receipt。

**Jimmy 的結論：** Receipt 要保留最小可追溯 evidence，不是保留所有對話。scope 和 input 寫清，才能讓收貨人知道本輪到底有沒有越界。

| Receipt 欄位 | 要記甚麼 | 不需要記甚麼 |
|---|---|---|
| Scope | 本輪只做／不做 | 所有可能 future action |
| Approved input | URL、schema、已批來源類別 | raw 私人資料全文 |
| Artifact | 檔名、版本、位置、簡述 | 每個 tool call transcript |
| Boundary | 不可讀／不可做 | 未來未批准 access |
| Status | ready-for-review 等 | 模糊的「已處理」 |

若內容涉及敏感資料，即使 receipt 本身也要遵守最小必要原則。記資料類別、權限狀態和 owner，通常比複製內容更安全。

## Run receipt 的 checks 和 unknown 怎樣寫：已驗證與尚未證明必須分開

「已 QA」不是一個有用的 check。check 要和本輪工作有關，例如每個具體主張是否回到 approved source、所有必填欄位是否存在、改動是否只在 working copy、artifact 是否符合 schema，或 reviewer 能否找到一個明確不合格例子。這些都應列清，讓下次能知道一輪 run 究竟經過哪些最低保護。

unknown／exception 同樣重要。資料不足、來源衝突、scope 外問題、review owner 缺席，都不應被 AI 或人偷偷補完。receipt 需要寫它們在哪裡、目前怎樣處理、是否已停在 internal queue。這不代表工作失敗；它代表團隊知道哪些地方還未能負責交出去。

**Jimmy 的結論：** 已檢查與仍未知必須分開。真正可靠的 receipt 不假裝零風險，它讓下一個 owner 一眼看見需要再判斷的地方。

| 本輪檢查 | 寫法例子 | 出現問題時 |
|---|---|---|
| Source check | 每個具體主張有 URL 或 unknown | flag，勿補猜 |
| Schema check | source、summary、unknown 齊全 | return draft |
| Boundary check | 無客戶資料、無外發 CTA | stop／移除 |
| Review check | owner 按 rubric 收貨 | accept／revise |
| Exception | 第三個來源方法不足 | 留 unknown，補資料後再跑 |

不要因為一項 check pass，便寫成「全部可靠」。check 只證明那一項符合；其他風險仍要由 scope、owner 和下次 evidence 處理。

## Owner decision 怎樣令 receipt 真正可收貨：accept、revise、stop 比「睇下先」清楚

receipt 最後需要一位 owner 的 decision。accept 代表本輪 artifact 在既定 scope 內可交下一手；revise 代表發現了明確需改的格；stop 代表 input、風險、scope 或 owner 條件未成立，不應繼續。這三個選項不是要把工作官僚化，而是讓團隊不再用模糊「好像可以」推進高風險 action。

status 也要誠實。ready-for-review 不等於 published；accepted internal draft 不等於已外發；一次 accepted 不等於流程已經可靠或值得擴大。這些層次保留後，receipt 才可以成為日後 value proof 和 governance decision 的乾淨 evidence。

**Jimmy 的結論：** Receipt 的最後一格不是 AI 自己寫 done，而是 owner 明確決定本輪下一步。人有收貨權，workflow 才有責任線。

| Decision | 何時用 | 下一步 |
|---|---|---|
| Accept | artifact 合乎本輪 scope 與 check | 交指定下一手／保留 receipt |
| Revise | 知道要補 input、format 或 rule | 只改明確一格後 rerun |
| Stop | 風險、資料、owner 或 scope 不成立 | 交 escalation／不繼續 action |
| Ready-for-review | 尚未有 owner decision | 等候 review，不外發 |

涉及寫入、付款、發送、刪除或公開設定時，receipt 不可代替 explicit human approval。把 approval 放在相應 action 前，才是安全做法。

## 一個公開安全例子：三篇公開文章的 internal research brief receipt

假設 AI 本輪任務是把三篇已批准公開文章整理成 internal research brief。scope 寫明只做 internal draft，不寫對外貼文、不新增事實、不讀 private drive。approved input 是三個公開 URL 和一個既定 briefing format；artifact 是一份 draft，內有三個重點、每點 source link 和 unknown list。

checks 記錄每個具體主張可回到 URL 或標 unknown，沒有未批准 CTA、客戶資料或對外承諾。exception 是第三篇缺少方法資料，因此保留 unknown，不補猜。reviewer 選 revise，要求補一個獨立來源後才可進下一輪；status 是 ready-for-review／revise，不是 published。

**Jimmy 的結論：** 這張 receipt 不證明研究已完美，也不證明內容可直接公開；它讓另一個人知道本輪確實做了甚麼、還欠甚麼、誰作了哪個決定。

| Receipt 格 | 例子內容 | 安全邊界 |
|---|---|---|
| Scope | 三個 URL → internal brief | 不外發、不新增事實 |
| Input | approved public URLs | 不讀私有資料 |
| Artifact | research-brief-draft.md | 只是 draft |
| Check | source／unknown／boundary | 不等於所有事實真確 |
| Exception | 第三 URL 方法不足 | 不補猜 |
| Decision | revise 後再 review | 不當作發佈批准 |

這是 synthetic 教學例子，不代表任何實際 client、文章或 production workflow。有價值的是 receipt 結構，而不是把私人資料放進去。

## 今日怎樣寫第一張 AI run receipt：用六格交代一輪工作，讓另一個人可決定下一步

找一輪你剛跑完的低風險 AI 工作，寫六格：本輪 scope、approved input、artifact、checks、unknown／exception、owner decision。每格一句已足夠，只要另一位 reviewer 能不用翻完聊天紀錄就理解這次發生了甚麼。若沒有 owner，先標 ready-for-review；不要替自己或 AI 宣佈 approved。

第一張 receipt 可以只留在本機或 private work folder。它不是對外 case study，也不是 ROI claim。當你有幾輪 receipt，才有乾淨 evidence 去看 rework、review time、repeatability，並決定是否寫 value proof card、改 workflow 或停止。

**Jimmy 的結論：** 一張好 receipt 的成功標準，是第二個人不靠 screenshot 或記憶，也能安全地 accept、revise 或 stop。這比 AI 說 done 更接近真完成。

| 六格模板 | 填甚麼 | 保護甚麼 |
|---|---|---|
| Scope | 本輪只做／不做 | 範圍不膨脹 |
| Input | approved／不可讀 | 資料邊界 |
| Artifact | 檔案／位置／版本 | 可交接證據 |
| Checks | 具體驗證項 | 品質最低線 |
| Unknown | 缺資料／例外／stop | 不確定可見 |
| Decision | owner + accept／revise／stop | 責任與下一步 |

要先為一條長期 workflow 定範圍，讀 [將一件重複工作寫成 AI work card](./練習-write-an-ai-work-card.md)；有多輪 receipt 後要判斷價值，讀 [為一次 AI 工作寫 value proof card](<../../05-AI Value Creator（AI價值創造者）/chapters/練習-write-an-ai-value-proof-card.md>)。

> 可靠不是 AI 說「完成」；是有人能看見這一輪做過甚麼、尚欠甚麼，並作出下一個決定。

← [返回 AI Builder](../README.md) · [按問題瀏覽](../../../學習地圖.md)
