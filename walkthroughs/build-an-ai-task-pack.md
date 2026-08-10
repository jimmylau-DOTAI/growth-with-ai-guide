# AI 每次都要重講背景？用五格寫一份可 review 的 AI task pack

你可能遇過這個情況：明明已經把要求講得很長，AI 還是寫得很泛；你換了一個 chat，又要重新解釋讀者、資料、語氣和上次改過甚麼。最後不是 AI 沒有 output，而是你沒有一份可以讓人和 AI 同時看懂「今次到底要交甚麼」的工作交代。

很多人以為解法是把所有舊檔案塞進去，或繼續加長 prompt。這樣往往只令重點更模糊，還可能混入不應分享的客戶、合約、CRM 或未公開資料。真正缺的不是更多內容，而是把本輪 task、可用材料、例子、邊界和收貨方式分清楚。

Jimmy 的判斷是：task pack 不是 AI 的魔法 prompt，也不是大型知識庫；它是一張讓一件工作可以安全起 internal draft 的 brief。它讓 AI 知道根據甚麼、不該猜甚麼、人又怎樣決定 pass、revise 或 stop。

| 五格 | 它先解哪個問題 | 做完後留下甚麼 |
|---|---|---|
| **Task** | 這份 output 幫誰完成／決定甚麼？ | 可交付 artifact |
| **Material** | 哪些資料可作根據、哪些仍未知？ | allowed material 範圍 |
| **Examples** | 「好」的 pattern 是甚麼、甚麼不可照抄？ | 可重用參考方式 |
| **Boundary** | 哪裡不能越過、何時應停？ | stop line |
| **Evaluation** | 誰按甚麼條件收貨？ | reviewer 與 pass criteria |

## AI task pack 是甚麼，為甚麼它比一段長 prompt 更有用？

Prompt 可以叫 AI 開始做，但它未必把你腦裡所有工作判斷說清楚。你寫「幫我做一份專業 briefing」時，AI 不知道 briefing 是給誰看、哪些材料是真正根據、資料不足可否自己補、完成後誰說了算。它只能用一般常識猜一份看似合理的內容。

Task pack 則把這些隱藏條件攤開。它不保證 AI 一次過做對，也不授權 AI 自動做更多事；它只是把本輪工作縮到一個可以被 AI 起草、被人檢查、被下一次重用的範圍。你會更快看出問題到底在任務、材料、權限還是完成線。

**Jimmy 的結論：** Task pack 的價值不是令 prompt 變長；而是令一件工作有清楚 input、output、unknown、stop line 和 review。

| 只用一句 prompt | 有 task pack 的工作 |
|---|---|
| 「幫我寫好個 briefing」 | 知道讀者、目的、artifact 和 reviewer |
| AI 自己判斷哪些材料可用 | Allowed material、unknown、not allowed 已分開 |
| 不滿意時只叫它再改 | 可指出哪條 pass criteria 未過 |
| 很容易越界或補資料 | 有 stop and ask 條件 |

當你可以把同一份 task pack 帶到另一個 AI chat 或交給同事，AI 工作才開始脫離「今次剛好問得好」的運氣。

## AI 第一份 task pack 應揀甚麼工作，才可以安全試一次？

第一次不要選最重要、最敏感或最難回退的工作。若你用真實客戶名單、付款、合約、CRM、未公開 offer 或需要直接外發的內容測試，task pack 還未幫到你學交代工作，就先引入資料權限和不可逆後果，結果很難看清是 workflow 問題還是風險問題。

較好的練習是一份只供 internal review 的 draft：把公開資料整理成 research brief、把已批准 outline 變成 teaching draft、或將一個重複 FAQ 先整理成問題清單。它要夠真，讓你能看見 AI 有沒有根據材料；也要夠小，讓 owner 可以清楚說出是否收貨。

**Jimmy 的結論：** 第一份 task pack 的目標不是自動化；是安全地試一次「AI 起稿、人 review、未知可見」的工作交接。

| 合適的第一輪 | 為甚麼適合 | 暫時不要選 |
|---|---|---|
| 公開資料 → internal research brief | 來源、欄位和 unknown 可核對 | 真實客戶／CRM 資料 |
| 已批准 outline → teaching draft | 可看 AI 有沒有跟結構走 | 未批准對外課程文案 |
| 固定 FAQ → internal question map | 可先整理，不必立即發布 | 付款、合約或正式系統寫入 |
| 一段 routine → work plan | 先搞清流程，不需執行 | 一次過接 connector／automation |

