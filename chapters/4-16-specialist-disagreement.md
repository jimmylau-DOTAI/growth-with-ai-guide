# 多個 AI 唔係一齊附和：點樣設計有用的 specialist review

當一份 AI 草稿令你不放心，很自然會想「再搵幾個 Agent 睇」。但開五個不同名字的 Agent，不會自動得到五種觀點；若它們讀同一份薄 context、被問同一句「你覺得點」，多數只會一起附和，或者一起猜。

真正的困難不是意見數量，而是意見能否幫你作決定。有人要核對 evidence、有人要檢查受眾能否理解、有人要旗標不應承諾的風險；這些不是同一個問題，也不應由「多數 bot 同意」取代負責人的判斷。沒有清楚分工時，分歧只會變成更多文字。

Jimmy 的看法是：有價值的 specialist review，不是模擬一個 AI 團隊開會，而是把不同 evidence、不同 rubric 和不同風險顯示出來，交回 human owner 作有責任的決定。分歧不是失敗；可回看的分歧，是提醒你下一步該核對甚麼的訊號。

AI 實戰 · AI Builder · specialist · review · disagreement · rubric · evidence · owner

| Specialist review 的一格 | 它解決甚麼問題 | 完成後留下甚麼 |
|---|---|---|
| Review question | 不讓每個 reviewer 重複講同一件事 | 一個不重疊的檢查問題 |
| Evidence boundary | 不讓 private context 無限擴散 | 完成該問題所需的最小材料 |
| Rubric | 不只交個人偏好 | 合格條件、red flag 和 stop line |
| Disagreement format | 不讓 owner 在長文裡找衝突 | claim、evidence、信心與未知 |
| Owner decision | 不把責任假裝交給投票 | 採納、拒絕或補資料的理由 |

## 多個 AI 點解仍會答到一樣：角色名不同，不等於檢查角度不同

把角色叫作「researcher」、「editor」、「strategist」不會自動產生不同判斷。若三個 Agent 都讀同一份材料、都被要求「review 一下」，它們沒有理由聚焦不同風險；結果通常是三份近似摘要，或者三個同時把一個未證實說法講得更肯定。

specialist 的分工應由問題開始，而不是由職位開始。Evidence checker 可以只回答「每個 external claim 有沒有可回看的公開依據」；clarity editor 只回答「哪三句令目標受眾不容易明白」；risk flagger 則只回答「哪句會造成不應承諾或不應自動化」。答案不同，是因為他們被要求檢查不同的東西。

**Jimmy 的結論：** 不同 specialist 的價值在於不同問題與不同 rubric，而不是不同 persona。兩位 reviewer 若會交出同一種答案，先重寫問題，別急著加第三位。

| 表面上的分工 | 實際仍會重複的原因 | 改成怎樣才有用 |
|---|---|---|
| 「三個 AI 一齊 review」 | 沒有指定各自問題 | 一個查 evidence、一個查 clarity、一個查 risk |
| 「一個做研究、一個做策略」 | 都讀同一批材料、交同一份摘要 | 為每人指定不同輸出欄位 |
| 「多數同意就過關」 | 沒有人被要求反證或查來源 | 讓 reviewer 指出缺口與 evidence |
| 「再問一個 AI」 | 新 reviewer 沒有新標準 | 先決定要補的是 evidence、rule 還是 authority |

開始前先問：這位 reviewer 獨有的問題是甚麼？若答案只是「再看看」，它不是 specialist review，而是重複生成。

## Review question 怎樣拆開：讓每位 specialist 只對一個可驗收問題負責

一個好 review question 要小到能夠說明何時算答完。例如「這份 draft 是否夠好」太大，因為它混合了事實、易明度、品牌、風險和決策；「每個外部主張是否附有公開來源」則可以用一張清單驗收。問題小，並不是令 review 表面化，而是讓問題真的有 owner。

也要避免把同一問題拆成不同說法。例如「內容是否可信」與「資料是否準確」若都沒有明確 evidence rule，很可能兩位 reviewer 又會交同一份感想。拆分要看不同的失敗模式：一位找沒有證據的 claim，一位找聽眾看不懂的句子，一位找超出權限或不應作出的承諾。

**Jimmy 的結論：** Review 問題應描述一個可確認的失敗模式，而不是描述一個理想人格。每一位 specialist 最後都要能交回一個清楚的 pass、flag 或 unknown。

