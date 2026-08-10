# 幾時應該行下一個 AI Stage？唔係睇工具，而係睇證據

做過一次漂亮 output，很容易令人覺得「可以升級」：加 automation、更多權限、更複雜 workflow，或者開更多 Agent。但一次成功可能只是 input 剛好齊、題目剛好簡單，或有人在最後補救。它不代表下一個範圍已經準備好。

下一個 AI stage 不是 badge。它代表你會增加一點 context、複雜度、權限或影響範圍；每加一層，例外、review 成本和責任也會增加。若沒有 evidence，所謂升級只是把未知與風險推到更大的工作面。

Jimmy 的看法是：AI 成長不是爬得愈快愈叻，而是每加一層複雜度前，都有足夠 evidence 證明你接得住。用 artifact、quality review、repeatability、control 和 owner 五個 gate，決定是試相鄰一步、留在原地練，還是先停下來修基礎。

AI 實戰 · AI Value Creator · stage readiness · evidence gate · governance · review · safe growth

| Evidence gate | 要看甚麼 | 未成立時怎樣做 |
|---|---|---|
| Artifact | input、output、版本可否回看 | 先由聊天變成可 review 工作物 |
| Quality | 有沒有標準與 reviewer | 補 context、rubric 或 acceptance |
| Repeatability | 是否見過多輪與例外 | 留在原範圍再跑 |
| Control | 可讀、不可做、stop line 是否清楚 | 不加權限、不接不可逆 action |
| Owner | 有沒有人維護、review、決定 | 不建立無主系統 |

## 一次成功點解不等於 ready：下一個 stage 會新增新的責任與風險

一條 workflow 在第一輪跑通，可以表示這個方向值得再看；但它不能證明不同資料、不同使用者、不同例外下都會穩定。特別是從 internal draft 走向 automation、從公開資料走向敏感資料、從一位 reviewer 走向多人使用，工作本身已經改變，不是原流程的自然延伸。

例如有人能把公開文章整理成一份 draft，不代表他已準備好讓 AI 直接發送內容。自動發送不只是多一個按鈕，它會新增收件人、承諾、時機、版本和 rollback 的責任。讀者若把 stage 當成工具難度表，就很容易忽略這些真正需要 evidence 的地方。

**Jimmy 的結論：** 下一個 stage 不是獎賞，而是一個新的工作範圍。先證明你能管理現有 input、artifact、review 和例外，才考慮增加權限或影響。

| 你想加的下一步 | 實際新增的是甚麼 | 先要有甚麼 evidence |
|---|---|---|
| 加 automation | 更少人手介入與更多例外 | repeatability 與 stop line |
| 加更多資料 | context 品質與私隱風險 | input boundary 與 source check |
| 加更多人使用 | 支援與一致性成本 | work card 與 owner capacity |
| 由 draft 變 send | 對外影響與承諾 | human approval 與 rollback |
| 拆成多 Agent | handoff 與責任複雜度 | artifact、rubric、escalation |

如果你只可以說「技術跑得到」，還沒有回答工作是否 ready。技術可行只是其中一個條件，不會自動取代治理和 owner。

## Artifact gate 怎樣確保工作可回看：先有一份人能收貨的結果

artifact 是一個可被人打開、比較、退回和修改的工作結果：可以是有 source 的 brief、固定欄位的 table、workflow note、review receipt 或 versioned draft。它讓團隊不需要依靠一段已經消失的 chat 記憶，也讓下一手知道 AI 到底交了甚麼。

若目前只有「AI 答得幾好」或「示範時有一個漂亮 output」，就還未有 artifact gate。先把 input、output 和版本留低，才可以讓 reviewer 指出問題，亦才有可能在下一輪比較有沒有改善。沒有 artifact 的 workflow，不能安全往上疊任何自動化。

**Jimmy 的結論：** 沒有可回看的 artifact，就沒有可靠的下一步。先把聊天結果變成可 review 工作物，才談 context、handoff 或更複雜的 AI system。

