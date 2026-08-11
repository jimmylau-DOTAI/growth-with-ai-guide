# 你唔係未識用 AI Agent：真正難係把一件工作交到可驗收

你可能已經很熟 ChatGPT：問問題、整理資料、寫初稿、幫你想方向。這些已經能省不少時間，但很多工作做到一半，你仍然要自己把答案搬到文件、核對資料、決定能否採用、處理例外，再把事情交給下一位。工具回了一段文字，不等於那段真工作已經交出去。

於是很多人跳到另一個極端：一聽到 AI Agent、Codex、connector 或 automation，便想叫 AI 自己讀完所有材料、自己改檔、自己發出去。問題不是模型不夠聰明，而是工作還未有清楚範圍、可用資料、停位和驗收者。你把一件講不清的工作交給 AI，它只會更快把不清楚放大。

Jimmy 的重點是：AI Agent 不是更神奇的聊天機械人；它是被交付一段有限、可檢查工作的執行者。由 ChatGPT 對話走到 Codex 做事，真正的轉變不是多裝一個工具，而是你能否把一件工作交到「人可以收貨、AI 知道何時應停」的程度。

| 你現在看到的情況 | 真正缺的不是甚麼 | 先留下甚麼 |
|---|---|---|
| AI 給到不錯答案，但後半段仍要自己收拾 | 一個可交接的工作單位 | scope、artifact、review |
| 想叫 Codex 幫忙改一個 workspace | 更長 prompt | allowed material、可改範圍、回退點 |
| 想做 Agent，卻怕它亂讀、亂改、亂發 | 更多 agent 或 connector | stop line、owner、human approval |
| 一條 routine 已做過幾次 | 一堆聊天紀錄 | 可重跑的 work brief 與驗收條件 |

## AI ChatGPT 對話和 AI Agent 工作，到底差在哪一段？

ChatGPT 對話通常由你帶著走：你貼資料、問一條問題、看一個答案，再決定下一句要問甚麼。它很適合探索、起草、比較選項和幫你拆開想法；但它不天然知道今次哪些資料可用、結果會交給誰、遇到未知要不要停，也不會自動留下下一位可接手的工作紀錄。

AI Agent 工作則多了一層「工作合約」。同一個模型可以仍然在聊天框裡使用，但你已經把任務、材料、邊界、交付和驗收說清楚。Codex 特別容易讓人看見這件事，因為它可以在指定 workspace 讀檔、提出計劃、處理被批准的一小部分改動，再把檢查結果和差異交回來；不過工具能做到，並不代表它有權自行擴大工作。

**Jimmy 的結論：** Chat 的完成線是「我得到一段有用回答」；Agent 工作的完成線是「一段有限工作有可檢查 artifact、清楚狀態和人手決定」。

| 問題 | ChatGPT 對話 | AI Agent 工作 |
|---|---|---|
| 你交出去的是甚麼 | 一條問題、一些材料或一個方向 | 一個有 scope、材料和完成線的 work unit |
| AI 主要負責甚麼 | 回答、起草、提出選項 | 讀指定 context、完成中間步驟、交回 artifact／receipt |
| 人仍然負責甚麼 | 判斷答案是否有用 | 定 authority、review、exception 和採用決定 |
| 完成後留下甚麼 | 一段 chat | output、檢查、未知與下一步 |

所以不要把 Agent 想成「AI 自己做晒」。它只是令一段本來要由你手動跟住的工作，可以在清楚責任下被交接、被檢查和被重新跑一次。

## AI Agent 第一份工作，為甚麼不應該由全自動開始？

第一次試 Agent 時，最常見的衝動是選最大的一件事：自動處理所有 inquiry、連 CRM、寫每一篇內容，或者直接改完整個網站。這些願望不是錯，但它們把很多未知、權限和例外綁在一起。第一輪一旦出錯，你甚至不知道問題出在 task、資料、工具、規則還是驗收。

第一份工作應該小到你能看懂它的每一步，也重要到你能分辨結果是否真的有幫助。它可以是把公開資料整理成一頁 research brief、檢查網站上一個明確顯示問題、把一份已批准 outline 變成 internal draft，或只把重複工作拆成一份可討論計劃。目標不是展示 AI 有多自主，而是證明你能管理一次安全、可回看的交接。

**Jimmy 的結論：** 第一個 Agent 不追求「替你做完一個部門」；它追求交回一份你能驗收、能拒絕、也能安全重跑的小成果。

| 適合作為第一份 Agent 工作 | 為甚麼適合 | 暫時不要做甚麼 |
|---|---|---|
| 公開資料 research brief | 來源範圍、格式和 review 容易定 | 將未核對說法寫成事實 |
| 一個已知 UI 顯示問題的檢查 | scope 小，可用 diff／screenshot 核對 | 改資料庫、登入、付款或核心邏輯 |
| 已批准材料的 internal outline | 可看結構和 unknown，不會直接外發 | 自己補未批准 offer／日期／價格 |
| 把 routine 拆成 work plan | 先看清 workflow，成本低 | 直接接真資料或開 automation |

你選的是一件「即使 AI 做得未完美，你仍然能指出它哪裡不對」的工作。這個可見性比第一輪省多少時間更有價值。

