# 第一張 AI work card 點樣寫：把重複工作由「想做 Agent」變成可 review 的責任

很多人想做 AI Agent、AI workforce 或 automation，但一問「它究竟負責甚麼、讀甚麼、交甚麼、錯了怎樣停」，答案還停在工具能力。這不是因為想法不夠好，而是工作本身還未被寫成一段可交接、可驗收的範圍。沒有這一步，之後無論接多少工具，都很容易變成範圍不清和人手救火。

AI work card 是把一件反覆出現的工作，先寫成有痛點、job、input、artifact、review、stop line 和一個可觀察變化的工作合約。它不是批准 automation、不是公開 case study、也不是把 AI 包裝得很大；它只讓你和 reviewer 先看清：AI 這一輪可安全負責哪一手，甚麼仍必須留給人。

Jimmy 的看法是：work card 的作用不是令你看起來有 AI team；是令你知道一件 AI 工作到底值不值得繼續。第一張卡應該小、真、低風險、可 review；寫得清，才有基礎變成 Skill、loop、service 或 value proof。

AI work card · AI agent · workflow design · artifact · human review · stop line · AI Builder · automation

| Work card 一格 | 要回答甚麼 | 留下甚麼 |
|---|---|---|
| Work pain | 原本哪一手反覆、慢、漏？ | problem statement |
| Job | AI 幫手的誠實工作名是甚麼？ | bounded role |
| Input | 可讀與不可讀甚麼？ | source boundary |
| Artifact | 它交甚麼可核對東西？ | draft／card／queue |
| Review／stop | 誰收貨、何時不能繼續？ | owner／acceptance／escalation |
| Observation | 今輪想看甚麼小變化？ | outcome note |
| Decision | retain、revise、stop？ | next action |

## 第一張 AI work card 應揀甚麼：不是最重要任務，而是重複、低風險、可收貨的一手

第一張卡不應選最敏感、最想一鍵完成或一錯便造成大後果的工作。它應該是你做過不止一次、有較清楚 input 和交付物、錯了可在對外前發現、有人願意 review、亦能觀察到一個小改變的 routine。這讓你練的是工作設計，而不是在第一輪就承擔所有風險。

適合例子包括把已批准公開資料整理成 internal brief、FAQ draft 或分類 queue；不適合的是直接回覆客戶、付款／合約決定、CRM 寫入、未批核公開發布或高後果專業判斷。這些不代表永遠不可用 AI，只代表它們不適合用來學第一張卡。

**Jimmy 的結論：** 第一張 work card 的安全起點，是一件真但低風險、輸出可 review、錯了會知道的工作。先把一手跑通，再談更大 automation。

| 工作候選 | 是否適合 | 原因 |
|---|---|---|
| 公開資料 → internal brief | 適合 | input 清楚、owner 可 review |
| FAQ 分類 draft | 適合 | artifact 可核對 |
| 固定格式 checklist | 適合 | rule 明確、風險低 |
| 對外客戶回覆 | 暫不適合 | 承諾與語氣風險 |
| CRM 寫入 | 暫不適合 | 私人資料／production |
| 付款、合約、醫療判斷 | 不適合第一輪 | 高後果責任 |

若沒有合適工作，不要硬起一張卡。先觀察本週哪一手由人重複做了三次，通常那裡才有最值得設計的起點。

## AI work pain 點樣寫：由人正在重做的摩擦開始，不要由工具功能開始

不要由「AI 可以做甚麼」開始，因為這會令你找一件事硬塞 AI。先用一句描述現時工作：每次＿＿時，由＿＿人手整理／檢查＿＿，最常出現的摩擦是＿＿。它讓你看見原本的成本是資料散、第一版漏題、交接不清、還是 review 等太久。

pain 不需要寫得宏大。愈具體，愈容易選一個 bounded action。例如「公開 FAQ 散在幾頁，editor 每次要找重複問題，初稿常漏題」比「提升內容效率」有用得多。前者直接指出 AI 可先試的整理範圍，也令你日後能觀察有沒有減少同一種重做。

**Jimmy 的結論：** Work card 的起點是人現在被迫重做甚麼，不是模型能展示甚麼。沒有真摩擦，AI 只是在找一個勉強要用的地方。

| 太空泛寫法 | 可觀察的 work pain | 可能的 bounded action |
|---|---|---|
| 提升效率 | FAQ 初稿常漏題又要重整 | 分類 approved FAQ |
| 做 AI agent | 來源散、briefing 每週重做 | 整理 source 成 draft |
| 自動化跟進 | owner 不知下一步／漏 handoff | 起 internal action queue |
| 建 knowledge base | 同事每次重問同一事 | 先做 approved FAQ draft |

若你無法說出 pain，先找使用者看一次目前怎樣完成這件事。不要讓 AI 替你發明問題，因為真正的價值會在真 workflow 裡。

