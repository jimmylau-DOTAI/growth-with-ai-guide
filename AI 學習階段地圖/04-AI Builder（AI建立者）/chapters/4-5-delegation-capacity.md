# 開更多 AI Agent 唔等於效率更高：真正限制你的是 delegation capacity，不是 agent 數量

當 AI 工具愈來愈多，很多人直覺以為生產力等於「同時開到幾多個 Agent」。於是開了研究、內容、coding、admin 幾個工作，但一天結束後，自己反而更忙：要重新交代背景、追問進度、把幾份 output 拼在一起、判斷哪一份可用、擔心有沒有漏掉對外或正本改動。

問題不是 Agent 不夠聰明，而是工作只是被派出去，未必真的被委派。真正的委派代表你已清楚定義工作、限制 input、知道要收甚麼 artifact、有一把可用的收貨尺、例外有 owner，並可在不逐步盯住的情況下安全接回結果。若這些仍在你腦內，Agent 越多，只會把你變成更繁忙的中轉站。

Jimmy 的判斷是：AI 時代更有用的指標不是個人生產力或 Agent 數量，而是 delegation capacity——你在同一時間可以安全地委派、看懂、驗收和接回多少件工作。它的上限由工作合約、權限、可觀察狀態、quality gate 和 recovery 決定；更深一層，也由你和團隊能否判斷 output 是否值得採用決定。

| Delegation capacity 的一格 | 它解的問題 | 缺少時會怎樣 |
| --- | --- | --- |
| Bounded work unit | 「幫我處理」太闊，AI 不知要交甚麼 | 每次要重新解釋，scope 漂移 |
| Permission boundary | 不知 AI 可讀、可寫、可外發甚麼 | 不敢放手，或放得太危險 |
| Observable state | 不知它做過甚麼、卡在哪裡 | 你不停追問、重跑、猜進度 |
| Evaluation／quality gate | AI 說完成但無人知道是否合格 | Output 累積，最後全靠你重做 |
| Recovery／owner | 出錯後不知回哪裡、誰決定 | 一錯就要你手動救火 |

## AI Agent 數量增加時，為甚麼你未必真的多了可委派的工作？

一個 Agent 在某次對話完成得很快，並不代表它已能讓你安全卸下工作。若它每次仍需要你在開始前把背景重新講一遍、過程中不斷看它有沒有偏、結果出來後由你重新查資料、整理格式、決定能否用，那麼只是把工作拆成更多溝通與監督，並沒有真正減少你的責任負荷。

真正的槓桿出現在 Agent 能接住一個清楚工作單位：有固定 trigger、已批准 input、可打開的 artifact、可見 check 和 named owner。這樣你不必盯住每一步，因為你知道它只會在指定範圍內做事；你亦不必自己重新完成一遍，因為 output 已經以你能驗收的格式交回。

**Jimmy 的結論：** Agent 的數量是供應；delegation capacity 才是你真正能管理的需求。只要驗收、責任和 recovery 仍卡在你一個人身上，開十個 Agent 不會令你有十倍產出。

看這兩種情況的分別：

| 表面上都叫「交給 AI」 | 實際是監督／外包 | 實際是可管理委派 |
| --- | --- | --- |
| 啟動工作 | 每次從零講背景 | 有 work card、trigger 和 input boundary |
| 過程 | 你不停追問它做成點 | 有 status／artifact 可看，例外才介入 |
| 收 output | 你由頭核對、再重做大半 | 有 acceptance、evidence 和 reviewer route |
| 出錯 | 你臨時想辦法救 | 有 needs input／approval／failed safe 與回退點 |
| 下次重跑 | 再寫一個長 prompt | 用相同 contract，根據 feedback 更新規則 |

如果日常仍是左邊，先改善一件工作如何被交代和驗收，不要先加更多 agent。

## Delegation capacity 同個人生產力有甚麼分別，點解管理者要看後者？

個人生產力問的是「我今天完成了多少」；delegation capacity 問的是「我同一時間可以安全地令多少件工作推進，而不失去品質和責任」。前者仍以你本人動手速度為中心；後者把重點放在工作是否被切成可交接單位、你能否設計收貨線、團隊能否看到狀態，以及錯誤會否在最後才回到你手上。

這個分別對任何想帶領 AI adoption 的人都重要。當你只追求自己快一點，AI 往往只是個人助手；當你能把一段工作變成多人／多 Agent 都看得懂、可驗收、可回退的 contract，你就開始建立可以被團隊採用的能力。這不是一夜之間把公司全部自動化，而是逐件工作增加可管理的委派空間。

