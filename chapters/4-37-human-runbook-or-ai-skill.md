# 唔係每條 SOP 都應該變成 AI Skill：怎樣判斷留作 human runbook，還是交給 AI 跑？

當你開始有一套做得順的 SOP，很自然會想把它全部交給 AI：下次只要按一下，便可以自動完成。但第一次把它交出去後，AI 往往照著正常情況跑，卻踩進原本由人憑經驗才會看見的例外：目標其實變了、資料不可信、對方的要求有特別語境，或 output 看似完整但不能替人作出承諾。

這不代表 SOP 沒價值，也不代表 AI 不能幫忙。問題在於很多 SOP 原本是寫給懂得判斷的人看的：它留下的是經驗提示，而不是每次都可被機械重跑的規則。若你只因為文件已經存在，就把它稱為 Skill，實際上只是把原來隱藏在人腦內的判斷交給 AI 猜。

Jimmy 的判斷是：human runbook 和 AI Skill 都是好資產，但負責不同工作。runbook 幫人看清情況、作取捨、處理例外；Skill 只應接住目標、材料、規則和完成線都較穩定、可驗收的一段。先分清責任，再決定 AI 應該 draft、協助、半自動跑，還是根本不在 scope。

| 判斷格 | 偏向 human runbook | 偏向 AI Skill |
| --- | --- | --- |
| 目標與情境 | 每次要重新定義問題或取捨 | 工作種類與 output 大致固定 |
| 判斷方式 | 依賴專業語境、關係、未寫下經驗 | 有清楚 schema、rubric、check 或 stop line |
| Input 邊界 | 需要大量敏感、未分類或未確認 context | 只讀已批准的材料與欄位 |
| Output 風險 | 會作承諾、改外部狀態或影響高責任決定 | 先交可 review 的 draft／artifact |
| 例外處理 | 每次例外都可能改變目標 | 例外可寫成固定 status 和交接方式 |

## 一份 SOP 已經寫得很完整，為甚麼仍然未必可以直接變成 AI Skill？

SOP 的完整程度，未必等於它能被 AI 安全重跑。有些 SOP 把「常見步驟」寫得很清楚，但關鍵決定仍靠執行者在不同情境下調整：這位客戶的語氣是否適合、哪一個來源可信、今次是否值得例外處理、某句話會否造成不必要承諾。這些東西如果沒有寫成規則、範圍和停線，AI 只會用統計上最像的答案補位。

另一方面，一份很短的流程也可以是好 Skill。假如目標固定、輸入已批准、輸出格式清楚、錯誤能被 check、例外有去處，即使只有幾步，AI 也能較可靠地做。分水嶺不是文件長不長，而是下一次執行時，AI 是否知道甚麼可以做、甚麼需要問、怎樣才算交得出。

**Jimmy 的結論：** SOP 是把經驗留下；AI Skill 是把可重跑的工作合約留下。前者可包含專業判斷提示，後者必須把 scope、input、完成線、quality gate 和 stop 寫得足夠明確。

可以先用這張對照表判斷：

| 你手上的文件說甚麼 | 它較像甚麼 | 還缺甚麼才可變 Skill |
| --- | --- | --- |
| 「按客戶情況調整」 | Human runbook | 哪些情況、可選做法、何時要 escalation |
| 「照上次做法」 | 人的記憶提示 | 可讀 source、版本、欄位與驗收標準 |
| 「寫一份好 proposal」 | 專業工作原則 | 明確任務、可批准材料、draft／release 邊界 |
| 「把三個指定 URL 填入固定 briefing 表」 | Skill 候選 | exception rule、review owner、回退方式 |

如果核心仍然靠「懂的人自然知道」，先把它保留為 runbook，再讓 AI 協助整理、起草或找出問題，毋須急著自動化。

## AI Skill 的工作單位要穩定到甚麼程度，才值得交出去？

穩定不代表每次內容完全一樣，而是工作形狀大致相同。AI 可以處理不同文章、不同日期、不同產品資料，只要它每次都知道要從哪一類已批准 input 讀甚麼、轉成哪一類 artifact、用甚麼標準檢查、交給誰 review。這種變化是資料變化，不是責任變化。

