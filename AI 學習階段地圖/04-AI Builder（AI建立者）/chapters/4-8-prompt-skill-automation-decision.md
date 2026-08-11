# Prompt、Skill、automation 還是暫時不 build？AI 工作先選最小足夠的形式

開始用 AI 後，很多人一見到重複工作就想砌 Agent、接 connector、寫 automation；又或者反過來，甚麼都用聊天 prompt 處理。兩種做法都容易令工作變得更亂：把一段未講清楚的流程接上 API，只會令錯誤更快、更難追；把一件明明可以固定處理的工作留在 chat 裏，則會令你每次都重新解釋同一件事。

真正的選擇不是哪個工具比較先進，而是這份工作到底屬於甚麼形狀。它是否只做一次？輸入和規則是否固定？哪一格真正需要判斷？output 是否有穩定 schema？錯了能否回退？owner 和驗收是否清楚？當這些仍不明確時，最成熟的答案往往不是 build，而是先畫工作地圖或直接停止。

Jimmy 的判斷是：Build 得好不是把所有步驟塞進 AI，而是用最小足夠的形式完成每一格。一次探索用 prompt；固定、可預期的執行用 deterministic automation；重複而仍需 context 與 judgment 的一段才包成 Skill；系統之間已有明確責任、schema 和回退時才接 connector。選錯形式，工具愈多只會把不確定放大。

| 工作形狀 | 最小足夠形式 | 它留下甚麼 |
| --- | --- | --- |
| 一次性探索、還在學問題 | Prompt／對話 | 初步想法、問題、下一步假設 |
| 固定規則、可預期轉換 | Script／deterministic automation | 可重跑結果與規則化 check |
| 重複、需 context／判斷、可收貨 | AI Skill／bounded loop | Artifact、quality gate、review receipt |
| 已批准系統交接、schema 穩定、可回退 | Connector pipeline | 受控同步／draft queue／狀態紀錄 |
| Input、owner、acceptance 未清 | Work map／stop | 未知、決策與暫不做範圍 |

## 每件 AI 工作都想砌 Agent，為甚麼反而會令流程更難管理？

Agent、connector 和 automation 看起來能一次解決很多事，但它們只會放大你已經設計清楚的流程。若工作本身沒有清楚 source、owner、完成線和停止條件，接上更多工具不會令它變得明確；AI 只會更快地用錯資料、重覆錯誤或把不該做的 action 帶到下一個系統。

同樣地，把所有工作都留在 prompt 裏也有成本。固定的欄位轉換、檔案命名、資料驗證或提醒，不需要 AI 每次重新理解；用模型處理這些確定性任務，既不穩定又難檢查。AI 最有價值的地方，是在需要比較 context、處理不確定、起草或提出選項的工作，而不是替代每一個規則。

**Jimmy 的結論：** 先選工作形式，再選工具。最先進的技術不是最適合的做法；最適合的做法是以最低複雜度守住這次工作需要的判斷、品質和回退。

先看這些常見誤配：

| 工作 | 容易做錯的選擇 | 較好的起點 |
| --- | --- | --- |
| 第一次研究新 topic | 立刻建 research Agent | 用 prompt 探索、列未知與 sources |
| 格式化固定欄位 | 每次叫 AI 幫你轉檔 | Script／deterministic rule + check |
| 重複寫 internal brief | 只存一段長 prompt | Skill + input boundary + review receipt |
| 系統之間資料交接 | 開 connector 後讓 AI 自由讀寫 | 先定 schema、draft queue、owner、rollback |
| 目標和完成線仍不清 | 先砌 automation 再找用途 | Work map／assumption ledger／stop |

當你能分清這些，技術選擇會少很多，工作反而更快落地。

## Prompt 最適合用在哪些工作，幾時不應急著把它變成 Skill？

