# AI Loop 點樣先唔係排咗期嘅 prompt：由目標、檢查、修正到下一輪的工作系統

很多人以為 AI 用得不夠好，是因為 prompt 不夠靚、模型不夠新、工具不夠多。於是每天都逐句叫 AI 做事：問一次、收一次 output、覺得不對就再加一句。這可以完成單次任務，但一旦工作要重複、要交接、要慢慢改善，所有判斷和修正仍然靠你記得、靠你在場。

另一個常見情況是把一條排程自動化叫做「Agent loop」：每天八點生成一篇內容、每週整理一次資料、每次出錯就再跑。它有 trigger、有 output，卻未必有任何機制把結果帶回下一輪。若上次缺 source、讀錯資料或 reviewer 退回，下一次還是做同樣的事，那只是重複執行，不是會學到和修正的 workflow。

Jimmy 的判斷是：Loop Engineering 不是新名詞，而是把 AI 由「一次回答」放進一個有目標、有可讀 artifact、有檢查、有修正和有停止線的回饋系統。Agent 可以執行任務；Loop 才令它知道結果有沒有過關、未過關時應補資料、改策略還是交回人，最後留下下一輪可用的規則。

| 一輪 Loop 的一格 | 它要解的問題 | 完成後留下甚麼 |
| --- | --- | --- |
| Goal／trigger | 不知為何啟動、甚麼才算完成 | 一個可驗收工作單位 |
| Plan／input | AI 用錯資料或猜錯範圍 | 已批准 context 與本輪計劃 |
| Bounded action | AI 一路做、越做越大 | 受控的工具 action／draft artifact |
| Check／feedback | output 出了但不知好不好 | pass、unknown、revise 或 stop evidence |
| Correction／routing | 出錯只懂再試 | input、approval、retry、recovery 的下一手 |
| Receipt／next loop | 下次又從零開始 | 可追溯 state、規則和下一個可改善點 |

## Prompt、Agent 和 AI Loop 有甚麼分別，為甚麼不能只看有沒有自動跑？

Prompt 是一次指示：你提供目的和 context，AI 回一個答案。Agent 則可以多做一些事：讀資料、選工具、執行步驟、產生 artifact。兩者都很有價值，但若任務完成後沒有人或規則檢查結果、也沒有把錯誤導向下一個行動，它們仍然只是一次執行，不會因結果變得更可靠。

Loop 的關鍵是 feedback 真的會改變下一步。它不是「再跑一次」，而是「根據這次 check 發現的問題，補 input、修規則、退回 draft、交 owner 決定，然後在清楚邊界內再跑」。沒有 feedback 的定時 prompt，就算每天自動執行，也不會因為昨天錯了而變好。

**Jimmy 的結論：** 自動跑不等於有 loop；只有結果被驗證、錯誤有去處、下一輪會因證據而調整，才是一條能累積可靠性的 AI loop。

可以這樣分辨：

| 形式 | 它做得到甚麼 | 它仍缺甚麼 |
| --- | --- | --- |
| Prompt | 問一次、答一次 | 重複工作、可見 state、驗收與回饋 |
| Agent | 讀資料、用工具、完成多步任務 | 結果是否可用、例外怎樣處理、何時停 |
| 排程自動化 | 在固定時間觸發同一動作 | 是否因上次結果而修正下一次 |
| AI Loop | 根據 check／feedback 改變下一步 | 仍需要清楚 input、stop、human gate |

如果拿走你本人後，流程只會不斷重覆同一個 prompt，卻沒有人知道 output 是否可用，那它未是一條真正的 loop。

## 一輪 AI Loop 應該怎樣由目標走到 feedback，才不會一路愈跑愈偏？

一輪 loop 不需要很複雜，但必須有明確順序。先定這輪要交甚麼工作結果，再給 AI 必要且批准的 input，然後限制它只做一段可控 action。完成後不能直接當作結束，要先用 check 看它是否符合完成線；不符合時，根據錯誤類型決定修、補、問或停，而不是一律叫 AI 再生成。

最危險的是缺了檢查這一格。沒有 check，AI 可能每次都很有效率地用錯資料、漏同一個欄、或把猜測當事實；因為系統沒有任何地方告訴它「這次為何不算過」。這種循環只是把錯誤排程化，而不是把工作設計成可改善。

**Jimmy 的結論：** Loop 的核心不是「再來一輪」，而是「這一輪的 evidence 會決定下一輪究竟要怎樣不同」。沒有可驗收 feedback，便沒有可以信任的修正。

一輪最小 loop 可按六步走：

1. **定目標**：定一個可驗收工作單位，而不是「幫我改善所有東西」。
2. **定 input 和 plan**：列明只讀甚麼、要做哪個 bounded action。
3. **執行**：AI 交 draft、比較表、diff 或另一個可打開 artifact。
4. **檢查**：驗證 schema、source、scope、未知、品質或使用情境。
5. **路由修正**：可修的 `revise once`；缺資料 `needs input`；取捨／外部 action `needs approval`；不可信則 `failed safe`。
6. **留 receipt**：記 input、check、決定、未做 action 和下一輪要改的規則。

