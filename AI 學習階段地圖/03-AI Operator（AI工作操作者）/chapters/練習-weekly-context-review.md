# 每星期 20 分鐘，點樣令 AI context 不會愈儲愈舊？用 retain、update、retire 做小型 review

notes、SOP、prompt、context pack 和 project note 愈來愈多時，最危險的不一定是找不到資料，而是找到了看似合理、其實已過期的規則。一條舊 brief、已推翻的假設或沒有人更新的 owner 資料，被下一個人或 AI 當成今天有效指示時，工作會很有信心地走錯。

直覺做法通常是「找一天整理所有筆記」。這往往太大，最後變成資料清倉而不是工作改善。更有效的是只 review 本周真的用過、令你返工、或已被新 evidence 推翻的少量 context；每條只決定保留、更新或退休，然後在下一輪工作驗證。

Jimmy 的判斷是：好的 AI context 不是存得愈久愈值錢，而是下一位拿起來時仍知道可不可以信。每周短 review 不是監控人或清理 Vault，而是一條讓工作規則保持可用的小型 reliability loop。

| Review 格 | 先問甚麼 | 留下甚麼 |
|---|---|---|
| 選題 | 哪些 context 本周真的影響了工作？ | 最多五條候選 |
| Evidence | 甚麼顯示它仍對／已過期？ | 可回看原因 |
| Decision | retain、update 還是 retire？ | 現行狀態 |
| Owner | 誰確認與更新？ | 責任與日期 |
| Next test | 下次怎樣知道決定有效？ | 一條驗證行動 |

## Context 愈多，點解不應每周整理所有筆記？範圍太大會令可靠性工作失焦

當內容多起來，很容易將「整理」理解成一次處理所有 prompt、所有資料夾、所有歷史筆記。這種工程不但很難開始，也會把注意力花在未影響任何工作的一堆收藏上。最後你或許得到較整齊的 folder，卻沒有修正那條本周真正令 AI 用錯資料的規則。

每周 review 的目標較小：只找下一輪最可能再影響 output 的 context。把範圍限制在五條以內，並不是偷懶；它是確保每一個決定都有 evidence、owner 和下次驗證，而不是做出一張無法維護的大清單。

Jimmy 的結論是：可靠性 review 先處理正在造成摩擦的 context，不是先處理看起來最亂的資料夾。

本周只從三種訊號中挑候選：

1. 本周真的用過的 context；
2. 本周令你返工、卡住或需要人補救的 context；
3. 已被新 source、決定或工作範圍明確推翻的 context。

其他未用過的資料可以先不動。若日後它重新影響一件工作，它自然會再次進入 review 範圍。

## retain、update、retire 點樣揀？決定不是憑感覺，而是看 evidence 與下一輪用途

同一份 context 不一定只有「留下」或「刪除」兩個選擇。它仍然可信時可以 retain；核心判斷仍有用但 source、owner、格式或 stop line 改了時應 update；已被推翻、過期或不再適用時應 retire。把三種情況分開，下一位便不會把歷史參考誤當現行指示。

`retire` 特別容易被誤解為刪掉所有記錄。其實它只表示「不要再拿這條當 current instruction」；歷史原因仍可保留在適當地方，讓日後知道為何曾經這樣做。這比讓過期規則悄悄留在工作 context 安全得多。

Jimmy 的結論是：context review 的價值不在保留得多，而在每條仍會影響工作的人都知道它現在是現行、待更新，還是只屬歷史。

| Decision | 適用情況 | 必須留下 |
|---|---|---|
| `retain` | 近期用過、仍可信、沒有反例 | 最後確認日期與用途 |
| `update` | 核心仍對，但 source、格式、owner 或範圍已改 | 改哪一格、根據甚麼、誰確認 |
| `retire` | 已推翻、過期或不再適用 | 不再作現行指示的原因與位置 |

若 evidence 還不足以決定，先標「待確認」而不是假裝 retain。下一輪先縮小任務測試，才做正式更新。

## Evidence 點樣寫先不會變成「我覺得過期」？留下可回看的工作訊號

「我覺得這條舊了」有時是對的，但它不能幫下一位判斷你為何改，也不能在下一輪驗證是否修正成功。若 context 會影響 AI output、對外內容或交接工作，決定最好至少連著一個可回看的工作訊號：新 source、owner 改變、同一 failure 重複、current state 與規則矛盾。

evidence 不需要變成嚴格研究報告。它只要足夠令 reviewer 看懂：這次 retain／update／retire 是因為甚麼發生，而不是因為某人臨時偏好。這也令過一段時間後，你可以看回這條規則的生命週期。

Jimmy 的結論是：context 的更新必須有工作證據，不是因為文件看起來舊就任意重寫。

可用 evidence 例如：

| 訊號 | 可以支持甚麼決定 |
|---|---|
| 公開 source 已改／URL 失效 | update 或 retire 一條材料規則 |
| workflow 兩次在同一格失敗 | update SOP／exception |
| owner／範圍已改 | update current state／approval route |
| reviewer 仍按這條規則抓到問題 | retain 目前 acceptance |

只寫 evidence 能看見的內容；不要把 raw chat、客戶資料、credentials 或敏感材料複製進 review ledger。