Prompt 最適合一次性、探索性或仍在定義問題的工作。你可能想理解一個新概念、試不同角度、把一段混亂想法整理成問題、或讓 AI 幫你問回還缺甚麼 context。這時候快速對話比建一份正式 workflow 更好，因為你仍在發現工作真正需要甚麼，而不是已經知道怎樣重跑。

過早把探索固定成 Skill，容易將第一次的偶然做法鎖死。每次目標不同、input 大幅不同、沒有穩定 output 或你仍不知怎樣收貨時，長 prompt 或 human runbook 已足夠；收集幾次真正遇到的錯和決定後，才有根據抽出 trigger、schema 和 quality gate。

**Jimmy 的結論：** Prompt 不是低級做法；它是探索和思考的正確形式。當你還未能清楚定義工作，先用 prompt 學習，而不是用 automation 假裝自己已有流程。

Prompt 適合這些情況：

1. 第一次研究或 brainstorm，結果仍是可變的。
2. 想整理觀點、比較方案、找出未知或寫第一版 outline。
3. 需要人持續參與，因為目標、語氣、策略或責任仍在變。
4. 任務很少發生，建置與維護成本大過可省時間。
5. Output 只是你下一步思考的 input，而不是可直接交付的成果。

當你發現自己反覆用同一類 input、同一種完成線、同一組 review 標準，才是從 prompt 走向 Skill 的信號；不是因為 prompt 已經很長。

## 固定執行工作為甚麼應先用 deterministic automation，而不是每次都叫 AI 判斷？

有些工作本質上不需要語言模型的彈性：將指定欄位轉成另一個格式、驗證日期、根據清楚規則分類、移動檔案、計算合計、按既定時間發提醒。這些事情用 AI 看似方便，但模型仍可能在格式、邊界值或例外上有隨機性；更重要的是，這些錯本來可以被明確規則完全防住。

deterministic automation 的好處不是「沒有 AI」，而是它把可預期部分做得一致、可測、可回退。當 workflow 裏同時有固定 execution 和真正 judgment 時，最好的設計通常是前者用 script／rule，後者才交給 AI。這樣 AI 不用浪費在當計算機，reviewer 也不用每次重看同一種格式錯。

**Jimmy 的結論：** AI 應該處理不確定、需要 context 的部分；能用清楚規則完成的事情，先用最低複雜度的 deterministic form。這不是保守，而是把可靠性留給最適合的地方。

可用這個分辨表：

| 問題特徵 | 較適合的形式 |
| --- | --- |
| 有清楚 yes／no 規則、固定欄位、可完全驗證 | Script／validator／deterministic automation |
| 每次需比較背景、解釋原因、處理語意差異 | AI prompt／Skill |
| 大部分固定、少部分需要判斷 | Rule 先跑，AI 只處理例外／draft |
| 資料經常變、schema 未定 | 先 map／prompt，不急著自動化 |
| 需要外部 action、責任高 | 先 draft／human gate，不因規則固定就自動 release |

把固定執行與 AI judgment 分開，也令後來的 bug 更容易追查：是規則錯、資料錯，還是模型判斷錯。

## 甚麼工作形狀值得包成 AI Skill，而不只是一次對話或 script？

Skill 適合重複出現、input class 和 output 類型開始穩定、但中間仍需要 AI 理解 context、組織內容或處理受控例外的工作。例如根據指定公開資料起 internal research brief、將已批准內容轉成不同渠道 draft、從 sample 資料找出需人確認的空格。這些工作不能只靠固定 mapping，但又不應每次由零開始聊天。

一份 Skill 的分水嶺不是它有沒有叫 Agent，而是它有沒有可以重跑的 contract：trigger、approved reference、steps、artifact、quality gate、stop／owner。沒有這些，AI 只是在一次 prompt 裏表現得較好；有這些，你才知道下一次應如何啟動、怎樣收貨、錯了走哪裡。

**Jimmy 的結論：** 將工作包成 Skill，是為了令需要判斷的重複工作有邊界和品質，不是為了把每一段 prompt 都升格成複雜系統。

