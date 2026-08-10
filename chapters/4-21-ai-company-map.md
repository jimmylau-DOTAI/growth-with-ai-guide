# AI 公司圖可以幫你入門，但唔係部署藍圖

一張「AI CEO、部門、Skills、Apps／MCP」的公司圖很容易令人興奮：它提醒你 AI 不只是一個 chat，也可以有做事方法、工具、記憶、檢查和不同工作位置。可是，當你由圖跳到 implementation，最常遇到的問題是每個角色都很像很厲害，卻沒有人知道它真正可以做甚麼。

圖上的部門名稱不是工作設計。你開一個 CEO Agent、QA Agent 或 Sales Agent，不代表它知道可以讀甚麼、可改甚麼、要交甚麼 artifact，或出錯時誰要接手。若這些邊界沒有被寫出來，一張 org chart 只會令模糊變得更有層次，而不會令 workflow 更可靠。

Jimmy 的看法是：AI 公司圖可以作入門地圖，幫你看見角色、Skills、工具和 review 可能如何配合；但真正部署必須回到一條條可驗收 workflow。每一手都要有 context、task、authority、artifact、verification 和 human approval／escalation，角色才真正交代得到。

AI 實戰 · AI Builder · AI company map · agent · skill · tool · workflow · boundary · approval

| 公司圖上的元素 | 教學上可以怎樣理解 | 真正要補的工作設計 |
|---|---|---|
| Skills | 可重用的做事方法 | trigger、input、steps、acceptance、exception |
| Apps／MCP | AI 接到外部工具的手 | read、write、send、publish 權限分開 |
| Agent | 在一定 context 內做一手工作 | task、artifact、stop line、handoff |
| QA 部門 | 防止「AI 話做完」當完成 | hard check、rubric、human approval |
| CEO／manager | 協調與取捨的教學比喻 | 明確 human owner 承擔高後果決定 |

## AI 公司圖點解容易令人誤會：部門名稱不是 workflow design

公司圖用 familiar 的職位名稱來解釋複雜系統，很適合入門。讀者看到「research、content、QA、manager」會理解 AI 可以不只回答問題，而是把一件工作拆成不同手。然而，一個角色名稱本身不會提供 source、權限、輸出格式或驗收標準。

這正是由比喻走到實作時最危險的跳步。若你只根據名字建立很多 Agent，它們可能都讀同一份模糊 context、都能修改同一個地方、都交一段難比較的文字。最後看似有一間 AI 公司，實際上沒有人知道哪個角色做錯、哪個角色有權、哪個角色真的創造了價值。

**Jimmy 的結論：** 公司圖可以保留作理解地圖，但不應被誤當部署藍圖。角色值得存在的原因，不是它名字像部門，而是它有一手清楚、可驗收、可停的工作。

| 圖上看起來有的東西 | 仍然未回答的問題 | 需要補上的 evidence |
|---|---|---|
| 一個 QA Agent | 它檢查甚麼、按哪條 rule？ | rubric 與 review receipt |
| 一個 CEO Agent | 它有沒有權作取捨或承諾？ | human owner 與 escalation |
| 一個 research Agent | 它可讀哪些來源、交甚麼？ | source bundle 與 brief |
| 一個工具連接 | 它可讀、可寫還是可發送？ | action boundary |
| 一個多 Agent 圖 | hand-off 如何發生？ | artifact、state 與版本 |

看到一張漂亮圖時，最有用的下一問不是「怎樣複製」，而是「圖中任何一格現在能交出哪一份可 review artifact？」答不到，就先把它留在教學層。

## Skills、Apps、Agent 與 QA 怎樣落到工作上：每個元素都要有自己的契約

Skill 是可重用方法，不是一段很長的 prompt；它要說清觸發條件、可用 input、步驟、合格標準和例外。Apps 或 MCP 是工具連接，不是自動授權；能讀資料不等於能改寫，能草擬不等於能發送。Agent 則是一個在限定 context 和 authority 中完成一手工作的 worker。

QA 也不應只放在最後。它可以是一個資料完整性檢查、一次 source review、或一個 human approval gate。重點是每個元素都知道自己交甚麼、不能做甚麼，以及下一手怎樣驗收。當它們有契約，才可以安全地組合；否則圖裡的線只是想像。

**Jimmy 的結論：** AI 系統的單位不是工具名稱，而是有 input、artifact、check 和 exception 的工作契約。先把每一格寫成契約，才知道需要 Skill、App、Agent 還是人類 review。

