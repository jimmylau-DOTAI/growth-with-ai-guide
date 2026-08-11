# 由 AI Builder 走到服務，不是把一個 demo 拿去賣

你用 AI 做出一個很好的 demo：它可以整理資料、起草內容、做一個小工具，或者讓一條工作快很多。很自然會開始想：「這件事可不可以幫別人做？可不可以變成服務？」這個想法沒有錯，但自己用得順的 demo，和別人願意付錢、敢交給你、之後仍能維護的服務，中間差了很多工作。

自己做 demo 時，許多東西不必說出口：你知道資料在哪裏、哪些地方不可靠、甚麼時候應該停、結果不對便自己改。當另一個人找你幫忙，這些隱性判斷必須變成清楚的範圍、交付、review、責任與例外處理；否則服務很容易變成無限量人手救火。

Jimmy 的看法是：客戶不是買你用哪個 AI 工具；他買的是一個範圍清楚、有人負責、看得到交付，也知道出問題怎樣處理的結果。Builder 走向服務的第一步不是把 Agent 命名或做一個很大的 AI OS，而是把一條已跑過的 workflow 寫成可管理、可驗收的承諾。

AI 實戰 · AI Value Creator · AI service · workflow productization · scope · artifact · owner · evidence

| 從 demo 變服務的一格 | 要回答甚麼 | 留下甚麼 |
|---|---|---|
| 真工作問題 | 對方反覆遇到甚麼摩擦？ | 可描述的 workflow pain |
| Bounded offer | 今次只處理哪一手？ | scope 與 out-of-scope |
| Approved input | 對方要提供甚麼、不可提供甚麼？ | input boundary |
| Artifact | 客戶實際收到甚麼？ | 診斷、draft、工作卡或 receipt |
| Review／approval | 誰判斷可用、怎樣修正？ | owner 與 acceptance |
| Evidence／next step | 何時保留、改良、擴大或停止？ | outcome 與 decision |

## 自己做得到與對外交付得到有咩分別：隱性判斷要變成明確契約

自己用一條 AI workflow 時，你通常了解所有背景：知道哪份資料是 current、知道有些內容不可靠、也知道哪個結果只是參考。這些判斷在你腦內可以很快完成；但對外服務時，客戶看不見，也不能假設會做同樣的補救。若你不把它們寫出來，客戶會以為 AI 可以處理比實際更多的事。

服務交付還多了責任問題：對方要提供甚麼資料？誰核對結果？資料變了誰更新？系統不如預期誰處理？哪些決定仍需客戶 owner？這些不是額外行政，而是令服務可維護、可被信任的核心。沒有它們，你只是在展示自己的能力，還未提供一份可以負責的 offer。

**Jimmy 的結論：** 「我做得到」證明你有能力；「我交付得到」代表別人能理解範圍、驗收成果、處理例外。由 Builder 走向服務，要先把隱性判斷變成可見契約。

| 自己做 demo 時 | 對外服務必須說清 | 否則會發生甚麼 |
|---|---|---|
| 自己知道資料在哪 | 客戶提供哪些 approved input | 資料缺失／範圍爭議 |
| 自己會判斷 output | 誰按甚麼標準 review | 客戶以為已可直接用 |
| 自己會手動補救 | exception 與 support 邊界 | 無限量修改與救火 |
| 自己知道何時停 | stop line 與 approval | AI 被誤用或越權 |
| 自己能承擔風險 | 客戶／服務方各自 owner | 責任不清 |

當你能把這些寫成一頁服務工作卡，客戶會更容易理解買到甚麼，也更容易信任那些暫時不在承諾內的事情。

## AI service 最小單位怎樣定：不賣「轉型」，先賣一個可管理承諾

不要一開始賣「幫你做 AI transformation」或「替你建立 AI 團隊」。這些說法太大，會把不同流程、資料、owner、風險和期待全混在一起。更誠實的起點是一個小而清楚的承諾：對方有哪個真工作問題、今次只處理哪一段、用甚麼已批准 input、交哪一份可檢查 artifact、由誰 review，然後在何時決定下一步。

例如對方每週要把幾個公開來源整理成 internal decision brief。你提供的未必是「全自動 research agent」，而是協助定義來源範圍、起可 review 的 briefing draft、建立檢查方法，並用幾輪結果判斷這條流程值不值得擴大。這種說法不誇張，但客戶能清楚看見自己買到甚麼。

**Jimmy 的結論：** 服務的最小單位不是工具或 Agent，而是一個可管理的工作承諾。範圍愈清楚，交付愈可信，也愈容易在客戶真工作裡開始。