| 現在有甚麼 | Artifact gate 是否成立 | 下一步 |
|---|---|---|
| 一段 chat 答案 | 不成立 | 存成有欄位的 draft |
| 一份沒有來源的摘要 | 部分成立 | 補 source／unknown 欄 |
| 一張固定格式的 brief | 較成立 | 加 reviewer 與版本 |
| 一份有 review receipt 的 draft | 成立 | 可看 repeatability |
| 多輪 versioned artifact | 很好 | 可討論相鄰一步 |

artifact 不需要完美才有價值；它只要讓人能看見工作狀態。可回看是 evidence 的起點，不是最後格式要求。

## Quality 與 repeatability gate 點樣分開：有人收貨，亦要重跑過見到例外

一份 artifact 有 reviewer，不代表 workflow 已經準備好擴大。Quality gate 問的是：有沒有清楚標準與合適的人檢查？例如每個 claim 是否有來源、未知有否標記、格式是否可交下一手。這讓團隊知道一輪結果是否可以收貨。

Repeatability gate 則問：同一範圍是否跑過幾次、是否見過常見返工和例外？一次順利可能只是好彩；多輪 run 才會顯示 input 是否常缺、reviewer 是否每次都有不同意見、AI 是否在未知時會正確停下。兩個 gate 都要過，才有理由考慮增加一層變化。

**Jimmy 的結論：** Quality 令一輪結果可被驗收；repeatability 令你知道這個驗收在真工作裡能否持續。只有兩者都穩，才不要把一次成功複製到更大範圍。

| Gate | 要問的問題 | 不成立時先做甚麼 |
|---|---|---|
| Quality | 誰按甚麼標準收貨？ | 補 rubric、reviewer、acceptance |
| Repeatability | 跑過幾次？見過甚麼例外？ | 留在原範圍收 receipt |
| Quality 有、repeatability 無 | 一次可用但未知是否穩 | 先多跑幾次 |
| Repeatability 有、quality 無 | 重複做但無一致標準 | 先定 checklist |
| 兩者都有 | 結果與問題可比較 | 看 control 與 owner readiness |

不要把正常的 revise 或 unknown 當成 gate 失敗。它們是 repeatability evidence，能幫你知道下一輪要修 context、rule 還是 workflow。

## Control 與 owner gate 點樣防止錯誤擴大：知道可做甚麼，也要有人接得住

control gate 確保 AI 不會因為想完成任務而越界。它要寫清可讀甚麼、不可做甚麼、何時停，以及哪些 action 必須有人批准。沒有這些，你不應增加資料、寫入、外發或其他不可逆動作，因為問題一旦出現，團隊可能不知道怎樣關掉或交給誰。

owner gate 則確保這條 workflow 不會變成無主系統。有人要負責維護 input、看 review、處理 exception、決定 retain／revise／stop。當小 pilot 擴大，owner capacity 也要跟上；不可以因為 AI 看起來減少手工，就假設人不再需要承擔決定。

**Jimmy 的結論：** control 和 owner 是安全成長的最後兩道 gate。知道 AI 可以做甚麼不夠；還要知道它不能做甚麼、出事誰接、下一輪誰決定。

| Gate 問題 | 成立的證據 | 未成立時的正確決定 |
|---|---|---|
| AI 可讀甚麼？ | approved input bundle | 不擴到新資料 |
| AI 不可做甚麼？ | action boundary 與 stop line | 不加 send／publish 權限 |
| 誰 review？ | 指定 reviewer 與 rubric | 不當 output 是完成品 |
| 誰處理例外？ | escalation owner | 不讓 AI 猜過去 |
| 誰決定下一步？ | decision owner 與日期 | 停在現有範圍 |

如果 owner 不存在或沒有 capacity，答案不是加一個 manager Agent。先修人的責任線，才有任何 AI system 可以安全地擴大。

## 三種健康 readiness 答案：試相鄰一步、留在原地練，或停下來修基礎

五個 gate 的目的不是逼人全部過關才可以動，而是幫你誠實選下一步。當 artifact、quality、repeatability、control 和 owner 大致成立，可試相鄰一步：只加一個可 review step、另一位 reviewer，或一個可撤回 action，然後重新收 evidence。

若 artifact 或 quality 未清楚，留在原地練往往更快。把 input、格式、review 理順後，workflow 會自然變穩；不必把「還未升級」當作落後。若 control 或 owner 不存在，則應停下來修基礎；這不是失敗，而是避免一個未有人承擔的系統帶來更大風險。