不穩定的工作則會在每次執行時重新定義目標。例如「今季我們應該服務哪個市場」、「這位客戶真正想要甚麼」、「這個公開說法會否影響合作關係」。AI 可以協助列選項、整理證據，但不應裝成可以用一份固定 Skill 代替人在語境中的取捨。

**Jimmy 的結論：** 值得做成 AI Skill 的不是「經常做」而已，而是「每次能以相近 input、相近規則、相近完成線交一份可驗收 output」的那一段。

先問這五條穩定度問題：

1. 這次和下次的工作目標，是否能用同一句完成定義描述？
2. AI 是否只需讀一組指定、已批准的 input class？
3. Output 是否有固定結構，令另一個人可清楚 review？
4. 已知錯誤是否能寫成 check、exception 或 stop line？
5. 即使目標、風險或外部責任改變，AI 是否知道要停下交回 owner？

若多數答案仍是「視乎情況」，不要把它硬包裝成 autonomous Skill。先將最穩的一小段切出來，例如只做資料整理、固定欄位草稿或品質檢查。

## Human runbook 和 AI Skill 怎樣在同一條 workflow 分工，才不會把人的判斷踢走？

最常見誤解是：要麼人做全部，要麼 AI 做全部。其實較好的設計通常是把一條工作拆成不同責任：人用 runbook 定問題、揀材料、處理例外、作 release 決定；AI Skill 在中間跑一段重複、可檢查的轉換。這樣 AI 省走的是重複整理，不是把專業責任偷偷拿走。

假設同事每週要整理三篇公開文章成 internal briefing。人仍然要決定本週研究甚麼、哪些來源值得信、結果是否改變團隊方向；AI 則可以在已批准 URL 裏抽出重點、保留原始連結、標記未知、按固定欄位起 draft。最後是否採用、是否延伸成公開內容，仍屬 human release。

**Jimmy 的結論：** Runbook 是判斷和責任的骨架；Skill 是其中一段可重跑的肌肉。把兩者接起，AI 才會放大人的工作，而不是把人的責任變成無人承擔的猜測。

同一個 workflow 可這樣切：

| 階段 | Human runbook 主要負責 | AI Skill 可以負責 |
| --- | --- | --- |
| 問題定義 | 這次為何要做、要服務誰 | 整理已有問題與相關材料 |
| Input 選擇 | 哪些材料可信、可用、不可讀 | 只讀 owner 指定範圍 |
| 轉換工作 | 判斷是否要改方向 | 抽取、分類、填 schema、起 draft |
| 例外處理 | 衝突、風險、外部承諾的取捨 | 留 state、列選項、按規則修一次 |
| Release | 採用、對外、覆寫、升級的責任 | 提供 receipt，不自行 release |

當每一格都有 owner，AI 便不會因為「可做」而越過「應否做」的問題。

## AI 可以讀多少 context，才不會為了自動化而把資料邊界打開？

很多 SOP 表面上很簡單，實際執行者卻需要看很多背景資料才知道怎樣做。這時候常見錯誤是為了令 AI 看起來更聰明，就把整個 vault、客戶資料夾、email 或 CRM 開放給它。即使 AI 因此能交到較像樣的 output，這也不等於 workflow 已設計得好；它可能只是把資料風險藏起來了。

較可靠的做法是先找出 minimal context：AI 完成這一段固定工作真正需要哪幾個欄位、哪個 approved brief、哪些公開資料。若必須靠大量未分類、敏感或沒有 owner 的 context 才跑得動，通常代表工作仍需要 human runbook 先作選材和判斷，而不是先擴大 access。

**Jimmy 的結論：** AI Skill 的 input 不是愈多愈好；最好的 Skill 只接到完成指定工作必需的已批准材料，其餘 context 留在人手判斷和 controlled handoff 裏。

可用這張 access 分辨表：