## 用 Codex 示範 AI Agent：一份真工作要交代哪五格？

假設有一個公開展示用的小型網站，首頁某個區塊在手機版顯示不齊。你不應只說「Codex，幫我整靚個首頁」，因為 AI 不知道可否改版面以外的東西、不知道哪個畫面是驗收依據，也不知道若問題涉及資料或部署應否繼續。

較安全的做法是把工作縮成五格。這五格不是 bureaucratic 表格，而是讓你和 AI 在開工前對齊：今次交甚麼、可看甚麼、不可碰甚麼、怎樣知道完成、遇到甚麼要停。即使用的不是 Codex，而是 Claude Code、ChatGPT 的 project 或其他 agent 工具，這五格仍然適用。

**Jimmy 的結論：** AI Agent 的第一個 prompt 不應是「開始做」，而是先把一份可驗收的工作交代清楚。

| 五格 | 這個網站例子的寫法 | 缺少時的風險 |
|---|---|---|
| **Task** | 找出首頁手機版文字被截斷的原因，提出最小修正 | AI 不知道要交甚麼 |
| **Allowed material** | 只讀 README、首頁相關程式和公開測試資料 | 讀到不應碰的檔案／資料 |
| **Scope／stop line** | 只改顯示層；涉及資料計算、登入或 deploy 即停 | 一個小修正變成全站改動 |
| **Artifact／evidence** | 交 diff、檢查結果和修改前後說明 | 有 output 但無法核對 |
| **Review owner** | 由網站 owner 決定是否採用及部署 | 沒人為結果負責 |

```text
先讀 README 和首頁相關檔案，說明你理解的手機版顯示問題。
今次只檢查及修改首頁顯示層；不要改資料計算、登入、付款、部署或任何 production setting。
先提出最小修改計劃，等人確認後才改。
改完後跑現有可用檢查，交回：改了甚麼、檢查結果、仍未驗證甚麼、怎樣回退。
若發現問題超出顯示層，停止並列出需要 owner 決定的問題。
```

這樣寫不是令 AI 變慢，而是把你原本要在事後補救的判斷，提早放到工作開始前。Agent 有清楚舞台，人才有真正控制權。

## AI Agent 有 output，為甚麼仍然不代表工作完成？

AI 很快給你一個 diff、文件或畫面時，最危險的誤會是把「看起來合理」當成「已經完成」。它可能只處理了最表面症狀、漏了某個畫面尺寸、誤解了原有邏輯，或者檢查其實根本沒有跑成功。若你沒有預先定好 evidence，最後只會靠感覺收貨。

這也是為甚麼 Agent 工作必須把 artifact 和 evidence 分開想：artifact 是它交了甚麼；evidence 是你憑甚麼判斷它可用。對內容工作來說，artifact 可以是 brief 或 draft，evidence 是來源、unknown 和 reviewer 意見；對 Codex 類工作，artifact 可以是修改，evidence 是 diff、測試、手動檢查與可回退位置。

**Jimmy 的結論：** AI 說「做完」只是狀態訊號；工作完成要由已約定的 evidence 和 owner review 共同決定。

| AI 交回的東西 | 還要問的問題 | 可作的 evidence |
|---|---|---|
| 一段內容 draft | 是否只用了允許材料？unknown 有沒有露出來？ | source list、review comment、改稿紀錄 |
| 一個 code diff | 是否只改了 scope 內位置？ | diff review、changed-file list |
| 一張畫面 | 是否真在目標尺寸／情境可用？ | 明確 scenario 的手動檢查 |
| 一句「tests passed」 | 跑了哪個檢查？有沒有 skip／fail？ | command output、已知未驗證項目 |

當 evidence 不足，正確結果可以是「還不能採用」。這不是否定 AI，而是保護你不會把一個未驗證 output 帶進下一個真實流程。

## 何時由 prompt 升成 AI Skill、automation 或 Agent loop？

不是每件工作都需要 Agent。有些一次性問題，用一段 prompt 配合人手 review 已經很好；有些工作重複但仍常變，先保留 human runbook 會比過早寫成 Skill 更可靠。只有當 input、輸出格式、常見例外和驗收方法已逐漸穩定，才值得把它升成可重跑的 Skill。

Automation 或 Agent loop 又再多一層要求：除了工作內容要穩，還要說清何時開始、資料怎樣到達、哪個 state 要被記錄、錯誤怎樣停、誰可批准下一步。把尚未理解的流程串起來，不會創造系統，只會更快重複混亂。

**Jimmy 的結論：** 先選最小足夠的工作形態；工作還未穩定時，保留人在 loop 裡，比假裝已自動化更成熟。

| 工作現況 | 比較合適的形態 | 先留下甚麼 |
|---|---|---|
| 一次性探索、答案未定 | Prompt＋人手整理 | 問題、材料、採用判斷 |
| 做過幾次、格式漸穩 | AI Skill | input、steps、quality gate、例外 |
| 有固定 trigger 和可讀 state | Automation pipeline | trigger、state、failure route、approval |
| 多步會反覆跑、每步可驗收 | Bounded agent loop | scope、tool boundary、review、stop line |