**Jimmy 的結論：** readiness 最成熟的答案，不一定是「升」。能說出為何要 retain、revise 或 stop，代表團隊正在按 evidence 成長，而不是按焦慮成長。

| Gate 狀態 | 健康答案 | 下一步 |
|---|---|---|
| 五格大致成立 | 試相鄰一步 | 一次只增加一種可回退變化 |
| Artifact／quality 不穩 | 留在原地練 | 補 context、rubric、review |
| Repeatability 未證明 | 多跑原範圍 | 收 exception 與 outcome |
| Control／owner 缺失 | 停下修基礎 | 寫 stop line、指定 owner |
| 技術不可行 | 不升級 | 換方案或保持人手 |

這三種答案都比「因為大家在用，所以繼續加」更有價值。它們讓工作真正可控，也讓團隊不會以為成熟只等於複雜。

## 一個公開安全例子：internal draft 未穩定前，為何不應直接接自動發送

假設有人已用 AI 將公開資料整理成 internal draft，想直接接到自動發送。artifact 有：每次都有一頁 draft；但 quality 未穩：不同 reviewer 仍會大改；repeatability 未證明：只成功過一次；control 不足：還未寫清哪些 claim 不可用；owner 未定：沒人負責最後內容。

這個例子的結論不是「不能再用 AI」，而是目前不應增加 send 的 action。下一步是留在 AI Super User／Operator 的工作範圍：補 context、acceptance 和 review record，先讓 internal draft 穩定。自動發送根本未在今輪選項之內，因為它會新增對外責任和 rollback 需要。

**Jimmy 的結論：** readiness 地圖保護你不會把最有風險的下一步誤當成最有進步的下一步。先讓 draft work 有 evidence，之後才談更大權限。

| Gate | 例子狀態 | 正確處理 |
|---|---|---|
| Artifact | 有 | 保留 draft 與版本 |
| Quality | 未穩 | 對齊 reviewer rubric |
| Repeatability | 只跑一次 | 多跑原範圍 |
| Control | claim boundary 未寫 | 加 unknown／stop rule |
| Owner | 未定 | 指定 content owner |
| 下一步 | 想自動 send | 暫不加入，先修基礎 |

這個例子只談公開資料與 internal draft；它不允許 AI 對外發送、讀取私人／客戶資料、改公開設定或進 production。

## 今日怎樣檢查 readiness：五格未清楚，就補最早缺的一格

挑最近做過的一件低風險工作，逐格寫下：我可以回看的 artifact、誰用甚麼標準 review、我見過的例外／返工原因、停止線、下一輪 owner。這五格不是考試；它們是讓你看見哪一層還沒有 evidence。

若五格大致清楚，只選一個相鄰、可回退的下一步；若其中一格空白，就先補最早缺的一格。你會發現很多時候下一步不是「升」，而是把一份 context note、checklist 或 handoff 寫得更好。這樣的停留，通常比加入更多技術更快帶來可靠結果。

**Jimmy 的結論：** AI 成長唔係爬得愈快愈叻；係每加一層複雜度之前，都有足夠 evidence 證明你接得住。五格未清楚，下一步不是升級，而是補基礎。

| Readiness card | 你要留下甚麼 | 安全起點 |
|---|---|---|
| Artifact | input、output、version | 一頁 internal draft |
| Quality | reviewer 與 checklist | source／unknown check |
| Repeatability | 例外與 rework 原因 | 三次 run receipt |
| Control | 可讀、不可做、stop line | draft only、缺 evidence 即停 |
| Owner | review、escalation、decision 人 | content owner |
| 相鄰一步 | 只增加一種變化 | 多一位 reviewer，不加 send |

在這五格未清楚前，不要因為做過一次 demo 就加 automation、更多資料權限、外部發送、客戶／私人資料、公開設定或 production。接著可看 [如何診斷一條 AI adoption bottleneck](5-13-diagnose-adoption-bottleneck.md)。

> AI 成長唔係爬得愈快愈叻；係每加一層複雜度之前，都有足夠 evidence 證明你接得住。

← [返回 AI Value Creator](../05-ai-value-creator.md) · [查看五段地圖](../CURRENT-JOURNEY.md)
