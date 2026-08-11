# 示範一次工作，AI 未必已學識：由 demo 到可重跑 Skill，中間還差哪五格？

你示範了一次工作：開了甚麼檔、按了哪些按鈕、怎樣整理資料、最後交了甚麼。這是很好的開始，因為它把原本只在你腦內的做法拉到可看見的表面。很多人於是以為 AI 已經「學會」，下一次可以直接照做；但換一份資料、少一個欄位、遇到一個例外或有人要求對外 action 時，它卻不知道為何要這樣做、甚麼可以改、何時該停。

問題是 demo 主要展示動作，不一定展示判斷。你可能在過程中默默分辨了來源是否可信、資料是否足夠、這次是否只做 draft、哪句話不能說得太肯定、誰應該最後收貨。人類同事看一次示範也許能追問補足，AI 或未參與原本情境的人卻很容易只模仿看得見的步驟，把隱藏標準漏掉。

Jimmy 的判斷是：示範不是 Skill 的終點，而是抽取 know-how 的入口。要由 demo 變成可重跑的 Skill，至少要補上 trigger、input boundary、judgment／reason、artifact＋acceptance、exception＋owner 五個空格，再用安全材料重跑幾次。這樣你驗證的不是 AI 有沒有記住動作，而是這段工作能否在清楚邊界下穩定交付。

| Demo 缺的空格 | 它要補甚麼 | 補完後留下甚麼 |
| --- | --- | --- |
| Trigger | 甚麼情況才應開始，而非任何事都照做 | 這份 Skill 的適用入口 |
| Input boundary | 只可讀甚麼、資料不足怎辦 | Approved reference 與禁止範圍 |
| Judgment／reason | 為何選這個做法、何時不適用 | 判斷原則、unknown 和 escalation |
| Artifact + acceptance | 交甚麼才可 review、何謂不合格 | 可打開 output 與 checklist |
| Exception + owner | 矛盾、越界、外部 action 時怎樣停 | Stop status、handoff 和 release owner |

## 看過一次 demo 的 AI，為甚麼仍然可能在下一次工作做錯？

Demo 讓 AI 或人看見「做了甚麼」，但未必看見「為甚麼這次可以這樣做」。同一個畫面動作在另一個情境可能有完全不同意思：你拖進一份文件，可能因為它是本輪唯一 approved source；你跳過一段資料，可能因為它沒有 owner；你沒有發出某份內容，可能因為它只可 internal review。這些都不會自動從滑鼠點擊或最後 output 推導出來。

一次成功還可能剛好碰上理想條件：資料齊、格式乾淨、沒有例外、你在旁邊即時補充、最後 reviewer 亦剛好知道該看甚麼。若把這次情況直接當一般規則，AI 便會在資料不齊、來源衝突、範圍改變或需要人承擔時，仍照著表面動作跑到底。

**Jimmy 的結論：** Demo 證明一個人曾經把工作做過；它不自動證明這個工作已被定義、可交接、可驗收。要變成 Skill，必須把看不見的標準與停止線寫出來。

可以這樣看同一個動作背後的隱藏內容：

| Demo 裏看見的動作 | 看不見但必須補的判斷 |
| --- | --- |
| 打開一份文件 | 為何它是 source of truth？哪些相似文件不可用？ |
| 將資料整理成表 | 哪些欄必填？資料不足時是否可留白？ |
| 選一個說法寫進摘要 | 哪個來源支持？何時應標 unknown？ |
| 按下「完成」 | 這只是 draft 還是有人已批准 release？ |
| 跳過某個步驟 | 這是一次例外還是每次都該跳過？誰可決定？ |

若這些答案仍只存在於你腦內，先將它們寫成 Skill 候選的規則，而不是叫 AI 下一次「照住做」。

## Demo 的 trigger 和 input boundary 怎樣補，才不會任何工作都被錯套同一套做法？

一段 demo 很容易讓人誤以為「這就是做法」，但每一個做法都有適用條件。假如你示範了把三篇公開文章整理成 internal brief，這不等於任何文章、任何研究題目、任何對外內容都可以用同一流程。沒有 trigger，Skill 會變成一把甚麼都想切的刀，最後例外愈來愈多、輸出愈來愈不可靠。

input boundary 同樣重要。你在示範中使用的資料可能剛好已公開、已批准、有清楚欄位；下一次若 AI 讀到客戶 chat、CRM、合約、付款資料、credentials、未公開策略或無 owner 的舊檔，它不應因為「之前示範過讀資料」便視為可用。要將情境寫清，AI 才不會用最寬鬆的解讀取代你的資料邊界。

**Jimmy 的結論：** Demo 要變 Skill，第一步不是把步驟錄得更長，而是寫清這份做法何時適用、只可讀甚麼、缺甚麼便不開始。Trigger 和 input 是比操作細節更早的品質閘。

由 demo 抽取時，先填：

