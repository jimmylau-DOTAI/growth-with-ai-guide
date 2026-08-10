# 唔好一開始砌 AI 團隊：先跑一條可停的 Agent loop

一聽到 AI Agent，很多人很快想像一間 AI 公司：研究員、寫手、reviewer、銷售、客服，各自有角色，再用很多工具把它們連起來。但角色愈多，愈容易說不清到底誰負責哪一段、錯了誰會發現、下一步誰能決定。

問題不在於多 agent 永遠不好，而是第一輪通常連一條可驗收工作也未跑過。沒有清楚 trigger、材料、artifact、check、state 和 stop line，多個角色只會把模糊工作傳得更快，dashboard 也不能證明任何事情已完成。

Jimmy 的判斷是：第一條 Agent loop 不需要像一間公司。它只需要把一段重複、低風險、可回退的工作安全跑完一次，交回可 review artifact 和 receipt；做不到時停回 owner，而不是自己擴大範圍。

| Loop 格 | 要解的問題 | 留下甚麼 |
|---|---|---|
| Trigger／context | 何時開始、只讀甚麼 | 安全 input |
| Skill／artifact | 只做哪一段、交甚麼 | 可 review output |
| Check／state | 怎樣驗收、目前在哪步 | receipt／status |
| Stop／owner | 何時停、誰決定 | human control |

## AI Agent loop 是甚麼，為甚麼一定要有回程？

Loop 不是「AI 可以自己做很多事」。它是一條有回程的工作路：某件事觸發、AI 讀指定 context、按一個工作規則交 artifact、經過 check 或 review，最後把狀態寫回來；若材料不足、權限不清或驗收未過，便停下來交回人。

很多 automation 只做了前半：定時讀資料、生成、寫回某處。少了 check、state 和 stop，錯誤會被定時製造但無人看見。Loop 的可靠性不在於走得多快，而在於任何一步都能回答「它現在在哪裡、根據甚麼、誰可以令它繼續」。

**Jimmy 的結論：** Loop 不在於步數，而在於它有回程：每次交 artifact 後能 check、留 state，遇到例外能回到 owner。

```text
trigger → approved context → bounded action → artifact
        → check / review → receipt / state → next run
                                  └→ exception → stop → owner decision
```

一條沒有回程的流程，不是較自主；它只是讓人更遲才發現它一直做錯。

## 第一條 AI Agent loop 應揀甚麼工作，才可以安全試跑？

第一次不要選需要對外承諾、讀私人資料或寫入正式系統的工作。你想學的是 loop 怎樣交接和停下，而不是一次過處理 CRM、付款、發送、部署或多人權限。範圍太大時，即使結果不好也很難知道該修 context、Skill、check 還是 ownership。

較好的起點是高頻、材料固定、成果可看、錯了可拒絕的一段工作。例如每週把三個公開來源整理成 internal research brief：AI 只讀指定 URL，交來源／重點／unknown／下一步四欄，editor review 後才決定是否使用。它不需要自行發文，更不需要接其他系統。

**Jimmy 的結論：** 好 first loop 是可重複、低風險、材料與成果可見、例外可停的一段工作；不是一個自行擴張的 AI 公司圖。

| 適合 first loop | 為甚麼 | 暫時不要做 |
|---|---|---|
| 公開來源 → internal brief | 可核對 source、欄位和 unknown | 外發、CRM 寫入、付款 |
| 已批准 outline → draft | 可 review 結構與 scope | 未批准 offer／承諾 |
| demo workspace 小檢查 | 可看 diff 和回退 | production deploy／核心資料改動 |

選到「錯了能停」的工作，你才會真的看到 stop line 是否有效，而不是只看一次漂亮 output。

## AI Agent loop 的 trigger、context、artifact 要怎樣寫，才不會自己愈做愈多？

Trigger 不是「每日自動跑」這麼簡單；它要說明甚麼條件出現才開始。Context 不是全部資料；它要限定本輪可讀的材料。Artifact 也不能只是「處理完成」；要指定交甚麼 draft、表格、queue 或 receipt，否則 AI 很容易把必要範圍外的事也當成自己要解決。

把三格寫清，才能把 Agent 的自主性限制在一個可驗收工作單位內。若來源缺失、task 未定或 output 不可 review，正確結果可以是 stop；不要用一個寬鬆 trigger 叫 AI 自己找更多資料、自己決定何時完成。

**Jimmy 的結論：** Trigger、context 和 artifact 是 loop 的工作邊界：它們決定何時開始、只憑甚麼做、最後交甚麼，而不是讓 AI 自行補完整條流程。