**Jimmy 的結論：** AI Builder 的成長，不是由「我一個人快了多少」衡量，而是由「我能否把一件工作設計到其他人或 AI 可安全接手、又能被我收貨」衡量。

可用這張表做自我診斷：

| 角度 | 個人生產力 | Delegation capacity |
| --- | --- | --- |
| 主要指標 | 自己完成件數／速度 | 可同時驗收的清楚工作單位 |
| 最大樽頸 | 個人時間、操作速度 | 品質標準、review 時間、責任設計 |
| 加一個 Agent | 多一個要顧的工具 | 多一條受控 output pipeline |
| 成功樣子 | 你做得更快 | 你不在場時工作仍可安全推進 |
| 失敗樣子 | 忙不過來 | 一堆看似完成、其實不敢用的 output |

當你發現自己「開得起 Agent、收不起 output」，那不是採用失敗，而是很準確地指出下一步要補的是 evaluation 和 review capacity。

## 一件 AI 工作要具備甚麼，才算可以由「幫手」升級成可委派？

並非所有工作都適合直接委派。若每次目標都不同、需要大量未分類敏感 context、output 沒有清楚完成線、失敗會直接改變客戶承諾或外部狀態，AI 最適合先做協助：整理、提問、起草、找出 unknown。過早把它叫成「已交辦」只會掩蓋真正仍由人承擔的判斷。

能升級成可委派的，是一個有邊界的工作單位。它不必很大，甚至可以只是一張 briefing draft、一次資料檢查或一個 sample feature slice；但你要說得出 input 從哪來、AI 可做甚麼、交甚麼 artifact、哪幾條 gate、誰決定下一步、出錯後怎樣回退。這些東西愈清楚，委派愈不依賴你一直在場。

**Jimmy 的結論：** 委派不是把一個大任務丟給 AI；委派是把一段工作切到「AI 可在清楚邊界內完成，人可在清楚證據下收貨」的大小。

一張最小 delegation card 可包括：

1. **Trigger／目的**：甚麼情況下要跑這件工作？
2. **Input boundary**：只可讀哪些已批准材料，哪些明確不可讀？
3. **Bounded action**：AI 只處理哪個轉換，不能順手擴大甚麼？
4. **Artifact**：它要交哪個 draft、表格、diff、receipt 或 state？
5. **Acceptance**：甚麼條件下 reviewer 可以採用、退回或停止？
6. **Exception／recovery**：資料不足、衝突、失敗或要外部 action 時誰接手？

若這六格仍答不出來，先把工作保留為 human runbook 或 AI-assisted task，毋須急著量化「已委派」。

## 權限、status、eval 和 recovery 怎樣決定你可同時管理幾多個 Agent？

即使每個 Agent 都有明確任務，缺少管理層仍會令容量很快卡住。沒有 permission boundary，你不敢讓它跑；沒有可讀 status，你要不停問進度；沒有 eval，你收到 output 也不敢用；沒有 recovery，一有錯就要立刻自己救。這些摩擦每件都不大，但同時管理五、十件工作時會成倍放大。

相反，當角色只讀指定資料、每次交 receipt、status 顯示 current step 和下一位 owner、gate 把可修錯和需決策錯分開、失敗有回退點，你不必將注意力平均灑在每一個 run 上。你的時間可以集中在真正需要專業判斷和 release 的少數 gate，這才是 delegation capacity 可以成長的原因。

**Jimmy 的結論：** 容量不是靠你學會同時盯更多畫面，而是靠 workflow 將不需要你即時判斷的事情變得可見、可檢查、可安全處理。

這五層如何互相支撐：

| 管理層 | 它令你不用親自做甚麼 | 沒有它的成本 |
| --- | --- | --- |
| Permissioning | 每次盯著它有沒有越界 | 不敢放手，或過度開權限 |
| Observability | 一直追問「做到邊」 | 狀態只在 chat，人變成中轉站 |
| Evaluation | 由頭重做一次才能收貨 | 「完成」無定義，output 堆積 |
| Recovery | 臨時找回舊版本、猜怎樣救 | 一錯就中斷整條 workflow |
| Handoff／owner | 代替所有人傳遞背景 | 你是唯一知道全局的人 |

想先寫清某一條工作怎樣留下狀態，可讀 [Agent 一直顯示 Loading，係未壞咗？先寫清 status contract](./4-39-agent-status-contract.md)。

## 委派容量的上限，為甚麼通常是你的驗收與判斷能力？

