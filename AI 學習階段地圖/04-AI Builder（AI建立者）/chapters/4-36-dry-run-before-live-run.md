# 第一個 AI live run 唔係直接按掣：怎樣用 dry run 逐格證明一條 workflow 可交付？

一條 AI workflow 在測試材料上跑到一次，很容易令人想直接接上真資料、排程、發送或覆寫。畫面顯示完成、output 也生出來，彷彿只差把開關打開。但到了真正影響同事、客戶或公開內容的時候，才發現來源讀錯了、例外沒有停、owner 不知道看甚麼，或者一出錯根本找不到哪一版可以回退。

「第一次跑到」只證明某次執行沒有立即失敗；它沒有證明資料讀對、輸出可驗收、同一條規則多次仍成立、敏感 action 有人承擔，或工具中斷後工作可以繼續。若第一次真 run 已經同時接真資料、正本寫入和外部發送，任何一個小錯都會被放大成不必要的 production accident。

Jimmy 的判斷是：第一個 live run 的目標不是證明 AI 夠自動，而是證明人仍然管得到它。dry run 把 input、draft、quality check、human release 和 recovery 分開，讓你在每一格看到應留下甚麼證據、何時要停、誰有權決定下一步；能逐格過關，才有根據擴大。

| 由測試到 release 的一格 | 它要驗證甚麼 | 完成後留下甚麼 |
| --- | --- | --- |
| Sample input | 工具是否只讀到指定、可用的材料 | input list／範圍紀錄 |
| Draft artifact | AI 是否能交可 review 的中間結果 | 草稿、比較表或狀態 receipt |
| Check + exception | 遇到缺資料、錯格式、衝突時是否停對位置 | pass／revise／unknown／stop 結果 |
| Human release | 誰確認可採用、可否對外、應否停止 | approve／revise／stop decision |
| Recovery receipt | 出錯或改版時是否能追查與回退 | 版本、已做／未做 action、回退點 |

## AI workflow 跑到一次，為甚麼仍然未等於可以接真資料或自動發送？

測試成功往往只是在一組乾淨、理想、已預備的 input 下成功。真工作卻會有缺欄位、來源中斷、格式改變、命名不一致、有人臨時改方向，或 output 出現一個看似合理但其實未證實的結論。這些不是 edge case；它們正是 workflow 要能運作的日常情況。

同一條流程的外部後果也不同。讓 AI 在 sandbox 交一份 draft，錯了只需重跑；讓它把同一份內容寄給客戶、寫回 CRM、覆寫正本或發布到社交平台，錯了就牽涉信任、資料、時間和人手補救。工具能力一樣，責任設計卻完全不同。

**Jimmy 的結論：** 一次 output 出到不是 release 標準。你要先證明它在受控範圍內讀對、停對、交得出可 review artifact，並知道出錯後怎樣回退，才值得考慮多一格真實權限。

這張比較表可幫你分清楚：

| 看見甚麼 | 它真正證明甚麼 | 它仍未證明甚麼 |
| --- | --- | --- |
| AI 生出一份完整草稿 | 某次 input 可產生 output | 來源、事實、邊界和多次穩定性 |
| 你親眼看過一次結果 | 這一次有人介入 review | 下次換人後也會知道怎樣收貨 |
| 工具可連到另一個系統 | 技術連線可能可行 | 是否應授予讀取、寫入或發送權限 |
| 一輪順利完成 | 本次沒有明顯失敗 | 例外、回退、維護和 release 是否可管理 |

當你不再把「做得到」當成「可以放手」，dry run 才有位置幫你把真正的風險看清。

## Dry run 的 sample input 怎樣選，才可以測流程又不把真風險帶進來？

sample input 不是隨便找幾份資料試一試。太乾淨的 sample 只會讓 AI 看起來很可靠；太接近真實客戶或 production data 的 sample，則把你本來想避免的資料和責任提早帶進測試。好的 sample 要足夠像真工作，能測到格式、例外和 review，但又可以被安全地刪除、重跑和討論。

對內容、研究或 briefing 類 workflow，最穩的開始是已公開、已批准的文章或 synthetic 資料；對資料處理或產品流程，可以用最小化、去識別化的 sample 和 sandbox。重點不是模擬所有情況，而是讓你第一次已能驗證「AI 只讀這些 input」和「有問題時它不會偷補」。

