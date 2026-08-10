# 接了幾個 connector，不等於你已經有 Agent system

把 AI 接到文件、表格、email 或其他工具，很容易令人覺得它終於「可以做事」。但 connector 只解決一件事：它能碰到哪個入口。它不會自動知道何時應做、可讀哪一份資料、誰收貨、遇到例外是否應停。

問題通常在接通後才出現：AI 能看更多資料，卻不知哪份是本輪批准材料；它能寫入某處，卻無人定義什麼才可寫；它能定時跑，卻沒有 receipt 告訴人是否做錯。工具連得愈多，這些沒有被定義的工作風險只會傳得更快。

Jimmy 的判斷是：connector 是手腳；Agent system 是有人把 trigger、input、工作規則、artifact、review、state 和 stop line 設計出來。先把工作系統說清，connector 才可能減少搬運，而不是把混亂擴散。

| 層次 | 要回答甚麼 | 沒有它會怎樣 |
|---|---|---|
| Connector | 能讀／寫哪個入口？ | 工具根本連不到 |
| Workflow | 何時、根據甚麼、交甚麼？ | AI 不知做哪段工作 |
| System | 誰驗收、例外怎樣停？ | 有 action 但無人負責 |

## AI connector 解決甚麼，為甚麼接通不等於可交工作？

Connector 令工具在技術上可以讀取、寫入或觸發另一個服務；例如把一個公開資料清單帶進摘要工作台。這很有價值，但它只說「可以到哪裡」，沒有說「應否去、應拿甚麼、結果可否採用」。

若工作沒有 scope，connector 反而會使問題更大：AI 看見更多材料卻無法分辨版本與權限，或把一個 draft 寫進正式位置。技術能力不能替代 work contract；任何讀寫能力都要先受限於本輪 artifact 和 boundary。

**Jimmy 的結論：** Connector 是能力入口，不是工作定義；先有可驗收 work unit，才決定是否需要接它。

| 有 connector | 仍要人／系統定義 |
|---|---|
| 可讀文件／表格 | 哪份屬 approved input |
| 可寫 draft | 哪裡只可 internal、誰批准正式寫入 |
| 可被 trigger | 甚麼情況才應開始 |

先問「沒有這條 connector，哪一段已清楚的工作做不到？」答不出，就先不要接。

## AI workflow 要有哪五格，connector 才不會把混亂傳得更快？

接工具前先寫五格：trigger、approved input、bounded action、artifact、review／stop。它們讓 connector 的讀寫能力只服務一段工作，而不是變成「AI 可以看和改任何東西」的模糊授權。

五格也讓你看到 connector 是否真有價值。若手動拿一條公開 URL、交一份 brief 已足夠，先跑 work card；若這個動作重複、資料範圍穩定、review 能處理，才值得連接入口減少搬運。

**Jimmy 的結論：** 先定 workflow，再接 connector；否則你只會把未定義工作更快地搬到更多系統。

| 五格 | 公開 briefing 例子 |
|---|---|
| Trigger | 指定公開 URL 被加入本輪清單 |
| Approved input | 只讀 URL、欄位定義、已批准格式 |
| Bounded action | 整理來源、重點、unknown、下一步 |
| Artifact | internal brief draft，不是外發內容 |
| Review／stop | editor review；缺來源／權限即停 |

當五格寫得出，connector 的角色就清楚：只把 approved input 送到 bounded action，不替 owner 作任何決定。

## AI connector 可以讀寫資料時，boundary 和 human approval 應放在哪裡？

讀取與寫入的風險不同。讀取要限制哪些資料可被看見；寫入更要限制目的地、可否覆蓋、是否只建立 draft。不能因工具技術上可用，就把客戶、合約、CRM、credentials 或 production data 當作一般 context。

Human approval 也不應放在最後一刻才想起。先在 workflow 寫清：哪些 output 永遠只停在 internal draft、哪些 action 必須由 owner 明確批准、哪些情況不准繼續。這讓 connector 可以做安全搬運，但不會把有後果的決定默認交給 AI。

**Jimmy 的結論：** Connector 的讀寫權限必須小於工作 scope；對外、不可逆、敏感或權限不清的 action 一律停在人手 approval 前。

| 能力 | 安全第一輪 | 不可直接做 |
|---|---|---|
| Read | 公開／synthetic、指定資料 | 私人 Vault、CRM、未批准文件 |
| Write | 新建 internal draft／queue | 覆蓋原檔、寫正式系統 |
| Send／deploy | 只產生候選內容 | 對外發送、production action |

這些 boundary 不是令 system 少功能；它是令你知道每個功能何時才值得被批准。

## 用公開資料摘要示範：connector、workflow 和 system 怎樣分工？

假設你把指定公開 URL 接入一個摘要工具。connector 的工作只是取得 URL 內容；workflow 定義它只交來源、三個重點、unknown 和下一步；system 再指定 editor 要 review 甚麼、資料不足時停在哪裡、哪個人決定是否採用角度。

若沒有後兩層，AI 就算每天自動生成 summary，也不能證明內容可信或值得採用。它可能讀錯版本、漏掉時間、把推論當事實，而沒有人知道哪一輪出事。把角色分開後，每層都可以被檢查。

**Jimmy 的結論：** 一個真正可管理的 Agent system，不是「AI 接到了資料」；而是 connector、workflow、review 和 owner 都有各自可驗收責任。

| 層 | 這個例子做甚麼 | 留下甚麼 |
|---|---|---|
| Connector | 取得指定公開 URL | approved input record |
| Workflow | 起四欄 internal brief | artifact 與 unknown |
| System | editor review、例外 stop | receipt／owner decision |

第一輪不要自動發布或接真資料。只要人能根據 receipt 判 pass、revise 或 stop，就已經比「接通很多工具」更接近系統。

## 想接新 connector 前，AI Builder 應怎樣做第一個安全決定？

第一步先選一段已經手動跑過、材料和 artifact 都穩定的低風險工作。用公開或 synthetic input 畫出五格，再問 connector 是否真的能減少某個明確搬運步驟；若工作本身仍不清楚，先不要接任何新入口。

跑一次 internal dry run 後，留下 input、artifact、check、unknown 和 owner decision。只有當同類流程多次穩定、例外有去處，才考慮增加讀寫範圍；任何外發、系統寫入、敏感資料或 production action 都仍需明確批准。

**Jimmy 的結論：** 先把工作系統做小、做清楚、做可停，connector 才會變成真正的槓桿，而不是更快傳播風險的管道。

| 你現在卡住的位置 | 接著讀甚麼 |
|---|---|
| 想先劃可讀／可改範圍 | [workbench contract](4-19-workbench-contract.md) |
| 想安全跑一段工作 | [先跑一條可停的 Agent loop](4-25-first-agent-loop.md) |
| 不知 prompt、Skill、automation 怎樣選 | [選最小足夠 working form](4-8-prompt-skill-automation-decision.md) |

可返回 [AI Builder stage](../04-ai-builder.md)。本文只用公開／synthetic 情境，不構成資料存取、系統寫入、外發或 production action 的批准。