| 太大的 offer | 改成可管理承諾 | 可驗收交付 |
|---|---|---|
| 「幫你 AI transformation」 | 診斷一條重複 workflow | workflow diagnosis card |
| 「建立 AI team」 | 設計一個 draft-only pilot | pilot canvas 加 control card |
| 「自動化 research」 | 公開來源變 internal brief | source／unknown brief |
| 「提升全公司效率」 | 比較一條流程的 review 時間與 rework | outcome receipt |
| 「AI OS 顧問」 | 建一張 AI work card 與 review rule | work card／run receipt |

小 offer 不代表價值小。它讓服務方與客戶可以共同學習，避免把未驗證的能力、ROI 或權限在第一天就賣出去。

## Input、artifact、review 與 scope 怎樣變成服務設計：客戶買的是可被收貨的結果

一個好的服務設計先列 input：客戶提供哪些已批准資料、哪些資料暫時不收、資料不足時怎樣處理。接著定 artifact：是診斷、template、internal draft、workflow map，還是 review receipt？這些交付要讓客戶打開後理解今次做了甚麼，而不是只收到一段聊天內容。

review 與 scope 同樣重要。誰可以判斷結果可用？服務方提供的是建議、草稿、設計還是可以直接執行的變更？哪些事情仍需客戶 owner 提供資訊或作決定？把 out-of-scope 寫清，不是推卸責任，而是保護雙方不將一個小 pilot 誤解成無限服務。

**Jimmy 的結論：** 客戶真正買的是一個可收貨的 artifact 和可預期的工作方式。input、review 和 scope 清楚，AI 服務才不會被工具熱潮拉成模糊承諾。

| 服務設計格 | 你要寫甚麼 | 一個安全例子 |
|---|---|---|
| Input | 客戶只提供哪些材料 | 已批准公開／內部 brief |
| Artifact | 今次可檢查交付 | 一頁 workflow diagnosis |
| Review | 誰按甚麼接受或退回 | 客戶 content owner |
| In scope | 服務方只做哪一手 | 起 internal draft 與 checklist |
| Out of scope | 暫時不做甚麼 | 不直接外發、不接 production |
| Exception | 資料不足／風險時怎樣做 | 標 unknown，交 owner |

第一個服務不應要求客戶一開始交全部 vault、CRM 或敏感資料。先用最小、安全 input 證明工作設計，才有資格討論下一個範圍。

## AI workflow 何時值得產品化：問題重複、交付穩定、責任有邊界

產品化不是因為一條 workflow 很新或很潮，而是它開始有三個穩定訊號。第一，工作問題真的重複出現，不是只有你一個人的偶然情況；第二，交付可以講清楚，例如一份診斷、一套工作包、一張可驗收 work card，或一段有 owner 的 pilot；第三，責任有邊界，知道甚麼是服務方可控制的設計，甚麼必須由客戶提供資料或作決定。

這些訊號不要求你已經有一個 SaaS 或完整自動化。它們要求的是你可以誠實地重複交付同一種價值，並在例外出現時不需要每次從零猜。當同一類客戶都遇到相同 workflow 摩擦、都能理解相近 artifact、都能用相近 review rule，服務才有產品化基礎。

**Jimmy 的結論：** 產品化不是把工作變得冷冰冰；是讓你和對方都知道甚麼叫完成，甚麼還要共同處理。重複問題、清楚交付、責任邊界，是比工具新穎更重要的產品化 evidence。

| 產品化訊號 | 你可以怎樣驗證 | 尚未成立時怎樣做 |
|---|---|---|
| 問題重複 | 不同人是否反覆遇到同一摩擦 | 先當一次性服務 |
| 交付穩定 | artifact 是否可用同一格式說明 | 繼續整理 template |
| Review 可重複 | owner 是否用相近 rule 收貨 | 補 rubric／acceptance |
| 例外可處理 | 是否能分類 input、scope、risk 問題 | 寫 stop／escalation |
| 邊界清楚 | 客戶與服務方責任可否分開 | 不急著擴大 offer |

若你還要每次靠自己腦內補十種例外，代表 workflow 很有學習價值，但暫未適合被承諾成可重複服務。

## 未量度的效果點解不可預先賣：先賣「減少未知」，再賣擴大結果

AI 很容易令人想先講節省多少時間、做到多少自動化、帶來多少收入。這些可能是未來值得量度的東西，但在一條新 workflow 未跑過之前，仍然只是假設。若服務方先把假設當保證，客戶期待會超過目前 evidence，也會令雙方在第一個例外出現時失去信任。

第一個服務更應該賣「減少未知」：找出哪條工作值得先試、定好 approval、留下 artifact 和 review record，讓下一輪判斷是否真的有價值。這不會令 offer 變弱，反而令你比只賣工具清單的人更可信；你承諾的是一個可驗收方式，而不是 AI 會解決所有問題。

