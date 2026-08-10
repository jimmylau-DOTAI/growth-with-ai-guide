# 企業 AI Agent 不只要識做：要有權限、review、紀錄和可停止的治理

一個 AI Agent demo 最容易展示速度：它可以讀資料、寫摘要、開 ticket、更新紀錄，甚至看似能自己完成很多步。真正進入團隊或企業後，最難的卻不是「做不做到」，而是它讀過甚麼、誰給它權限、錯了誰會發現、出了例外怎樣停。這些答案不清楚，自主只會把風險更快傳到更多地方。

很多人一聽「governance」就以為要先寫一大本政策，因此乾脆略過。其實第一輪最實用的治理很具體：讓每一條 Agent workflow 說得清可讀甚麼、可做甚麼、不可做甚麼、誰批准、留下甚麼紀錄、遇到何事必須停止。這不是減慢創新，而是讓小範圍試行可以真的安全地累積 evidence。

Jimmy 的看法是：企業 Agent 的價值，不是少了幾個人手點擊；而是它在清楚權限、可見 state 和 human owner 負責下，穩定完成一段可驗收工作。治理不是 demo 的附錄，它正是 Agent 由玩具走到真工作的一部分。

企業 AI Agent · agent governance · permissions · human review · audit log · stop line · workflow · AI adoption

| Agent 治理的一格 | 要回答甚麼 | 最後留下甚麼 |
|---|---|---|
| Input scope | 它可以讀哪一些已批准材料？ | source boundary |
| Action scope | 它只能起草、可更新，還是可外發？ | permission rule |
| Owner／approval | 誰驗收、誰可升級或叫停？ | named responsibility |
| State／log | 人怎樣看回它做過甚麼？ | run receipt／audit trail |
| Exception | unknown、衝突、敏感情況怎樣辦？ | escalation／fallback |
| Scale gate | 何時才值得加權限或擴大？ | evidence-based decision |

## 企業 AI Agent 為何不能只看 demo：一次成功不等於可以安全交付

Demo 常在最理想的材料、最清楚的 prompt 和講者隨時補救的情況下進行。它能證明某個 capability 存在，卻未必能證明 Agent 面對資料缺失、多人協作、不同權限或例外情況時仍能安全完成。把 demo 當成 production readiness，是企業 Agent 最常見的誤會之一。

真工作需要的不是更長的展示，而是可追問的答案：這次 Agent 讀了哪份資料？用了甚麼規則？有沒有把 uncertain content 當事實？哪個 owner 看過結果？如果 output 不對，能否找回原因並停止下一步？答不到，代表它仍是可探索概念，而非可負責 workflow。

**Jimmy 的結論：** Demo 證明「看似做得到」；治理得住的 pilot 才開始證明「可以交給人試」。先讓 Agent 在受控 workflow 留下可驗收 evidence，才有資格談更大權限。

| Demo 常見樣子 | 真 workflow 仍缺甚麼 | Pilot 要補回甚麼 |
|---|---|---|
| 一次漂亮 output | input 是否可用與完整 | approved source boundary |
| 講者即時修正 | 誰負責正常 review | named owner／acceptance |
| 看似自動完成 | 錯誤是否可被截停 | stop line／fallback |
| 沒講資料來源 | 日後能否回看原因 | run log／receipt |
| 展示很多 capability | 哪一手真的有價值 | bounded work unit |

如果你現在只有 demo，最好的下一步不是加更多 action，而是選一個低風險、draft-only 的工作單位，把 input、owner、review 和 log 補實。

## Agent 可以讀甚麼、做甚麼點樣定：權限要跟工作，不是跟 AI 兩個字

不要因為某個工具有很多 capability，就一開始開放所有 access。權限應貼住第一輪真正需要完成的工作：若只需把已批准產品資料整理成 internal draft，就不需讀客戶私人對話；若 output 只供內部 review，就不需有發送或寫入 production 的權限。最小必要權限令 team 知道自己究竟在承擔甚麼。

同樣地，Action scope 也要拆開。讀取、整理、草擬、標記、提議、更新內部紀錄、對外發送，風險完全不同。把它們全部叫「Agent 幫手」會掩蓋最重要的邊界。先讓 AI 做低風險且可 review 的一手，只有在 evidence、owner 和 rollback 都清楚時才逐步加權限。

**Jimmy 的結論：** 權限不是「信不信 AI」的選擇，而是「這條工作最少需要甚麼」的設計。範圍愈貼近 workflow，治理愈容易落地。

