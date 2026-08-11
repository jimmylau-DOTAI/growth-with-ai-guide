# AI 點解反覆犯同一個錯：不要只加 prompt，先把可檢查規則放到模型外面

你明明已經在 prompt 寫得很清楚：品牌名不要加空格、必須有五個欄位、日期要用指定格式。頭幾次 AI 做得很好，過一陣又犯回同一個錯；你再提醒一次，它又短暫變好。這種「好一陣、壞一次、再好一陣」最令人困惑，因為看起來它好像明白，又好像沒有學會。

問題通常不只是模型不夠聰明。長對話、工具輸出、compaction、不同執行環境和每次拿到的 context 都會令早期叮囑不再處於它眼前。你以為規則已經留在它腦裡，其實每一輪它都要靠當刻收到的材料重新理解工作；一句短、早、夾在聊天中間的提醒，很容易在長流程裡失去作用。

Jimmy 的看法是：要分開「AI 識不識做」與「同一條工作做不做得可靠」。前者主要是模型能力；後者需要把能講清楚的規則、格式和安全界線放到模型外面，以檢查、artifact、review 和 stop line 撐住。不是每個錯都要卡死，但能被客觀判斷的錯，不應永遠靠下一次 prompt 記得。

AI 反覆犯錯 · prompt · context window · AI memory · AI reliability · validation · guardrail · AI Builder

| 同一個錯反覆出現時 | 先問甚麼 | 應留下甚麼 |
|---|---|---|
| 規則是否仍在 context？ | 它這次真的看得見嗎？ | 可重用 rule card |
| 這個錯能否客觀判斷？ | 另一人按規則也能判對錯嗎？ | deterministic check |
| 錯了能否安全攔下？ | 會否直接流到下一步？ | review／stop line |
| 是規則還是 judgment？ | 情境改變時是否仍適用？ | boundary note |
| 下次如何不靠記憶？ | 可否自動／半自動驗證？ | receipt／checklist |

## AI 明明答應過仍會犯錯點解：它不是長期記住你每一句叮囑

很多人以為同一段對話代表 AI 已經記住之前所有規則。實際上，模型每次要回答時，只能根據當輪送進 context 的內容理解工作。對話愈長，工具回傳愈多，系統愈可能摘要、壓縮或減少較早內容；你最初那句「品牌名不要加空格」未必仍以完整形式出現在它眼前。

所以再次提醒會暫時有效，不是因為模型終於學會，而是你把規則重新放回最近的 context。這個做法對一次性工作無問題，但對反覆 workflow 很脆弱：下一次新對話、不同人接手或歷史被壓縮後，同一個錯仍會回來。

**Jimmy 的結論：** Prompt 是當次工作的 context，不是永久記憶。若一條規則對交付很重要，不能只靠它曾經在聊天出現過。

| 你看到的現象 | 較可能的機制 | 不應只做甚麼 |
|---|---|---|
| 剛開新對話很準 | 規則仍在最近 context | 假設永遠會記住 |
| 長流程後又錯 | 早期內容被壓縮或淡化 | 再加一條更長叮囑 |
| 換人／換工具又錯 | context 沒有一起交接 | 以為模型「退步」 |
| 同一錯忽好忽壞 | input／context 每次不同 | 只怪模型不穩定 |

下一次遇到反覆錯，不要先問「點樣寫得更兇」。先找這條規則有沒有一個獨立、會隨 workflow 帶著走的地方。

## Context window 怎樣令規則失效：長對話會把重要與可見混成兩回事

可以把 context window 想成一張有限大小的工作桌。你的指示、資料、歷史對話、工具結果和這一輪要生成的內容都要放在桌上；桌面滿了，系統便要摘要或取捨。你覺得重要的早期短句，未必在壓縮機制眼中有足夠結構或優先度保留下來。

這不代表所有長對話都不可靠，也不代表要把每條 prompt 寫得更長。真正要做的是把重要、可重用的規則改成有名稱、有結構、在每次 run 都會被讀取的 artifact；例如 brand rule、schema、acceptance checklist 或 work card。這讓規則不再依賴某一段聊天的偶然位置。

**Jimmy 的結論：** 「重要」不等於「每次都可見」。要令規則耐用，請把它由一句叮囑變成可被每次 workflow 明確帶入的結構化材料。