## AI job 名點樣起：名字要說明交付，不要假裝甚麼都識

「AI 助手」「研究 Agent」「AI OS」聽起來很大，但另一個人仍不知道它實際交甚麼。誠實 job 名應把 role 和 artifact 放進名稱，例如 FAQ draft assistant、公開來源 brief 整理員、每週 internal research queue。它們可能不華麗，卻能讓 owner 立刻問對問題：input 是甚麼？誰 review？何時算完成？

Job 名是 scope control 的一部分。若一個名字容許任何工作被塞進去，card 很快變成無限責任；若它清楚只交一個 artifact，使用者和 reviewer 就知道本輪不能把策略、外發、付款或其他高風險 action 都交給 AI。

**Jimmy 的結論：** 好 job 名不是形容 AI 有幾勁，而是說清它替哪個 workflow 交哪一份東西。交付愈清楚，範圍愈可信。

| 太空泛名稱 | 誠實 job 名 | 它交甚麼 |
|---|---|---|
| AI 助手 | FAQ draft assistant | FAQ 分類 internal draft |
| 研究 Agent | 公開來源 brief 整理員 | source-linked brief |
| AI 客服 | 常見問題分類 draft worker | queue／draft，不直接回覆 |
| AI OS | 每週 internal research queue | fixed-format review queue |
| Growth agent | approved content idea sorter | 內部選題／缺口清單 |

若 job 名寫完仍要用很長一段補充「其實它還會做很多」，代表第一張卡範圍太大。拆成幾張 card，通常比一張萬能 Agent 更安全。

## Input 和 artifact 點樣界定：只讀甚麼、不可讀甚麼、交甚麼要寫到另一人能檢查

input 和 artifact 是 work card 的骨架。先寫只可讀甚麼、不可讀甚麼、交付 artifact 是甚麼、artifact 必須有甚麼。這不只是寫得詳細；它讓 reviewer 可以判斷 AI 有沒有跨過本輪範圍，也讓下一個人不必回到聊天紀錄猜資料來源。

安全例子可以是：只可讀已批准公開 FAQ、公開活動資料和指定格式；不可讀客戶資料、未公開 offer、CRM、私人文件；交付是本機 FAQ 分類 draft，必須包括每題來源位置、重複題和待確認問題。這種 boundary 讓你可以練 workflow，而不需把敏感資料帶進去。

**Jimmy 的結論：** AI 工作可否被信任，先看 input 和 artifact 有沒有清楚邊界。沒有來源界線的 output，很難安全 review；沒有 artifact 的 AI，只是聊天。

| Card 欄位 | 要寫甚麼 | 安全預設 |
|---|---|---|
| Approved input | 允許來源與格式 | public／approved／最小必要 |
| Not allowed | 不可讀資料與 action | CRM、credentials、private vault |
| Artifact | 檔案／queue／draft | 可開、可核對、可交接 |
| Must include | 必填 source／unknown／format | schema 可檢查 |
| Location | 工作位置／版本 | 不靠聊天歷史 |

如果 artifact 需要直接進 production，先把 action 拆開：work card 可以先只交出可 review draft，正式寫入另設 approval gate。

## Review 和 stop line 點樣令 AI work 可交接：不要只寫「做完我看一看」

「AI 做完後我看一看」不是 review rule，因為不知道誰看、看甚麼、不合格會怎樣。card 要寫 reviewer、至少一條 acceptance standard，和哪些情況 AI 必須停下來標記而不可自行完成。例如每項可回到原資料、unknown 不補成事實、格式可交下一手；遇到個人資料、未公開資訊或需要對外回覆時，必須停止。

stop line 不是宣告 AI 失敗，而是把例外安全地交回人。若沒有這條線，Agent 容易把搞不定的地方用流暢答案遮過去，最後由忙碌的人在更後面發現。明確 stop line 同時會令使用者較願意試，因為他知道不是一放手便失去控制。

**Jimmy 的結論：** AI work card 要有人的收貨權和 AI 的停止線。這兩格清楚，才叫可交接 workflow，不是一次性 demo。

| Review／stop 格 | 寫法例子 | 為何重要 |
|---|---|---|
| Reviewer | content owner | 誰承擔最後判斷 |
| Acceptance | 每項可回原資料 | 可判斷 pass／return |
| Unknown rule | 缺資料即標待確認 | 不補猜 |
| Stop line | 出現私人資料即停 | 保護資料邊界 |
| Action boundary | 未 review 不可外發 | 防止越權 |

若你還未有 reviewer，先不要把工作卡升格成自動化。可以先自己用 checklist review，但需清楚 status 仍是 practice／internal。

## 第一輪 observation 點樣選：看一個貼近原摩擦的改變，不要急著證明 ROI