當以下大多成立時，便可考慮 Skill：

| 問題 | 適合 Skill 的訊號 |
| --- | --- |
| 重複性 | 做過幾次，工作目標和 output 類型相近 |
| Context | 只需一組已批准、可列出的 input class |
| Judgment | 有需要 AI 比較、解釋、起草或標記 unknown 的一格 |
| Acceptance | 能寫出幾條 pass／revise／stop 的標準 |
| Owner | 有人能 review、更新規則、決定外部 action |
| Recovery | 出錯時能保留 draft／receipt，不直接破壞正本 |

若其中核心幾格仍未有答案，先用 prompt 或 human runbook 學清工作，不急著 build。想進一步寫成 contract，可讀 [Skill 唔係存低一段長 prompt](./4-6-skill-is-quality-gate.md)。

## Connector pipeline 幾時值得接，點解它不是一張 permission pass？

Connector 的價值是把兩個已講清楚責任的系統接起來，減少人手搬運已批准資料。它不代表 AI 因此可讀所有帳戶資料、可隨意寫入下一個系統、更不代表它可以自己對外採取 action。若 input schema、output schema、owner、review 和回退仍未定義，connector 只是把本來需要人看住的錯誤變成更快的同步錯誤。

較成熟的 connector pipeline 通常只接一段很小的交接：指定欄位 → 受控 draft queue，或 approved record → 可 review 的變更預覽。它先證明資料在正確範圍、缺欄會停、output 有 schema、owner 能收貨，才可能逐格增加寫入或頻率。這是對責任設計的延伸，不是技術連通本身的獎勵。

**Jimmy 的結論：** Connector 接起的是一段已被證明可管理的工作交接，不是把資料和責任一次過交走。沒有清楚 contract 時，最安全的 connector 是暫時不接。

接 connector 前，先答五格：

1. **讀甚麼**：只限哪些已批准、必要的 input／欄位？
2. **交甚麼**：output schema 是甚麼，缺欄／未知怎樣表示？
3. **可做甚麼**：只寫 draft queue、還是可寫回正本？
4. **誰收貨**：哪位 reviewer 在哪個 state 採用、退回或停止？
5. **出錯怎樣停**：schema 改了、資料過期、check 不過時，怎樣 block、rollback、通知 owner？

例如 AI 可以將三篇公開文章整理成有 source link、claim、unknown 的 research table，放到 internal review queue；它不因此得到讀私有帳戶、發 DM、改 CRM、開廣告或對外發布的權限。

## 「暫時不 build」幾時反而是最成熟的 AI 決定？

工具文化很容易令「不 build」看起來像落後。但若 input 未清、owner 不在、acceptance 寫不出、資料過期或工作本身還未做過幾次，任何 automation 都只是在把未知固化。你可能花很多時間接工具、修例外，最後才發現真正問題是流程根本不值得存在，或人尚未決定要甚麼結果。

暫時不 build 不是甚麼都不做。它可以是先畫 work map、記 assumption ledger、收集幾次 input／output、寫 human runbook、用 prompt 做探索，或將敏感 action 留在 draft。這些是令未來 build 更快、更少返工的工作；它們會讓你看見應自動化哪一段，而不是把整條混亂直接數碼化。

**Jimmy 的結論：** 當 input、owner 或 acceptance 未清楚，stop 不是拖延，而是避免你把一個還未理解的工作變成難以維護的技術債。先看清楚，才是 AI Builder 的速度。

以下情況先不要 build：

| 訊號 | 今天較好的動作 |
| --- | --- |
| 每次目標都不同 | 用 prompt／human conversation 定義問題 |
| Input／source of truth 未定 | 畫資料地圖、問 owner、整理 source |
| Output 沒有可驗收標準 | 先寫反面 acceptance／review rubric |
| 沒人負責 approve／維護 | 暫不自動化，先定 owner |
| 一出錯不能回退或影響外部責任 | 只做 draft／sandbox／working copy |
| 還未真實做過幾次 | 記錄手動流程與例外，等模式浮現 |

