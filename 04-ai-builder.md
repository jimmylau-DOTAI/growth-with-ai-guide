# AI Builder：由 AI output，走到可靠工作系統

你開始做 Skill、Agent、automation 或 connector。真正分水嶺不是工具有多少，而是 input、完成線、quality gate、例外和 human review 有沒有被設計出來。

> **成功不是它跑得起，而是你知道它何時交得出、何時該停、出錯誰會發現。**

## 第一篇先讀

[你唔係未識用 AI Agent：你未把一件工作交到可驗收](chapters/4-40-start-here-from-chat-to-ai-work.md) — 先把 chat、Agent、Skill 的分別放回一件可驗收的真工作，然後才用 Codex 或其他工具試跑。

## 呢一關真正要建立的五個能力

1. [將 Agent 放入 bounded loop](chapters/4-7-first-bounded-agent-loop.md)，先定 scope、工具閘和停止線。
2. [將做穩的 routine 包成 Skill 品質閘](chapters/4-6-skill-is-quality-gate.md)，令下一次可重跑、可驗收。
3. [讓工作記憶有 lifecycle](chapters/4-14-work-memory-lifecycle.md)，只在需要時找回仍然可信的經驗。
4. [按 context 和驗收切分 loop 或 specialist](chapters/4-13-loop-or-specialist.md)，唔係照公司圖開更多角色。
5. [先寫一張可驗收 AI work card](chapters/4-20-ai-work-card.md)，用真 artifact 證明一個 AI 工作單位。

## 先由最貼近你的問題開始