第一張 work card 不用證明收入、節省人手、客戶滿意度或公司轉型。只選一個與原痛點最接近的 observation，例如材料齊到第一版可 review 的時間、漏題／漏欄次數、被退回補資料的原因，或 reviewer 接手前需要重整幾多次。這會令學習與 workflow 設計保持相連。

觀察不是 KPI competition，也不是用來收集不必要資料。它只是讓你知道這條 card 應否再跑，下一輪應改 input、format、review rule 還是 handoff。若你一開始用很大的 ROI 詞，反而會令一次 run 的小 evidence 承受不必要期待。

**Jimmy 的結論：** Work card 的第一輪只需一個貼近痛點的小觀察。先看有沒有少一次不值得的重做，再談更大的價值。

| 原本摩擦 | 可觀察甚麼 | 暫時不要聲稱 |
|---|---|---|
| 資料散、初稿漏題 | 漏題／退回原因 | 固定節省工時 |
| 格式常重整 | 到可 review 的時間 | 全面效率提升 |
| handoff 不清 | owner 是否可接手 | 全團隊 adoption |
| source 常不足 | unknown 是否正確標出 | output 絕對準確 |

若 observation 顯示 cleanup 比原本更多，不需要勉強保留。這正是 card 幫你及早發現 workflow 不值得擴大的價值。

## 一個公開安全例子：FAQ draft assistant work card

假設每次整理已批准公開資料時，editor 要手動找重複 FAQ，第一版常漏題又要重整。這張 card 的 job 是 FAQ draft assistant；只可讀公開 FAQ、公開活動資料和已批准格式；不可讀客戶資料、未公開 offer、CRM 或私人文件。artifact 是本機 FAQ 分類 draft，必須包括每題來源、重複題和待確認欄。

content owner review，標準是每項可回原資料、unknown 不補事實、格式可交下一手。遇到個人資料、未公開內容或任何需要對外回覆的情況，AI 停下來標記。本輪只觀察材料齊到 reviewer 可接手的時間和被退回原因；decision 由 owner 選 retain、revise 或 stop。

**Jimmy 的結論：** 這張 card 沒有把 AI 說成客服或全能 agent，但讓人清楚看到一段可安全試、可 review、可改善的工作。這正是 Builder 應先建立的基礎。

| Card 格 | 例子內容 | 邊界 |
|---|---|---|
| Work pain | FAQ 資料散、初稿漏題 | 不誇大成全流程問題 |
| Job | FAQ draft assistant | 不叫 AI 客服 |
| Input | approved public data | 不讀私有資料 |
| Artifact | internal FAQ draft | 不直接更新網站 |
| Review／stop | owner／unknown／敏感即停 | 不自行外發 |
| Observation | review time、退回原因 | 不宣稱 ROI |

這是 synthetic 教學例子，不代表任何特定客戶、FAQ 或 DotAI workflow 已有相同成果。它示範的是 work card 如何把 AI 角色寫得誠實、可治理。

## 今日怎樣寫第一張 AI work card：先填七格，再決定是否值得 build

挑一件你已做過不止一次的低風險工作，依序填：work pain、job、approved input、artifact、review／stop、this-round observation、next decision。每格一句已可開始，但要讓另一人看懂它能做甚麼、不能做甚麼、誰負責收貨。若某格仍是「到時先算」，那一格就是本週要先補的工作設計。

第一張 card 可以只留本機或 private work record。不要因為寫完 card 就接 CRM、付款、外發或不可逆 action；先用它跑一個 internal draft，再留 run receipt。當你有多輪可回看 evidence，才可考慮把穩定部分變成 Skill、loop、service 或 value proof。

**Jimmy 的結論：** Work card 的完成不是你有一個 Agent 名字，而是你有一段清楚、可 review、可停止、值得再跑的工作責任。寫得出，才值得 build。

| 今日先填 | 合格訊號 | 寫不出時先做甚麼 |
|---|---|---|
| Work pain | 有具體重做摩擦 | 觀察一次現有 workflow |
| Job | 說得出交甚麼 artifact | 縮小 role |
| Input／artifact | 有資料和交付邊界 | 定 source／schema |
| Review／stop | 有 owner、acceptance、fallback | 保持 draft-only |
| Observation | 一個貼近 pain 的變化 | 不先講 ROI |
| Decision | retain／revise／stop | 跑一次小試行 |

想記錄本輪實際交了甚麼和誰收貨，讀 [AI 話做完時點樣先收貨](./練習-write-an-ai-run-receipt.md)；想在多次 run 後誠實判斷價值，讀 [AI 有冇真價值點樣證明](<../../05-AI Value Creator（AI價值創造者）/chapters/練習-write-an-ai-value-proof-card.md>)。

> AI work card 的作用不是令你看起來有 AI team；是令你知道一件 AI 工作到底值不值得繼續。

← [返回 AI Builder](../README.md) · [按問題瀏覽](../../../README.md)