**Jimmy 的結論：** Dry run 的 input 應該是「足以暴露 workflow 問題、但錯了仍然可回退」的最小真實感材料；不是為了證明 AI 一定成功而挑最容易的一組。

選 sample 前，可以問：

1. 它是否已公開、已批准或 synthetic，且不含客戶、CRM、付款、合約或 credentials？
2. 它能否代表真正會遇到的欄位、格式或小型不完整情況？
3. 我能否明確列出 AI 只可讀哪幾份 input？
4. Output 能否只落在 sandbox／draft，而不會改動正本？
5. 如果跑壞了，能否由乾淨 sample 重新開始？

若其中一條答不到，先縮小 sample 或收窄工作單位。這不是拖慢測試，而是讓測試結果真的可以相信。

## AI 交出 draft artifact 後，reviewer 應怎樣知道它有沒有讀錯或猜錯？

一份 draft 本身並不夠。Reviewer 仍要看見 AI 根據甚麼 input、它在哪些位置沒有把握、做過甚麼檢查、哪些 action 刻意沒有做。否則 review 變成逐字重新做人手工作，AI 只是多了一層需要驗證的黑盒。

可 review 的 artifact 不必是複雜 dashboard。它可以是一張有原始連結與未知欄的比較表、一份標有 source section 的 briefing、一次變更前後的 diff，或一張 run receipt。核心是人可以打開它、追到 input、指出具體錯誤，並決定應 revise、approve 還是 stop。

**Jimmy 的結論：** AI 的第一個交付物不應是「最終答案」，而是讓人有足夠證據去判斷它下一步能否繼續的 draft artifact。

一份 draft receipt 最少可包含：

| 欄位 | Reviewer 要從中看到甚麼 |
| --- | --- |
| Input class／清單 | 它只讀了哪些指定材料 |
| Draft output | AI 實際交回的內容、表格或變更預覽 |
| Evidence／check | 哪些欄位、來源或規則已核對 |
| Unknown／exception | 哪些資料不足、衝突或不能確認 |
| 未做 action | 它沒有發送、覆寫、部署或擴大讀取甚麼 |
| 建議下一步 | 要由哪個 owner approve、revise 或 stop |

有了這六格，review 不再只是「睇吓啱唔啱」，而是一個可以把 workflow 帶到下一格或安全停下的決定。

## AI workflow 的 check 和 exception 應該怎樣在 release 前逐格過？

第一輪 dry run 不需要一個龐大的測試平台，但要先決定最少的 quality checks。這些 checks 應對應你最怕出現的錯誤：資料是否齊、來源是否可追、格式是否符合、內容有沒有越過 scope、出現未知時有沒有明確停下。若不預先寫出來，reviewer 通常只會憑感覺看「像不像可以用」。

同樣重要的是例外路徑。Check 不通過時，AI 不應一概重新生成；有些問題只需依 schema `revise once`，有些需要補 input，有些涉及矛盾判斷或外部 action，必須交回 owner。把這些分開，才能分辨 workflow 是需要一個小修正，還是根本未準備好 release。

**Jimmy 的結論：** Quality check 不是在最後找錯字，而是讓每個已知風險有一條可預期的去向：通過、修一次、待補、待批，或停止。

以 internal briefing 為例，第一輪可以只檢查：

| Check | 通過時 | 不通過時 |
| --- | --- | --- |
| 指定來源齊全 | 繼續生成 draft | `needs-input`，列出欠哪一項 |
| 每個主張有原始位置 | 可交 reviewer | 標 `unknown`，不得補猜 |
| 必需欄位存在 | 可以 `revise once` | 交 diff + check 結果 |
| 沒有越過指定 scope | 可進 human review | `stop`，要求 owner 重定義範圍 |
| 沒有外部／正本 action | 可保留在 draft 層 | 若需要 action，轉 `human release` |

想把例外狀態寫進 Skill，可讀 [AI 一遇資料不足就繼續猜？Skill 要先寫好 exception ladder](./4-34-skill-exception-ladder.md)。

## Human release 點樣由「幫手睇下」變成一個清楚的責任決定？

很多 workflow 的 human approval 只是最後一句「麻煩睇下」。這令 reviewer 不知道要核對甚麼、是否有權停、拒絕後要怎樣回到前一步，也不清楚一旦按了 approve 是否代表會真正影響外部世界。結果人既不敢放手，又很容易因忙碌而略過真正需要看的地方。