| Agent action | 第一輪合理預設 | 尚未具備前不可做甚麼 |
|---|---|---|
| 讀資料 | 已批准、最小必要來源 | 不讀私人 vault／CRM／credentials |
| 整理／分類 | 固定格式 internal output | 不把推論當事實 |
| 起草內容 | draft-only | 不直接對外發送 |
| 建議下一步 | 標出 confidence／unknown | 不替 owner 批准 |
| 更新狀態 | 可 review 的內部表／receipt | 不寫 production system |
| 執行 action | human approval 後才考慮 | 不自行付款、發信、改公開設定 |

若你無法列出某一項 access 為何必要，暫時不要開。Agent 能力多不代表每一項都應在第一輪使用。

## Agent 的 owner 與 human review 點樣設計：有人收貨才叫完成

「最後由人 review」聽起來安全，但若沒有指定誰、何時、按甚麼標準 review，實際上責任仍會落在最後看到 output 的人。這會令同事怕用、也令錯誤容易在忙碌時靜靜流過。企業 Agent 的 review 不是一個模糊提醒，而是一個可被安排的工作關口。

先分清不同 owner：資料 owner 決定 input 是否可用；工作 owner 決定 artifact 是否符合目的；action owner 決定能否進下一步；治理 owner 處理超出 scope 的例外。小團隊同一人可兼任，但角色和責任仍要說清。這讓 Agent 出現問題時，大家知道應回到資料、規則、workflow 還是 decision。

**Jimmy 的結論：** Agent 不是有一個人「大概會看」就安全；它需要明確 owner、acceptance rule 和 escalation。有人能收貨，也有人能叫停，工作才算可治理。

| 關口 | 誰應負責 | 要做的判斷 |
|---|---|---|
| Input approval | data owner | 材料是否已批准、是否最小必要 |
| Artifact review | work owner | 是否可用、完整、符合目的 |
| High-risk action | action owner | 是否容許外發、寫入或改設定 |
| Exception | escalation owner | 是否停止、退回或改規則 |
| Run record | workflow owner | 今次學到甚麼、下次怎樣調整 |

若沒有 named owner，先把 Agent 停在 internal draft 層。不要把「之後有人看」當成授權更高風險 action 的理由。

## Agent 點樣留下可回看的 state：log 不是監控，而是讓人找回原因

當 Agent 產出不理想，最需要的不是問它「為何這樣想」，而是能回看這次工作實際發生了甚麼：用了哪些 input、哪些規則、輸出甚麼、哪裡標 unknown、誰 review、最後怎樣決定。沒有這些 state，團隊只能靠記憶猜問題，下一次自然又會重複同一種錯誤。

run receipt 不必很複雜。第一輪可以只記六格：work purpose、approved input、Agent action、artifact、review result、exception／next decision。它既能幫 owner 交接，也能為日後調整 prompt、rule 或 workflow 留下 evidence。重點不是監控人，而是讓工作可以被理解與改善。

**Jimmy 的結論：** 可見 state 是 Agent 可治理的基礎。不是所有細節都要記，但每一次重要 run 都應足以讓人知道它做了甚麼、在哪裡停、下次要改甚麼。

| Receipt 格 | 例子 | 為何需要 |
|---|---|---|
| Purpose | 產出 internal weekly brief | 知道 output 服務哪個決定 |
| Approved input | 三個公開來源 | 可回看資料邊界 |
| Agent action | 整理、標 unknown、起 draft | 不把能力講得太大 |
| Artifact | briefing draft 加 source link | 讓人可 review／接手 |
| Review | owner accepted／returned | 讓品質責任可見 |
| Next decision | revise template／stop／rerun | 讓學習累積 |

沒有 receipt 的 Agent run 仍可做實驗，但難以作為團隊日常工作。先把 state 留下，才容易發現它何時值得改善或停用。

## Agent 遇到例外點樣停：unknown、fallback 與 escalation 比「自主」更重要

真正危險的不是 Agent 不知道，而是它不知道自己不知道，仍繼續執行。資料缺失、來源衝突、敏感內容、超出原有範圍、review owner 不在，都是常見例外。若 workflow 沒有 stop line，系統會把不確定當作正常輸入，最後由人用更高成本收拾。

因此每條 Agent workflow 都要先寫未知怎樣處理：標記 unknown、交回指定 owner、只輸出 draft、或退回人工處理。fallback 不是 failure；它是保護學習速度與信任的設計。當例外被分類，團隊也能判斷是要補 input、改 rule、縮 scope 還是根本不值得繼續。