不要因為工具叫自己「agent」就把它放到最後一格。真正決定形態的，是工作是否已經清楚到足以被安全重跑。

## AI Agent 最容易出事的四個誤會，應該怎樣拆開？

第一個誤會是以為 Agent 能自己補齊不清楚需求；第二個是以為讀得越多 context 越好；第三個是看到第一輪 output 便立即接真資料、外發或部署；第四個則是把多個角色名稱當成多 agent 系統。這些做法看似進取，其實都把人該做的定義、授權和驗收藏了起來。

較好的做法不是每次都加規則，而是把問題還原到工作哪一格未清楚：task 未定、材料未批准、權限不清、review 沒人、還是例外沒有去處。找對卡位，下一步通常會變得很小、很具體；找錯卡位，AI 只會幫你把一個大問題寫得更像完成。

**Jimmy 的結論：** AI Agent 的風險通常不是「不夠聰明」，而是人把未定義的工作、未批准的資料或未驗收的結果誤交給它。

| 常見說法 | 真正問題 | 第一個修正 |
|---|---|---|
| 「叫它自己想方法」 | scope 和完成線未定 | 先寫最小 artifact 與 stop line |
| 「塞晒所有資料，佢自然會懂」 | allowed material 和 relevance 未分 | 只給本輪需要、可用的 context |
| 「第一次跑到就接真資料」 | 沒有 dry run 和失敗處理 | 先用公開／synthetic 資料試跑 |
| 「每個職位開一個 agent」 | context、authority、驗收其實未分開 | 先按交接與 verification 切工作 |

這四個誤會一旦拆開，你會發現很多「Agent 問題」其實先是工作設計問題。先把工作講清楚，才值得談更複雜的工具架構。

## 用一個安全的 AI Agent 試跑，怎樣知道值得繼續？

完成第一輪後，不要只問「它好不好用」。更有用的是回看：它是否在預定 scope 內完成？哪一格 context 最常缺？reviewer 是否能快速指出可採用與不可採用？如果同類工作明天再來，你能否用同一份 brief 讓人或 AI 再跑一次？

若答案大致是可以，下一步不是馬上放大，而是把剛剛學到的例外、檢查和修改原因寫回 work card。若答案是否定，也不是失敗：你已找出這條工作還缺 evidence、owner、資料或流程定義。這比投入一大堆時間後才發現根本不適合 automation 好得多。

**Jimmy 的結論：** 第一輪的成功不是 AI 代替了你；而是你得到足夠 evidence，決定這條工作應保留、修正、升成 Skill，還是停下來。

| 試跑後看到的訊號 | 最合理的下一步 | 暫時不要做甚麼 |
|---|---|---|
| output 清楚、review 快、例外少 | 把做法寫成 work card 或 Skill 草稿 | 直接擴到所有工作 |
| 同一資料缺口反覆出現 | 補 context pack 或 owner 問題 | 叫 AI 每次猜一次 |
| 結果常要人重做大半 | 回到 task／quality gate 重設 | 只換模型或加更多 agent |
| 涉及高後果 action | 保留 human approval、改用 dry run | 將自動化當成必然下一步 |

你不是要一次過變成 AI Builder。你只需先選一段真工作，讓 AI 在可見邊界內幫你跑一輪，然後用 evidence 決定下一步。這就是由「AI 會答問題」走到「AI 可以在人的判斷下參與創造價值」的起點。

## 想由 ChatGPT 走到 AI Builder，下一步應該看哪一篇？

如果你現在仍然不知道要把哪件工作交出去，先從一張 work card 開始，而不是從選 agent framework 開始。它會迫你把 input、output、完成線、owner 和例外寫出來；這些資訊日後才能變成 Skill、loop 或 automation，而不是只留在一段對話裡。

若你已有一條工作想試，也請先選低風險、可回退、可 review 的版本。真正的 AI Builder 不在乎用了幾多模型或 connector，而在乎每次交接後有沒有留下下一次可以少猜一次的規則、evidence 和決定。

**Jimmy 的結論：** 由聊天走到 Agent 的下一步，是寫清第一個可驗收 work unit；不是追求更大、更自動或更多角色的 demo。

| 你現在卡住的位置 | 接著讀甚麼 | 會留下甚麼 |
|---|---|---|
| 不知道一件工作怎樣才算可交 AI | [答案不等於一份工作](./4-22-answer-is-not-work.md) | work unit 的完成線 |
| 想即刻寫第一張 work card | [跟住填第一張 work card](./練習-write-an-ai-work-card.md) | 一份可 review brief |
| 已有好 prompt，想知道何時變 Skill | [Skill 其實是一份工作合約](./4-23-skill-is-a-work-contract.md) | Skill 的 input、quality gate、exception |
| 想安全試第一條 loop | [先跑一條可停的 Agent loop](./4-25-first-agent-loop.md) | bounded loop 的 stop line |

可返回 [AI Builder stage](../README.md) 看其他入口。本文以公開 agent-building 指引和 Jimmy 的工作判斷整理；它不構成資料、權限、部署、對外發送或任何 production action 的批准。