| 元素 | 它應回答的問題 | 不可偷步變成 |
|---|---|---|
| Skill | 何時觸發、如何做、怎樣合格？ | 無邊界的萬用 prompt |
| App／MCP | 這輪可讀、可寫、可發送甚麼？ | 一接通就全權操作 |
| Agent | 它只對哪一手 artifact 負責？ | 一個能做所有事情的人格 |
| QA gate | 用哪個 rule 擋住哪種錯誤？ | 最後一句「已檢查」 |
| Human owner | 哪個高後果決定由誰承擔？ | 讓模型投票代替責任 |

當一個元素的合約仍然說不清，最安全做法是先讓它只讀、只草擬或只回報 unknown，直至工作事實足夠支持更大權限。

## 由 org chart 變成可跑 workflow：先畫六格，再決定是否要拆角色

不要先畫八個職位。先挑一條真工作，寫出六格：context、task、authority、artifact、verification、human approval／escalation。這些問題會自然告訴你，工作是否只需要一條 bounded loop，還是某一段確實需要不同 specialist。

例如如果所有步驟只讀同一類公開資料、產出同一種 brief，並由同一 owner 用同一份 checklist review，一條 loop 可能已足夠。若其中一段要處理不同資料域、不同權限或不同驗收者，才有拆分 worker 的理由。角色不是由圖表數量決定，而是由工作 boundary 長出來。

**Jimmy 的結論：** 一條完整 workflow 比一張大 org chart 更有價值。先畫工作 hand-off，再按 context、authority 和 verification 的真實差異決定要不要新增 Agent。

| Workflow 格 | 你要寫甚麼 | 它幫你決定甚麼 |
|---|---|---|
| Context | 可讀的最小資料與 current state | 要不要分資料域 |
| Task | 本輪唯一要完成的事 | 工作是否足夠狹窄 |
| Authority | 可做與不可做的動作 | 是否需要不同權限角色 |
| Artifact | 每手要交的可見結果 | hand-off 如何驗收 |
| Verification | 哪條 rule 或誰作檢查 | 是否要獨立 review |
| Escalation | 何時交回哪位 owner | 哪些決定不屬於 AI |

答到六格後，才知道系統真正需要的形狀。答不到時，公司圖只可以留作學習地圖，不能當 implementation plan。

## 工具連接點解不等於授權：read、write、send、publish 必須拆開

最容易被忽略的是 Apps、MCP 或其他外部連接。人見到 AI 可以接到文件、email、資料庫或網頁，就很自然以為它「可以幫你做」。但每一種動作的風險不同：讀取可以幫整理，寫入會改變資料，發送會影響他人，公開則可能不可逆。

所以工具能力一定要落到 action boundary。即使 AI 能看見一份草稿，也不代表它能改；即使它能起草 email，也不代表能夠寄出。把權限分開，不會減少工具價值，反而令你可以先在低風險 read／draft 面累積 evidence，再決定是否需要下一級 action。

**Jimmy 的結論：** 接到工具只代表可能性，不代表授權。每個 workflow 都要把 read、write、send 和 publish 分開，讓人知道 AI 做到哪一格、又在哪一格必須停。

| 動作層級 | 可以先做甚麼 | 需要額外甚麼 |
|---|---|---|
| Read | 看已批准公開資料、整理摘要 | 最小 source scope |
| Draft | 產生 internal draft、分類或 checklist | artifact 與 review rule |
| Write | 修改指定可回退檔案 | 明確檔案範圍與 diff |
| Send | 對外傳出訊息 | human approval 與收件範圍 |
| Publish／production | 公開或改變 live 系統 | 明確權限、最後確認與 rollback |

若你仍未能說明 send 或 publish 由誰批准，先不要把它放進 Agent 的 job。讓 AI 停在 draft／review queue，已經足夠開始建立可靠能力。

## 一個公開安全例子：由公司圖拆成 learning brief workflow

假設你想把幾篇已批准的公開文章整理成內部 learning brief。公司圖可能把它畫成 source intake、draft worker、QA 和 manager；這個畫法有助理解不同位置，但仍要回到每一手的可見工作。

Source intake 只讀公開 URL，交來源、作者、主張和未知；draft worker 只讀已核對 brief，交一份內部草稿，不能外發；reviewer 只讀草稿和 rubric，交 pass、revise、unknown 或 stop 的原因；human owner 才決定是否保留、修改、用於教學或轉成公開內容。小型工作未必需要四個長駐 Agent，同一個 AI 也可以在不同 step 按 contract 順序工作。