選一件下星期可能又會再做、即使 AI 寫錯也能安全拒絕的工作。這會讓你的第一輪 review 有真正的學習價值。

## Task 格怎樣寫，先不會把「幫我寫篇文」當成任務？

「幫我寫一篇文」只是一個 output 名稱，不是一件完整工作。AI 不知道文章是要幫新手理解、讓 owner 比較方向，還是準備對外發布；沒有這個用途，它很容易把素材拼成一大段內容，卻沒有幫任何人作出下一步決定。

Task 格要先寫清誰會用這份 output、他看完要完成或決定甚麼、以及今次只交甚麼 artifact。這會限制 AI 不要自己擴大到發送、發布、改系統或補造事實，也讓 reviewer 可以用同一個目的收貨。

**Jimmy 的結論：** Task 不是「要 AI 做甚麼格式」，而是「誰要用這份成果完成甚麼、今次只能交到哪一步」。

| 模糊講法 | 可 review 的 Task |
|---|---|
| 幫我整好個 briefing | Internal workshop owner 要判斷 FAQ 方向；交一份含待確認欄的 briefing draft |
| 幫我研究一下 | 內容 owner 要決定是否值得深入；交五條問題、公開來源和 unknown 表 |
| 幫我寫得專業啲 | Reviewer 要比較兩個教學開場；交兩個只根據已批准材料的 draft |

```text
讀者／owner：＿＿＿＿＿＿＿＿＿＿
他看完要決定／做到甚麼：＿＿＿＿＿＿＿＿＿＿
今次交甚麼 artifact：＿＿＿＿＿＿＿＿＿＿
本輪不包含甚麼：＿＿＿＿＿＿＿＿＿＿
```

Task 一寫清，你便能立即發現有些願望還未是可交 AI 的工作：例如沒有 owner、沒有完成線，或其實需要先有人作業務決定。

## Material 格怎樣分 approved、unknown 和 not allowed，才不會令 AI 補故事？

AI 可以把一段過期資料、舊例子或未確認轉述寫得同樣有自信。若你只說「根據以下資料」，AI 未必知道哪份可當事實、哪份只可作語氣參考、哪個地方必須留空。於是最危險的情況便出現：內容看似完整，卻把未知變成了肯定句。

Material 格的工作是分流，不是收藏。Approved 是本輪可以依據的已批准或公開材料；unknown 是仍要 owner、研究或下一輪確認的缺口；not allowed 則明確說明不能讓這個工具看到、不能在這次工作使用的資料。三欄能保護你不會以「AI 需要 context」為由越過資料邊界。

**Jimmy 的結論：** Context ready 不等於材料多；而是 AI 知道哪裡可根據、哪裡應標 unknown、哪裡根本不可碰。

| 材料狀態 | AI 今次怎樣用 | 人仍要做甚麼 |
|---|---|---|
| **Approved** | 根據它起 internal draft，列出來源 | 確保版本／日期仍適用 |
| **Unknown** | 在對應位置標待確認，列出要問的問題 | 補 evidence、問 owner 或縮小範圍 |
| **Not allowed** | 不讀、不引用、不要求取得 | 保持在受控流程或改用安全替代 |

```text
Approved：公開活動頁、已確認 topic、兩個已發布示例。
Unknown：最終日期、價格、是否有合作方出席。
Not allowed：報名名單、付款資料、客戶紀錄、未批准 offer。
```

若一項資料會改變對外承諾、權限或核心結論，不能只放在 unknown 然後繼續寫最終稿；應先 ask owner 或 stop。

## AI example 應怎樣用，才不會變成照抄舊文章或舊答案？

Example 的價值是讓 AI 看見「這類工作什麼感覺才對」：開場怎樣先說讀者問題、表格怎樣讓人 review、語氣何時要保守。它是一個 pattern，不是可以搬到新工作上的事實庫。尤其是舊文章的日期、數字、客戶語境和成效說法，很可能不再適用。