下一輪可能是再次執行，也可能是停下來改 brief、補 source 或不做。能安全停止，本身也是 Loop 正確運作的結果。

## AI Loop 的 input、source of truth 和 context 為甚麼要在開始前先固定？

Loop 會重複運行，這正是它有價值也有風險的原因。若每輪都讓 AI 隨意從聊天記憶、舊 output 或整個資料夾找材料，錯誤很容易被帶到下一輪，然後被看成「上次的結論」。沒有 source of truth 的 loop，可能愈跑愈自信，但它累積的是沒有根據的內容。

固定 input 並不等於要把所有 context 寫死。它只表示每輪要清楚知道：哪些資料是這次可讀、哪些是參考、哪些是不可讀、資料不足時怎樣標記。當真正需要新資料或更大範圍時，AI 應交問題給 owner，而不是偷偷擴大 access。

**Jimmy 的結論：** Loop 的記憶不能只靠上一輪 output。每輪都要能回到一個已批准、可追溯的 source of truth，否則 feedback 只會令偏差更穩定。

開始前可寫一張 input card：

| 項目 | 要寫清楚甚麼 |
| --- | --- |
| 觸發條件 | 甚麼情況下值得跑這一輪？ |
| Source of truth | 哪些文件、欄位、URL 或狀態是本輪基準？ |
| 允許 context | AI 只可讀甚麼已批准材料？ |
| 禁止範圍 | 哪些客戶、CRM、private vault、production 資料不可讀？ |
| 資料不足 | 何時要標 unknown／needs input，而非補猜？ |
| 輸入版本 | 怎樣知道本輪用的是哪一批資料？ |

這些東西令同一條 loop 換人、換工具或隔一段時間後，仍可被安全理解和重跑。

## AI Loop 的 check 和 feedback 怎樣令它真的「因結果而改變下一步」？

很多人說「有 feedback」，其實只是人看完後在下次 prompt 裏隨口說「改好少少」。這種 feedback 沒有被結構化、也沒有對應到任何特定錯誤，下一位人或下一次 run 根本不知道應如何使用。它更像一次聊天意見，而不是 workflow 的可重用學習。

可用的 feedback 至少要指出：哪個完成線沒過、證據是甚麼、這是可規則化的錯還是需要判斷、下一輪要改 input、rule、review 還是 scope。這樣每個不合格結果才有一條可選擇的路，而不是被一概重新生成。

**Jimmy 的結論：** Loop 不是 AI 自己給自己評分；它要有與工作結果分開的 check，並把 feedback 變成可看到的下一步規則。

一個簡單 feedback router 可以是：

| Check 發現甚麼 | Feedback 怎樣記 | 下一輪改甚麼 |
| --- | --- | --- |
| 少必填欄位 | `schema-missing` + 欠欄清單 | 加入／修正 schema check，revise once |
| 找不到原始來源 | `source-unknown` + 位置 | 補 input 或保留 unknown，不生結論 |
| 兩個可信來源矛盾 | `judgment-needed` + 選項 | Owner 決定立場／縮 scope |
| Output 不適合讀者情境 | `brief-misaligned` + reviewer reason | 重寫 brief／讀者問題，不只改句子 |
| 工具中斷／版本不明 | `failed-safe` + 最後可信 state | 回退、修工具或停止重跑 |

當 feedback 有名字、有 evidence、有去向，才值得說這條 workflow 每輪都在學；否則它只是每輪都重新開始。

## AI Loop 點樣設 stop condition、成本邊界和 human approval，先不會變成「自己亂跑」？

Loop 不等於 fully autonomous。讓 AI 多跑幾步，不代表它可以自行決定何時花更多資源、擴大資料讀取、覆寫正本或對外發送。這些 action 會改變責任和風險，若沒有明確 stop condition，AI 最容易在「想完成任務」的驅動下越跑越大。

一個可管理的 loop 要在開始前就定好上限和 escalation：最多處理幾個 input、最多 revise 幾次、何時要交回人、預算／token／時間過了怎樣停、甚麼 action 只能留在 draft。這些不是為了阻止自動化，而是確保自動化只在你實際願意承擔的範圍內運作。

**Jimmy 的結論：** 安全的 loop 不以「跑到最後」為目標，而以「在正確條件下繼續、在不確定時可預期地停下」為目標。Human approval 是責任設計，不是 AI 失敗。

上線前最少答這七條：

1. 甚麼 trigger 才可以跑？
2. 本輪最多讀甚麼、跑多久、花多少資源？
3. 它依據哪個 source of truth 和哪份 Skill／rule？
4. 哪個 artifact 證明這一格已完成？
5. 哪些 checks 會攔住壞 output？
6. 哪些狀態必須 needs input、needs approval 或 failed safe？
7. 哪些 action 永遠只可由人 release，例如外發、覆寫、付款、權限或敏感資料？

答不出時，先縮小 loop。不需要先造多 Agent 或多 integration，才會有一條值得信任的工作系統。

## 第一條 AI Loop 應該揀甚麼工作，才可以學到真實 feedback 又不會製造大風險？