**Jimmy 的結論：** 這個 workflow 的價值不在角色有幾多，而在每一手都能看見 context、artifact、check 和 owner。只有當這些真的不同，才值得拆 specialist。

| 工作位置 | 可讀甚麼 | 要交甚麼 | 不可做甚麼 |
|---|---|---|---|
| Source intake | 公開 URL | source brief 與 unknown | 引入私人資料 |
| Draft worker | 已核對 brief | internal draft | 對外發送 |
| Reviewer | draft 與 rubric | review receipt | 自行批准 |
| Human owner | 前三手 artifact | final decision | 把責任交給 AI |

這個例子只在公開、低風險的內部草稿層工作。它不讓 AI 接觸客戶資料、改 production、改 visibility、外發訊息或自行公開內容。

## AI 公司圖常見錯誤：部門愈多、工具愈多，未必愈成熟

部門愈多不等於成熟。一條可以停、可以驗收、有 owner 的 workflow，通常比十個角色 prompt 更有用。另一個錯誤是以為接通工具就可以讓 AI 做完；其實 read、write、send 和 publish 的權限不同，將它們混在一個角色只會令錯誤代價變大。

最後是把 QA 放在結尾。對外、權利、金錢、資料和重大決定，應在入口與關鍵 hand-off 設 gate；若等到最後才檢查，錯誤可能早已被寫入下游 artifact。好設計不是在最後抓錯，而是讓錯誤在最小的工作格停下。

**Jimmy 的結論：** AI 成熟度不是圖上有幾個部門、接了幾多工具，而是每個 workflow 是否有清楚 boundary、可驗收 artifact 和正確的人類決定點。

| 誤會 | 真正問題 | 較好的下一步 |
|---|---|---|
| 部門越多越成熟 | 角色未有工作契約 | 先寫一條六格 workflow |
| 接工具就可以自動做 | 權限未分級 | 先 read／draft，再審批 |
| QA 最後才檢查 | 錯誤已流到下游 | 在入口與 hand-off 加 gate |
| CEO Agent 可作最終決定 | authority 被錯放 | 指定 human owner |
| 多 Agent 一定更快 | hand-off 成本未計 | 先驗證一條 bounded loop |

當你的公司圖能被翻譯成幾張工作卡，圖就由想像變成一個有用的設計工具；不能翻譯的部分，暫時只是靈感。

## 今日怎樣用公司圖開始：從一個角色拆出一條低風險工作

如果你已有一張 AI 公司圖或一串 Agent 名稱，今天不需要重畫整張圖。挑其中一個角色，選一件不涉及外發、私人資料或不可逆操作的真工作，填六格：它可讀甚麼、只做哪一手、不可做甚麼、交哪一份 artifact、誰怎樣驗收、甚麼情況交回人。

如果其中一格答不到，不代表你失敗；它代表這個角色還停留在比喻層。先把缺少的 context、rule 或 owner 補出來，然後在一個內部 draft 小任務跑一次。只有跑過、留下 output 和 review receipt 的角色，才值得進一步擴大。

**Jimmy 的結論：** AI 公司圖幫你理解角色；workflow boundary 才令每個角色真正交代得到。先讓一個小角色在一條小工作上可靠，之後才建更大的系統。

| 角色職位說明書 | 你要寫甚麼 | 安全起點 |
|---|---|---|
| Context | 已批准最小材料 | 三篇公開文章 |
| Task | 只完成一手工作 | 整理 source brief |
| Authority | 可做與不可做 | 可草擬，不可外發 |
| Artifact | 可 review 結果 | source／unknown 表 |
| Verification | rule 與 reviewer | claim-source checklist |
| Escalation | 何時交回誰 | 資料不足給 content owner |

未做到這一輪低風險驗證前，暫時不要新增大量 Agent、給整個 vault 或 Drive access、連接外部發送、改 visibility 或進 production。下一步可看 [答案不等於一份工作](4-22-answer-is-not-work.md)，再把角色圖中的一格變成真正的 AI work card。

> AI 公司圖幫你理解角色；workflow boundary 才令每個角色真正交代得到。

← [返回 AI Builder](../04-ai-builder.md) · [按問題瀏覽](../BROWSE.md)
