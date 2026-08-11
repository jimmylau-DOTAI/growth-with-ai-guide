# 你未必需要更多 Agent：先分清一條 AI Loop 還是要拆 Specialist

工作一複雜，最容易出現兩種反應：有人想把每一個職位都變成一個 AI Agent；亦有人把所有資料、工具和決定塞進同一個「全能 Agent」。兩邊一開始都會很有速度，直到它拿錯背景資料、越權改了東西，或者交出一份沒有人知道怎樣驗收的結果。

問題通常不在於 Agent 數量不夠，而在於工作本身還未被說清楚。一條工作究竟是同一個人可以按固定規則反覆做的流程，還是不同部分需要不同資料、不同授權和不同驗收者？未分清這件事，畫 router、parallel worker 或多 Agent 圖，只是把模糊分得更複雜。

Jimmy 的看法是：AI 分工不是職位分工，而是 context、authority、artifact、verification 和 escalation 的分工。先用一條範圍小、會停、有人驗收的 loop 跑出證據；只有當不同部分真的不能共用背景、權限或檢查方式，才把它拆成 specialist。

`AI 實戰 · AI Builder · AI Agent · bounded loop · specialist · routing · context · verification`

| 你現在看到的工作形狀 | 先用甚麼方式理解 | 完成後要留下甚麼 |
|---|---|---|
| 只需要查找已知資料 | reference / retrieval | 可追查的資料與未知項目 |
| 步驟固定、每次輸入相近 | workflow | 清楚輸入、步驟和輸出格式 |
| 要在一個小範圍內查、做、自查、再決定下一步 | bounded loop | scope、stop line、checklist 和結果 |
| 每一段要用不同背景、權限或驗收者 | specialist routing | 每個角色的交接物、owner 和升級規則 |

## AI Agent 分工的第一個誤會：複雜工作不等於要很多 Agent

看到一項工作有很多步驟，不代表它有很多獨立問題。假如每一步都在處理同一類資料、用同一套規則、最後由同一位 owner 以同一份 checklist 驗收，拆成四個 Agent 只會多了四次交接、多四份不一致的狀態，和更多「究竟誰要負責」的空位。

相反，有些表面上只有兩步的工作，卻根本不應由同一個 Agent 處理。例如一段要讀公開資料、另一段要判斷是否能夠公開、最後還要由有發佈權的人確認；它們的資料範圍和責任線已經不同。這時候硬塞進一條 loop，反而令越權和誤判更難看見。

**Jimmy 的結論：** 不要由「幾多角色」開始，而要由「每一手正在處理甚麼、可做甚麼、誰驗收」開始。若答案仍然是一套 context、一個授權範圍、一種驗收，先不要拆。

| 表面現象 | 真正要問的問題 | 常見較好起點 |
|---|---|---|
| 工作有六個步驟 | 六步是否都用同一套資料和同一份 checklist？ | 一條 bounded loop |
| 團隊有四個職位 | 職位是否真的各自擁有不同權限或交付物？ | 不要按職位硬拆 |
| 要讀資料再寫草稿 | 寫作是否只用已核對資料，且可由同一 owner review？ | loop 加清楚 stop line |
| 要處理不同資料域 | 每一域是否有獨立 access rule、owner 或驗收？ | 先寫 specialist contract |

當你能用一句話說清楚「這一手只對甚麼結果負責」，才值得考慮把它變成一個角色。說不清的角色，不是 specialist，只是一個更難 debug 的提示詞。

## Bounded loop 適合甚麼工作：同一個 context 內反覆完成一件可驗收的小事

bounded loop 不是讓 AI 無限思考，而是讓它在一個已定義的工作範圍內重複四件事：讀取允許的資料、產生一個指定格式的結果、按既定規則自查、遇到未知或例外就停。它適合的不是「很聰明的工作」，而是輸入與驗收已經有一定穩定度的工作。

例如你要把三份已批准的公開活動資料整理成內部 briefing 草稿：輸入是已批准文件，輸出是固定欄位，檢查是資料齊不齊和連結能否開啟；遇到矛盾、缺欄或需要發送外部訊息時，就停下來交人。這不是小看 AI，而是把它放在最能產生穩定價值的位置。

**Jimmy 的結論：** 一條好的 loop 要有「可以自己走的範圍」，亦要有「絕對不可以自己跨過的線」。沒有 stop line 的 loop，只是把未決定的責任交給工具。

| Loop 的一格 | 在公開／synthetic briefing 例子裡的意思 | 留下的可驗收痕跡 |
|---|---|---|
| Input boundary | 只讀已批准的活動 brief 和 FAQ | 輸入清單 |
| Work step | 整理要點、草擬固定欄位 | briefing draft |
| Check | 檢查日期、連結、欄位是否齊全 | checklist 結果 |
| Stop line | 資料衝突、缺資料、要對外發送 | `needs-human-review` 標記 |
| Owner | 內容 owner 決定能否使用 | review 記錄 |

你可以把一條 loop 想成一張小小的工作卡：它不需要知道整間公司的所有事情，只需要在自己的範圍內把一件工作交得準、交得回看得到。想先把這張工作卡寫得更清楚，可接著看 [由 Prompt 變成 Skill 的工作合約](./4-23-skill-is-a-work-contract.md)。