| 格 | 公開 briefing 例子 | 需要防甚麼 |
|---|---|---|
| Trigger | 指定三條公開 URL 已被加入本輪清單 | 看到任何網頁便自行 research |
| Context | 只讀 URL、欄位定義、已批准格式 | 讀私人筆記或未批准資料 |
| Artifact | 四欄 internal brief＋unknown＋receipt | 「完成」但無人可 review |

只要這三格有任何一格講不清，先回到 work card；不要以為加 connector 就能補足工作定義。

## AI Agent loop 的 check、state 和 stop line 怎樣保護下一次？

Check 要回答這一輪是否過了最小條件，例如每個重點能回到 source、unknown 是否可見、欄位是否完整；state 則保留今次 input、output、check 結果與現在位置。兩者讓下一輪不必靠 chat 記憶，也讓人能追查某個 output 為何出現。

Stop line 是可靠性最後一格：材料涉及私人資料、證據衝突、要對外承諾、需要權限或 reviewer 不在時，AI 不可用「合理假設」繼續。它應留下 exception 和 owner 問題，等待真正可決定的人處理。

**Jimmy 的結論：** check 防已知錯、state 讓工作可回看、stop line 把責任交回人；缺任何一格，loop 只是自動重複風險。

| Loop 結果 | 要留下甚麼 | 下一步 |
|---|---|---|
| Pass | artifact、check、receipt | owner 決定是否採用／下一輪 |
| Revise | 未過的 gate 和修正範圍 | 只重跑指定一段 |
| Stop | 缺口、原因、owner 問題 | 補條件，不自行繼續 |

這亦是為何第一輪只做 internal run：你要先證明 state 和 stop 在錯誤出現時真的有用，才談加速或擴大。

## 何時才需要拆多個 AI Agent，而不是保留一條 loop？

任務有很多步，不代表要拆很多角色。先問不同部分是否真的需要不同 context、權限或驗收方式；若都是同一批資料、同一個 owner、同一份 artifact 的小步驟，一條有清楚 Skill 的 loop 已足夠。過早拆分只會增加 handoff、成本和「到底誰做錯」的問題。

只有某段工作確實需要另一組已批准材料、獨立的 quality review，或不同的人有權決定時，才有理由成為 specialist。切分的依據不是公司組織圖，也不是要展示 multi-agent，而是每個 worker 的 context、authority、verification 已有真正邊界。

**Jimmy 的結論：** Agent 分工要按 context、權限和驗收切；三者沒有不同時，先把一條 loop 跑穩比開更多角色更有價值。

| 看到的情況 | 較好設計 |
|---|---|
| 同一資料、同一 owner、同一份 brief | 一條 loop＋一個 review gate |
| 另一段需不同批准資料／檢查 | 拆 specialist，但寫清 handoff artifact |
| 有多工具但無 owner／check | 先不叫 multi-agent，回到 work card |

多 agent 只應在單一 loop 的責任已清楚、但確實不足以安全處理不同工作邊界時才出現。

## 第一條 AI Agent loop 跑完後，怎樣決定是否值得再跑或擴大？

跑完後不要只問「有沒有慳時間」。先看 receipt：它有沒有只讀批准材料、artifact 是否真的可 review、check 有沒有抓到已知錯、unknown 是否有正確停下，owner 能否迅速決定 pass／revise／stop。這些比一次 output 的漂亮程度更能說明 loop 是否可管理。

若同類 low-risk run 已重複幾次、input、artifact、check 和 exception 穩定，才把它升成 Skill 或 bounded loop 候選；若每次都要臨時補 scope、換材料或找不同 owner，繼續保留 work card 和 human review。未穩之前擴到真資料或外部 action，只會放大你還未理解的例外。

**Jimmy 的結論：** 第一條 loop 的成功不是自動化程度；而是它證明一段工作能交清、驗到、停得住，並知道下一次應修哪一格。

| 你下一個卡位 | 接著讀甚麼 | 留下甚麼 |
|---|---|---|
| 想先判斷是否應 build | [五個 build gate](4-12-ready-to-build.md) | build decision |
| 想把工作變成可重跑 Skill | [Skill 是工作合約](4-23-skill-is-a-work-contract.md) | Skill candidate |
| 想加 quality check | [Agent reliability loop](4-24-agent-reliability-needs-a-loop.md) | rule、review、stop line |
| 想決定 loop／specialist | [Loop 還是 specialist](4-13-loop-or-specialist.md) | handoff boundary |

可返回 [AI Builder stage](../04-ai-builder.md) 看其他入口。例子只用公開／synthetic 情境；本文不構成資料存取、系統寫入、外發、部署或任何 production action 的批准。