只要今天成功避免了一條錯的 automation，你已經替未來省下不少維護成本。

## 用一批公開 URL 走一次，Prompt、automation、Skill、connector 會各自做哪一格？

假設你每週會處理一批公開 URL，目標是學習並產生 internal research material。這是一個很好的例子，因為同一條大流程裏同時有一次性思考、固定執行、AI judgment 和可能的系統交接；把所有步驟都交同一個 Agent，反而最難看出哪部分值得 build。

先用 prompt 問「這批資料可能在回答甚麼問題、還缺甚麼 context」；然後用固定規則抽取 URL、標題、日期、重覆項；再由 AI Skill 比較論點、標 evidence 強弱、整理 unknown 和教學角度；只有在 schema 穩定、owner 批准、只寫入 review queue 時，才考慮 connector 把表格交到下一個受控系統。這樣每種形式只做自己最擅長的一格。

**Jimmy 的結論：** 好 workflow 從來不是「全部用 AI」或「全部自動化」，而是每一段工作都有最小、最清楚、最可驗收的形式，令 AI judgment 和固定規則互相補位。

| 工作格 | 較合適的形式 | 本輪不應做甚麼 |
| --- | --- | --- |
| 找問題、探索角度 | Prompt | 假裝已經有固定流程 |
| 抽 URL／標題／日期、去重 | Deterministic automation | 叫 AI 猜遺失欄位 |
| 比較主張、標來源強弱、起 brief | AI Skill | 將未確認內容當成結論 |
| 將通過 schema 的 draft 放入 queue | Connector pipeline | 直接寫 CRM／對外發布 |
| Input／owner／acceptance 不清 | Work map／stop | 為了跟潮流硬接工具 |

這也是一條 safe first move：先讓每格留下 artifact，再根據 review evidence 決定哪一格真的值得自動化。

## 想為一件工作選第一個 AI 形式，最安全的開始是甚麼？

挑一件你最近想 build、但仍有點混亂的工作，不要先開工具清單。先寫它是否重複、哪些步驟只需固定規則、哪些真的需要 context 和判斷、input／output 是否穩定、誰收貨、錯了怎樣回退。你會發現很多工作其實只需要一個 prompt 或一條簡單 validator；也有些值得做成 bounded Skill，但不應接 connector。

最安全的第一步是選最小形式，保留 working copy 和 human review。若答案是 prompt，先探索並記錄模式；若答案是 automation，先在 sample 跑規則；若答案是 Skill，先只交 internal draft；若答案是 connector，先只接到 review queue；若答案是 stop，先把未知寫出來。這些都不是退而求其次，而是正確的 AI Builder 決定。

**Jimmy 的結論：** 工具選擇的成熟度，不在於你最後用了多少技術，而在於你有沒有勇氣選擇「剛好足夠」，並在條件未成熟時先不 build。

可以跟這六步判斷：

1. 這件工作是探索一次、重複固定，還是重複但需要判斷？
2. 哪些部分可用確定規則完成，哪些部分必須讀 context？
3. Input、owner、artifact、acceptance 和回退是否已寫得出？
4. 選最小形式：prompt、rule、Skill、connector 或 stop。
5. 先用 public／synthetic／sample input，output 只落 draft／working copy。
6. 收集幾輪 check／review evidence，才增加權限、頻率或系統連接。

暫時不要因為「可以叫 AI 做」就把每一步變 Agent；不要把 connector 當作 permission pass；也不要在 input、owner、acceptance 未清時硬砌 automation。若要先把工作切成可驗收單位，可讀 [先寫一張可驗收 AI work card](./4-20-ai-work-card.md)；若你已經選擇 Skill 形式，讀 [Skill 唔係存低一段長 prompt](./4-6-skill-is-quality-gate.md)。

← [返回 AI Builder](../README.md) · [按問題瀏覽](../../../README.md)
