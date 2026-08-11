# 想做 AI workforce？先寫一張可驗收 AI work card

「我有五個 Agent」、「我想整一個 AI OS」聽起來很大，但最重要的問題通常仍未有答案：它這星期替誰完成了哪一件可檢查的工作？如果輸入不清、交付看不到、出錯沒有停線，Agent 名稱再多也只是一個很難驗收的承諾。

第一個 AI worker 不需要很自主。它只需要接走一件重複、低風險、可回看的小工作，並且讓人知道它能讀甚麼、交甚麼、誰收貨、何時不應繼續。這種清楚比一個「萬能助手」更容易帶來穩定價值，也更容易被團隊學會。

Jimmy 的看法是：AI workforce 的第一個證明不是一個大腦，而是一張有人看得懂、做錯會停、交付可檢查的工作卡。AI work card 把一個可重複工作變成可討論、可比較、可保留或停掉的單位，而不是把一切包裝成已自動化。

AI 實戰 · AI Builder · AI worker · work card · workflow · artifact · owner · outcome evidence

| AI work card 的一格 | 它解決甚麼問題 | 完成後留下甚麼 |
|---|---|---|
| 工作痛點 | 不為了用 AI 而造一個角色 | 一個真實重複摩擦 |
| AI job | 不讓工作責任太籠統 | 一句能說清的工作名稱 |
| 已批准 input | 不讓 worker 亂讀資料 | 最小可信材料包 |
| Artifact | 不讓完成只是一句聲稱 | 可 review 的 draft、表或 receipt |
| Review / stop | 不讓 AI 自己宣布成功 | owner、checklist、停線 |
| Outcome evidence | 不先吹噓成果 | retain、revise 或 stop 的觀察 |

## AI worker 點解經常變成空話：有角色名，卻答不到它實際交甚麼

很多 AI project 由角色名稱開始：sales agent、marketing agent、research agent、AI assistant。這些名字很容易令人想像它能做很多事，卻沒有指出它在一次工作中會交出甚麼 artifact。沒有 artifact，團隊無法 review；沒有 review，又無法知道它是減少了工作，還是只是多製造一份要人收拾的內容。

真正的工作單位應小到可以被驗收。例如「每週把已批准公開 FAQ 整理成 internal FAQ draft」比「customer service agent」清楚得多。前者有固定 input、可見輸出、已知 owner 和明確邊界；後者可能暗示讀取客戶資料、對外回覆、承諾價格，卻沒有任何授權或停止規則。

**Jimmy 的結論：** 不要先問「這個 Agent 叫甚麼」，先問「它交甚麼、誰會檢查、出錯會在哪裏停」。答到這三件事，才有一個值得保留的 AI job。

| 聽起來很大 | 真正缺少甚麼 | 改成可驗收的工作 |
|---|---|---|
| 「customer service agent」 | input、權限與外發邊界 | 內部 FAQ draft assistant |
| 「research agent」 | source 與交付物不清 | 公開文章 evidence brief assistant |
| 「AI marketing team」 | 每個角色責任重疊 | 每週內容資料整理 worker |
| 「AI OS」 | 工作單位與 owner 未定 | 三張已跑過的 work card |
| 「自動化助理」 | 完成線與 stop line 未寫 | 固定欄位的 review queue |

如果一個角色只可以用一句「它會幫手做嘢」形容，先不要把它當 workforce。先把工作縮小成一張可以被人拿起來 review 的卡。

## Workbench contract 與 AI work card 有甚麼不同：一個管本輪，一個定義可重複工作

workbench contract 是一輪工作開始前的安全說明：這次可讀甚麼、可改甚麼、現行 state 是哪一份、甚麼時候要停止。它像一次任務的工作場，確保 AI 不會因為空白而讀錯版、擴 scope 或自行推進不可逆動作。

AI work card 則是把同一類小工作長期定義下來：它為誰解決甚麼痛點、固定使用哪些 input、每次交甚麼 artifact、誰 review、如何看它是否值得繼續。contract 可以每輪不同；card 幫團隊辨認哪些工作已變成可重複能力。

**Jimmy 的結論：** contract 令一次 AI 工作安全發生；work card 令一個重複工作可以被保留、比較和改善。先用 contract 跑過，再決定值不值得變成 card。

| 比較項 | Workbench contract | AI work card |
|---|---|---|
| 時間範圍 | 今次的一輪工作 | 可重複的工作單位 |
| 重點 | state、scope、actions、stop line | pain、job、artifact、owner、outcome |
| 主要問題 | 今次可怎樣安全地做？ | 這個 worker 值不值得長期保留？ |
| 成功證據 | diff、check、handoff | 多輪 artifact 與 outcome observation |
| 關係 | 每次執行的工作場 | 可重複能力的說明卡 |

如果你未曾在一個清楚 contract 內跑過這件工作，work card 仍只是猜想。先由小型、可回看的 run 開始，才有證據定義它真正的 job。

## 一張 AI work card 應怎樣寫：由工作痛點走到可驗收 artifact

