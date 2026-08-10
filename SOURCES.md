# Sources and evidence policy

> Local candidate · 未公開

《Growth with AI》不是把別人的帖文、影片或報告搬過來。每篇攻略都分三層：

1. **外部來源講甚麼**：只連回原始公開頁面，不鏡像原文、影片、圖片、OCR 或轉錄。
2. **Jimmy 的判斷**：從來源延伸出的工作模型，會明確標示為 Jimmy 的解讀，不冒充原作者結論。
3. **可以怎樣試**：只給低風險、可自行驗收的練習；不構成產品承諾、顧問建議或自動化授權。

來源是教學 evidence，不是「保證有效」的證明。社交帖、影片、研究摘要和報告的可信度不同；每篇會保留它的適用範圍。

<a id="ai-user"></a>

## AI User：由問答到交工作

- **原始來源：** [設計師 Riven：Claude Cowork：把 AI 從聊天工具變成會做事的工作夥伴](https://www.instagram.com/p/DY4odI8k1ho/)
- **來源提供：** 以工作包、材料與輸出取代單句問答的實例。
- **Jimmy 的延伸：** 「目標、處境、材料、驗收、邊界」是低風險委派工作的 briefing 模型。
- **限制：** 一則公開 carousel 不是效率、準確度或產品能力的獨立驗證；任何對外、金錢、客戶或高風險決定仍要人手覆核。

<a id="ai-user-vocabulary"></a>

## AI User：術語是工作位置圖

- **原始來源：** [莎莉 Sally：Claude Code／Codex beginner glossary](https://www.threads.com/@sally.sales.ttt/post/DZhUO3Uj-Zv)；[黃小木：AI 名詞小白完整入門教程](https://x.com/ai_xiaomu/status/2074346821611405531)
- **來源提供：** 以新手容易碰到的 AI、coding-agent 與 connector 名詞，降低第一層語言門檻。
- **Jimmy 的延伸：** 名詞不應作字典考試，而應放回「目標、材料、工具、執行、驗收」的工作位置；知道位置不等於獲授權操作。
- **限制：** 兩篇為 2026 年公開教學內容；術語、產品介面和功能會變。本 library 不把它當 current documentation，也不以認識 MCP／API／Agent 授權任何連接、資料上傳或外部操作。

<a id="ai-user-configuration"></a>

## AI User：安全配置，不是 prompt 清單

- **原始來源：** [傑森所長：Claude 新手官方路線圖](https://www.threads.com/@jasonxtsai/post/DZ7TmAuD_DP)
- **來源提供：** 用 workspace、背景資料、真任務、connector 和 automation 排出一條新手 onboarding 路線。
- **Jimmy 的延伸：** 第一輪只需要建立工作間、最小工作說明、安全材料、低風險任務和 human review；connector／automation 要另作 permission decision。
- **限制：** 所有工具、connector、功能和「五日」效果均是日期化外部教學資訊，未獨立驗證。不要將客戶、合約、CRM、付款、credentials 或 production data 放入這類練習。

<a id="ai-user-counter-question"></a>

## AI User：先反問，再回答

- **原始來源：** [小盧歐巴：讓 AI 先反問，補齊思考盲區](https://www.instagram.com/adian_066/reel/DXZO3RwEldY/)
- **來源提供：** 在回答前檢查資訊是否足夠、問高影響問題、標註影響與預設假設的協作框架。
- **Jimmy 的延伸：** 反問是高風險或模糊任務的 clarification gate；它要把缺口和假設變成可 review 的初稿，而不是把每次對話拖成問卷。
- **限制：** 單一社交內容不是模型品質、prompt 效果或商業成果的證明。AI 仍可能問錯、漏問；高風險決定、外發和敏感資料仍須真人 owner review。
- **相關公開文章：** [先反問，再回答](chapters/2-6-counter-question.md)；[三個力度的反問指令](walkthroughs/ai-counter-question-before-answering.md)。

<a id="ai-user-workbench"></a>

## AI User 加讀：第一個 AI 工作台

- **原始來源：** [@gengdaJ：Codex App 從 0 到 1 入門長文](https://x.com/gengdaJ/status/2051891231953920174)
- **來源提供：** 以非技術用戶角度說明界面地圖、權限和低風險第一任務，將 agent 理解成工作現場而不只是聊天框。
- **Jimmy 的延伸：** 第一件工具不應按「是否 coding」選，而要按一件低風險、可給材料、可設邊界、可驗收的工作選。
- **限制：** 原文來自 2026-05，UI、價格、額度、connector 和功能可能已改變；本 library 不把它當現時產品規格，也不鏡像文章或圖片。

<a id="ai-super-user"></a>

## AI Super User：由收集 prompt 到 context 複利

- **原始來源：** [陳乃誠：別再收集 prompt 咒語大全了](https://www.facebook.com/photo.php?fbid=10236423011784806&set=a.1034465271333&id=1516495867)；文中引用 [Jeff Su：How I'd Learn AI From Scratch in 2026](https://www.youtube.com/watch?v=msFxQ7OYPj8)
- **來源提供：** 由 prompt collection 轉向熟悉一個模型、提供 context 與回收 feedback 的學習觀點。
- **Jimmy 的延伸：** 能累積的不是 prompt，而是已被人確認過的例子、標準和修改原因。
- **限制：** Facebook 來源在整理時只取得公開 metadata 和圖像文字；它是學習觀點，不是「AI 必然愈用愈似你」的成效保證。
- **相關公開文章：** [由收集 prompt 到 context 複利](chapters/2-2-context-compounding.md)；[五格組一個 AI task pack](walkthroughs/build-an-ai-task-pack.md)。

<a id="ai-super-user-capability-loop"></a>

## AI Super User：工具會換，能力要留下

- **原始來源：** [FlowOps Daily：AI 時代普通人真正需要培養的 5 種能力](https://x.com/FlowOpsDaily/status/2086689378202710031)
- **來源提供：** 把提問、資訊篩選、結構、工具協同與判斷／復盤放入一條 AI 學習回路。
- **Jimmy 的延伸：** 五格不是另一套 Stage，而是每一件真工作都可反覆跑的能力線：問清工作、揀對材料、排好結構、分配工具、人手 review 並留下下一次規則。
- **限制：** 單一公開文章的五能力與任何練習時間建議，不是經獨立驗證的能力模型、效率保證或 DotAI 課程成果。公開文章不鏡像原文或圖片；敏感資料、外發、付款、CRM 寫入及 production action 仍須真人 owner review。
- **相關公開文章：** [學 AI 唔好只追新工具：5 個能力令你每次真工作都會累積](chapters/2-14-tools-change-capabilities-stay.md)。

<a id="ai-super-user-thinking-friction"></a>

## AI Super User：筆記要有加工，才會變成可重用 context

- **原始來源：** [王啟樺：為什麼 Obsidian 是最理想的筆記系統](https://www.instagram.com/p/DYdTqD_msnk/)；延伸參考：[techwith.ram：Blueprint for a Brain: Claude + Obsidian](https://www.instagram.com/p/DZMAemcia7Y/)
- **來源提供：** 以本機文字、連結與結構化筆記作為可被人和 AI 重用的個人知識系統觀點。
- **Jimmy 的延伸：** 一份資料必須有自足標題、自己的判斷、關係和去處，才由收藏變成可交接的 context；工具不是答案，加工習慣才是。
- **限制：** 兩則公開 carousel 是作者的個人系統觀點，不證明任何 app、Markdown、folder 結構或 AI connector 必然提高品質。不要以「AI-readable」為由放入客戶、合約、CRM、credentials 或 production data。

<a id="ai-work-reflexes"></a>

## AI Super User 加讀：AI 工作反射，不是指令清單

- **原始來源：** [羅達 Rhoda：Claude Code 新手大禮包](https://www.facebook.com/AV8D.levelup/posts/1593227049478740/)
- **來源提供：** 以當時 Claude Code 的 command、比喻和新手情境，說明開場建立背景、中途檢查、暫停／重開和 review 的需要。
- **Jimmy 的延伸：** 可帶走的不是一組會過時的 command，而是「定義 → 對齊 → 檢查 → 控制 → 驗收」的 AI 工作反射。
- **限制：** 原帖來自 2026-07；command、model、介面、價格、權限和 memory 行為可能已改變。本 library 不把它當目前產品規格，也不鏡像圖像、OCR 或全文。

<a id="ai-operator"></a>

## AI Operator：AI-readable project onboarding

- **原始來源：** [半熟蛋的 AI 筆記：Obsidian 作為 AI 看得懂的筆記資料庫](https://www.threads.com/@softboiledai/post/DaRYuMtEhJK)
- **來源提供：** 把專案背景、流程、規則和下一步整理成新 AI 可以先讀的筆記入口。
- **Jimmy 的延伸：** 將 context 按當前任務、長期偏好、項目規則和可重用 Skill 分流，讓問題可以被定位和修正。
- **限制：** 這是作者的個人筆記工作法；四層模型是本指南的教學框架，不是所有工具皆有完全相同的功能。
- **相關公開文章：** [一頁 onboarding pack](chapters/3-8-project-onboarding-pack.md)；[current-state note](chapters/3-12-current-state-not-chat-history.md)。

<a id="ai-operator-portability"></a>

## AI Operator：擁有 context，租用工具

- **原始來源：** [陳乃誠：如果 AI 工具突然收掉，你餵給它的東西帶得走嗎？](https://www.facebook.com/photo.php?fbid=10236380471161317&set=a.1034465271333&id=1516495867)
- **來源提供：** 將工具更替的風險放回使用者能否保留自己的 context、規則與工作材料。
- **Jimmy 的延伸：** 真正可攜的不是所有檔案，而是工作所需的判斷、例子、規則、owner 和完成線；換工具仍有重新連接成本。
- **限制：** 公開 Facebook 內容是個人工作法，不是 migration、安全或備份保證；任何可攜 pack 都不可包含 credentials、客戶、合約、CRM 或 production config。
- **相關公開文章：** [擁有 context，租用工具](chapters/3-2-own-context-rent-tools.md)；[portable context pack](chapters/3-9-portable-context-pack.md)；[安全的 replacement test](chapters/3-11-tool-replacement-test.md)。

<a id="ai-operator-context-routing"></a>

## AI Operator：AI 記憶是脈絡分流，不是 chat history

- **原始來源：** [Vink：Codex 記憶最佳使用方法](https://x.com/Vinkyu567/status/2072945322121375860)
- **來源提供：** 以 context、AGENTS、Skills 和 memory 的不同用途說明工作資料不應全塞進同一段對話。
- **Jimmy 的延伸：** 將當前任務、長期偏好、項目規則和可重用 workflow 分開，目的不是令 AI「記得更多」，而是出錯時知道應改哪一層。
- **限制：** X 文章和任何工具的 memory 行為、介面與 retention 規則都可能改變；這不是資料保存、權限或模型記憶的保證。
- **相關公開文章：** [AI 記憶是脈絡分流](chapters/3-3-context-routing.md)；[記憶四層設定法](walkthroughs/ai-memory-four-layers.md)。

<a id="ai-operator-control-layer"></a>

## AI Operator：專業判斷是 agent 工作的控制層

- **原始來源：** [Anthropic Research：Agentic coding and persistent returns to expertise](https://www.anthropic.com/research/claude-code-expertise)
- **來源提供：** 研究以 Claude Code usage data 觀察到，人多數決定「做甚麼」，agent 多數決定「怎樣做」；較強 task-domain expertise 與較佳 session success 有關。
- **Jimmy 的延伸：** 當 AI 接手部分 execution，人要更清楚定義問題、提供 context、設 completion line、驗收和承擔責任；這是 control layer，不是「人完全不用做」。
- **限制：** 該研究針對 2025–2026 年 Claude Code sessions，不能直接外推到所有 agent、香港公司、非 coding workflow 或商業 ROI；它也不取代各工作場景的 human owner 和專業審核。

<a id="ai-operator-memory-cost"></a>

## AI Operator：記憶成本先於工具速度

- **原始來源：** [朱騏：一人營運系統／記憶成本](https://www.facebook.com/chuchi.writing/posts/27981469418126866)
- **來源提供：** 以一人營運中的 SOP、checklist 和已寫下的做法，說明反覆重新想起工作方式的隱性成本。
- **Jimmy 的延伸：** AI 系統的第一步常常不是買更快工具，而是把重複工作先看見、寫下和留可更新的記憶；未看清的工作不應直接自動化。
- **限制：** 原始公開內容有部分附件未能讀取；它是工作方法觀點，不是任何一人公司、工具或自動化的成效證明。一次性工作未必值得維護記憶。

<a id="ai-builder"></a>

## AI Builder：可靠 Agent 的 guardrails

- **原始來源：** [INSIDE Side Chat：Agent 該怎麼分工？](https://www.youtube.com/watch?v=BJ92fomIRJM)；延伸閱讀：[Yanhua：Agent 的本質是一個 while loop](https://x.com/i/article/2083489102637551616)
- **來源提供：** Agent 的分工、工具調用與可靠性需要工作邊界、驗證和控制層，而不是只靠模型或角色名稱。
- **Jimmy 的延伸：** 能用確定性規則檢查的事，應在交付前加 guardrail；需要判斷的事，保留給人和模型在清楚邊界內處理。
- **限制：** 這些公開內容不是 Jimmy／DotAI production system 的 audit，也不保證任何 Agent 架構的安全性、成本或商業成效。

<a id="ai-builder-harness"></a>

## AI Builder：可靠性靠 harness，不只靠 prompt

- **原始來源：** [軒轅的編程宇宙：AI Agent 工作原理是甚麼？Harness 又是甚麼？](https://www.youtube.com/watch?v=B91bZL8wcAI)
- **來源提供：** 將 Agent 的指令、工具、狀態與可檢查的外部約束分開理解的公開技術教學。
- **Jimmy 的延伸：** 能由 schema、固定規則、permission、test 或 human gate 卡住的錯，不能只寫成一句「請小心」的 prompt；harness 的作用是令錯誤可被發現和攔截。
- **限制：** 影片不是任何特定 agent、framework 或 production system 的安全 audit；可寫成規則的部分和仍需人判斷的部分，要按每條 workflow 分開設計。
- **相關公開文章：** [可靠性靠 harness](chapters/4-1-harness-not-prompt.md)；[AI 反覆犯錯的三類檢查](walkthroughs/ai-repeats-the-same-mistake.md)。

<a id="ai-builder-quality-gates"></a>

## AI Builder：Skill 是品質閘，不是 prompt 技巧

- **原始來源：** [Kai Chen：Addy Osmani agent skills / production-grade engineering skills](https://www.threads.com/@kai_ch_chen/post/DZjS95gE1PM)
- **來源提供：** 將 AI 工作標準化為可重用 Skill，並把 reference、流程與品質檢查連在一起的公開教學材料。
- **Jimmy 的延伸：** Skill 的價值不是儲存一段更長 prompt，而是寫清 trigger、input、steps、quality gate、exception 和 stop；這樣才可重跑和 review。
- **限制：** 社交 carousel 及其工程案例不證明任何 Skill 在所有工作場景都可靠；不應把 credentials、客戶資料、付款、外發或 production 權限寫進 Skill。

<a id="ai-builder-exception-ladder"></a>

## AI Builder：Skill 的例外處理與 human approval

- **原始來源：** [OpenAI Agents SDK：Human-in-the-loop](https://openai.github.io/openai-agents-python/human_in_the_loop/)；延伸參考：[Addy Osmani：Agent Skills](https://github.com/addyosmani/agent-skills)。
- **來源提供：** 前者展示敏感 tool call 可暫停，待人 approve／reject 後再 resume；後者將 AI coding 工作的流程與 quality gate 整理成可重用 skill resources。
- **Jimmy 的延伸：** 不論是否採用任何特定 SDK，重複 AI 工作都要把「資料不足、超出範圍、規則不通過、執行失敗、需要 release」分成不同狀態；每一格應留下可讀 state、下一位 owner 和未完成 action。
- **限制：** OpenAI 文件說明的是其 SDK 的 approval flow，不代表所有模型、工具或 workflow 都有同一個 pause／resume 行為；GitHub repository 亦不是 Jimmy／DotAI 的 production audit。這篇只教低風險 draft workflow 的 exception language，不授權外發、覆寫、付款、改權限、存取客戶資料或宣稱安全／可靠性保證。
- **相關公開文章：** [AI 一遇例外就繼續猜？Skill 要先寫好 exception ladder](chapters/4-34-skill-exception-ladder.md)。

<a id="ai-builder-planning-judgment"></a>

## AI Builder：先說清假設，再讓 AI 動手

- **原始來源：** [OpenAI：How OpenAI uses Codex](https://cdn.openai.com/pdf/6a2631dc-783e-479b-b1a4-af0cfbd38630/how-openai-uses-codex.pdf)；延伸參考：[OpenAI：Codex Max white paper](https://cdn.openai.com/pdf/8a9f00cf-d379-4e20-b06f-dd7ba5196a11/OAI_WhitePaper_Codex-maxxing26.pdf)。
- **來源提供：** 兩份 OpenAI 文件把 context、implementation plan、expected behavior、review criteria 和迭代放進 AI coding 的工作流程，而不是將第一個 model output 當成完成。
- **Jimmy 的延伸：** 在 plan 前把已知事實、暫時假設、仍要問與不可碰分開，令 AI 可以先交一份可回覆的 assumption ledger；這是把 scope／acceptance 變得可對話，不是要求所有人寫大型 spec。
- **限制：** 文件描述 OpenAI 自身與 Codex 使用脈絡，不證明任何人採用 assumption ledger 就必然減少錯誤或適用於所有非 coding 工作；本文章只用 synthetic/local sample 示範，不使用客戶 brief、CRM、合約、credentials 或 production data。
- **相關公開文章：** [AI 未開始做已經估錯？先寫 assumption ledger](chapters/4-35-assumption-ledger-before-build.md)。

<a id="ai-builder-staged-release"></a>

## AI Builder：由 dry run 走到 human release

- **原始來源：** [OpenAI Agents SDK：Human-in-the-loop](https://openai.github.io/openai-agents-python/human_in_the_loop/)；延伸參考：[OpenAI Agents SDK：Tool guardrails](https://openai.github.io/openai-agents-python/ref/tool_guardrails/)。
- **來源提供：** SDK 文件展示敏感 tool call 可先暫停等待 approval，以及 guardrail 可 allow、reject 或 halt；它把「未批准」「被拒絕」「可繼續」當成顯式 runtime 狀態。
- **Jimmy 的延伸：** 不論是否使用該 SDK，第一條 AI workflow 應由 sample input、draft artifact、check／exception、human release、recovery receipt 分段走；先證明人能管理狀態，再談更多 automation。
- **限制：** 這不是任何 workflow 的 production approval、安全 audit 或部署建議；SDK 的特定 API 不等於其他工具也有相同行為。文章不授權外發、覆寫、付款、改權限、接客戶資料或把一次 approval 說成可靠性保證。
- **相關公開文章：** [第一個 live run 唔係按掣：先用 dry run](chapters/4-36-dry-run-before-live-run.md)。

<a id="ai-builder-runbook-or-skill"></a>

## AI Builder：human runbook 與 AI Skill 的分界

- **原始來源：** [Addy Osmani：Agent Skills](https://github.com/addyosmani/agent-skills)；延伸參考：[Skill anatomy](https://github.com/addyosmani/agent-skills/blob/main/docs/skill-anatomy.md)。
- **來源提供：** 公開 repository 將 Skill 描述成有明確 use case、步驟、checkpoints、verification 與 exit criteria 的 workflow，而不是只供參考的長文件。
- **Jimmy 的延伸：** 當目標、輸入、可檢查規則和 output 相對穩定，才適合讓 AI 重跑；人需要重定義問題、做高風險取捨或承擔責任的部分，應保留在 human runbook／release。
- **限制：** 此 repository 是工程工作方法，不證明所有 SOP 都可安全自動化，也不代表任何 Skill 可取代專業、法律、財務、客戶或管理決定。文章只使用 generic／synthetic workflow，不能帶出內部 runbook、客戶資料或 credentials。
- **相關公開文章：** [唔係每條 SOP 都應該變成 Skill](chapters/4-37-human-runbook-or-ai-skill.md)。

<a id="ai-builder-status-contract"></a>

## AI Builder：長時間 Agent 的 status 與可恢復狀態

- **原始來源：** [OpenAI Agents SDK：Results](https://openai.github.io/openai-agents-python/results/)；延伸參考：[RunState](https://openai.github.io/openai-agents-python/ref/run_state/)。
- **來源提供：** 文件區分 final output、pending interruptions、run state 與 resume；狀態可以保存足夠資料以接續被 approval 等原因中斷的工作。
- **Jimmy 的延伸：** 對任何多步 AI workflow，使用者應看得見它是 running、needs-input、needs-approval、failed-safe 或 ready-for-review；每一格要有 current step、artifact、下一位 owner 和下一個 action。
- **限制：** SDK 的狀態 API 不等於每個 AI 工具都有同樣 runtime；文章不保證 timeout、重試、資料保存、observability 或 production reliability。它不應用作收集私人對話、客戶內容或 credentials 的理由。
- **相關公開文章：** [Agent Loading 好耐，係未壞咗？先寫清 status contract](chapters/4-39-agent-status-contract.md)。

<a id="ai-builder-loop-engineering"></a>

## AI Builder：Loop Engineering 是回饋系統設計

- **原始來源：** [黃志弘：Loop Engineering／讓 AI 自己把任務跑完](https://www.instagram.com/p/DZ4yy1WGFMy/)
- **來源提供：** 用多步執行、檢查與再嘗試，解釋為何 AI workflow 不等於一次生成。
- **Jimmy 的延伸：** loop 的核心是 feedback：input 不足、output 不合格、例外或 human review 會令流程回到正確一格，而不是無限叫模型再試。
- **限制：** 它不是 autonomous agent 的成效或安全保證；沒有 stop line、owner、quality gate 和可回看的 evidence，loop 只會更快地重複錯誤。
- **相關公開文章：** [Loop Engineering 是回饋系統設計](chapters/4-3-loop-engineering.md)；[六步 workflow loop 設計](walkthroughs/ai-workflow-loop-design.md)；[五個 build gate](chapters/4-12-ready-to-build.md)。

<a id="ai-builder-demo-to-skill"></a>

## AI Builder：示範不是完整 Skill

- **原始來源：** [沈重宗：OpenAI Codex Record & Replay／示範式學習](https://www.threads.com/@jackshenaiadvisor/post/DZ7nZbED_Yx)
- **來源提供：** 將「人示範一次工作，系統觀察流程」帶入 AI workflow 討論的公開 teaching framing。
- **Jimmy 的延伸：** 一次 demo 只能揭露動作；要成為可重跑 Skill，還要補 trigger、允許 input、judgment、acceptance、exception 和 human review。
- **限制：** 這則 Threads 不是 OpenAI 官方產品文件；它不能證明 Record & Replay 功能目前可用、可安全部署或能學會隱含判斷。公開文章只將其當成「示範不等於學會」的教學入口，不宣稱產品規格或成效。
- **相關公開文章：** [由 demo 到 Skill](chapters/4-11-demo-to-skill.md)。

<a id="ai-builder-multi-agent"></a>

## AI Builder：多工具不等於多 agent 協作

- **原始來源：** [阿蔺 A-Lin：Claudian × opencode 的多模型工作流](https://x.com/alin_zone/status/2049482987402899559)
- **來源提供：** 一個把不同模型和工具接進同一知識工作環境的公開實例。
- **Jimmy 的延伸：** 多個 channel、model 或 connector 只有在 owner、角色、交接 artifact、verification 和 conflict rule 都被定義後，才稱得上 multi-agent；否則只是多個工具並排。
- **限制：** 原帖不驗證任何工具組合、模型、成本、私隱或協作成效；不要以「多 agent」名稱掩蓋未定義的權限和責任。

<a id="ai-builder-loop-specialist"></a>

## AI Builder：Loop 與 specialist 的分工

- **原始來源：** [Instagram Reel：Graph Engineering — 何時用 Loop，何時用 specialist graph](https://www.instagram.com/reel/DbaH2fNiHnX/)（作者未能確認）
- **來源提供：** 將 retrieval、固定 workflow、可用工具反覆判斷的 Loop，以及 domain specialist routing 作出教學式對比。
- **Jimmy 的延伸：** 先按 context、authority、artifact、verification 和 escalation 切工作；Loop 和 specialist 只是不同的受限自主形態，不應按 org chart 或流行名詞硬套。
- **限制：** 原始 Reel 的作者／caption 未能可靠確認，內容是 teaching heuristic，不是 framework benchmark 或架構選型定論；高風險、客戶、財務、permissioned 或不可逆行動仍需 scoped tools、stop line、audit 與 human approval。
- **相關公開文章：** [Loop 還是 specialist](chapters/4-13-loop-or-specialist.md)。

<a id="ai-builder-delegation"></a>

## AI Builder：委派容量，不是個人生產力表演

- **原始來源：** [張維峰：Claude Managed Agents／Jess Yan 訪談整理](https://www.facebook.com/jerry.chang.505523/posts/10241069291524671/)
- **來源提供：** 以 managed agents、任務委派與驗證為中心的公開訪談整理。
- **Jimmy 的延伸：** Agent 的價值是讓人可同時管理更多有明確完成線的工作；真正瓶頸轉為任務定義、authority、evidence、exception 和 reviewer capacity。
- **限制：** 這不是效率、headcount、成本或商業成果承諾；委派範圍愈大，越要縮小第一輪風險並保留 human release。
- **相關公開文章：** [委派容量不是開更多 agent](chapters/4-5-delegation-capacity.md)。

<a id="ai-builder-market-signal"></a>

## AI Builder：市場訊號 triage，不是爆款複製

- **原始來源：** [雪踏烏雲：如何從零開始打造自己的爆款監控系統](https://x.com/Pluvio9yte/status/2082386081794961733)
- **來源提供：** 作者以相對基線、分層快篩與少量深讀，將零散同行內容變成可回看研究隊列的個案。
- **Jimmy 的延伸：** 市場訊號先回答「值不值得花更多時間研究」；只有深讀後形成的假設，再配合自己的結果，才決定一個 pattern 是否值得留下。
- **限制：** 作者的帳號數、平台資料、R／M／Tier 公式、成本與工具組合均未由本 library 獨立驗證，亦可能不適用於香港或任何特定平台。它不支持「追蹤爆款即可帶來 lead／收入」或複製第三方內容的主張。
- **相關公開文章：** [市場訊號怎樣由收藏變成判斷](walkthroughs/pick-topics-from-competitor-signals.md)；它只屬職能應用案例，不在五階段的首次閱讀路線。

<a id="ai-builder-workbench-contract"></a>

## AI Builder：workbench contract，先定工作場再動手

- **原始來源：** [火山哥：Codex 工作流影片](https://x.com/huoshan007/status/2084916064228626584)。
- **來源提供：** 以可回退 workspace、先讀 project map、範圍／驗收、分級權限、測試與 handoff，示範 AI 參與多步工作時應保留的操作節奏。
- **Jimmy 的延伸：** 將這個 coding-workflow 示範抽成通用的 workbench contract：目的、現行 state、可讀 references、允許 actions、驗收／handoff 和 stop line。它適用於任何需要 AI 在有限工作環境內協作的任務，不是某個工具的功能教學。
- **限制：** 這是 creator 的公開教學示範，並非任何 workspace、permission model、測試覆蓋、資料安全或商業結果的獨立驗證。不可因此把 Vault、客戶、合約、CRM、credentials 或 production data 放入 AI context；任何外發、刪除、覆寫、安裝、設定或網絡 action 仍要按風險由人明確審批。
- **相關公開文章：** [先寫一張 workbench contract](chapters/4-19-workbench-contract.md)。

<a id="ai-builder-work-card"></a>

## AI Builder：AI workforce 先由一張可驗收 work card 開始

- **原始來源：** [關登元：Claude Code 商業系統作品集](https://www.facebook.com/story.php?story_fbid=10164225099079194&id=775234193)。
- **來源提供：** 作者以不同部門的 named systems 和 recurring AI tasks 組成 portfolio，讓「AI 可以幫甚麼工作」有一個可指認的職能地圖。
- **Jimmy 的延伸：** 不把案例數量當成熟度；一個可信 AI worker 要先有 work pain、approved input、inspectable artifact、review / stop 與 outcome evidence。work card 是把 AI work 由抽象角色變成可討論、可保留或停止的最小單位。
- **限制：** 這是作者自述的 public portfolio，不獨立證明系統已 production-ready、可完全自動化、可安全處理任何資料，或帶來時間、成本、收入和品質成果。不可將 customer-facing、金錢、合約、合規、個人資料或不可逆操作當成 first worker。
- **相關公開文章：** [先寫一張可驗收 AI work card](chapters/4-20-ai-work-card.md)。
- **相關公開文章：** [跟住填第一張 AI work card](walkthroughs/write-an-ai-work-card.md)。

<a id="ai-builder-company-map"></a>

## AI Builder：AI 公司圖是教學比喻，不是部署藍圖

- **原始來源：** [Jack Shen：把 Codex 組成一間 AI 公司](https://www.threads.com/@jackshenaiadvisor/post/DbpPEYhERqG)。
- **來源提供：** 以 CEO、部門、Skills 和 Apps/MCP 把抽象 AI stack 翻成新手較易理解的公司語言。
- **Jimmy 的延伸：** 角色圖只適合作為 onboarding map。真實設計必須逐手寫清 context、task、authority、artifact、verification 和 human approval；只有這些東西不同，才有理由拆 agent 或 specialist。
- **限制：** 來源的圖像及其角色數量、速度、品質和成本主張沒有獨立 architecture、security、permission、evaluation 或 outcome 驗證。它不代表任何多 agent 架構已可用，更不授權工具寫入、對外發送或部署。
- **相關公開文章：** [公司圖是入門，不是部署藍圖](chapters/4-21-ai-company-map.md)。

<a id="ai-builder-memory-lifecycle"></a>

## AI Builder：工作記憶要有 lifecycle

- **原始來源：** [Facebook 公開帖文：cross-agent engineering memory](https://www.facebook.com/groups/gaitech/posts/1744889666695241/)；延伸參考：[hamanpaul/paulsha-hippo](https://github.com/hamanpaul/paulsha-hippo)。Facebook 作者未能確認。
- **來源提供：** 以 capture、retrieval、application attribution、reinforce／contradict／retire 描述跨 session 工作經驗怎樣被重新使用。
- **Jimmy 的延伸：** AI 工作記憶要由 evidence → task-specific recall → verified application → lifecycle 組成；儲存、找回、讀到和用對是四件不同的事。
- **限制：** 公開帖文作者身份未能確認；外部 repository 不是 Jimmy／DotAI 部署、相容性、成本、私隱或成效證明。不可鏡像原帖圖片、OCR 或全文，也不可因此將 Vault、客戶資料或 production data 接入任何 memory system。
- **相關公開文章：** [工作記憶的 lifecycle](chapters/4-14-work-memory-lifecycle.md)。

<a id="ai-builder-readable-state"></a>

## AI Builder：可讀 state 才可驗收

- **原始來源：** [Thariq：Fable 如何以可讀 script、JSON 與驗證步驟處理 launch video](https://x.com/trq212/status/2064826394589442448)
- **來源提供：** 一個公開創作 workflow，將 raw material 轉成 transcript、選段理由、JSON edit state，再以檢查步驟回看 output。
- **Jimmy 的延伸：** AI 可接手的是已外化為 source、state、bounded change、verification 和 human decision 的工作段落；不只是「叫它做創作」。
- **限制：** 這是單一公開 creator workflow，不能證明任何影片工具、render pipeline、agent 或創作品質必然可靠。讀者頁不鏡像影片、轉錄、asset 或技術步驟；敏感素材、權利、事實和 taste 仍由人負責。
- **相關公開文章：** [先把工作變成可讀 state](chapters/4-15-readable-state.md)。

<a id="ai-builder-specialist-review"></a>

## AI Builder：specialist review 要容許有理由的分歧

- **原始來源：** [Chris：Claude Projects 智囊團／讓不同顧問互相衝突](https://www.instagram.com/p/DZFOPFFE9TX/)；補強機制：[OpenAI：A practical guide to building agents](https://openai.com/business/guides-and-resources/a-practical-guide-to-building-ai-agents/)。
- **來源提供：** 前者將不同角色的 knowledge、禁忌與 review 視角分開；後者說明 multi-agent 只應在單一 agent 的清楚工具／指令仍不足時才增加，且 agents 需要在明確 guardrails 內運作。
- **Jimmy 的延伸：** specialist 的價值來自不重疊的 review question、最少必要 evidence、rubric、分歧格式與 human owner decision；多數 AI 同意不等於安全或正確。
- **限制：** 原帖是 creator 的 Claude Projects 教學與 lead-magnet，並非多 agent 準確度 benchmark、專業意見或任何風險決策的保證。不可把法律、財務、醫療或合規判斷交給 AI 投票，也不可把 private context 無限制分給多個 worker。
- **相關公開文章：** [設計有用的 specialist disagreement](chapters/4-16-specialist-disagreement.md)。

<a id="ai-builder-rules-and-judgment"></a>

## AI Builder：固定規則、計算與 AI 判斷要分工

- **原始來源：** [Dustin GMAT：14 場 AI 學員訪談／AI 不只是聊天，而是第二套工作系統](https://www.threads.com/@dustin_gmat/post/DZSXdadj2ir)
- **來源提供：** 公開訪談整理指出，欄位對欄位的計算不應由 LLM 猜；固定格式、欄位和規則宜交給 deterministic 方法，AI 再處理解釋、歸納與例外。
- **Jimmy 的延伸：** 先分出可重跑規則／計算和需要 context 的工作判斷，才決定 AI 應在哪一格起草、解釋或提示未知；最終取捨仍屬 human owner。
- **限制：** 這是 creator 的訪談整理，並非計算準確度 benchmark、模型能力測試或技術／財務建議。任一公式、資料來源、權限或高後果決定仍須由適當 owner 獨立驗證。
- **相關公開文章：** [固定規則與 AI 判斷分工](chapters/4-17-rules-versus-judgment.md)。

<a id="ai-builder-independent-review"></a>

## AI Builder：獨立 review 回到 evidence，不只信自我檢查

- **原始來源：** [Dustin GMAT：14 場 AI 學員訪談／AI 不只是聊天，而是第二套工作系統](https://www.threads.com/@dustin_gmat/post/DZSXdadj2ir)
- **來源提供：** 公開 carousel 提出 verification 比 output 更重要，並建議審查者回到 raw data 與結果，而非依賴前一輪討論脈絡。
- **Jimmy 的延伸：** worker 的生成過程、原始材料、review rubric 和 owner decision 應分開；獨立 review 要保留 evidence 和任務範圍，但不把未驗證推理當成結論依據。
- **限制：** 這不是不同模型比較、AI reviewer 準確度、法律／合規審核或外發批准的證明。AI reviewer 即使 pass，敏感、對外、不可逆或高後果決定仍由 human owner 負責。
- **相關公開文章：** [獨立 review](chapters/4-18-independent-review.md)。

<a id="ai-value-creator"></a>

## AI Value Creator：採用、治理與量度

- **原始來源：** [Notion Research：Inside the AI Transformation](https://www.notion.com/resources/inside-the-ai-transformation)（[研究報告 PDF](https://downloads.ctfassets.net/spoqsaf9291f/4C7Y2LaCO2rMJJEYzfPXPy/326d6f24c26302c66cd326579d04e77a/GloablAITransformation_ResearchReport.pdf)）
- **來源提供：** 全球 desk-based respondents 對 AI 成熟度、integration、governance 和 measurement 的自報調查。
- **Jimmy 的延伸：** AI adoption 的下一步是讓一條真 workflow 接好 context、權限、驗收和指標，而不是只增加帳戶或工具。
- **限制：** 這不是香港 SME census 或因果實驗；調查相關性不代表加入文件、治理或量度就必然創造價值。

<a id="ai-value-creator-adkar"></a>

## AI Value Creator：training 前先有 awareness 和 desire

- **原始來源：** [Foundor.ai：ADKAR 變革管理——成功的五個步驟](https://foundor.ai/zh-Hant/blog/blogadkar-change-management-model)
- **來源提供：** ADKAR 的 Awareness、Desire、Knowledge、Ability、Reinforcement 變革管理框架。
- **Jimmy 的延伸：** AI adoption 不是先排一堂工具課；先找到對方的真工作摩擦和安全第一個成果，才有意欲將新做法放回日常 workflow。
- **限制：** ADKAR 是變革框架，不是 AI adoption 成效證明；不可用它推論任何團隊必然接受工具、完成培訓或產生 ROI。

<a id="ai-value-creator-first-safe-outcome"></a>

## AI Value Creator：由第一個安全成果開始

- **原始來源：** [數位敘事力期刊：Claude 教育應用手冊](https://www.facebook.com/Journal.of.Digital.Narrative/posts/122208977030587238/)（[公開手冊](https://claude-edu-handbook.vercel.app/)）
- **來源提供：** 將 AI 學習拆成 Concept → Guiding → Doing → Resources，並在任務中保留先想清楚、再動手、最後確認的教學結構。
- **Jimmy 的延伸：** 第一次不應派工具清單，而應讓人完成一件小而真、安全、可留下、有人 review 的工作 artifact，再用 feedback 選下一步。
- **限制：** 這是台灣教育導向的公開 handbook，不是香港教育／企業政策、課程成效或產品規格；不應用它授權未成年人無監督使用、上傳敏感資料或跳過 human review。
- **相關公開文章：** [第一個安全成果](chapters/5-10-first-safe-outcome.md)。
- **相關公開文章：** [45 分鐘完成第一個安全 AI 成果](walkthroughs/lead-a-first-safe-ai-outcome.md)。

<a id="ai-value-creator-visible-ladder"></a>

## AI Value Creator：成長路線要看得見，人才知道下一步

- **原始來源：** [LeoAido：Claude Code 7 個段位](https://www.instagram.com/p/DZXaDrrGuvY/)；[Jimmy Lau：AI User → AI Growth Builder](https://www.threads.com/@jimmylau.ai/post/DbvT0ooki1b)
- **來源提供：** 一個把 AI 使用拆成可見能力層次的外部示例，及 Jimmy 對「由工具到真工作、再到持續系統」的原創公開表述。
- **Jimmy 的延伸：** Growth with AI 的五個 Stage 只用作找下一步的導航，不是身份、考牌、職級或必經順序；每個 Stage 都要回到一件安全、可驗收的真工作。
- **限制：** 沒有通用的 AI 成熟度標準；不同工具、角色、年資和行業都不能直接比級。這不是能力認證、招聘標準或商業承諾。
- **相關公開文章：** [AI 成長路線要看得見](chapters/5-3-visible-ladder.md)；[五個 readiness gate](chapters/5-11-next-stage-readiness.md)。
- **相關公開文章：** [由真工作診斷 Stage](chapters/5-12-diagnose-stage-from-work.md)。

<a id="ai-value-creator-workflow-diagnosis"></a>

## AI Value Creator：先診斷 AI adoption 卡位

- **原始來源：** [Dustin GMAT：14 場 AI 學員訪談／AI 不只是聊天，而是第二套工作系統](https://www.threads.com/@dustin_gmat/post/DZSXdadj2ir)
- **來源提供：** 從公開訪談整理出常見卡位：資料分散、流程太長、數字不應亂猜、外發要人核對、敏感資料與驗證限制；並主張由一條真 workflow 開始拆解。
- **Jimmy 的延伸：** 將表面「AI 用唔到」分成可行性、workflow、能力、意欲、治理五格，並只處理最早不成立的一格。這是教學與 coaching 的工作診斷法，不是人格或能力評分。
- **限制：** 這是 creator 對 14 場訪談的公開整理，不是代表性市場研究或任何陪跑成效證明。五格診斷是 Jimmy 的轉譯；不可用它收集私人 chat、客戶資料、醫療／財務／法律意見，亦不可把人貼成固定等級。
- **相關公開文章：** [先診斷 adoption 卡位](chapters/5-13-diagnose-adoption-bottleneck.md)。
- **相關公開文章：** [用五格找出 AI adoption 真正卡位](walkthroughs/diagnose-an-ai-adoption-bottleneck.md)。

<a id="ai-super-user-evidence"></a>

## AI Super User：生成前分清 evidence、判斷、未知和假設

- **原始來源：** [KeiraWashington：AI 電商詳情頁先理解產品，再生成內容](https://www.threads.com/@keirawashington854/post/DZrZBXAgWOc)
- **來源提供：** 「先理解材料、後生成」的公開工作流程 framing。
- **Jimmy 的延伸：** 將材料分成 evidence、interpretation、unknown 和 assumption，讓 internal draft 可 review，而不是把空白填成事實。
- **限制：** 社交帖不代表 AI 能自行 fact-check、驗證產品或保證內容正確；高後果或對外內容仍要適當 owner 確認。
- **相關公開文章：** [材料、判斷、未知和假設](chapters/2-8-evidence-before-generation.md)；[先理解，再生成](chapters/2-5-product-understanding.md)；[理解報告的八項檢查](walkthroughs/ai-understand-product-before-generating.md)。

<a id="ai-operator-work-map"></a>

## AI Operator：先畫 work map，再談 workflow

- **Source status：** 目前沒有可核對、直接支持這個 framework 的公開 primary source。舊 Facebook share URL 的公開 preview 不能驗證這個內容，因此不再當作公開 evidence。
- **Jimmy framework candidate：** 將一條工作外化為 trigger、input、owner、state、output，目的是找出卡點和交接邊界；它是對齊工具，不是 automation approval。
- **Release status：** local review / owner decision required。若 Jimmy 日後確認可作自己的公開 framework，文章必須清楚寫作 Jimmy 的工作方法；否則只留在 Vault，不進 GitHub release。
- **限制：** 一張 map 不證明流程已更快、已接入任何系統或可安全自動化；例外和不可逆動作仍由 human owner 決定。

<a id="ai-builder-skill"></a>

## AI Builder：Skill 是品質閘，不是長 prompt

- **原始來源：** [Kai Chen：Addy Osmani agent skills / production-grade engineering skills](https://www.threads.com/@kai_ch_chen/post/DZjS95gE1PM)
- **來源提供：** 將 AI 工作標準化為可重用 skill 的公開教學材料。
- **Jimmy 的延伸：** Skill 應有 trigger、reference、steps、quality gate 和 stop；它把完成標準和例外變得可 review。
- **限制：** 這不證明任何 runtime、skill library 或 delivery outcome；不能把 secret、客戶資料、付款、外發權限或 production credentials 寫進 Skill。

<a id="ai-value-creator-outcome"></a>

## AI Value Creator：用 workflow outcome，不用工具名證明價值

- **原始來源：** [Jobsdb Hong Kong：Sales & Marketing AI skills 實戰教學](https://hk.jobsdb.com/zh/career-advice/article/salesandmarketingai%E6%8A%80%E8%83%BD%E5%AF%A6%E6%88%B0%E6%95%99%E5%AD%B8cv%E5%90%B8%E7%9D%9B%E5%AF%AB%E6%B3%95)
- **來源提供：** 以實際工作場景、產出和 review 講能力的職場 framing。
- **Jimmy 的延伸：** AI 價值要用一段有範圍 workflow 的可 review artifact 和誠實比較來看，不要把工具 badge 或 demo 當成成果。
- **限制：** 外部職場文章不是能力測試、香港市場保證或 business outcome 證明；任何數字仍要按自己的流程獨立驗證。

<a id="ai-value-creator-proof-card"></a>

## AI Value Creator：value proof card 要同時寫成果與邊界

- **原始來源：** [Jobsdb Hong Kong：Sales & Marketing AI skills 實戰教學](https://hk.jobsdb.com/zh/career-advice/article/salesandmarketingai%E6%8A%80%E8%83%BD%E5%AF%A6%E6%88%B0%E6%95%99%E5%AD%B8cv%E5%90%B8%E7%9D%9B%E5%AF%AB%E6%B3%95)。
- **來源提供：** 用工作場景、AI 協助、輸出／review 和結果描述能力的職場 framing，而非只列工具名字。
- **Jimmy 的延伸：** value proof card 將一次 AI 工作寫成 pain、scope、AI role/input、artifact、review/control、observation、boundary 和 next decision。它是私有學習／決策記錄，不是自動變成 case study。
- **限制：** Jobsdb 文章針對職場能力與 CV 寫法，不是 AI 成效研究、客戶案例、ROI 證明或公開 case 授權。proof card 不可帶入客戶、學員、CRM、合約、付款、私有 transcript、未批准數字或可識別個案。
- **相關公開文章：** [跟住填一張不誇大的 value proof card](walkthroughs/write-an-ai-value-proof-card.md)。

<a id="ai-super-user-feedback"></a>

## AI Super User：把 feedback 變成可重用判斷

- **原始來源：** [陳乃誠：別再收集 prompt 咒語大全了](https://www.facebook.com/photo.php?fbid=10236423011784806&set=a.1034465271333&id=1516495867)
- **來源提供：** AI 學習由 prompt collection 轉向 context 與 feedback 的公開教學 framing。
- **Jimmy 的延伸：** 只有有原因、適用範圍、owner 與失效條件的重複修正，才值得成為下一次可用 reference。
- **限制：** 這不代表任何工具會自動學懂使用者偏好，也不應把老闆、客戶或同事的臨時意見直接寫成永久共享規則。
- **相關公開文章：** [把 feedback 變成判斷](chapters/2-9-feedback-into-judgment.md)；[把一條 feedback 變成下次可用的判斷](walkthroughs/turn-feedback-into-a-rule.md)。

<a id="ai-super-user-tier-one"></a>

## AI Super User：每種工作一個 Tier-1 default

- **原始來源：** [羅達 Rhoda：Claude Code 新手大禮包](https://www.facebook.com/AV8D.levelup/posts/1593227049478740/)
- **來源提供：** 以實際工作反射、context 和 review 來理解 AI 工具使用的公開教學 framing。
- **Jimmy 的延伸：** Tier-1 是一個工作決定：在一個明確工作上，挑最容易累積 context、review 和修正反射的暫定 default，並預設 reset trigger。
- **限制：** 這不是產品 benchmark、當前功能文件或資安評估；一個工具不會因為適合某一類工作，就適合所有資料、所有人或所有公司。

<a id="ai-super-user-review-loop"></a>

## AI Super User：review 令下一稿變好

- **原始來源：** [陳乃誠：別再收集 prompt 咒語大全了](https://www.facebook.com/photo.php?fbid=10236423011784806&set=a.1034465271333&id=1516495867)
- **來源提供：** 將 feedback 納入 AI 學習的公開教學 framing。
- **Jimmy 的延伸：** rubric、pass / revise / stop 和 revision memo 令 review 由最後一眼變成下一次可用的小型學習 loop。
- **限制：** 這不證明 AI self-review 可取代人，也不等於 pass 後便能外發、採用或進 production。

<a id="ai-operator-portable-context"></a>

## AI Operator：portable context pack

- **原始來源：** [陳乃誠：如果 AI 工具突然收掉，你餵給它的東西帶得走嗎？](https://www.facebook.com/photo.php?fbid=10236380471161317&set=a.1034465271333&id=1516495867)
- **來源提供：** 將 AI 工作資料的可攜性放回使用者可保留 context 的公開討論。
- **Jimmy 的延伸：** portable pack 只帶當前工作所需、可信且允許帶走的 context，連同 owner、更新日期和 stop line。
- **限制：** 這不驗證任何 tool migration、security 或 memory 功能；不能把 credentials、CRM、contact、contract 或 production config 放入 pack。

<a id="ai-builder-smallest-form"></a>

## AI Builder：選最小足夠的 working form

- **原始來源：** [施育廷：LINE x Gemini 多源資訊整合與自動化內容生成](https://www.facebook.com/groups/gaitech/posts/1719799119204296/)
- **來源提供：** AI workflow、資料整合與自動化架構的公開參考。
- **Jimmy 的延伸：** 固定 execution 優先使用最小、可預期方法；只有重複且仍需判斷的工作才用 AI / Skill，input、owner 或 acceptance 未清時應 map 或 stop。
- **限制：** 這不證明任何 platform、connector、integration、成本或 delivery outcome；固定流程一樣需要 owner、review 和 recovery。

<a id="ai-builder-evidence-loop"></a>

## AI Builder：以 evidence loop 驗收，而非看 screenshot

- **原始來源：** [張維峰：Codex 瀏覽器開發模式](https://www.facebook.com/jerry.chang.505523/posts/openai-%E7%82%BA-codex-%E6%8E%A8%E5%87%BA%E4%BA%86-developer-mode-for-browser-use%E9%81%A9%E7%94%A8%E6%96%BC-chrome-%E5%92%8C-codex-%E7%9A%84-in-app-bro/10240851270714287/)
- **來源提供：** 從畫面檢查走到 DevTools / state evidence 的公開技術教學 framing。
- **Jimmy 的延伸：** 完成線應是可重跑的 reproduce → inspect → patch → verify → report loop，並說清驗證範圍。
- **限制：** 這不是任何網站、表單、API 或 production workflow 已被驗證的聲明；browser access、test result 或 response 都不授權公開、寫入或 deploy。

<a id="ai-builder-regression-pack"></a>

## AI Builder：最小 regression pack

- **原始來源：** [數字黑魔法：AI Agent 驗收與回歸測試](https://www.youtube.com/watch?v=H0XmxIalAEQ)；補強機制：[OpenAI：A practical guide to building agents](https://openai.com/business/guides-and-resources/a-practical-guide-to-building-ai-agents/)。
- **來源提供：** 前者將反覆人工驗收轉成可重跑 regression case；後者建議 guardrails 應由真實 edge case 和 failure 逐步加上，而不是假設一條 rule 已足夠。
- **Jimmy 的延伸：** 先由高頻、傷害高、可觀察、可重現的三至五個錯建立 fixed case；分開 hard check、reviewer flag 和 human-only decision。
- **限制：** 作者的個人經驗不是統計；pass 不代表未測到的風險不存在，也不可用 LLM score 取代人類對外承諾、事實、權利或發布決定。

<a id="ai-value-creator-govern-measure"></a>

## AI Value Creator：pilot 的最小治理與量度

- **原始來源：** [Notion Research：Inside the AI Transformation](https://www.notion.com/resources/inside-the-ai-transformation)
- **來源提供：** 將 governance、integration 和 measurement 放入 adoption 討論的全球調查 framing。
- **Jimmy 的延伸：** 一張 control card 加一兩個明確 observation，足以決定 pilot 應 retain、revise 或 stop；量度要同時看到價值與風險。
- **限制：** 這不是香港 SME benchmark、privacy / compliance approval 或 ROI 承諾；不可用 KPI 監控員工或收集不必要資料。

<a id="ai-value-creator-scale-stop"></a>

## AI Value Creator：擴大或停止 adoption

- **原始來源：** [梁文宣：91APP AI Agent 平台與企業信任](https://www.facebook.com/wenshiuanliang/posts/pfbid0oEMdoMmZr4QbYnmVwgNWkJMmfuwZ8z3xa7ab9yfG638QHT5tdERssW6atxthk9ehl)
- **來源提供：** 以治理和企業信任理解 AI agent adoption 的公開參考。
- **Jimmy 的延伸：** 每次擴大都要重新看 evidence trend、例外、owner capacity、新風險和 rollback；治理不夠時先修或 stop。
- **限制：** 這不構成任何公司的 permission、security、compliance 或 expansion advice；低風險 draft 不可直接推到客戶資料、外發或財務 action。

<a id="ai-value-creator-demo-proof"></a>

## AI Value Creator：分清 demo 與 value proof

- **原始來源：** [Jobsdb Hong Kong：Sales & Marketing AI skills 實戰教學](https://hk.jobsdb.com/zh/career-advice/article/salesandmarketingai%E6%8A%80%E8%83%BD%E5%AF%A6%E6%88%B0%E6%95%99%E5%AD%B8cv%E5%90%B8%E7%9D%9B%E5%AF%AB%E6%B3%95)
- **來源提供：** 用 work scene、AI role、review 和 output 解釋能力的職場 framing。
- **Jimmy 的延伸：** demo、reviewed artifact、bounded pilot observation 和 approved proof 是不同證據層，不能跳級成 case study 或 ROI。
- **限制：** 職場文章不是招聘市場統計、客戶案例、能力保證或 business outcome 證明；私有 course／client material 不會進公開 library。

<a id="ai-builder-bounded-loop"></a>

## AI Builder：第一條 bounded agent loop

- **原始來源：** [Yanhua：Agent 的本質是一個 while loop](https://x.com/yanhua1010/status/2083509592479449279)
- **來源提供：** 以 loop 說明 agent 如何反覆執行、檢查和繼續的公開技術解釋。
- **Jimmy 的延伸：** 第一條 agent loop 應先限制在可撤回、可 review 的 draft workflow；首輪目標是 evidence，不是 autonomy。
- **限制：** 這不是任何 runtime、framework、schedule 或 automation 的安全性、成本或成效保證；不可用外發、付款、CRM、客戶資料或不可逆行動作為 first loop。

<a id="ai-value-creator-pilot"></a>

## AI Value Creator：設計有 owner 的 adoption pilot

- **原始來源：** [Notion Research：Inside the AI Transformation](https://www.notion.com/resources/inside-the-ai-transformation)
- **來源提供：** 將 integration、governance 和 measurement 放入 AI adoption 討論的全球調查 framing。
- **Jimmy 的延伸：** 一個 pilot 要有問題、範圍、最小 input、artifact、owners、controls、evidence 和 decision date；缺一格就先不跑。
- **限制：** 該調查不是香港 SME benchmark 或因果實驗；這篇不構成客戶案例、ROI 承諾、員工監控方案或自動化授權。

<a id="ai-operator-content-system"></a>

## AI Operator：內容要由真訊號走到可交接流程

- **原始來源：** [Google Search Central：Creating helpful, reliable, people-first content](https://developers.google.com/search/docs/fundamentals/creating-helpful-content)。
- **來源提供：** Google 對 people-first、原創、可信、清楚作者／方法與避免只為流量大量生成內容的公開指引。
- **Jimmy 的延伸：** 將這些內容原則放回工作流程：先讀真訊號與現有材料，才形成 angle brief、draft、review 和下一輪 feedback；AI 可協助整理，但不能代替受眾判斷、事實核對或發佈責任。
- **限制：** Google 文件不是內容營銷成效、SEO 排名、lead、香港市場或 AI 寫作品質保證；它只支援這批文章的公開內容／信任 framing，不證明任何 campaign 或 creative workflow 的結果。
- **相關公開文章：** [真資料先於 AI 內容](chapters/3-13-live-data-before-ai-content.md)；[AI 寫內容不等於內容系統](chapters/3-14-content-system-not-ai-writing.md)；[先找最接近贏的一步](chapters/3-15-seo-starts-with-near-win.md)；[創作工作仍需要 grammar](chapters/3-16-creative-work-needs-grammar.md)；[campaign content workflow](chapters/3-17-campaign-content-workflow.md)。

<a id="ai-builder-practical-agents"></a>

## AI Builder：由一件真工作開始，保留 guardrails 和 human intervention

- **原始來源：** [OpenAI：A practical guide to building agents](https://openai.com/business/guides-and-resources/a-practical-guide-to-building-ai-agents/)。
- **來源提供：** 對 workflow、單一／多 agent orchestration、明確工具、guardrails、可逆與高風險 action 的 human intervention，以及由簡入繁的公開 agent-building 指引。
- **Jimmy 的延伸：** Builder 不從 agent team、connector 或 UI 開始，而從一件可驗收工作、可讀 state、明確 scope、quality check、evidence 和 owner decision 開始；Skill、loop、automation 或 specialist 都只是不同工作形態。
- **限制：** OpenAI 文件不是 Jimmy／DotAI runtime audit、產品規格、成本／安全／商業成果保證，也不授權任何 client、CRM、payment、credentials、production data、外發或不可逆 action。本文庫仍以 Jimmy 的 work card、contract 和 receipt 方法作教學轉譯。
- **相關公開文章：** [五個 build gate](chapters/4-12-ready-to-build.md)；[答案不等於工作](chapters/4-22-answer-is-not-work.md)；[Skill 是工作合約](chapters/4-23-skill-is-a-work-contract.md)；[可靠 loop](chapters/4-24-agent-reliability-needs-a-loop.md)；[第一條 agent loop](chapters/4-25-first-agent-loop.md)；[AI coding 的 scope](chapters/4-26-ai-coding-needs-scope.md)；[connector 不是 agent system](chapters/4-27-connector-is-not-an-agent-system.md)；[automation pipeline](chapters/4-28-automation-is-a-pipeline.md)；[workflow moat](chapters/4-29-workflow-moat-is-not-ui.md)；[content agent](chapters/4-30-content-agent-starts-with-evidence.md)；[AI video role system](chapters/4-31-ai-video-is-role-system.md)；[新工具採用](chapters/4-32-new-tool-adoption-decision.md)；[content direction](chapters/4-33-content-direction-is-problem-memory.md)；[跟住填 AI run receipt](walkthroughs/write-an-ai-run-receipt.md)。

<a id="ai-value-creator-adoption"></a>

## AI Value Creator：用真 workflow、治理和量度看 adoption

- **原始來源：** [Notion Research：The State of Global AI Transformation](https://www.notion.com/resources/inside-the-ai-transformation)；[OpenAI：Practices for Governing Agentic AI Systems](https://openai.com/index/practices-for-governing-agentic-ai-systems/)。
- **來源提供：** 一份全球受訪者調查將 integration、governance、measurement 放入 transformation 討論；OpenAI 的白皮書則將 agentic systems 的責任和安全實務放回可追責的 operational context。
- **Jimmy 的延伸：** AI value 不以 account、工具名或一次 demo 證明，而以一段真 workflow 的 owner、review、evidence、adoption 和下一個 scale／stop decision 來判斷；portfolio、proposal、課程或服務都要誠實寫清能證明甚麼、未能證明甚麼。
- **限制：** Notion 的調查不是香港 SME census、因果實驗或 ROI benchmark；OpenAI 白皮書不是任何公司的合規、permission 或 deployment approval。它們不支持客戶成效宣稱，也不授權收集私人資料或自動執行高風險 action。
- **相關公開文章：** [由 Builder 走到服務](chapters/5-14-builder-to-service.md)；[展示 AI work](chapters/5-15-show-your-ai-work.md)；[AI growth 是減法](chapters/5-16-ai-growth-is-subtraction.md)；[proposal 是未來工作](chapters/5-17-proposal-is-future-work.md)；[可被找到和信任的答案](chapters/5-18-answers-people-can-find-and-trust.md)；[adoption 需要 distribution](chapters/5-19-adoption-needs-distribution.md)；[教判斷](chapters/5-20-teach-ai-judgment-not-answers.md)；[enterprise agent governance](chapters/5-21-enterprise-agent-governance.md)；[founder risk](chapters/5-22-founder-risk-changes-by-stage.md)；[AI visibility](chapters/5-23-ai-visibility-is-evidence.md)；[use before build](chapters/5-24-use-before-build.md)；[demo vs value](chapters/5-7-demo-versus-value.md)。

## 不能在這裡出現的內容

- 客戶、學員、CRM、付款、合約或未公開 offer；
- 私有 Vault source note、會議記錄、raw transcript、OCR、下載 asset 或 signed URL；
- credentials、tokens、內部 agent 名稱、production dashboard 或可直接操作外部系統的資料；
- 未能確認作者、權利或原始網址的材料。