因此 task pack 要把「可參考」和「不可複製」一起寫。這不只保護來源與公開安全，也逼你說清其實想 AI 學的是結構、深度、語氣，還是某種欄位設計。若你不能說清，AI 只會模仿表面詞句，結果既不像你，也不一定適合今次讀者。

**Jimmy 的結論：** Example 是讓 AI 學 pattern，不是讓 AI 偷搬舊內容；每個 example 都要配一條不可以照抄的邊界。

| Example 類型 | 可以學甚麼 | 不可照抄甚麼 |
|---|---|---|
| 已公開教學文章 | 痛點 → 解釋 → 做法的節奏 | 原文段落、作者主張、舊數字 |
| 已認可 internal draft | 欄位、深度、review 方法 | 私人資料、未公開結果、專有說法 |
| 舊 FAQ | 問題分類與語氣 | 過期政策、今天未確認答案 |

```text
Pattern to follow：每個問題先說明讀者卡位，再給可檢查做法，unknown 要可見。
Do not copy：不可照搬舊文數字、客戶語境、效果承諾或任何未批准 CTA。
```

把 example 寫成 pattern 後，AI 就較容易在新材料和新讀者之下生成自己的 draft；而不是只是把熟悉句子換幾個字。

## AI boundary 和 stop line 要怎樣寫，才不會由 internal draft 變成越權行動？

很多 AI 工作不是在起稿時出事，而是在「既然已做了，不如順便」時越界：順便讀更多資料、順便把資料寫入系統、順便發送、順便替 owner 作承諾。若 task pack 只寫想得到甚麼，沒有寫今次不可做甚麼，AI 和人都很容易把 workflow 誤當成已有授權。

Boundary 要寫得跟今次工作一樣具體：只可整理哪些材料、只可交 internal draft、遇到哪些狀況必須停下。Stop line 不是阻礙進度；它令未知、權限和高後果決定在正確的人手位出現，而不是在一份看似成功的 output 裡被掩蓋。

**Jimmy 的結論：** Boundary 不是一句「注意安全」；它是寫清 AI 在本輪只能做到哪一格、哪裡必須交回人。

| Boundary 類型 | 可以怎樣寫 | 為甚麼重要 |
|---|---|---|
| Only do | 只根據指定公開材料起 internal draft | 防止 scope 無聲擴大 |
| Do not do | 不發送、不發布、不寫入系統、不補造資料 | 不把 draft 當 execution |
| Stop and ask | 涉及私人資料、未批准說法、衝突 evidence 即停 | 讓 owner 在需要時決定 |

```text
本輪只可做：整理指定公開資料，交一份 internal FAQ draft。
本輪不可做：外發、發佈、寫入 CRM／任何系統、補造未知資料。
遇到以下情況 stop and ask：材料涉及私人資料、沒有來源的 claim、需要業務／權限決定。
```

一條清楚 stop line 讓你可以安心先試 AI；因為它同時說明甚麼不屬於這一次試跑。

## AI Evaluation 怎樣定 pass criteria，才不會只用「感覺幾好」收貨？

AI 的 output 很容易流暢、完整、像一份成品；但你若只憑第一眼覺得不錯，下一輪很難說明哪裡真是可採用、哪裡仍要改。Evaluation 格將「好不好」變成 reviewer 可以逐項檢查的條件，亦讓 AI 知道這次不是只要交一大段文字。

開始時三個條件已經足夠。選和任務最有關的：例如重要主張能否回到 approved material、unknown 有沒有露出、指定欄位是否齊、是否越過 boundary。不要寫「要有質素」或「要專業」，因為連人也說不出怎樣驗證，AI 更無法自查。

**Jimmy 的結論：** Evaluation 不是最後挑錯字；它是預先定義這份 internal draft 能否進入下一位人手 review 的完成線。

| 模糊要求 | 可 review 的 pass criteria |
|---|---|
| 不要亂講 | 重要主張可回到 approved material；沒有根據的內容標 unknown |
| 寫清楚 | 每一段有指定欄位，reviewer 能看出下一步 |
| 不要越界 | 無外發、無系統寫入、無未批准資料 |
| 方便同事接手 | 最後列出 materials、unknown 和 owner 問題 |