| 項目 | 問題 |
| --- | --- |
| Trigger | 是哪類重複工作、資料到甚麼程度才值得開始？ |
| Purpose | 這輪只交 internal draft，還是有不同責任？ |
| Allowed input | 哪些指定 URL、檔案、schema 或 sample 可讀？ |
| Source of truth | 有衝突時以哪一份為準？ |
| Not allowed | 哪些私有、敏感、未分類或外部資料不可讀？ |
| Data shortage | 少了甚麼便 `needs input`，不可自行補猜？ |

如果這些問題答不出，今天的正確成果是補 input map，不是讓 AI 練習操作更多檔案。

## Demo 裏的隱藏 judgment 怎樣寫出來，AI 才不會只模仿表面動作？

最有價值的 know-how 往往不是動作，而是選擇：為何這份資料可信、哪個例子不可用、甚麼時候寧願留白、何時應請 owner 決定、哪些語句不能對外說。人做事時常靠經驗把這些判斷壓縮成很快的直覺；demo 只捕捉結果，未必捕捉了你當時排除過甚麼選項。

不是所有 judgment 都要變成硬規則。有些可寫成 yes／no check，例如「沒有原始來源便不可作具體事實 claim」；有些適合留下 rubric 或 reviewer flag，例如「這段文字是否會令初學者誤解」；還有些必須由 owner 決定，例如公開承諾、客戶語境、品牌立場、付款／權限 action。分開這些，AI 才不會將一個人的經驗錯誤地模仿成不可變動的流程。

**Jimmy 的結論：** 將 judgment 寫出來，不是要把人的專業全部自動化，而是讓 AI 知道哪些可按規則做、哪些要標 unknown、哪些必須交回人。這才是 demo 轉 Skill 的真正學習。

可把每個「為何」路由到正確位置：

| Demo 裏的判斷 | 合適寫法 |
| --- | --- |
| 必填欄位／資料格式 | Hard rule／schema check |
| 來源可信度與資料不足 | Evidence rule + unknown／needs input |
| 語氣、讀者理解、教學取捨 | Reviewer rubric／flag |
| 策略、客戶、品牌承諾、release | Human-only owner decision |
| 新奇或一次性情境 | 留在 human runbook／assumption ledger |

如果某個判斷仍說不清，不要假裝 AI 已經學會；在 Skill 裏寫「遇到這種情況停下來問」比寫一條假的規則可靠。

## Demo 的最終 output 怎樣變成可 review artifact 和 acceptance，而不是一段影片或一次截圖？

一段 demo 可能有一個漂亮結果，但它不必然是下一位能打開、檢查、採用或退回的 artifact。若下一次只剩影片、截圖或對話記錄，reviewer 仍要自己找出 input、重做檢查、猜 AI 是否漏了甚麼。這令「示範得成功」與「工作可交接」之間出現很大斷層。

Skill 需要把最後結果定義成有結構的 artifact，連同完成線。它可以是一頁 research brief、一張表、一份 draft、一個 diff 或 run receipt；重點是它有固定欄位、來源、unknown、版本和 reviewer 能用的 checklist。這樣 output 才不是一次性生成物，而是 workflow 中可被下一步讀取的工作狀態。

**Jimmy 的結論：** Demo 的最後畫面不是 acceptance。真正的 acceptance 是另一個人不看原影片，也能根據 artifact 和 checklist 判斷這次是否通過、哪裡要退回、哪些 action 尚未發生。

例如「公開文章 → internal learning brief」可定：

| Artifact 部分 | Acceptance 問題 |
| --- | --- |
| Source list | 每項事實是否回到指定原始 URL？ |
| Claim／observation | 是否分開可支持內容和 Jimmy 判斷？ |
| Unknown／counterpoint | 資料不足、衝突是否被標記，而非硬填？ |
| Scope note | 有沒有清楚這只是 internal draft，未外發？ |
| Review receipt | 誰看過、pass／revise／stop、下一步是甚麼？ |

這份 artifact 即使日後換工具、換 Agent，仍能被同一把 acceptance 使用；這正是 Skill 比 demo 更耐用的原因。

## Demo 遇到資料不足、衝突或外部 action 時，exception 要怎樣補回去？

一次示範通常走的是順利路徑：資料齊、工具正常、沒有衝突、最後 output 可以交。真實工作卻不是這樣。原始 URL 可能失效、兩個來源可能矛盾、有人可能突然要求把 internal draft 對外發送、工具可能中斷，或 AI 發現工作其實超出原本 scope。若 demo 沒有這些情況的處理，AI 最容易把「照住做」理解為「無論甚麼都繼續做」。

例外不需要一次想完所有 edge case。先把你做這件工作時真實見過或最可能遇到的幾個情況寫出來：缺 input、規則不過、判斷衝突、工具失敗、外部／正本 action。為每一類指定 AI 要留下甚麼 state、誰接手、它刻意不做甚麼。這令停下變成正確交付，而非被誤解為 Agent 做不到。