**Jimmy 的結論：** 能安全停止的 Agent，比看似完全自主的 Agent 更有企業價值。Stop line 令錯誤不會悄悄變成行動，也讓下一輪有清楚改善方向。

| 例外訊號 | Agent 應怎樣做 | 人怎樣接手 |
|---|---|---|
| Source 不足／矛盾 | 標 unknown，不補猜測 | data owner 補資料或決定停 |
| 內容超出 scope | 不繼續 action | workflow owner 改範圍 |
| 需要敏感決定 | 只出 options／draft | action owner 批准 |
| Review owner 缺席 | 不進下一步 | 等待或退回 queue |
| 重複品質問題 | 留 receipt、暫停 rerun | 檢查 rule／input／tool fit |

如果 stop line 被看成「妨礙自動化」，通常代表範圍仍太大。先縮小工作單位，讓停與回復成為正常流程的一部分。

## 一個公開安全例子：Agent 把 approved sources 變成 internal briefing draft

假設一個團隊希望讓 Agent 每週把幾份已批准公開來源整理成 internal briefing。第一輪的 input scope 只限固定公開來源；Agent action 只限整理、標記 unknown 和起草固定格式；artifact 是一份內部 draft 加 source link；content owner 必須 review，沒有 approval 不得外發或寫入其他系統。

每次 run 留一張 receipt：使用哪幾份來源、資料缺什麼、owner 退回了甚麼、下一次應改 template 還是補 source。若 Agent 遇到來源衝突、需要未公開資料，或 review owner 未準備好，它就停止並交回人處理。三次後才以 rework、review time、repeatability 判斷是否值得擴大。

**Jimmy 的結論：** 這個 Agent 的價值不在於模仿人「全自動做 research」，而在於把一段低風險工作做成有 input boundary、human review、可回看 evidence 的可治理 routine。

| 治理格 | 例子設定 | 第一輪不做甚麼 |
|---|---|---|
| Input | approved public sources | 不讀客戶資料／私人 vault |
| Action | 整理與 internal draft | 不直接外發 |
| Owner | content owner review | 不讓模型批准 |
| State | source、unknown、review receipt | 不只留聊天紀錄 |
| Stop | conflict／missing input 即停 | 不補猜測 |
| Scale | 三次 run 有 evidence 才談 | 不預先承諾 production |

這是 synthetic 教學情境，不代表任何特定企業、Agent 或系統已有同樣成果。它的目的，是讓讀者看見治理可以由一個很小、很實際的 workflow 開始。

## 今日怎樣為下一個 Agent 寫治理卡：先回答五行，再決定是否值得 build

在你下一個 Agent 想法前，先寫五行：可讀甚麼；可做甚麼；不可做甚麼；由誰批准；一遇到甚麼就停止並交回誰。再補一行：這次 run 怎樣留下可回看的 artifact 和 receipt。若其中一格寫不出，代表它仍是一個值得探索的概念，暫未適合進企業 workflow。

不要用更長 prompt 掩蓋這些空格，也不要因為其他公司講 autonomous agent 就把高權限 access 當成熟。先做一條 scope 小、draft-only、有 owner 的 pilot，讓真 evidence 告訴你下一步應加規則、加訓練、加權限，還是停止。

**Jimmy 的結論：** 企業 Agent 的起點不是能力清單，而是一張治理卡。寫得出權限、owner、state 和 stop line，才值得讓它進入真工作。

| 今天先寫 | 合格訊號 | 未合格時怎樣處理 |
|---|---|---|
| Read | 已批准、最小必要 input | 移除不必要 access |
| Do／do not do | action scope 清楚 | 縮回 draft／整理 |
| Owner | review 與 escalation 有名字 | 指定人後才跑 |
| Receipt | 能回看 input、action、result | 補 run log 模板 |
| Stop line | exception 有 fallback | 不讓 Agent 繼續猜 |
| Scale gate | evidence 後才談擴大 | 先跑小範圍 pilot |

想先把 Agent 的工作邊界寫清，讀 [workbench contract](4-19-workbench-contract.md)；要設計第一條可停的 Agent workflow，讀 [先跑一條可停的 Agent loop](4-25-first-agent-loop.md)。

> 企業 Agent 的價值，不是少了幾個人手點擊；而是它在清楚權限、可見 state 和人手負責下，穩定完成一段可驗收工作。

← [返回 AI Value Creator](../05-ai-value-creator.md) · [按問題瀏覽](../BROWSE.md)