| 放在聊天裡的規則 | 放在 workflow artifact 的規則 | 差別 |
|---|---|---|
| 很早的一句提醒 | named brand／format rule card | 可被明確重新讀取 |
| 講者口頭記得 | checklist／schema | 可交接給另一人 |
| 混在長 prompt | input／output contract | 可檢查是否符合 |
| 出錯才再說 | run 前／run 後固定 check | 不靠臨時救火 |

若一條規則只對某個情境有效，請同時寫出適用邊界。結構化不是把所有東西硬卡死，而是讓每一次使用知道何時要帶入、何時不應套用。

## AI reliability 怎樣由模型外面撐住：input、validation、review 和 stop line 缺一不可

模型只負責 workflow 的其中一格：理解、生成、分類、比較或提出選項。要讓一件工作可靠交付，還需要 input boundary、格式或參數驗證、human review、例外處理和停止線。這些不是要取代 AI，而是令它的 output 不會因一個可預見錯誤直接流進下一步。

第一個 practical step 不需要建一整套企業 guardrail。只要挑一個反覆、可判斷的錯，在 output 後加一個固定檢查，例如品牌寫法、必填欄位或日期格式。錯了就標出來或退回，不要讓 AI 自己補猜。由零到一個可靠檢查，通常比把 prompt 由 500 字加到 2,000 字更有用。

**Jimmy 的結論：** 可靠性不只在模型裡；它在模型前後的工作設計。先加一個不靠人記得的檢查，讓同一錯不會無聲通過。

| Workflow 格 | 它保護甚麼 | 安全預設 |
|---|---|---|
| Input boundary | 不把錯／敏感材料送進去 | 已批准、最小必要 input |
| Model action | 只做適合 AI 的判斷／生成 | bounded draft |
| Validation | 攔住可客觀判斷的錯 | flag／return，不自動補 |
| Human review | 處理語氣、意圖、例外 | named owner |
| Stop line | 不確定時不繼續 action | unknown → escalation |
| Receipt | 下次知道錯在哪裡 | rule／result／next fix |

如果錯誤涉及敏感決定、對外發送或不可逆 action，單靠 format check 不足夠。保持 draft-only，加 human approval，才是正確邊界。

## 哪些 AI 錯可以用規則卡住：分清確定性錯、半確定性錯和 judgment

不是每個錯都應用硬規則。品牌名、日期格式、必填欄位、數值範圍這些可客觀驗證的錯，適合抽出 prompt，交給 check。語氣是否合適、哪個方案優先、內容是否有說服力，則高度依賴情境；若硬把它卡成單一規則，可能反而殺掉 AI 的應變能力。

中間有一類「半有規則」最需要小心。例如「對客戶要正式」聽起來像規則，但正式的程度會隨關係、目的和內容改變。這時可把確定部分寫成固定要求，例如不可作未證實承諾、必須有 owner review；其餘保留給 AI 提供選項和人作最後判斷。

**Jimmy 的結論：** 只有另一個不懂情境的人也能按同一條規則判斷對錯的事情，才適合卡死。其餘應用 guiding context、review 和 evidence，不應假裝可自動化。

| 錯誤類型 | 例子 | 最合適處理 |
|---|---|---|
| 有規則 | 日期、品牌名、必填欄位、數值範圍 | deterministic validation |
| 半有規則 | 敏感措辭、內容長度、優先次序 | 部分 check 加 human review |
| 要判斷 | 語氣、策略、創意、關係處理 | AI options 加 owner judgment |
| 高風險 action | 發送、付款、公開設定 | approval／stop，不自行執行 |

當你不確定是哪一類，先問：「我能否讓一個完全不懂這件事的人照規則判對錯？」答不到，就先不要把它做成 hard gate。

## 三個最值得先加的 AI 檢查：固定字詞、結構完整和數值格式

第一個檢查應選低風險、高頻、明確。固定字詞包括品牌、產品名、專有名詞；結構完整包括必須出現的欄位、段落或 source link；數值與格式包括日期、百分比、金額、編號或 table schema。這些都不需要模型「更聰明」，只需在交付前確認是否符合。

最重要的規則是：檢查發現問題時，不要讓它偷偷補一個看起來合理的答案。應該列出不符合的地方、退回需要補的 input，或交 owner 決定。好的 check 是令錯誤可見並阻止它過關，不是製造另一層未被發現的猜測。

