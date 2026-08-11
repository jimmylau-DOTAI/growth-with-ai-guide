# 第一條 AI Agent loop 唔使證明它很自主：先證明它交得出可驗收成果

想開始用 Agent 或 automation 時，最誘人的畫面往往是「每天自動做完一件事」：自動寫內容、自動整理 lead、自動回覆、甚至自動更新系統。但 schedule 和工具連線解決不了真正困難的部分：input 是否清楚、資料可否讀、output 有沒有人敢收、出了錯能否停、下一步是否會影響客戶、正本或外部世界。

第一次就把 email、CRM、付款、發佈或 production action 交出去，通常學不到最重要的東西。只要結果不好，你很難判斷問題是資料、prompt、工具、權限、review 還是 workflow 本身；而且錯誤已可能跨過可回退邊界。真正值得先驗證的，並不是 Agent 有多自主，而是它能否在清楚範圍內交出一份人敢驗收的 artifact。

Jimmy 的判斷是：第一條 Agent loop 應該是 bounded loop——選一件重複、低風險、可回退的 routine，限制它只讀最小 input、只交 draft、經過 named review，再把 gap 留成下一輪規則。這樣你買到的是清楚 evidence：它在哪些條件下可靠、哪一格要修、何時不應擴大，而不是一個看起來很自動的標籤。

| Bounded loop 的一格 | 它要避免甚麼 | 完成後留下甚麼 |
| --- | --- | --- |
| Routine choice | 一開始揀高風險、太大的工作 | 一個重複、低風險、可驗收單位 |
| Input boundary | AI 讀太多、讀錯或碰敏感資料 | 指定公開／已批准／synthetic input |
| Bounded action | Agent 順手擴大、外發或改正本 | Draft-only 的明確輸出 |
| Check + review | AI 說完成但人不知怎樣收貨 | Checklist、reviewer、pass／revise／stop |
| Receipt + next loop | 每輪失敗都由零開始 | Gap、版本、未做 action、下次改一格 |

## 第一條 AI Agent loop，為甚麼不應該由「每日自動做完某件事」開始？

每日自動做完一件事聽起來很有效率，但它假設了幾件未必成立的事：每天的 input 都一樣清楚、output 有固定完成線、系統知道例外、每次都有合適 reviewer、以及自動 action 錯了仍能回退。對剛開始的人來說，這些假設大多還未被驗證；一個 schedule 只會讓未解的問題更頻繁地發生。

尤其當工作接到真實資料或對外 action，第一輪的錯誤成本很高。自動發一篇不準確內容、把資料寫錯 CRM、在錯誤時間寄 email，並不因為「AI 幫手」而變得容易收回。你需要先在 draft 層看清 AI 怎樣讀資料、怎樣處理未知、怎樣被人驗收，才有資格討論是否值得加頻率或權限。

**Jimmy 的結論：** 第一條 loop 的目的不是證明 AI 可以一直自己跑，而是證明它在有限範圍內能穩定交出一個可驗收、可回退的工作結果。自動化是後面的選擇，不是第一輪成功標準。

可用這張對照避免太早跳步：

| 一開始想做的事 | 為何太早 | 更好的第一輪版本 |
| --- | --- | --- |
| 每天自動發社交內容 | 主張、品牌、發佈責任未驗證 | 只起一份有 evidence 的 content draft |
| 自動同步 CRM | 資料正確性、欄位、回退未驗證 | 用 sample schema 產生變更預覽 |
| 自動回覆客戶 | 語境、承諾、私隱風險高 | 用公開／synthetic 情境起 internal response draft |
| 自動整理所有公司資料 | context 太廣、來源不可信 | 只整理 3 篇指定公開文章成 briefing |
| 做 autonomous agent team | 角色、handoff、review 未成熟 | 先跑一條單 agent bounded loop |

先讓一件小工作被安全收貨，通常比展示十個自動化圖更快帶來真正的學習。

## 甚麼工作適合做第一條 bounded Agent loop，甚麼工作應暫時避開？