| 資料情況 | 較合理處理 |
| --- | --- |
| 已公開／已批准、欄位明確 | 可成為 Skill 的 input class |
| 內部但有 owner、用途清楚 | 先走受控 draft test，再決定是否可用 |
| 客戶、CRM、付款、合約、未公開策略 | 預設不進第一版 Skill；由 human runbook 決定是否另設治理 |
| 沒有來源、過期或未分類的歷史資料 | 不讓 AI 大量掃讀；先有人整理與確認 |

若你需要寫清楚 input 和 workspace 邊界，可讀 [先寫一張 workbench contract](4-19-workbench-contract.md)。

## AI output 出錯時，怎樣判斷它只可交 draft 還是可以自動執行？

output 的風險不只在於它會否有錯，也在於錯了會改變甚麼。AI 生成一張可讓人 review 的 internal draft，錯了通常可以修改或丟棄；AI 自己發出客戶 email、改 CRM、發布內容、覆寫正本或作出付款／權限 action，錯了的成本和回退難度完全不同。

這代表同一個 AI Skill 可以先在 draft 層有用，不需要等到可以 autonomous 才算成功。當它反覆交出可驗收 artifact、已知錯有 check、例外有 stop、owner 也能管理 recovery，才可逐格討論是否增加更多權限。沒有這些證據前，維持 human release 是正確設計。

**Jimmy 的結論：** 「AI 可以做到」不等於「AI 應自己執行」。先讓 output 成為可 review draft，才有機會累積足夠證據決定是否增加外部 action。

可用風險層次設計 output：

1. **協助層**：AI 列問題、摘要、起草；人仍完成主要工作。
2. **Draft Skill 層**：AI 根據批准 input 交固定 artifact；人 review、採用或修正。
3. **受控寫入層**：只在 sandbox／可回退位置寫入，保留 receipt 和 approval。
4. **Human release 層**：任何對外、正本、權限、付款或高責任 action 都由人決定。

不要跳過中間層。能把一個 draft Skill 跑穩，本身已是有價值的 AI Builder 成果。

## 想由一條 SOP 開始做第一份 AI Skill，最安全的拆法是甚麼？

不用把整條 SOP 一次過自動化。先選其中最重複、輸入最清楚、結果最容易驗收的一段，並保留原來 runbook 來處理選題、例外、release 和需要專業語境的判斷。這樣即使第一次 Skill 跑得不理想，影響也只留在一個可回退的小工作單位。

例如你可以把「每週整理三篇已批准公開文章成 internal briefing draft」做成第一個 Skill，而不是把「決定公司本月內容策略、研究、撰寫、發佈、回覆留言」整條流程交給 AI。前者有固定 input、欄位和 review；後者混合了多個不同風險與責任，應先由 runbook 拆開。

**Jimmy 的結論：** 第一份 AI Skill 的成功，不是把 SOP 消失，而是讓人更清楚看到哪一段可以可靠重跑、哪一段仍需要人的判斷與批准。

可以跟這六步拆：

1. 選一條你已做過多次的 SOP，但只圈出其中一段固定工作。
2. 寫下人必須決定甚麼、AI 可以先做甚麼、AI 必須停下來問甚麼。
3. 限定 AI 只讀已批准、公開安全或受控的 input class。
4. 定義它要交的 draft artifact、check 和 named reviewer。
5. 為資料不足、規則不過、外部 action 寫 stop／exception 狀態。
6. 用 sample 或 sandbox 跑一次，保留 runbook，不給 autonomous release。

暫時不要把所有 SOP 都轉成 AI Skill；不要因為 AI 能起草就開放全部資料；更不要把 draft 當成替代人的專業意見、責任或批准。若你已判斷一段工作夠穩定，可讀 [Skill 其實是一份工作合約](4-23-skill-is-a-work-contract.md)；若仍不清楚例外如何交回人，讀 [AI 一遇資料不足就繼續猜？Skill 要先寫好 exception ladder](4-34-skill-exception-ladder.md)；若真正卡在需求未講清楚，讀 [Build 前先寫 assumption ledger](4-35-assumption-ledger-before-build.md)。

← [返回 AI Builder](../04-ai-builder.md) · [按問題瀏覽](../BROWSE.md)