**Jimmy 的結論：** 從一個你能客觀驗證、又常出錯的地方開始。最好的檢查不是幫你完成，而是不讓不確定內容假裝已完成。

| 檢查 | 一條規則 | 出錯時怎樣做 |
|---|---|---|
| 固定字詞 | 品牌名必須完全符合 approved spelling | flag，按 rule 修正 |
| 結構完整 | brief 必須有 source、unknown、owner 三格 | 缺一格即退回 draft |
| 數值格式 | 日期須 YYYY-MM-DD，百分比 0–100 | 列為待確認，不補猜 |
| Source boundary | 只可用 approved source list | 停止，交 data owner |
| Action boundary | 未 review 不可外發 | 留在 internal queue |

規則會過期，例如品牌改名、欄位變動、政策更新。每一個 check 都需要 owner 和更新日期，否則它遲早會攔錯東西，最後被整個關掉。

## 一個公開安全例子：internal briefing 為何要把「必有來源」搬出 prompt

假設 AI 每週把三份已批准公開來源整理成 internal briefing。團隊最常見的錯不是 AI 不會寫，而是有時忘記附 source link、有時把不完整資料寫成肯定句、有時漏了 unknown 欄。若只在 prompt 寫「記得要有來源」，長期跑下去這條提醒可能失效。

較好的設計是定一張 output schema：每個 item 必須有 source、summary、unknown、owner review 四格；run 後先檢查四格是否齊，缺少時只標出缺口並停在 internal draft。content owner 對照原文後才接受，AI 不自行補來源、不外發。下次若又有退回原因，再把它寫成新的明確 rule 或留給 human judgment。

**Jimmy 的結論：** 這個例子不是要把每個內容決定自動化，而是把「一定要有來源」這種客觀要求由記憶變成可檢查的工作規則。

| 原本靠 prompt | 改成 workflow check | 保留給人 |
|---|---|---|
| 「記得附來源」 | 每項必有 source 欄，缺即 flag | 判斷來源是否真正 relevant |
| 「不要亂猜」 | unknown 欄不可留空 | 決定怎樣補資料 |
| 「格式要一致」 | schema 必填欄位 | 決定內容優先次序 |
| 「小心發送」 | 未 review 不可出 internal draft | 決定是否可對外使用 |

這是 synthetic 教學情境，不代表任何特定 client 或 system 已有相同流程。它說明的是可靠性怎樣由 prompt 以外的工作設計建立。

## 今日怎樣處理 AI 反覆錯：選一個可判斷錯，寫 rule、check、owner 和 stop

找最近一個反覆出現、令你每次都要提醒 AI 的錯。先判斷它是否客觀：有沒有一條規則讓另一人也能判對錯？若有，寫成一句最小 rule，放入一張 card 或 checklist；再決定 run 後誰檢查、出錯時是 flag、退回還是停止。不要一開始自動修補。

如果這個錯其實需要語氣、策略或關係判斷，請不要硬做 check。改為給 AI 較好的 context，要求列出不確定處，並讓 owner review。你要建立的不是一堆 rigid rules，而是知道哪些工作應交給 deterministic system、哪些應保留 AI flexibility 和 human responsibility。

**Jimmy 的結論：** AI 又犯同一錯時，最有用的問題不是「我再怎樣叮囑？」而是「呢個錯有冇規則？」答到，就把規則搬到模型外面；答不到，就改善 context 與 review。

| 今天的四格 | 寫甚麼 | 安全預設 |
|---|---|---|
| Rule | 可客觀判斷的一句要求 | 小而清楚 |
| Check | run 後怎樣驗證 | flag／return |
| Owner | 誰負責更新與收貨 | named person |
| Stop | 不確定／越界時怎樣辦 | unknown → human |
| Receipt | 下次記甚麼 | error pattern／next rule |

想進一步設計整條 workflow 的可靠性，讀 [可靠性是 harness 問題](./4-1-harness-not-prompt.md)；想知道 feedback 怎樣變成下次更穩的判斷，讀 [把 feedback 變成判斷](../../02-AI Super User（AI熟練使用者）/chapters/2-9-feedback-into-judgment.md)。

> AI 出錯不一定代表它不懂；先分清這是一個需要更多 judgment 的問題，還是一個本來就應由 workflow check 擋住的問題。

← [返回 AI Builder](../README.md) · [按問題瀏覽](../../../學習地圖.md)