適合第一條 loop 的工作通常有三個特徵：它真的會重複、錯了影響低、完成後有一個人可以看得懂並驗收的 artifact。它不必很簡單，但要能被切到一段清楚工作，例如指定資料整理、固定欄位 brief、sample 文件格式檢查、課程 FAQ 候選分組。這些工作能讓你測到 input、step、check、exception 和 review，而不需要一開始處理高責任 action。

不適合的工作則通常混合了太多未知：未經審核的客戶承諾、報價／合約、付款、真實 CRM 寫入、外部發佈、production deployment，或一句「幫我改善所有東西」。它們不是永遠不能用 AI，而是要先用 human runbook、assumption ledger、working copy 和 draft 分開風險，否則你無法知道第一輪問題在哪裡。

**Jimmy 的結論：** 第一條 Agent loop 應讓你看見真實例外，又不會讓一次錯誤變成真實損失。選「重複、低風險、可驗收」的工作，而不是「最重要、最令人興奮」的工作。

| 適合第一條 | 暫時避開 |
| --- | --- |
| 已指定公開文章的 internal brief | 客戶 email／承諾／報價／合約 |
| Sample 資料按 schema 的整理／分類 | CRM、付款、權限或 production write |
| 已批准材料的 FAQ／outline draft | 未 review 的品牌對外發佈 |
| Local working copy 的小型可回退改動 | 未測試 code deployment |
| 固定格式的 quality check receipt | 「自動幫我改善全部 business」 |

若一件工作屬於右邊，先拆其中一小段變成 draft-only task，或暫時保留在人手流程裏。

## Bounded loop 的 input boundary 怎樣設，才不會一開始就接錯資料？

Agent 想幫得好，很自然會被要求讀更多 context。但第一條 loop 的目標不是證明它能搜遍所有資料，而是證明它能在一組清楚材料下做對一個小工作。若你一開始讓它讀整個 vault、email、CRM 或歷史資料夾，任何錯誤都難以追查：它究竟依據哪一份？舊資料有沒有混進來？敏感資料是否不必要地被暴露？

最小 input boundary 應該列明：本輪只讀哪些 URL、檔案、欄位或 synthetic records；哪些資料明確不可讀；資料缺失時要交哪份 receipt。公開／已批准材料和本機 sample 特別適合第一輪，因為它們既能測工作形狀，又不會把客戶、合約、付款、credentials 或未公開策略帶進試跑。

**Jimmy 的結論：** Bounded loop 的「聰明」不在於看最多，而在於它只看完成這輪工作真正需要的材料，並在缺資料時誠實地停下，而不是用更多 context 掩蓋不清楚的流程。

開始前填這張 input card：

| 項目 | 要定義甚麼 |
| --- | --- |
| Allowed input | 指定 URL、檔案、schema、sample 或已批准 brief |
| Source of truth | 有衝突時以哪一份為準 |
| Not allowed | 客戶、CRM、付款、合約、credentials、private vault、未分類歷史資料 |
| Data shortage | 少了哪一項便要 `needs input`，不可自行找替代資料 |
| Input record | 本輪實際讀過甚麼，讓 reviewer 可回看 |

如果 input card 寫不出來，先不要啟動 Agent；這代表你仍在定義工作，而不是已準備好委派。

## Agent 在第一條 loop 裏應該只做甚麼 action，點樣避免 scope 一路變大？

AI Agent 很容易因為「想完成任務」而多做幾步：把 internal draft 改成對外內容、看到資料不足便上網補、發現一個相似問題便順手改其他檔案。對探索來說，主動性有時有用；對第一個 loop 來說，這會令你分不清 output 的品質來自哪個改動，也會把本來可回退的測試帶到更高風險。

bounded action 的做法是讓 Agent 只做一種明確轉換，並把 output 限在 draft／working copy／receipt。它可以分析、整理、分類、起草、預覽變更；但不自動發送、覆寫、付款、改權限、部署或擴大讀取。任何需要越過這條邊界的 action，都應該轉成 question／approval，而不是由 Agent 自行完成。