好的第一條 loop 不是最重要的工作，而是重複、低風險、能看見成果、能由人清楚驗收的一段。例如把指定公開內容收集成每週內部摘要、從已批准資料抽出課程 FAQ 候選、將 sample 表格填成固定 briefing draft。這些任務能讓你測 input、artifact、check、feedback 和 receipt，又不需一開始接 CRM、客戶承諾或 production deployment。

不適合的第一條，往往包含太多不同責任：自動改報價、直接回覆客戶、未經 review 發品牌內容、用未測試 code 部署，或「幫我改善所有東西」。這些不是不能做，只是需要先把人手判斷、資料邊界、exception 和 release 分開，否則你不知道失敗時應修哪一格。

**Jimmy 的結論：** 第一條 loop 要讓你學會設計 feedback，不是讓你最快展示 AI 多自主。選一件錯了也可回退、但足夠真實會出現例外的工作，才最有教學價值。

| 適合第一條 loop | 暫時不適合第一條 loop |
| --- | --- |
| 每週公開資料的 internal briefing draft | 未經審核的客戶承諾／報價／合約 |
| 課程 FAQ／常見問題候選整理 | 直接對外發布的品牌內容 |
| 指定資料的格式檢查與 review receipt | 未測試的 code deployment |
| Sample 工作卡的分類／下一步 draft | 開放式「幫我改善所有事情」 |

分界線很簡單：重複、低風險、可驗收。三個條件少一個，先把工作再拆細。

## AI Loop 最常見的三種假象，點樣避免把重複執行當成學習？

第一種是假象是「排咗期的 prompt」：每天自動生成同一類 output，但沒有檢查、沒有保存 feedback、下一次不會不同。第二種是「AI 自己話已完成」：看似有 review，但 check 和執行都由同一個模型自評。第三種是「人手接駁的多步流程」：每一步都要你複製貼上、解釋、再判斷，系統本身並未保存 state 或交接規則。

這些做法不必被全盤否定；它們可以是探索起點。但若你把它們誤稱為 loop，便容易太早加資料權限和外部 action，以為 AI 已有一套能自己修正的系統。先誠實知道目前只是 prompt、Agent task 或半人手 SOP，才能補到真正缺少的 check／feedback／receipt。

**Jimmy 的結論：** 分辨 loop 的一句問題是：拿走原本一直在場的人後，流程會否仍然留下足夠狀態，讓另一位 owner 知道 output 是否過關、錯了怎樣處理、下一輪要改甚麼？

可用這張檢查表：

| 看起來像 loop 的東西 | 它欠的是甚麼 |
| --- | --- |
| 每天定時出一篇內容 | Check、reader feedback 和下一輪規則 |
| Agent 自動說「done」 | 獨立 acceptance／human review |
| 多步 chat prompt | 可讀 state、artifact handoff、exception route |
| 不斷 retry | Failure evidence、回退點、stop condition |
| 很多 Agent 分工 | 清楚工作邊界、source、reviewer 和 release owner |

先補最缺的一格，不要以為加更多工具或更多 Agent 就會自然變成可靠 loop。

## 想設計第一條 AI Loop，最安全的開始是甚麼？

第一個 loop 可以很小：選一件只產生 internal draft 的重複工作，限制 AI 只讀公開／已批准材料，要求它交一個固定 artifact，定三條 check 和三種例外，再由 named owner review。這已足夠讓你看見 feedback 是否真的回到下一輪，不需要先建立 autonomous agent team。

例如每週把三篇指定公開文章整理成一張 briefing：AI 只讀 URL，輸出主張／原始連結／unknown 三欄；缺 URL 就 `needs input`，兩個說法衝突就 `needs approval`，格式少欄才 `revise once`，owner 採用或退回後留下 receipt。下一週用同一張 receipt 看要補哪一條規則，而不是重新寫一個更長 prompt。

**Jimmy 的結論：** 第一條 loop 的成功，是你可以指出它的 input、artifact、check、feedback、stop 和下一輪改動；不是它可以在沒有人看的情況下跑得最久。

可以跟這六步開始：

1. 選一件重複、低風險、只交 draft 的工作。
2. 寫清 trigger、source of truth、允許 input 和不可碰範圍。
3. 定一份可 review 的 artifact，不收「AI 說完成」。
4. 寫三條可檢查 quality gate 和 pass／fail routing。
5. 定 stop condition、human approval 和 recovery receipt。
6. 跑三次 sample／公開安全 input，才根據真實 feedback 補下一條規則。

暫時不要將 loop 接 CRM、付款、客戶資料、外發或不可逆部署；不要把多跑幾次當作已經學習；也不要把一致性誤當成正確性。若要先設計一個有邊界的 Agent 工作單位，可讀 [先跑一條可停的 Agent loop](4-25-first-agent-loop.md)；若要把已知錯收進固定檢查，可讀 [AI 做到一次唔等於可以交付：Skill 點樣用 quality gates](4-2-quality-gates.md)。

← [返回 AI Builder](../04-ai-builder.md) · [按問題瀏覽](../BROWSE.md)
