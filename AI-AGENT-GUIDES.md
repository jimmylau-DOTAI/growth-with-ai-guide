# AI Agent 實戰攻略：由「想試」到「真係幫你做事」

Agent 唔係一個 Stage，亦唔係一個只屬於 developer 的玩具。

Stage 講緊：**你而家有能力負責到哪一步。**

Agent 攻略講緊：**你想令 AI 幫你處理哪一種工作。**

所以你可以未識 build Agent，但已經開始學識安全地用一個；亦可以識得做 Agent demo，但未準備好交畀團隊或客戶。

```text
用 Agent
→ 管理 Agent 做一件重複工作
→ Build 一個受控制的 Agent workflow
→ 證明它值得保留、擴大或停止
```

## 先找你現在是哪一種需要

| 你而家想做甚麼 | 最適合 Stage | 先讀哪裡 | 你暫時不用做甚麼 |
|---|---|---|---|
| 想知道 Agent 是甚麼、可否幫你完成第一件工作 | AI User → AI Super User | [第一件真工作點樣交畀 AI](chapters/2-1-from-answers-to-real-work.md) | 不用先造 bot、接 connector 或學 code。 |
| 想令 AI 每次理解正確資料，而不是亂猜 | AI Super User → AI Operator | [五格組一個 AI task pack](walkthroughs/build-an-ai-task-pack.md) | 不用把全部 Drive／Vault 畀它讀。 |
| 想交一件重複工作畀 AI，但仍然想自己控制 | AI Operator → AI Builder | [先畫 work map](chapters/3-6-work-map-before-workflow.md) | 不用先開 multi-agent。 |
| 想真的 build 第一個 AI 幫手 | AI Builder | [先寫一張可驗收 AI work card](chapters/4-20-ai-work-card.md) | 不用先做 autonomous agent team。 |
| 想知道一個 Agent demo 有冇價值、值唔值得推廣 | AI Value Creator | [Demo、pilot 和 proof](chapters/5-7-demo-versus-value.md) | 不用一開始承諾 ROI、節省人手或全面自動化。 |

## 五段 Agent 成長路線

### 1. AI User：先試一件安全工作

你未需要「有 Agent」。先學清楚：AI 不只是答問題，它可以按你提供的材料交一份可 review 的 draft。

**完成證明：** 你能指出它幫你完成了哪件工作、你檢查了甚麼、哪裡仍要改。

- [由問 AI 到交工作](chapters/2-1-from-answers-to-real-work.md)
- [術語不是考試](chapters/1-1-vocabulary-before-workflow.md)
- [先分清材料、判斷、未知和假設](chapters/2-8-evidence-before-generation.md)

### 2. AI Super User：畀 Agent 足夠但不過量的 context

AI 每次做得唔穩，未必是模型不夠強；可能它不知道目標、來源、好例子、限制和未知位。

**完成證明：** 下一次處理同類工作，你不必重新講全部背景。

- [Context 不是長 prompt](chapters/2-2-context-compounding.md)
- [五格組一個 AI task pack](walkthroughs/build-an-ai-task-pack.md)
- [令下一稿真改善的 review loop](chapters/2-11-review-loop-next-draft.md)

### 3. AI Operator：令 Agent 有現況、review 和交接

呢一關唔係「畀 AI 更多自由」。係令一條重複工作有 input、現況、owner、review 和 handoff；人或 AI 都不需要靠上次整段 chat 猜。

**完成證明：** 新 owner 可以找到現行資料、知道下一步、知道何時應停。

- [先畫 work map](chapters/3-6-work-map-before-workflow.md)
- [用 current-state note 留下現行判斷](chapters/3-12-current-state-not-chat-history.md)
- [人的價值上移到控制層](chapters/3-4-control-layer.md)
- [怎樣為新同事或 AI 寫 onboarding pack](chapters/3-8-project-onboarding-pack.md)

### 4. AI Builder：Build 一個受控制的 AI 工作單位

到呢一關，先講 Agent、Skill、loop、automation。目標不是令 AI 很自主；目標是一個 AI 幫手可以讀指定材料、交指定 artifact、過指定檢查、遇到例外會停。