**Jimmy 的結論：** Demo 變 Skill 的關鍵不是把順利路徑教得更快，而是讓 AI 在不順利時仍然知道怎樣安全交回工作。懂得停，才代表它沒有把隱藏風險帶到底。

可用這張 exception table 補齊：

| 發生甚麼 | AI 要留下甚麼 | 它不可做甚麼 | 下一位 |
| --- | --- | --- | --- |
| 缺指定資料 | `needs input` 欠項清單 | 用相似資料自行補 | 提供資料／owner |
| 來源互相矛盾 | `needs approval` 選項與原始位置 | 自己挑一邊當結論 | Judgment owner |
| 格式／必填欄不過 | `revise once` diff + check | 順手改 scope | AI 按規則修，reviewer 看 |
| 工具中斷 | `failed safe` 最後可信 state | 不斷重跑覆蓋舊結果 | Workflow owner |
| 要對外／改正本 | Draft + release request | 自行發送、覆寫、升權 | Human release owner |

想把這些狀態寫得更完整，可讀 [AI 一遇資料不足就繼續猜？Skill 要先寫好 exception ladder](./4-34-skill-exception-ladder.md)。

## Demo 後要跑幾次、看甚麼 evidence，才值得說它是一份 Skill 候選？

一次 demo 成功只告訴你「這個人曾在這個情況下做到」。要說這段工作可重跑，最少要在不同但相近、安全的 input 下跑幾次，看看它能否維持 input boundary、交相同類型 artifact、通過同一把 acceptance，以及例外是否走到正確 owner。你不需要等到零錯才開始整理，但要有 evidence 指出它的可靠範圍。

每次重跑亦不應同時改一切。若你發現問題，先判斷是 trigger、input、judgment、artifact、gate 還是 exception 缺口；每輪只改一格，再用同一類 case 比較。這樣 demo 才會慢慢變成有版本的工作 contract，而不是一段被遺忘在影片庫的操作記錄。

**Jimmy 的結論：** Skill 候選的門檻不是「AI 完全不犯錯」，而是你知道它在甚麼條件下可用、錯了會怎樣被看見和處理、下一輪要從哪裡改善。

可用這個 evidence checklist：

1. 是否已在 2–3 個相近、安全 input 下重跑，而非只在一個理想 case 成功？
2. 每次是否只讀批准資料，沒有擴大 context 或 action？
3. 是否交到同類 artifact，並通過固定 acceptance？
4. 有沒有至少一次資料不足／不合格情況，並走到正確 exception／owner？
5. 是否有 review receipt，令下一位知道採用、退回或停止的原因？
6. 規則是否有人負責更新／retire，而不是變成過期操作？

多數答案為「是」時，才可將 demo 整理成一份 draft Skill，先在 draft-only workflow 內繼續成熟。

## 想將一段 demo 變成第一份 Skill 候選，最安全的開始是甚麼？

不要先錄一個很長的端到端流程，也不要先把最重要的客戶工作交給 AI。選一件低風險、做過幾次、只交 internal draft 的 routine，並用公開或 synthetic input 重跑。你的任務是將當時隱藏判斷拆成五格，而不是證明 AI 可以完整複製你全部工作。

第一版可以只是一張半頁 card：trigger、allowed input、judgment／unknown、artifact＋acceptance、exception＋owner。跑完後請 reviewer 用同一張 card 收貨；若有一格仍只靠「你自己知」，就把它列作下一輪要補的規則或 stop condition。這種小步測試，才會令 know-how 真正變成可交接資產。

**Jimmy 的結論：** 示範是把 know-how 拉出腦袋的入口；acceptance 和 exception 才是把它變成可重跑 Skill 的地方。第一份 Skill 候選只需證明一段小工作可被安全重演，不需假裝已經 autonomous。

可以跟這六步開始：

1. 選一件低風險、重複、draft-only 的工作，避開客戶／production action。
2. 從 demo 寫出 trigger、allowed input、source of truth 和不可碰範圍。
3. 列出你當時其實做過的三個 judgment，分別寫成 rule、review flag 或 human decision。
4. 定義一份可打開 artifact 和三條 acceptance，不能只留影片／截圖。
5. 補 3–5 個真實 exception 的 state、owner 和未做 action。
6. 用公開／synthetic input 重跑 2–3 次，留 review receipt，再決定是否升成 Skill。

暫時不要因為一次示範成功就叫它 autonomous；不要把 demo 畫面當成可讀工作狀態；也不要因為錄過一次便開放私人 chat、CRM、合約、付款、credentials 或 production setting。若你要把這份候選寫成正式工作合約，可讀 [Skill 唔係存低一段長 prompt](./4-6-skill-is-quality-gate.md)；若你仍未知道哪段工作應保留人手，讀 [唔係每條 SOP 都應該變成 AI Skill](./4-37-human-runbook-or-ai-skill.md)。

← [返回 AI Builder](../README.md) · [按問題瀏覽](../../../README.md)
