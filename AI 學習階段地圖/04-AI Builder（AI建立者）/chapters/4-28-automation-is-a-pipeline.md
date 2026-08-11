# 自動化不是 prompt 串連：它是一條有例外處理的 pipeline

把 prompt 接到表格、再接到另一個工具，很容易令人覺得已經完成自動化。真正開始運作後才發現：輸入少了一格、資料格式變了、AI 不確定卻照樣往下走，最後沒有人知道錯誤在哪一站發生，也無人知道應否重跑。

問題不是工具串得不夠多，而是每一站沒有說清接甚麼、交甚麼、誰負責、遇到甚麼不准繼續。自動化可以減少搬運，但它不會自動創造工作定義、資料權限或驗收責任；缺了這些，只是更快傳遞混亂。

Jimmy 的判斷是：可靠 automation 是一條有 trigger、approved input、規則與 AI 分工、artifact、check、exception 和 owner 的 pipeline。它的目標不是「自己跑晒」，而是每一站都知道何時可交接、何時應停。

| Pipeline 格 | 要回答甚麼 | 留下甚麼 |
|---|---|---|
| Trigger／input | 何時開始、只接哪份資料 | approved input |
| Rules／AI | 哪些固定、哪些需判斷 | 可解釋處理 |
| Artifact／check | 交甚麼、怎樣過關 | 可 review output |
| Exception／owner | 出錯怎樣停、誰決定 | 可管理例外 |

## AI automation pipeline 為甚麼不是把幾個 prompt 串在一起？

Prompt 串連只說每個工具大概做甚麼，沒有說資料何時可信、站與站之間交接什麼、失敗是否可見。當第一站 output 少欄、格式改變或不確定，下一站仍可能把它當成完成資料，錯誤一路被包裝得更完整。

Pipeline 則把工作拆成有契約的站：每站有 input、action、artifact 和 check；不能過關就走 exception，不把未知靜靜交到下一站。這讓你不用猜「AI 今日為何怪」，而能指出是哪一站、哪條條件需要修。

**Jimmy 的結論：** 自動化不是讓事情自己跑；是讓每一站知道接甚麼、交甚麼、何時不能再跑。

```text
trigger → approved input → rule / AI action → artifact → check
                                                   ├→ pass → next approved step
                                                   └→ exception → owner / stop
```

少了 exception 的自動化，不是更流暢；它只是令錯誤更難被定位。

## AI pipeline 哪些工作應交規則，哪些才交給 AI 判斷？

固定格式、欄位有沒有齊、來源是否存在、日期是否有效，通常應由明確規則檢查。它們不需要 AI 發揮創意，反而需要穩定可重複。把這些交給 AI 猜，會令同一個可驗證錯不斷重演。

理解語氣、比較角度、從模糊材料整理可 review draft，才是 AI 較適合參與的地方；但 AI 的結果仍必須交 artifact、露出 unknown，並由人處理最終判斷。不要把「AI 可以處理模糊」誤解成它可自行決定責任與後果。

**Jimmy 的結論：** 規則守住已知條件；AI 處理需要語言與判斷的受限工作；權限、承諾和不可逆 action 永遠留在人手位。

| 工作類型 | 放在哪一層 |
|---|---|
| 欄位、格式、來源存在 | 固定 rule／check |
| 摘要、分類、internal draft | AI action＋review |
| 對外發送、正式寫入、敏感決定 | owner approval／stop |

分工一清楚，AI 失誤就不會被錯當成「所有自動化都失敗」，而是能回到正確一層修。

## AI pipeline 第一輪應選甚麼，才可安全驗證 exception？

第一條 pipeline 不要接 CRM、付款、正式發送或 production data。選一段用公開／synthetic input 就能跑的低風險工作，例如把指定公開材料變成 internal brief。你要驗證的是：unknown 有沒有被標出、資料不齊時是否停下、reviewer 能否根據 artifact 作決定。

此時資料格式改變、來源缺失或 AI 不確定，都不是失敗；它們正是你要看到的 exception。若第一輪從未遇過例外便急著接真系統，將來才出事時你仍不知道是 retry、改 rule、問 owner 還是停止。

**Jimmy 的結論：** 第一個 pipeline 的成功不是完全自動，而是它第一次遇到資料不足或格式錯時，仍知道怎樣留下 exception 並交回人。

| 第一輪設計 | 安全做法 |
|---|---|
| Input | 指定公開 URL／synthetic table |
| Artifact | sources、重點、unknown、下一步的 internal brief |
| Check | 欄位齊、來源可回查、unknown 可見 |
| Exception | 缺來源／格式錯即 stop，交 owner |
| 不可做 | 外發、CRM 寫入、付款、production deploy |

你不是在測試 AI 有多神奇，而是在測試自己設計的工作管道會不會在錯誤出現時仍可管理。

## AI pipeline 的 exception、retry 和 stop rule 應怎樣分？

不是所有錯都應 retry。欄位偶爾缺失、來源暫時不可讀，可能可以重試一次或要求補資料；但權限不清、資料敏感、對外承諾、核心 evidence 衝突時，retry 只會更快把不應做的事做下去。這些必須 stop 並交 owner。

Exception rule 要讓下一位人看得出為何停：哪一站失敗、input 是甚麼、已試甚麼、需要誰決定。這比一句「automation failed」有用，因為它直接把例外變成可處理的工作，而不是一個無人理解的技術訊號。

**Jimmy 的結論：** Retry 處理暫時、可驗證的技術缺口；stop 處理權限、證據與責任缺口，兩者不能混。

| 看到的例外 | 正確下一步 |
|---|---|
| 指定公開 URL 暫時讀不到 | 記錄後有限 retry 或改人工補 input |
| 固定欄位缺失 | stop 這一輪，要求補欄位 |
| source 衝突／核心事實未證實 | 標 unknown，owner／research 決定 |
| 要寫正式系統／外發 | 必須 human approval，不自動 retry |

每條 exception 最少留下 input、失敗站、已做 check、下一步 owner。這就是 pipeline 能被人真正接手的原因。

## 自動化跑完後，怎樣用 artifact 和 receipt 判斷是否值得擴大？

不要只量它跑得多快。先看 artifact 是否真能幫 owner 作決定、check 是否抓到已知錯、exception 是否正確停下、reviewer 是否不用靠 chat 猜發生甚麼。這些 evidence 證明 pipeline 有沒有真的減少人手搬運，同時沒有把人手判斷藏起來。

同類 internal run 重複幾次、input、output、exception 與 review 都穩定後，才考慮增加資料來源、connector 或下一個 action。若每輪仍有不同 owner、不同未知、不同成果要求，保留 work card 和 human review 比硬接 automation 更成熟。

**Jimmy 的結論：** Pipeline 的完成線不是它能自動跑；而是每次跑完都留下足夠 evidence，讓人決定 keep、revise、stop 或才值得擴大。

| 你下一個卡位 | 接著讀甚麼 |
|---|---|
| 想把固定條件寫成 quality gate | [固定規則與 AI 判斷分工](./4-17-rules-versus-judgment.md) |
| AI 同類錯不斷重演 | [Agent reliability loop](./4-24-agent-reliability-needs-a-loop.md) |
| 想安全跑第一個工作單位 | [先跑一條可停的 Agent loop](./4-25-first-agent-loop.md) |

可返回 [AI Builder stage](../README.md)。本文只用公開／synthetic 情境，不構成資料存取、系統寫入、外發或 production action 的批准。