## Specialist routing 幾時先值得拆：資料、權限、交付或驗收已經不能混用

specialist 不是一個比較型的 Agent 名稱，而是一個有邊界的責任位。真正值得拆的訊號，是某一段工作需要另一套不能混用的 context、另一個授權範圍、另一種交付物，或者另一位能作最終判斷的人。這些差異若只存在於職位稱呼，而不在工作契約裡，就還未構成 specialist。

最常見的錯誤是把「有人做研究、有人寫文、有人 review」當成天然分工。真正的分工應寫得更具體：研究那一手只可處理公開資料，交出主張、連結與未知；寫作那一手只可根據已核對資料起草；review 那一手只檢查公開安全、範圍與格式；只有人類 owner 可決定是否公開。每一手的能力和限制都看得見，才可安全交接。

**Jimmy 的結論：** 拆 specialist 的理由不是「AI 可以扮多人」，而是讓不同的 context、authority 和 verification 不會在同一個黑盒裡混在一起。

| 若出現這個差異 | 為何不宜硬塞給同一 worker | specialist 要交甚麼 |
|---|---|---|
| 不同資料域 | 一手不應自動取得另一域的資料 | 已允許資料的摘要與未知 |
| 不同權限 | 可草擬不代表可外發或可寫入系統 | 可 review 的 draft |
| 不同 artifact | 研究清單、草稿、風險判斷不是同一種交付 | 清楚格式的 hand-off |
| 不同驗收者 | 內容、合規、營運各自有不同判斷責任 | 對應的 check 結果 |
| 不同升級路徑 | 例外情況要交給不同 owner | 明確 escalation reason |

一個好 specialist 應該能被拔出來單獨檢查：它讀了甚麼、不能讀甚麼、交了甚麼、失敗時找誰。若這四件事寫不出來，先回到一條較小的 loop，而不是急著加 router。

## Router 不是總指揮：它只負責把清楚的工作交到清楚的責任位

很多 Agent 圖把 router 畫在中央，好像它是最聰明的 manager。但 router 本身不會消除模糊：如果它不知道每個 specialist 可以讀甚麼、該交甚麼、怎樣才算合格，它只會把錯誤更快地送到下一站。

因此，router 應被當成一條可驗收的分流規則，而不是神秘的意圖判斷。例如「已核對公開來源、需要產生教學草稿」才交給 learning worker；「來源不明或牽涉未公開資料」一律標記 human review；「草稿準備公開」才交安全 reviewer。分流的條件越明確，越容易回看錯誤發生在哪一格。

**Jimmy 的結論：** 先有角色合約與交接物，後有 router。沒有已寫清楚的 route rule，router 只是一個包裝得更漂亮的猜測。

| Router 應看見的訊號 | 可以做的分流 | 不應自行做的決定 |
|---|---|---|
| 來源已批准、格式齊全 | 交給整理／草擬 loop | 宣稱資料一定正確 |
| 資料來源不明 | 停下並交 human review | 自己補寫或猜測 |
| 需要公開安全檢查 | 交給 reviewer | 直接發佈 |
| 例外涉及不同 owner | 帶著原因交到指定 owner | 自行改權限或繞過流程 |

router 的價值是令工作去到正確的檢查點，而不是取代所有判斷。若你的工作目前只有同一套 context 和同一個 review 點，直接用一條 loop 通常更透明。

## Parallel Agent 工作何時反而變慢：未有合併規則就不要同時開工

「可以 parallel」聽起來很有效率，但前提是每一手真的互不依賴。假如兩個 worker 要讀同一份未定稿資料、各自修改同一個輸出，最後又沒有指定誰負責合併，速度換來的通常是衝突、重複和難以追查的版本。

適合 parallel 的情境是工作已分成獨立的輸入和輸出，而且合併規則一開始已寫好。例如一個 worker 檢查公開連結是否有效，另一個 worker 檢查文件欄位是否齊全；兩者各自交 JSON／表格結果，最後由一個固定 check 合併成「可 review」或「需停下」。這不是多開 Agent，而是先設計好可合併的 evidence。

**Jimmy 的結論：** parallel 不是要同時開幾多個工具，而是每個輸出能否獨立驗收、能否按同一規則合併。未有 merge rule，就先順序跑。

| 開 parallel 前的檢查 | 答「未有」時怎樣做 | 答「有」時留下甚麼 |
|---|---|---|
| 輸入是否互不依賴？ | 先順序處理前置資料 | 各自 input contract |
| 輸出是否不會互相覆寫？ | 改成不同 artifact | 獨立輸出位置 |
| 是否有明確合併者？ | 指定 human 或固定 verifier | merge owner |
| 有沒有同一份合格標準？ | 先寫 checklist | merged receipt |

當你無法說明兩份結果怎樣合併，代表工作仍是一件事，而不是兩件可 parallel 的事。先把它做成一條可靠 loop，比畫一個很壯觀的 graph 更有用。

## 一個公開安全的例子：把公開文章變成可 review 的學習草稿