Human release 應該是一個明確工作狀態：指定 owner 收到完整 draft receipt，按預先定義的標準選擇 approve、revise 或 stop。它不是要人逐步操作 AI，而是要人在會改變責任、公開狀態、正本資料或資源成本的門檻前真正作決定。

**Jimmy 的結論：** Approval 的價值不在多一個按鈕，而在令所有人知道「這一刻之前 AI 做過甚麼、這一刻之後誰承擔甚麼、拒絕後工作去哪裡」。

一張 release card 可用這些欄位：

1. 本輪 input 是甚麼類別，是否仍在批准範圍？
2. AI 交了哪個 draft artifact，還有哪些 unknown？
3. 哪三條 check 已過、哪一條仍未過？
4. Owner 可選的 action：approve、revise、stop，各代表甚麼？
5. 若 approve，下一個 action 是否只內部採用，還是真正對外／寫入正本？
6. 若 revise／stop，保留哪一版、由誰處理下一步？

沒有這些東西時，把 output 留在 draft 層不是失敗；這正是 dry run 成功守住責任邊界的證明。

## Recovery receipt 為甚麼是第一個 live run 的必要部分？

AI workflow 出錯並不可怕；真正危險是出錯後不知道它讀了甚麼、改到哪裏、哪一個版本可信、是否已經對外做過 action。沒有 recovery state，大家容易用更多 retry 掩蓋問題，最後連本來正確的 output 都難以分辨。

Recovery receipt 不需要記錄每一個技術細節。它只要讓人可追查這次 run 用了哪類 input、從哪個版本開始、哪些 check 通過／不通過、AI 有沒有外部 action、下一次可從哪個乾淨位置重跑。這也令日後工具更新或換人時，workflow 不會完全依賴當時在場的人。

**Jimmy 的結論：** 可以安全回退的 workflow，不是永遠不出錯；而是每次出錯後仍保留一個人看得懂、可選擇重跑或停止的可信狀態。

每次 dry run 後，留這張最小 receipt：

| 要記甚麼 | 為甚麼 |
| --- | --- |
| Run 日期、工作單位和版本 | 知道自己在看哪一次結果 |
| Input class／清單 | 能重現或排除錯的資料 |
| Draft artifact 位置 | 找回人工 review 的實際輸出 |
| Check／exception 結果 | 知道是通過、待補、待批還是失敗 |
| 已做／未做 action | 防止將草稿誤當成已發送或已寫入 |
| 回退與下一位 owner | 知道怎樣安全重跑、誰可決定停止 |

若 receipt 找不到，先不要擴大權限或規模。先把可讀 state 補回來，因為這是你日後管理變更的基礎。

## 想為第一條 AI workflow 做 dry run，最安全的開始是甚麼？

第一個 dry run 不需要挑最重要的流程。反而應選一件重複、低風險、只交 draft、可以用公開或 synthetic input 驗證的工作，例如根據三篇已批准的公開文章起一份 internal briefing，或把指定 sample 資料整理成比較表。這樣即使 AI 讀錯或停錯，影響也留在可回退範圍內。

試跑的成功標準也不該是「今天有沒有自動完成」。更好的問題是：AI 是否只讀指定材料？是否交出有 evidence／unknown 的 draft？check 失敗時有沒有進正確狀態？owner 是否能清楚決定 approve、revise 或 stop？你能否找回上一版重新開始？

**Jimmy 的結論：** 第一個 dry run 的成果是一張你可以信任的 release card 和 recovery receipt；有了它，才值得一格一格增加真實資料、頻率或 automation。

可以跟這五步試：

1. 選一條只交 internal draft 的重複工作，勿接客戶／production 資料。
2. 準備已公開、已批准或 synthetic sample，列出 AI 只可讀的 input。
3. 指定 draft artifact、三條 quality check 和未知時的 exception 狀態。
4. 由 named owner 用 release card 選 approve、revise 或 stop；不自動外發。
5. 留低 recovery receipt，確認可追查、可回退後才討論擴大。

暫時不要在第一次 live run 接 CRM、付款、客戶資料、外發、正本覆寫或不可逆部署；一次 human approval 亦不代表 workflow 已 production-ready。想把重複已知錯收進每次都會跑的檢查，可讀 [最小 regression pack](./4-10-minimum-regression-pack.md)；想知道 output 是否真能收貨，可讀 [設計獨立 review](./4-18-independent-review.md)。

← [返回 AI Builder](../README.md) · [按問題瀏覽](../../../README.md)