- AI 答得好，但你仍然要自己做完後半段：[答案不等於一份工作](chapters/4-22-answer-is-not-work.md)
- 有一段好 prompt，卻每次仍要由零開始：[Skill 其實是一份工作合約](chapters/4-23-skill-is-a-work-contract.md)
- AI 未開始做已經估錯、改完先發現需求唔係咁：[先寫 assumption ledger](chapters/4-35-assumption-ledger-before-build.md)
- Skill 一遇資料不足、錯誤或對外 action 就一路猜：[先寫 exception ladder](chapters/4-34-skill-exception-ladder.md)
- workflow 跑到一次就想接真資料／外發：[先用 dry run 分段過關](chapters/4-36-dry-run-before-live-run.md)
- 想把所有 SOP 變 Agent：[先判斷它該是 human runbook 還是 AI Skill](chapters/4-37-human-runbook-or-ai-skill.md)
- 想讓 AI 直接改正本、又怕改壞：[先劃可回退 workspace](chapters/4-38-reversible-workspace-before-ai-change.md)
- Agent Loading 好耐，不知應等定介入：[先寫 status contract](chapters/4-39-agent-status-contract.md)
- AI 同一種錯一再出現：[先把錯分清楚，再設計可靠性](chapters/4-24-agent-reliability-needs-a-loop.md)
- AI 反覆犯同一個錯，加多幾句叮囑仍無效：[先做三類錯與三個檢查](walkthroughs/ai-repeats-the-same-mistake.md)
- 想一開始砌 AI 團隊：[先跑一條可停的 Agent loop](chapters/4-25-first-agent-loop.md)
- AI coding 愈做愈多、範圍卻愈來愈亂：[先砍 scope，再談功能](chapters/4-26-ai-coding-needs-scope.md)
- 接了很多工具，卻不知道是否真的有 Agent system：[connector 不等於工作系統](chapters/4-27-connector-is-not-an-agent-system.md)
- 想把 prompt 串成自動化，但怕出錯沒人知：[自動化是一條有例外的 pipeline](chapters/4-28-automation-is-a-pipeline.md)
- 有 chatbot／dashboard，卻不知道什麼才是可累積資產：[workflow 資產不在 UI](chapters/4-29-workflow-moat-is-not-ui.md)
- 想做內容 Agent，卻不想只自動出廢文：[先整理 evidence](chapters/4-30-content-agent-starts-with-evidence.md)
- AI 影片工具不停換：[先按角色設計影片系統](chapters/4-31-ai-video-is-role-system.md)
- 新模型、MCP、connector 不停出，怕接錯又怕落後：[先用五格判斷值不值得接](chapters/4-32-new-tool-adoption-decision.md)
- 每週都在出內容，卻沒有清楚要回答誰的問題：[內容方向是受眾問題的長期記憶](chapters/4-33-content-direction-is-problem-memory.md)
- Agent 反覆犯同一個錯：[能寫成規則的，不要只靠 prompt](chapters/4-1-harness-not-prompt.md)
- 想把重複做法存下來：[Skill 是品質閘](chapters/4-6-skill-is-quality-gate.md)
- 示範過一次工作，想知道是否已可變 Skill：[由 demo 補齊標準、例外與驗收](chapters/4-11-demo-to-skill.md)
- 想安全試第一條 Agent：[bounded agent loop](chapters/4-7-first-bounded-agent-loop.md)
- 不知何時用 prompt、Skill 或 automation：[選最小足夠的 working form](chapters/4-8-prompt-skill-automation-decision.md)
- 有個 project 想交 AI 處理，但怕它讀錯或改多咗：[先寫一張 workbench contract](chapters/4-19-workbench-contract.md)
- 想把 AI 變成可交代的工作幫手：[先寫一張可驗收 AI work card](chapters/4-20-ai-work-card.md)
- AI 話做完、你卻不知怎樣收貨：[跟住填一張 run receipt](walkthroughs/write-an-ai-run-receipt.md)
- 想即刻把一件工作寫成 AI work card：[跟住填第一張 work card](walkthroughs/write-an-ai-work-card.md)
- 睇到多部門／AI 公司圖，想知道實際怎樣落地：[公司圖是入門，不是部署藍圖](chapters/4-21-ai-company-map.md)
- 有一條 routine 想 build，但怕太早：[先過五個 build gate](chapters/4-12-ready-to-build.md)
- 不想再把 screenshot 當完成證明：[evidence loop](chapters/4-9-evidence-loop.md)
- 每次改動都怕壞了別處：[最小 regression pack](chapters/4-10-minimum-regression-pack.md)
- 有很多筆記／memory，卻不知道哪些仍然可信：[讓工作記憶有 lifecycle](chapters/4-14-work-memory-lifecycle.md)
- AI 出了結果但無法說清改過甚麼：[先把工作變成可讀 state](chapters/4-15-readable-state.md)
- 想讓多個 AI review，卻只得到一堆附和：[設計有用的 specialist disagreement](chapters/4-16-specialist-disagreement.md)
- 想加更多 AI 工作，卻不知自己其實驗收得幾多件：[委派容量不是開更多 agent](chapters/4-5-delegation-capacity.md)
- 既要處理數字，又要做判斷：[固定規則與 AI 判斷分工](chapters/4-17-rules-versus-judgment.md)
- AI 說自己已 check，你仍然不敢信：[設計獨立 review](chapters/4-18-independent-review.md)
- 想為 output 加上完成前檢查：[quality gates](chapters/4-2-quality-gates.md)
- 想理解多步 AI 工作為何要有 feedback：[loop engineering](chapters/4-3-loop-engineering.md)
- 同樣用 AI，為何別人快一個檔次：[先設計可驗收 workflow](walkthroughs/ai-workflow-loop-design.md)
- 想開多個 agent，但不知自己是否真的有一個團隊：[multi-channel 和 multi-agent 的分別](chapters/4-4-multi-channel-vs-multi-agent.md)
- 想知道何時要加 agent、何時只需一個 loop：[Loop 和 specialist 的分工](chapters/4-13-loop-or-specialist.md)

下一步是 [AI Value Creator](05-ai-value-creator.md)：用真 workflow、owner、evidence 和安全治理，帶人創造可回看的價值。