```text
Reviewer：＿＿＿＿＿＿＿＿＿＿
Pass criteria：
1. 每項重要內容可回到 Approved material。
2. Unknown 明確標示，沒有補成事實。
3. 只交 internal draft，沒有越過 Boundary。
Handoff note：列出已用材料、待 owner 決定的問題和下一步。
```

有了 reviewer 和條件，結果可以是 pass、revise 或 stop。這三種都比「AI 做完了」更有用，因為它們真正決定下一步。

## 用公開 workshop briefing 跑一次：五格 task pack 怎樣連起來？

假設你要為一個公開 workshop 做 internal briefing，供內容 owner review。你有公開活動頁、已確認的三個 learning points 和兩個已發布示例；最終日期和 price 尚未確認。這正好適合練 task pack，因為你能起稿、又能清楚看見 unknown 去了哪裡。

這個例子不是要你照抄 workshop 寫法，也不是要 AI 把自己變成活動營運者。它只是示範：同一份工作若五格都清楚，AI 可以把已知整理成 draft，而最敏感的問題仍保留給 owner。你學的是工作交接，不是把流程自動化。

**Jimmy 的結論：** 一份 task pack 成功，不是它令 AI 寫得像完成品；而是它讓 reviewer 一眼分清已知、unknown、不可做和下一步。

| 五格 | 這次的寫法 | Reviewer 看甚麼 |
|---|---|---|
| Task | 交一頁 internal briefing，供 owner 判斷內容方向 | 是否真的支持這個決定 |
| Material | 公開活動頁、確認 topic；日期／價格列 unknown | 有沒有把未知寫成事實 |
| Examples | 兩個公開教學文章的結構 pattern | 有沒有照搬舊主張 |
| Boundary | 不讀名單、不發送、不發布、不寫系統 | 有沒有越過 internal draft |
| Evaluation | 來源可回查、unknown 可見、欄位齊 | pass、revise 或 stop |

```markdown
# Task pack：公開 workshop internal briefing

**Task**
Owner：content owner；Artifact：一頁內部 briefing draft；用途：決定內容方向。

**Material**
Approved：公開活動頁、三個已確認 learning points；Unknown：最終日期、價格；Not allowed：名單、付款、未批准 offer。

**Boundary / Evaluation**
只交 internal draft；重要內容需有來源、unknown 可見、最後列 owner 問題。
```

跑完後只需寫一條 receipt：哪一格最難填、AI 哪裡仍猜錯、下次要補哪一條 rule。這才讓下一份 task pack 比今次更好。

## 填完 AI task pack 後，下一步怎樣真的用它，而不是存成另一份筆記？

先把五格貼進你正在使用的 AI 工作台，只帶入本輪 Approved material，要求它交 internal draft，並在最後列出 unknown 和需要 owner 決定的問題。不要先把 task pack 接到外發、CRM、付款、部署或完整 automation；第一輪只要驗證它能不能讓 reviewer 更快收貨。

review 後，保留的不是整段 chat，而是一條最有用的修改理由。例如「新手 briefing 必須先交代讀者正在做哪件工作」或「無 evidence 的成效說法要標 unknown」。下一次相近工作先帶入這條 rule；若還是不穩，繼續在 AI Super User 練習，不要過早假裝已可成為 Skill。

**Jimmy 的結論：** Task pack 的完成線不是填完模板；是它令下一次同類工作少猜一次、reviewer 更容易作出 pass／revise／stop。

| 你現在卡住的位置 | 接著讀甚麼 | 會留下甚麼 |
|---|---|---|
| 不知資料缺口可否起稿 | [資料未齊唔等於要停](../chapters/2-12-is-context-ready-to-draft.md) | draft-ready decision |
| 想分清 evidence、解讀與 unknown | [生成前先分 evidence 和未知](../chapters/2-8-evidence-before-generation.md) | 四欄 brief |
| 已有 first draft，想令第二稿真的較好 | [AI 第二稿 review loop](../chapters/2-11-review-loop-next-draft.md) | revision memo |
| 同類工作已穩定重複 | [AI Operator stage](../03-ai-operator.md) | SOP、state、exception |

可返回 [AI Super User stage](../02-ai-super-user.md) 看其他入口。本文只用公開／synthetic 情境；task pack 不構成資料存取、外發、系統寫入或 production action 的批准。