一張好 card 的第一格不是工具，而是工作痛點。它應指出哪個重複摩擦、等待或漏項正在發生；然後把痛點轉成一個狹窄 job。接著才界定 worker 可讀的已批准 input，並指定一份每次都能看見的 artifact。

最後兩格保護這張卡不變成宣傳：review／stop 說明誰用甚麼條件收貨、何時必須交人；outcome evidence 則只觀察是否減少漏項、縮短可 review 前時間或減少 rework。它不是先承諾省多少錢、取代多少人，因為那些結果要由多輪真實使用證明。

**Jimmy 的結論：** AI work card 的六格把「AI 幫到手」翻譯成可以驗收的工作設計。每格都填到，才值得叫它一個 AI worker。

| Work card 格 | 需要回答甚麼 | 不應寫成甚麼 |
|---|---|---|
| 工作痛點 | 哪個重複問題正在發生？ | AI 很潮、想試新工具 |
| AI job | worker 只負責哪一種工作？ | 萬能助手、全能 Agent |
| Input | 只准讀哪些材料？ | 整個 Drive、Vault 或所有歷史 |
| Artifact | 每次交甚麼可見結果？ | 「已經處理了」 |
| Review / stop | 誰查、怎樣查、何時停？ | AI 自己說成功 |
| Outcome evidence | 哪一兩個觀察會支持 retain？ | 未驗證的收入或節省承諾 |

用 card 的目的不是為每個工作貼標籤，而是迫使團隊把 input、output 和責任線在啟動前說清楚。

## Artifact 與 review 點樣令 AI worker 變得可信：交 review queue，不是直接取代人

AI worker 最安全而有用的第一個交付，往往是一個 review queue：一份可供人檢查的 draft、表格、分類結果或缺口清單。它能把重複整理工作前移，卻不會自動把未確認內容變成客戶回覆、公開內容或系統寫入。

review 需要對準 artifact。假如 worker 的 job 是整理 FAQ，reviewer 不應只問「好不好」，而要看每個答案能否回到批准資料、未知是否標出、格式是否符合。當出現未公開 offer、個人資料、對外回覆或 evidence 不足，worker 要停並留下一個明確問題，而不是嘗試幫忙補完。

**Jimmy 的結論：** 好的 AI worker 先幫你生產可 review 的工作面，而不是直接拿走人類的責任。能安全停下的 worker，通常比會強行完成的 worker 更值得擴大。

| Artifact 類型 | 人可以怎樣驗收 | 一開始不應自動做甚麼 |
|---|---|---|
| FAQ draft | 對照已批准內容與來源 | 直接回覆客戶 |
| Research table | 查 link、日期、unknown 欄位 | 把推論寫成事實 |
| Content outline | 看結構、來源與承諾 | 自行公開或排程發文 |
| Data gap list | 確認缺口與 owner | 自動補資料或改數字 |
| Review receipt | 按 rubric 決定 revise／stop | 代替 owner 批准 |

只要 artifact 還未能被人用一個清楚 checklist 收貨，先不要擴大 worker 的權限。先把 review queue 做穩，才談真正的 automation。

## Outcome evidence 點樣誠實量度價值：觀察 retain、revise 或 stop，不預先吹成果

一張 work card 不需要一開始就證明 ROI，但它必須知道自己要觀察甚麼。最有用的起點是只選一兩個能從工作留下的痕跡看見的指標，例如每輪漏題數、由資料齊備到可 review 的時間、rework 次數、或因不確定而正確停下的個案。

這些數字不是用來把所有價值縮成 KPI，也不是要在還未跑過幾輪前宣稱「節省了多少錢」。它們是幫 owner 以 evidence 判斷：這個 worker 是否真的減少一個摩擦？需要修正 input 或 rubric？還是根本不值得保留？

**Jimmy 的結論：** outcome evidence 是保留、改善或停止工作卡的依據，不是 AI project 的廣告標語。未驗證的結果，要誠實地留作假設。

| 想觀察的事情 | 可以留下的 evidence | 可得出的下一步 |
|---|---|---|
| 是否減少漏項 | 每輪漏題／缺欄數 | 補 input 或保留流程 |
| 是否加快 review | 資料齊備至可 review 的時間 | 看是否值得重跑 |
| 是否減少 rework | reviewer 退回次數與原因 | 修 prompt、rule 或 job 範圍 |
| 是否正確停下 | unknown／stop receipt | 補 escalation 或權限邊界 |
| 是否值得保留 | 多輪結果與 owner 感受 | retain、revise 或 stop |

先用 observation 取代承諾，能讓你日後真的有東西可說：不是「AI 一定會創造價值」，而是「這一條工作在甚麼條件下顯示出可保留的價值」。

## 一個公開安全例子：FAQ draft assistant 如何由痛點變成 work card

假設一個團隊每週都要把已批准的公開 FAQ 和活動資料整理成 internal FAQ draft。原本不同人每次翻資料，常在 review 後才發現漏題或答案無法回到來源。這是一個重複、可回看的痛點，適合作為第一張卡，而不是直接做 autonomous customer service。