**Jimmy 的結論：** 第一條 loop 的完成線是「交出可 review 的 draft」，不是「直接改變外部世界」。限住 action 並非降低 AI 價值，而是令你可以明確看見它哪一部分真的可靠。

為 action 寫一個小合約：

1. AI 這次只處理哪一個轉換？例如「3 個 URL → briefing table」。
2. 它只可用哪些工具，結果只可寫到哪個 working copy？
3. Output 必須包含哪些欄位、unknown 或 evidence？
4. 任何資料不足、衝突、scope 增加時，它要留下甚麼狀態？
5. 它明確不能做甚麼：外發、寫正本、排程、付款、權限、部署？

這五句令 Agent 的主動性只在可驗收的盒子內發揮；盒子外的決定仍由 owner 負責。

## 第一個 Agent draft 應該怎樣驗收，才不會只靠「睇落 OK」？

如果 reviewer 只在最後憑感覺說「好似可以」，bounded loop 不會學到任何可重用的東西。你需要一張短 checklist，專門針對這個小工作最容易出錯的地方。它不需要是完美 rubric，三條能指出「不過關長甚麼樣」的標準已足夠令你比較不同 run。

例如研究 brief 的 reviewer 不必驗證所有世界知識，但可以看：每個事實是否有原始連結、資料不足是否被標 unknown、AI 有沒有超出指定 sources、output 是否按 schema 完成。這些檢查將「內容像不像」轉成可見 evidence；若有一條不過，便可以指向 input、step 或 rule，而不是只說 AI 不夠好。

**Jimmy 的結論：** Review 的目的不是找完所有錯，而是令你知道這份 draft 有沒有過本輪完成線、沒過的錯屬於哪一類、下一輪該改哪一格。

第一輪可用三條 checklist：

| Check | Reviewer 怎樣看 | 不過關時怎樣走 |
| --- | --- | --- |
| Evidence | 每個重點能回到指定來源／欄位 | 標 unknown 或 `needs input`，不補猜 |
| Scope | AI 沒有使用未批准資料、沒新增外部 action | Stop／收窄 action，保留 receipt |
| Artifact | 固定欄位齊、內容可讀、已列出未知 | `revise once`，交 diff／check 結果 |

若這三條都通過，代表本輪 draft 可以被 internal 採用或進下一個受控步驟；不代表它已可自動發佈或等於 workflow 全面成熟。

## Bounded loop 出現錯誤或資料不足時，下一輪應該修甚麼，甚麼時候應停止？

第一輪失敗不是壞事，它正好揭示 workflow 的缺口。關鍵是不要同時改 prompt、工具、資料、scope 和 checklist，否則下一次變好／變差都不知道真正原因。每次只把錯分類為 input、rule、artifact、judgment、工具或 scope 問題，然後只改最接近原因的一格，才會積累可用 evidence。

有些錯可以直接修：少了一個必填欄、格式不對、已知 schema 不過，可以 `revise once`。有些錯不能讓 AI 自己修：少原始資料要 `needs input`，兩個來源矛盾要 `needs approval`，工具中斷要 `failed safe`，任何外部 action 都留在 human release。停止不是放棄，而是避免 workflow 在錯條件下愈跑愈遠。

**Jimmy 的結論：** Bounded loop 的核心能力不是永遠成功，而是每次 gap 都能被正確路由：可修的修一次、缺資料的等人補、需判斷的交 owner、不可信的安全停下。

每輪完結留一張 gap receipt：

| 看見甚麼 | 本輪只改甚麼 | 下一輪不應做甚麼 |
| --- | --- | --- |
| 缺來源／資料 | 補 input card 或 source list | 不用猜測替代內容 |
| 格式／欄位錯 | 修 schema／check | 不順便重寫整個任務 |
| 讀者問題不對 | 修 brief／goal | 不只換幾個字再跑 |
| 要求變大／涉外部 action | 收窄 scope 或取得 approval | 不自動加權限或發送 |
| 工具／狀態中斷 | 留 failed-safe state | 不覆蓋舊版本一直 retry |