假設一個團隊想把已公開的文章整理成內部可 review 的學習草稿。這個例子不涉及客戶資料、帳戶權限或自動發佈；它的重點是看清楚每一手真正要負責的東西，而不是模仿任何公司的架構。

先不要把流程叫作「multi-agent system」。先看四個可見的交付：來源是否可確認、教學草稿是否只用已核對材料、公開安全是否過關、以及誰有權將草稿推進下一步。只要其中一格由不同人以不同規則驗收，才有拆 specialist 的理由。

**Jimmy 的結論：** 這類流程的安全不是來自更多 Agent，而是每一次 hand-off 都能回答「由哪裡來、現在可做甚麼、下一個誰負責」。

| 責任位 | 只可做的事 | 交付物 | 碰到甚麼必須停 |
|---|---|---|---|
| Source intake | 讀公開來源、記下可確認主張與未知 | source brief | 來源或授權不清楚 |
| Learning worker | 根據已核對 brief 草擬教學內容 | draft | 需要補外部事實 |
| Reviewer | 檢查範圍、格式、公開安全 | review receipt | 有私人資料或未核對主張 |
| Human owner | 決定下一步、補判斷或拒絕 | final decision | 任何需外部承諾的動作 |

在 source intake 這一格內，可以有一條 bounded loop：讀已允許來源、抽取主張、按 checklist 自查、遇到未知就標記停下。整個流程則是 specialist routing，因為 intake、寫作、review 和決定分別有不同的 context、權限和驗收者。

## 由一條 loop 升級成 specialist 的實際判斷：先看交接成本是否換到更少風險

拆 specialist 會帶來好處，也帶來成本。好處是界線清楚、權限更小、錯誤較容易定位；成本是每一手都要寫 contract、保存狀態、處理 hand-off，以及面對不同角色意見不一致。若工作量很小、風險很低、同一個 owner 已能可靠驗收，這些成本可能比收益更大。

所以升級時不必一次拆到最細。先從一條 bounded loop 跑幾次，記錄它常在哪裏停、哪種例外最多、哪一段總要不同 owner 重看。當重複證據顯示某一段需要不同 context、不同 check 或不同授權，才把那一格分出去。這讓架構是由工作事實長出來，不是由圖表逼出來。

**Jimmy 的結論：** 只有當拆分令權限更小、驗收更清楚、例外更容易升級時，specialist 才是升級；否則它只是增加 hand-off。

| 觀察到的證據 | 下一步 | 暫時不要做甚麼 |
|---|---|---|
| 同一份 checklist 已能穩定驗收 | 保持一條 loop，補強 stop line | 為了好看硬拆多 Agent |
| 同一 loop 經常因資料域不同而停 | 把資料域寫成獨立 specialist contract | 讓 worker 自行擴大 access |
| 同一份輸出要兩種專業 check | 分開 review receipt 和 owner | 把兩種判斷混成一個分數 |
| 例外總是找不同人決定 | 寫清 escalation route | 讓 router 猜誰應負責 |

你不需要一次畫完完整 Agent 架構。最有價值的第一張圖，是一條你今天能夠驗收、明天能夠改的工作 loop；之後才按真實的 context 和 review 壓力，把必要的部分拆開。

## 今日可以怎樣開始：先寫一張 AI 工作卡，再決定是否要分流

如果你現在已經有一個複雜想法，先不要由 router 或 Agent 名稱開始。挑一件低風險、可回看的工作，例如整理已批准的公開資料成 internal draft。它應該不會直接發送訊息、不會寫入 production system，也不會接觸私人或客戶資料。

把下面五格寫出來後，你會比畫任何架構圖更快看見答案：若五格都屬同一個小範圍，試 loop；若答案自然分成不同 context 或不同 owner，才把那一格拆成 specialist。這也能幫你避免把「AI 會做」誤當成「AI 應該做」。

**Jimmy 的結論：** 最安全的第一步不是建立一隊 Agent，而是建立一張能說清楚邊界的工作卡。先讓一件工作可靠，再讓架構變複雜。

| 工作卡欄位 | 你要寫清楚甚麼 | 一個安全起點 |
|---|---|---|
| Context | 它可讀哪些已批准資料 | 三份公開文件 |
| Authority | 它可做與不可做甚麼 | 可草擬，不可外發 |
| Artifact | 最後要交甚麼 | 固定欄位的 draft |
| Verification | 誰以甚麼條件檢查 | owner 用 checklist review |
| Escalation | 不確定時交回誰 | `needs-human-review` 給內容 owner |

先跑這一張卡一次，保留 input、draft、check 和停下原因。未有這些痕跡前，暫時不要接私人資料、不要把 AI 接到外部發送或 production 寫入，也不要為了名稱漂亮而建立 router。下一步可看 [如何由一條小工作開始建立 AI loop](./4-7-first-bounded-agent-loop.md)，再看 [為何 AI Agent 要有 loop，而不是一次性回答](./4-3-loop-engineering.md)。

> AI 分工唔係職位分工，而係 context、authority、artifact、verification 同 escalation 分工。

← [返回 AI Builder](../README.md) · [按問題瀏覽](../../../學習地圖.md)