job 可以叫 FAQ draft assistant；input 只限公開 FAQ、已核對活動 brief 和已批准回答格式；artifact 是一份分類 draft，每題標示來源和待確認問題。editor 對照原資料 review；遇到未公開 offer、個人資料、外部回覆或未知 claim 便 stop。每輪觀察漏題數、可 review 前時間和 rework 次數，再決定是否保留或改良。

**Jimmy 的結論：** 這是一張完整但誠實的 AI work card：它交的是 review queue，不是直接對客戶承諾。先把一個小工作做好，已經是 AI workforce 的真正開始。

| Work card 格 | FAQ draft assistant 的內容 | 可回看證據 |
|---|---|---|
| 痛點 | 翻資料慢、漏題後才補 | 舊 review 的漏題原因 |
| Job | 每週起 internal FAQ draft | 固定工作名稱 |
| Input | 公開 FAQ、批准 brief、格式 | source list |
| Artifact | 分類 draft、來源、未知 | review queue |
| Review / stop | editor review；敏感／外發即 stop | receipt 與 owner |
| Outcome | 漏題、review 前時間、rework | 多輪觀察表 |

這個例子只處理公開資料和內部草稿。它不讓 AI 讀取客戶資料、直接回覆、修改價格／offer、對外發送或連接 production 系統。

## Dashboard、portfolio 與 Agent 數量為何不等於 AI workforce：先有真實工作卡

dashboard 只會展示狀態；它無法替一張卡補回 input、artifact、owner 和 stop line。若底下的工作單位仍然模糊，總控台只是在集中混亂。同樣地，先造很多 Agent 角色也不會自動變成 portfolio；一串名稱不等於有人能看懂它們各自交出甚麼。

真正有說服力的 portfolio 是幾張真的跑過的 card。每張卡有公開安全的說明、可驗收 artifact、review receipt 和誠實的 outcome observation。這些資料既可幫團隊改良 workflow，亦能在適當時候轉成公開教學或案例的骨架，而不需要暴露客戶或未公開工作。

**Jimmy 的結論：** AI workforce 不是一個 dashboard 畫面，也不是 Agent 數量。它是一組被真實工作證明過、界線清楚、可以保留或停止的工作卡。

| 看似很完整的東西 | 為何未必有用 | 先補哪一格 |
|---|---|---|
| 很漂亮的 dashboard | 只看見狀態，看不見工作契約 | input、artifact、owner |
| 十個 Agent 名稱 | 角色責任可能重疊 | 每個 job 的可驗收輸出 |
| AI portfolio landing page | 未必有真實 evidence | review receipt 與 outcome |
| 一個很大的 AI OS 圖 | 缺少第一條可跑工作 | 低風險 work card |
| 預測節省的數字 | 未做多輪觀察 | retain／revise／stop evidence |

先有三張小而可靠的 card，再做 dashboard 或 portfolio，會令你展示的不是概念，而是工作如何被安全地重新設計。

## 今日怎樣填第一張 AI work card：選一件重複、低風險、可 review 的工作

選一件你已經重複做過、但不涉及外發或不可逆操作的工作。它最好有較穩定的 input，能產生一個 draft、table 或 checklist，並有一位人類 owner 可以 review。不要挑一開始就要讀整個 vault、處理客戶資料或連接 production 的任務。

填六格後，只跑一個小 contract。保留 input、artifact、review receipt、unknown 和 outcome observation；若任何一格答不到，就先不要叫它 AI worker。你會發現有些所謂 automation 其實只是問題未定義，有些則非常適合變成第一張真正的 card。

**Jimmy 的結論：** AI workforce 的第一步不是做一個大腦，而是把一件真工作交得清楚。卡愈小、邊界愈可見，愈容易走到下一個可靠的 AI Builder 能力。

| 第一張 card | 你要填甚麼 | 安全起點 |
|---|---|---|
| 工作痛點 | 一個重複摩擦或漏項 | 每週整理公開 FAQ |
| AI job | 狹窄、可說清的工作 | FAQ draft assistant |
| Input | 已批准最小材料 | 公開資料與格式 |
| Artifact | 可 review 的輸出 | 分類 draft 加來源 |
| Review / stop | owner 與停線 | editor review、缺 evidence 即停 |
| Outcome | 先觀察一兩項 | 漏題與 rework 次數 |

跑過一次後，可接著看 [實際填第一張 AI work card 的 walkthrough](./練習-write-an-ai-work-card.md)，再以 [五個 build gate](./4-12-ready-to-build.md) 檢查是否真的準備好擴大。暫時不要把 card 直接連到外部發送、不可逆操作、客戶或私人資料、公開設定或 production 寫入。

> AI workforce 的第一個證明不是一個大腦，而是一張有人看得懂、做錯會停、交付可檢查的工作卡。

← [返回 AI Builder](../README.md) · [按問題瀏覽](../../../README.md)