**Jimmy 的結論：** outcome 是用 pilot 證明的，不是用 pitch 承諾的。先讓客戶看見 workflow 變得可用、可控和可改善，再用 evidence 討論是否值得投資更多。

| 早期很想說的話 | 為何太早 | 較誠實的承諾 |
|---|---|---|
| 「一定省 X 小時」 | 未跑過不同 input 與 review | 比較可 review 前時間與 rework |
| 「幫你全自動化」 | 權限、例外、owner 未定 | 先交 draft-only pilot |
| 「一定提升收入」 | 商業結果受多個因素影響 | 找 workflow outcome evidence |
| 「AI 會替你做晒」 | 客戶仍需資料與決定 | 定雙方 owner 與 handoff |
| 「一做就可 scale」 | 未有 repeatability／rollback | 先跑 bounded scope |

在公開 portfolio 或提案裡，同樣不要把未驗證結果寫成既有客戶成效。展示工作方法、artifact 和 evidence boundary，通常更能建立長期信任。

## 一個公開安全例子：把公開來源 decision brief 變成第一個 service pilot

假設某類團隊每週要把幾個公開來源整理成 internal decision brief。服務方可以先提供一個 workflow diagnosis：了解現時來源在哪、哪一步最常重做、誰最終需要 brief。第一個範圍只限已批准公開來源與 internal draft，不接客戶資料、不對外發送，也不改任何 production 系統。

交付可以包括一張 source boundary、固定 brief template、review checklist 和三次小 run 的 outcome receipt。客戶 owner 對照原文 review，服務方協助看退回原因是 input、format、quality rule 還是工作手法。三次後大家才 decide retain、revise、stop 或小幅擴大。

**Jimmy 的結論：** 這個例子不是賣「全自動 research agent」，而是交一段可驗收、可學習的 workflow service。客戶買到的是清楚的下一步，不是一個未被證明的承諾。

| 服務格 | 例子中的內容 | 邊界 |
|---|---|---|
| 問題 | 公開來源整合反覆重做 | 不承諾全公司轉型 |
| Input | 已批准公開來源 | 不收客戶／私人資料 |
| Artifact | brief template、draft、receipt | internal review only |
| Review | 客戶 owner 對照來源 | AI 不自行批准 |
| Evidence | 時間、rework、未知 | 不預先宣稱 ROI |
| Decision | 三次 run 後取捨 | 可 retain、revise、stop |

這是公開安全的 synthetic service scenario，不代表任何特定客戶已有相同結果，也不授權服務方或 AI 處理 credentials、CRM、對外發送、公開設定或 production action。

## 今日怎樣把自己的一條 workflow 變成 service card：先寫為誰、解甚麼、交甚麼、怎樣停

選一條你自己已跑過、而且能解釋 input、artifact、review 與例外的低風險 workflow。先不要把它叫 AI OS，也不要急著承諾 ROI；用一張 service card 寫下：為誰解甚麼重複問題、今次只處理哪一手、對方要提供甚麼、安全邊界是甚麼、交甚麼 artifact、誰 review、何時 decide 下一步。

如果其中一格答不到，代表你仍在 Builder 的學習期，這沒有問題。先繼續在自己或公開 synthetic 場景跑出 evidence；當問題、交付和責任越來越穩定，服務自然會變得可討論。這樣走向顧問或教育工作，會比先賣一個很大的承諾更可靠。

**Jimmy 的結論：** 由 AI Builder 走到服務，不是把一個 demo 拿去賣；是把一條已跑過的 workflow 變成別人能理解、能驗收、能共同維護的工作承諾。

| Service card | 你要寫甚麼 | 安全起點 |
|---|---|---|
| 為誰 | 哪類工作者有同一摩擦 | 需要公開資料 brief 的團隊 |
| 問題 | 真正重複 pain | 來源分散、review 重做 |
| 範圍 | 今次只做哪一手 | internal draft workflow |
| Artifact | 客戶可收甚麼 | template、draft、receipt |
| Review／stop | 誰收貨、何時停 | client owner、缺 evidence 即停 |
| Evidence／decision | 怎樣看下一步 | 三次 outcome 後取捨 |

未有清楚 service card、client owner 和安全邊界前，不要將 AI 接到客戶資料、外部發送、公開設定或 production。下一步可看 [如何展示你的 AI work，而不是只展示工具](./5-15-show-your-ai-work.md)。

> 客戶不是買你用哪個 AI 工具；他買的是一個範圍清楚、有人負責、看得到交付，也知道出問題怎樣處理的結果。

← [返回 AI Value Creator](../README.md) · [按問題瀏覽](../../../README.md)