AI 可以很快產生很多 output，但這不會自動變成更多價值。若你一天只能認真 review 三份工作結果，那麼即使十個 Agent 同時完成，餘下七份也只是排隊等待你的判斷；若它們沒有清楚 evidence、acceptance 和優先次序，排隊只會變成焦慮和返工。

更重要的是，你不能真正驗收一件完全不理解的工作。你可以委派陌生領域的資料收集、初步分析或問問題，但對高風險結論、專業意見、承諾或決策，仍需要具備能力的 owner 或適當 reviewer。否則不是委派，而是在把不確定外包給一個看起來很自信的工具。

**Jimmy 的結論：** Delegation capacity 的天花板不是你可開幾多 Agent，而是你和團隊可用清楚標準安全驗收幾多件工作。增加容量的第一步常常是提升 review 設計，而不是增加生成速度。

可先把 output 按 review 負荷分三類：

| 類型 | 例子 | 較合理的管理方式 |
| --- | --- | --- |
| 低風險、固定格式 | 資料欄位檢查、內部 outline | 自動／半自動 gate + 抽樣 review |
| 中風險、需要語境 | 內容 draft、research brief | Named reviewer + evidence／rubric |
| 高風險、外部責任 | 客戶承諾、付款、權限、production change | Human owner 必須 decision／release |

你可以先增加第一類的可委派數量，再慢慢練第二類的 rubric；第三類不應用 Agent 數量來解決。

## 一人想開始練 delegation capacity，怎樣數出自己真正的起點？

不需要先買 agent platform，也不用猜自己「理論上能管理幾多」。回看上星期：有幾件工作你真的交給 AI 或其他人處理，而且你沒有在每一步旁邊監督？當中有幾件有寫下收貨標準、你事後真的對照過？再問有幾件出錯時你不用從零救火，因為已知道誰接手、哪一版可信？

這個數字可能很小，甚至是零，但它不是失敗。它是一個很清楚的診斷：你現時的 bottleneck 在哪一格。如果你交得出但收不到，先加 acceptance；如果 output 可以收但一直要追進度，先加 status；如果一出錯就停止，先寫 exception／recovery。不要把所有問題都錯當成模型不夠好。

**Jimmy 的結論：** Capacity 不是自我感覺，而是已被驗收的委派工作數。從一件有清楚標準、能安全收回的任務開始，才會逐步變成真正可管理的槓桿。

可以每週做一次五分鐘檢查：

1. 上週有多少件工作是由 AI／他人完成，而你沒有全程盯住？
2. 當中多少件有可看見的 artifact、acceptance 和 reviewer？
3. 當中多少件你實際採用、退回或停止，並留下決定？
4. 哪一件最常需要你反覆補背景、重做檢查或手動救火？
5. 下週只挑一件，補一個最缺的 gate、status 或 handoff artifact。

記下第三條的數字，才是你當前可驗收 delegation capacity。目標不是立刻變大，而是令每次增加一件時，品質與責任不會一起失控。

## 委派容量有甚麼邊界，幾時不應因為 AI 而硬拆工作？

有些工作價值就在於一個人由頭到尾的判斷連續性：處理高度敏感關係、在不完整資訊下作策略取捨、承擔法律／財務／人事責任、或第一次探索一個尚未理解的問題。這些工作可以有 AI 協助，但未必應被硬拆成多個 Agent task；過度切割反而會失去原本的語境和責任感。

同樣地，委派得多不等於做得好。十件平庸、無人驗收的 output 不比一件真能被採用的工作更有價值。對團隊而言，先令一個人把一條低風險 workflow 跑穩、留下可教的規則，往往比一次過宣稱要自動化二十個部門更可持續。

**Jimmy 的結論：** Delegation capacity 是手段，不是 KPI。它只應在工作已切得開、結果驗收得到、責任仍有人承擔時增加；不能以 AI 工具進步為理由跳過人的判斷。

先保持這三個邊界：

1. 不把你和團隊完全驗收不到的專業結論當作可自動委派。
2. 不為了湊 Agent 數量而把有必然順序或高度語境的工作硬拆。
3. 不讓 AI 接客戶、CRM、付款、合約、credentials、production write 或外發權限，直至有明確治理、review 和 release evidence。

若你想把一件具體工作寫成可管理 unit，可讀 [先寫一張可驗收 AI work card](./4-20-ai-work-card.md)；若你要先判斷應保留人手 runbook 還是做成 Skill，可讀 [唔係每條 SOP 都應該變成 AI Skill](./4-37-human-runbook-or-ai-skill.md)。

← [返回 AI Builder](../README.md) · [按問題瀏覽](../../../README.md)