只要一輪只修一格，三次之後你便能開始看見哪個部分真的提升了可靠性。

## 第一次 bounded loop 完成後，甚麼 evidence 才值得讓你考慮擴大？

一輪順利跑完很鼓舞，但不應立刻接真實資料或自動發送。你首先要看到多次在相近、受控條件下的證據：AI 是否一直守住 input boundary、artifact 是否穩定通過 checklist、例外是否進了正確狀態、reviewer 是否不用從零重做、recovery receipt 是否真的能找回上次狀態。這些證據比一次漂亮 demo 更接近真實可靠性。

擴大也應一次只動一格。也許先增加一個 input 類型，或先從 synthetic 換到已批准 internal draft，或先增加頻率但仍不給外發權限。若同時改資料、工具、output、reviewer 和 release，出問題後便很難知道哪個變更帶來風險。保守不是慢，而是讓你有能力由 evidence 做決定。

**Jimmy 的結論：** 擴大 loop 的資格不是「它很自動」，而是「你已有足夠 receipt 證明它在哪些邊界內可靠、出錯時仍可管理」。每次只增加一份權限或一個變數，才能保持可學習。

可用這個擴大檢查：

1. 是否已至少多次通過同一份 acceptance，而不是只成功一次？
2. 是否真的出現過一兩種例外，並被正確停止／交接？
3. Reviewer 是否能快速讀 artifact，而不是重新做人手工作？
4. 有沒有清楚 owner、status 和 recovery receipt？
5. 下一步只準備增加哪一個變數，其他邊界是否保持不變？

若任何一條未答到，先再跑受控 draft。這不是拖延，而是避免把未知直接升級成 production risk。

## 想建立第一條 bounded Agent loop，最安全的開始是甚麼？

最安全的開始是選三篇已批准公開文章，讓 Agent 在一個受控資料夾交一張固定表：每篇重點、原始連結、可支持觀察、未知。人用 evidence、scope、artifact 三條 checklist review；沒有一項允許它自動發文、寫 CRM、改正本或讀私有 vault。這已足夠測到 Agent 是否能按清楚 context 做可驗收工作。

真正要留意的不是它一開始寫得多漂亮，而是它在資料不足、格式不合格或來源矛盾時做甚麼。只要它能留下正確 status 和 receipt，你便已經有一個可改善的第一條 loop；下一次再選一格——input、rule、artifact 或 review——慢慢優化。這比一開始建一隊 autonomous agents 更接近 AI Builder 的實力。

**Jimmy 的結論：** Build 第一條 loop 的目的，是買到清楚 evidence，不是買到「自動」標籤。先令 AI 安全地交一份 draft，才有根據令它日後承擔更多。

可以跟這六步開始：

1. 選一件重複、低風險、可驗收的 routine。
2. 寫清 allowed input、source of truth、不可碰範圍。
3. 限定 AI 只交一份 draft artifact 到 working copy。
4. 定三條 checklist 和 named reviewer；不收「AI 說完成」。
5. 寫 needs input、revise once、needs approval、failed safe 的停止／修正規則。
6. 用公開或 synthetic input 跑三次，保留 receipt，才考慮增加一個新變數。

暫時不要接 email、CRM、付款、客戶資料、公開發佈、正本覆寫或 production deployment；不要在第一輪同時換 prompt、工具、資料與 acceptance；亦不要將一次成功叫作 autonomous system。想先把工作範圍寫成更清楚 contract，可讀 [先寫一張 workbench contract](./4-19-workbench-contract.md)；要把例外寫成共同語言，可讀 [AI 一遇資料不足就繼續猜？Skill 要先寫好 exception ladder](./4-34-skill-exception-ladder.md)。

← [返回 AI Builder](../README.md) · [按問題瀏覽](../../../學習地圖.md)