| Reviewer | 它只回答的問題 | 可驗收交付 |
|---|---|---|
| Evidence checker | 每個 external claim 有沒有可開啟來源？ | 缺 link 的句子清單 |
| Clarity editor | 目標讀者會在哪三句卡住？ | 原句、原因與替代寫法 |
| Risk flagger | 有沒有誇大、敏感承諾或越權動作？ | red flag 與停下原因 |
| Format checker | 是否符合已批准的內容結構？ | checklist pass／fail |
| Human owner | 在現有 evidence 下可否推進？ | final decision 與理由 |

如果一項問題不能被寫成「哪句、哪格、哪條 evidence」，就把它留給 human owner 的整體判斷，不要假裝它可由 AI 自動評分。

## Evidence boundary 點樣防止 review 變成更多猜測：每人只讀完成該格所需材料

讓每位 specialist 讀所有資料，看似更全面，實際上常令它們一起受同一段 context 影響，也會不必要地擴散敏感材料。對 evidence checker 而言，可能只需要 draft 內的外部 claim 和公開來源清單；對 clarity editor 而言，只需要目標受眾描述與文章段落；它未必需要知道任何不相關的公司背景。

最小 evidence 亦令意見較容易回看。當 reviewer 說某個 claim 有問題，owner 可以問「它根據哪一份材料指出」；當資料不足，reviewer 應回傳 unknown，而不是因為 context 不完整就自行補足。這讓 review 是一份 evidence receipt，不是一段很有自信的評論。

**Jimmy 的結論：** 少而對的 evidence，比多而混雜的 context 更能製造有用分歧。每位 reviewer 只拿完成自己問題所需的材料，並清楚標出看不到的地方。

| Reviewer 需要的材料 | 不必自動給它的材料 | 資料不足時應怎樣做 |
|---|---|---|
| Claim 與公開來源清單 | 所有內部策略與聊天紀錄 | 標 unknown，要求補 link |
| 受眾說明與文章段落 | 客戶資料、價格、未公開方案 | 只提出易明度問題 |
| 已批准的風險規則 | 全部 business context | flag 後交 human owner |
| 格式 rubric 與 draft | 不相關的原始來源包 | 回報缺欄與版本問題 |

這個邊界不是削弱 reviewer；它是讓每一個 flag 都知道來自哪個範圍。沒有足夠材料時，最正確的 review 不是猜，而是停止並叫 owner 補資料。

## Rubric 與 red flag 怎樣令意見可比較：由「我覺得」變成可 review 的判斷

沒有 rubric 的 reviewer 很容易交出漂亮但不可行動的意見，例如「更有說服力」、「語氣再 professional 一點」。這些話未必錯，但 owner 無法比較兩位 reviewer 的建議，也無法知道改完是否真的過關。rubric 是把「甚麼情況值得 flag」先寫出來。

rubric 不需要量化一切。它可以只是三個紅旗：外部主張沒有來源、把推論當事實、或草稿出現未被授權的外部承諾。當 red flag 出現，reviewer 不必替 owner 作最後決定；它只需標出句子、相關 evidence、風險類型和所需下一步。

**Jimmy 的結論：** rubric 的作用不是把判斷假裝成客觀分數，而是令不同意見可以在同一張桌上比較。沒有 rule 的分歧是偏好；有 rule 的分歧才是可處理風險。

| Rubric／red flag | reviewer 要交甚麼 | owner 可以怎樣決定 |
|---|---|---|
| 每個 external claim 有公開依據 | claim、link 或缺 link | 補來源、刪除或標待驗證 |
| 不把推論寫成事實 | 原句與推論標記 | 改寫或要求補 evidence |
| 不作未批准承諾 | 觸發句與承諾類型 | 保留、刪除或交負責人 |
| 受眾看得明白 | 最難三句與原因 | 改寫、保留或改目標受眾 |
| 不越出本輪範圍 | 超出 change request 的位置 | 回退修改 |

reviewer 可以說「這格不符合已定標準」，但不應自行將 rule 改掉、宣稱已批准，或以一個分數壓過 owner 的取捨。

## AI review 出現分歧後點處理：先分 evidence、rule 與 authority

分歧不是要由多數決處理。兩位 reviewer 得出不同結論，首先要問他們是否看過不同 evidence；若是，問題是材料未對齊。若材料相同但使用了不同 rubric，問題是規則沒有先定清楚。若兩邊 evidence 和 rule 都相同，卻仍是要在品牌、風險或承諾之間取捨，那便是 authority 問題，必須交回有責任的人。

這個分類很重要，因為它防止「再問多一個 Agent」變成預設答案。新增一個 reviewer 未必帶來新 evidence、新 rule 或新 authority；它只會令原本的矛盾被更多字包住。先知道分歧是哪一類，才知道下一步是補資料、重跑 rule，還是停止等待 owner。