## 20 分鐘 ledger 點樣填？每一行要讓下一位知道這條 context 現在可不可以信

ledger 的作用不是記錄所有思考，而是把一條 context 的現行狀態壓成可交接行。它需要同時回答：這條是甚麼、本周有甚麼 evidence、決定是甚麼、誰負責、下一次怎樣驗。若少了任何一格，下一位仍然要問你「所以可以繼續用嗎？」

最多五行的限制很重要。它逼你把 review 變成可完成 routine，而不是新的一輪資料整理。當某條 context 需要大量背景時，ledger 只連到 source of truth，不把所有內容搬過來。

Jimmy 的結論是：一張有效 ledger 不記錄你看過多少資料；它讓下一位知道哪一條規則已被判斷、又會在甚麼情況再次被檢查。

```markdown
# Weekly context review：日期／owner

| Context item | 本周 evidence | Decision | Owner／date | 下一次怎樣驗 |
|---|---|---|---|---|
| ＿＿＿＿ | ＿＿＿＿ | retain / update / retire | ＿＿＿＿ | ＿＿＿＿ |
```

填完一行後，讀一次：若不看原始 chat，另一位人能否知道它現在可不可以使用？不能，就補 source、owner 或 next test，而不是寫更多心得。

## update 和 retire 後，下一輪點樣不會又讀錯？只改一條最影響工作的 context 再驗

review 很容易變成同時換工具、搬 folder、改所有 SOP。這樣即使下一輪變好，也不知道是哪個改動有效；若仍然出錯，更難回退。每周 review 的價值在於讓你有一條小而可驗證的改動，不是令整個系統瞬間變整齊。

選一條 `update` 或 `retire` 的 context，在下次低風險工作刻意驗證：新 AI session 是否讀到 current source？它能否分清歷史和現行？資料不足時有沒有停？這一輪結果才會成為下一次 retain 或再 update 的 evidence。

Jimmy 的結論是：context 變可靠不是因為你一次改了很多，而是每次都能證明一條現行規則真的被正確使用。

執行時按以下順序：

1. 選一條最影響下一輪 output 的 `update`／`retire`；
2. 只修 source of truth、owner、格式或 stop line 中一格；
3. 用公開或 synthetic 小工作開新 session 測；
4. 觀察它是否仍引用舊規則；
5. 將結果寫回下一周 ledger。

若還是讀錯，先補最早缺的 context 層；不要一次加十份文件或直接怪模型。

## 用公開 briefing context 跑一次：20 分鐘 review 怎樣令下一輪少信錯規則

以下是 synthetic 例子。你有一份「公開來源 → internal briefing」的 context pack。本周發現一個 URL 失效、一條未知標記規則仍幫 reviewer 找到缺口、舊 CTA 格式已不再對應目前 output。這三條都是可安全 review 的工作訊號。

ledger 不需要帶入任何客戶或私有內容；它只記現行工作的 context 狀態。下一輪 brief 由新 session 起草時，會按更新後來源、保留未知標記、而不再讀取退休 CTA 格式。

| Context item | 本周 evidence | Decision | 下一次怎樣驗 |
|---|---|---|---|
| 已批准來源清單 | 一個公開 URL 已失效 | update | 新 run 必須標失效，不補猜 |
| 未知標記規則 | reviewer 本周用它找到兩處缺口 | retain | 下次仍按同一 rubric review |
| 舊 CTA 格式 | 現行工作不再有該 output | retire | 不放進新 task pack |

Jimmy 的結論是：這張 ledger 的成果不是整理得漂亮，而是下一位不用靠印象就知道哪條 context 還有 authority。

這個例子只適合低風險工作。敏感資料、外部承諾與高影響決定仍要使用相應的權限與審批，不能用一張 weekly note 取代治理。

## 今日怎樣跑第一輪？只 review 三至五條有真實訊號的 context

不要等所有 context 都整理好才開始。揀本周最影響工作的一至三條，最多五條，填 evidence、decision、owner／date 與 next test。你完成的不是整理任務，而是一張能在下次工作前打開、知道哪條規則仍可信的判斷卡。

第一輪結束後，只改一條最影響下一次 output 的 context，然後在低風險 run 測它。若一條已 retire，請確保它不再被當成 current instruction；若一條 retain，仍要在新 evidence 出現時重新判斷。

Jimmy 的結論是：好的 AI context 不是存得愈耐愈值錢；是下一次有人拿起來時，仍然知道它可不可以信。

今天請完成：

1. 只選三至五條有本周訊號的 context；
2. 為每條寫 evidence、retain／update／retire、owner 與 next test；
3. 不把 raw chat、私有資料或 credentials 放入 ledger；
4. 優先修一條最影響下一輪的 context；
5. 下周用新 run evidence 再判斷它。

要先分清「今天仍有效」和歷史過程，可讀 [新 AI 一入 project 就要翻晒 chat？你需要的是 current-state note](./3-12-current-state-not-chat-history.md)。如果 review 的是已跑過的重複工作，讀 [一條 routine 跑完，下一步改甚麼？](./3-10-routine-review.md)。

---

← [返回 AI Operator](../README.md) · [按問題瀏覽](../../../學習地圖.md)
