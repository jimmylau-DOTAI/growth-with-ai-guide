# AI Builder（AI建立者）：親手建立可靠 AI 工作系統

你想用 Codex、Skill、Agent 或 automation 處理更多工作，但又怕 AI 讀錯、改多咗、遇到例外繼續猜，最後反而要花更多時間收拾。

真正的分水嶺不是工具有多少，而是一份工作有沒有清楚的 input、artifact、品質檢查、例外處理、人手 review 和停止線。

> **完成這一關後，你會留下：** 一張 AI work card、一次可停止的試跑、明確的品質閘和 run receipt。

## 先由這篇開始

[你唔係未識用 AI Agent：你未把一件工作交到可驗收](chapters/4-40-start-here-from-chat-to-ai-work.md)

不用先讀完這一關所有文章。先用一篇最貼近現況的攻略做一次，再回來補你真正需要的部份。

## 暫時不用急著做

未需要一開始砌 multi-agent 團隊、接高權限 connector 或讓 AI 直接對外發送。

## 本關全部攻略與練習

- 📘 攻略：[AI Agent 反覆犯同一個錯，唔一定係 prompt 唔夠長：你可能需要的是 harness](chapters/4-1-harness-not-prompt.md)
- 📘 攻略：[AI workflow 每次一改就怕另一格壞？先把三至五個重複錯變成 minimum regression pack](chapters/4-10-minimum-regression-pack.md)
- 📘 攻略：[示範一次工作，AI 未必已學識：由 demo 到可重跑 Skill，中間還差哪五格？](chapters/4-11-demo-to-skill.md)
- 📘 攻略：[你唔係未識用 AI Agent：真正難係把一件工作交到可驗收](chapters/4-12-ready-to-build.md)
- 📘 攻略：[你未必需要更多 Agent：先分清一條 AI Loop 還是要拆 Specialist](chapters/4-13-loop-or-specialist.md)
- 📘 攻略：[AI 記憶唔係儲得愈多愈好：要有 evidence、召回、驗收同退休](chapters/4-14-work-memory-lifecycle.md)
- 📘 攻略：[點解 AI 做完你都唔知啱唔啱？先把工作變成可讀 state](chapters/4-15-readable-state.md)
- 📘 攻略：[多個 AI 唔係一齊附和：點樣設計有用的 specialist review](chapters/4-16-specialist-disagreement.md)
- 📘 攻略：[唔好叫 AI 猜數：固定規則、計算同判斷要分開](chapters/4-17-rules-versus-judgment.md)
- 📘 攻略：[AI 自己 check 自己未夠：點樣設計獨立 review](chapters/4-18-independent-review.md)
- 📘 攻略：[唔好淨係叫 AI 做嘢：先寫一張 workbench contract](chapters/4-19-workbench-contract.md)
- 📘 攻略：[AI 做到一次唔等於可以交付：Skill 點樣用 quality gates 令結果過到收貨線？](chapters/4-2-quality-gates.md)
- 📘 攻略：[想做 AI workforce？先寫一張可驗收 AI work card](chapters/4-20-ai-work-card.md)
- 📘 攻略：[AI 公司圖可以幫你入門，但唔係部署藍圖](chapters/4-21-ai-company-map.md)
- 📘 攻略：[AI 交出一段答案，不等於它交到一份工作](chapters/4-22-answer-is-not-work.md)
- 📘 攻略：[你以為 Skill 是一段 prompt，其實它是一份工作合約](chapters/4-23-skill-is-a-work-contract.md)
- 📘 攻略：[AI Agent 反覆犯錯，不一定要換模型：先把錯分清楚](chapters/4-24-agent-reliability-needs-a-loop.md)
- 📘 攻略：[唔好一開始砌 AI 團隊：先跑一條可停的 Agent loop](chapters/4-25-first-agent-loop.md)
- 📘 攻略：[AI Coding 愈快，人愈要識砍 scope 同驗收](chapters/4-26-ai-coding-needs-scope.md)
- 📘 攻略：[接了幾個 connector，不等於你已經有 Agent system](chapters/4-27-connector-is-not-an-agent-system.md)
- 📘 攻略：[自動化不是 prompt 串連：它是一條有例外處理的 pipeline](chapters/4-28-automation-is-a-pipeline.md)
- 📘 攻略：[真正的 workflow 資產，不在 chatbot UI](chapters/4-29-workflow-moat-is-not-ui.md)
- 📘 攻略：[AI Loop 點樣先唔係排咗期嘅 prompt：由目標、檢查、修正到下一輪的工作系統](chapters/4-3-loop-engineering.md)
- 📘 攻略：[內容 Agent 點樣先唔會變成自動出廢文：先把證據整理好，再開始寫](chapters/4-30-content-agent-starts-with-evidence.md)
- 📘 攻略：[AI 影片工具不停換，怎樣先建立一條不會跟工具一起失效的影片系統？](chapters/4-31-ai-video-is-role-system.md)
- 📘 攻略：[新 AI 工具、模型、MCP 值唔值得接？先用一條真工作判斷，不要被 demo 帶著走](chapters/4-32-new-tool-adoption-decision.md)
- 📘 攻略：[內容方向不是每週選題清單：怎樣把讀者問題變成 AI 可以幫你累積的長期記憶？](chapters/4-33-content-direction-is-problem-memory.md)
- 📘 攻略：[AI 一遇資料不足就繼續猜？Skill 要先寫好 exception ladder，令它知道何時停](chapters/4-34-skill-exception-ladder.md)
- 📘 攻略：[AI 未開始做已經估錯？Build 前先寫 assumption ledger，唔好等改完才發現前提錯了](chapters/4-35-assumption-ledger-before-build.md)
- 📘 攻略：[第一個 AI live run 唔係直接按掣：怎樣用 dry run 逐格證明一條 workflow 可交付？](chapters/4-36-dry-run-before-live-run.md)
- 📘 攻略：[唔係每條 SOP 都應該變成 AI Skill：怎樣判斷留作 human runbook，還是交給 AI 跑？](chapters/4-37-human-runbook-or-ai-skill.md)
- 📘 攻略：[AI 改文件、網站或資料前，點樣先劃一個可回退 workspace，唔怕它直接掂正本？](chapters/4-38-reversible-workspace-before-ai-change.md)
- 📘 攻略：[Agent 一直顯示 Loading，係未壞咗？先寫清 status contract，令人知道何時等、何時介入](chapters/4-39-agent-status-contract.md)
- 📘 攻略：[切模型、開幾個 chat 唔等於 multi-agent：怎樣判斷你有的是工具選擇，還是可交接的 AI team？](chapters/4-4-multi-channel-vs-multi-agent.md)
- 📘 攻略：[你唔係未識用 AI Agent：你未把一件工作交到可驗收](chapters/4-40-start-here-from-chat-to-ai-work.md)
- 📘 攻略：[開更多 AI Agent 唔等於效率更高：真正限制你的是 delegation capacity，不是 agent 數量](chapters/4-5-delegation-capacity.md)
- 📘 攻略：[Skill 唔係存低一段長 prompt：怎樣把重複 AI 工作寫成可重跑的品質閘？](chapters/4-6-skill-is-quality-gate.md)
- 📘 攻略：[第一條 AI Agent loop 唔使證明它很自主：先證明它交得出可驗收成果](chapters/4-7-first-bounded-agent-loop.md)
- 📘 攻略：[Prompt、Skill、automation 還是暫時不 build？AI 工作先選最小足夠的形式](chapters/4-8-prompt-skill-automation-decision.md)
- 📘 攻略：[AI 話做完、畫面又似樣，為何仍未算完成？你缺的是可重跑的 evidence loop](chapters/4-9-evidence-loop.md)
- ✍️ 練習：[AI 點解反覆犯同一個錯：不要只加 prompt，先把可檢查規則放到模型外面](chapters/練習-ai-repeats-the-same-mistake.md)
- ✍️ 練習：[AI workflow 點樣由逐句指令變成可驗收循環：第一條 loop 要有檢查、狀態和停止線](chapters/練習-ai-workflow-loop-design.md)
- ✍️ 練習：[AI 話做完時點樣先收貨：用一張 run receipt 看清交付、檢查、未知和下一步](chapters/練習-write-an-ai-run-receipt.md)
- ✍️ 練習：[第一張 AI work card 點樣寫：把重複工作由「想做 Agent」變成可 review 的責任](chapters/練習-write-an-ai-work-card.md)

## 何時值得進入下一關？

當你已留下「一張 AI work card、一次可停止的試跑、明確的品質閘和 run receipt。」而且知道它在哪些情況不適用，就可進入 [AI Value Creator（AI價值創造者）：帶人用 AI 創造可證明價值](<../05-AI Value Creator（AI價值創造者）/README.md>)。這不是考牌；如果工作仍然卡在這一關，留在這裡多試一次反而更好。

[← 回到學習地圖](../../README.md)