**完成證明：** 有一張 work card；清楚 input、artifact、review／stop；出錯可找到、可修正、可回復。

- [呢條 routine 係咪 ready to build？](chapters/4-12-ready-to-build.md)
- [先寫一張可驗收 AI work card](chapters/4-20-ai-work-card.md)
- [跟住填第一張 work card](walkthroughs/write-an-ai-work-card.md)
- [Skill 是品質閘](chapters/4-6-skill-is-quality-gate.md)
- [安全試第一條 bounded agent loop](chapters/4-7-first-bounded-agent-loop.md)

### 5. AI Value Creator：將 Agent 接入真 workflow，再看價值

一個 Agent 交到 output，不等於它創造了價值。要看它是否被真 workflow 採用、有 owner、有安全界線，以及能否比較 rework、cycle time、漏項或其他合適證據。

**完成證明：** owner 能根據 evidence 決定 retain、revise、scale 或 stop。

- [AI transformation 不只是 access](chapters/5-1-governance-not-access.md)
- [設計 adoption pilot](chapters/5-6-design-adoption-pilot.md)
- [Demo、pilot 和 proof](chapters/5-7-demo-versus-value.md)
- [最小治理與量度](chapters/5-8-govern-and-measure-pilot.md)

## Agent 專題攻略：按你想解決的問題讀

| 專題 | 先問自己甚麼 | 主要 Stage | 攻略入口 |
|---|---|---|---|
| Agent 可否幫我？ | 這件工作低風險、我看得懂、可 review 嗎？ | User → Super User | [第一件真工作](chapters/2-1-from-answers-to-real-work.md) |
| Agent 應該讀甚麼？ | 有沒有剛好夠用的材料、例子和限制？ | Super User → Operator | [AI task pack](walkthroughs/build-an-ai-task-pack.md) |
| Agent 可否接手？ | 工作已畫清楚嗎？有 owner 和現況嗎？ | Operator | [Work map](chapters/3-6-work-map-before-workflow.md) |
| Agent 做甚麼工作？ | 它替誰交甚麼 artifact？ | Builder | [AI work card](chapters/4-20-ai-work-card.md) |
| Agent 應否變 Skill／automation？ | 做法夠穩、風險夠低、驗收夠清嗎？ | Builder | [Prompt、Skill、automation 的選擇](chapters/4-8-prompt-skill-automation-decision.md) |
| Agent 可以做到邊？ | 它可讀、可建議、可寫 draft、可送出到哪一步？ | Operator → Builder | [Workbench contract](chapters/4-19-workbench-contract.md) |
| 要一個 Agent 還是多個？ | context、權限、artifact、驗收真的不同嗎？ | Builder | [Loop 還是 specialist](chapters/4-13-loop-or-specialist.md) |
| Agent 出錯怎算？ | 我是否找得到錯、修得到、回得去？ | Builder | [最小 regression pack](chapters/4-10-minimum-regression-pack.md) |
| Agent 是 demo 還是有用？ | 有沒有真 artifact、owner、限制和 evidence？ | Builder → Value Creator | [Evidence loop](chapters/4-9-evidence-loop.md) |
| Agent 值唔值得擴大？ | workflow 有沒有改善？風險及治理是否跟得上？ | Value Creator | [擴大或停止](chapters/5-9-scale-or-stop.md) |

## 一個安全例子：活動資料 follow-up assistant

假設團隊每次活動後，都要根據**已批准**的活動 brief 和 FAQ 整一份 internal follow-up draft。

```text
AI User：先叫 AI 用兩份批准資料整一稿，自己對照原文 review。
AI Super User：加上目標受眾、語氣示例、不可寫的內容和輸出格式。
AI Operator：指定 current brief、owner、review queue 和遇到缺資料時的 handoff。
AI Builder：寫成 work card／Skill；只准產生 internal draft，不能直接外發。
AI Value Creator：比較可 review 前所需時間、漏項和 rework；再決定 retain、改進或停止。
```

呢個唔係客戶案例，亦唔代表已上線。它只是展示：同一個 Agent 題目，會隨責任增加而在不同 Stage 有不同做法。

---

← [按問題瀏覽](BROWSE.md) · [查看成長路線](CURRENT-JOURNEY.md)