**Jimmy 的結論：** AI 的分歧只是一個訊號，不是一場投票。先定位它缺 evidence、缺 rule，還是需要 authority，才是安全而有速度的處理。

| 分歧類型 | 你看到甚麼 | 正確下一步 |
|---|---|---|
| Evidence conflict | reviewer 引用不同資料，或一方回不到來源 | 回到 source，補資料或標 unknown |
| Rule conflict | 同一材料下用不同 checklist／stop line | owner 先定適用 rule，再要求重跑 |
| Authority conflict | 涉及品牌、風險、承諾或責任取捨 | human owner 留下決定與理由 |
| Scope conflict | reviewer 對本輪可改範圍理解不同 | 回看 change request，必要時退回 |
| Output conflict | 結論不同但 evidence 和 rule 一致 | 比較可驗收後果，交 owner 選擇 |

只要分歧被留成可讀 receipt，它就不會浪費。它會成為下一次要補充的 evidence、要修正的 rubric，或必須保留給人類的決定界線。

## 一個公開安全例子：三位 reviewer 點樣檢查 workshop draft

假設一份基於公開材料的 workshop draft 要做 internal review。Evidence checker 只看每個 external claim 是否有公開來源；clarity editor 只找目標學員最可能不明白的三句；risk flagger 只看誇大、敏感承諾和不應自動化的地方。三人都不會發文、改價錢、接觸客戶或宣稱自己已批准。

例如 evidence checker 旗標一個沒有連結的成效句，clarity editor 說同一句對新手太抽象，risk flagger 則指出它聽起來像對外保證。這不是三人「打交叉」；它們從不同 rubric 指向一個更清楚的 owner 問題：保留這句需要甚麼 evidence？若沒有，應改成哪種不承諾的說法？

**Jimmy 的結論：** 專業 review 的成果不是三份長 comment，而是一張 owner 可以處理的 receipt：哪句有問題、基於甚麼、屬於哪類風險、下一步誰決定。

| Specialist | 只可檢查甚麼 | 交付格式 | 不可做甚麼 |
|---|---|---|---|
| Evidence checker | claim 與公開來源關係 | 缺 link／可確認清單 | 補寫外部事實 |
| Clarity editor | 新手讀者理解障礙 | 原句、原因、替代說法 | 改變品牌承諾 |
| Risk flagger | 誇大與越權風險 | red flag 與 stop reason | 直接刪改或批准 |
| Human owner | 三份 receipt 的取捨 | final decision | 假裝 AI 已替他承擔責任 |

這個例子只處理公開、低風險的 internal draft。它不授權任何 specialist 讀取私人／客戶資料、對外發送訊息、改動 production 系統或自行公開內容。

## 今日怎樣跑第一次 specialist review：兩位 reviewer 已足夠

第一次不必開五個角色。選一份低風險 internal draft，例如一頁基於公開材料的教學草稿，然後只設兩位 reviewer：一位只查 evidence，一位只查新手是否看得明。為每人填四格：它的問題、可讀 evidence、red flag、固定輸出格式；最後再寫清楚 human owner 是誰。

若兩位 reviewer 最後仍交出一樣的 comment，不代表需要加第三個 AI。先問他們是否真的有不同問題、不同 evidence boundary 或不同 rubric。把這三樣重寫後再跑一次，通常比增添角色更能看出真實風險。

**Jimmy 的結論：** 先讓兩個小而清楚的檢查點有效，再考慮更多 specialist。AI review 的成熟不是角色數量，而是 owner 能否根據 receipt 作更好決定。

| 第一次 review card | Reviewer A | Reviewer B |
|---|---|---|
| Review question | 每個 claim 有公開來源？ | 新手會卡在哪三句？ |
| Evidence | claim 加 source list | draft 加受眾說明 |
| Red flag | 缺 link、推論當事實 | 術語未解釋、前提缺失 |
| Output | 可確認／缺口清單 | 原句、原因、替代說法 |
| Owner | 內容 owner 最後決定 | 內容 owner 最後決定 |

保留兩份 receipt 和 owner 的決定，下一次才知道分工有沒有真的幫到 review。暫時不要讓 AI 互相投票批准、不要把它們接到對外發送或 production 寫入，也不要因為叫 specialist 就把不相關的 private context 分給它們。下一步可看 [如何設計獨立 review，而不是叫多個 AI 一齊附和](4-18-independent-review.md)。

> 有價值的 AI 團隊，不是一齊鼓掌；而是把不同 evidence 和風險放上枱，令真正的 owner 判斷得更清楚。

← [返回 AI Builder](../04-ai-builder.md) · [按問題瀏覽](../BROWSE.md)
