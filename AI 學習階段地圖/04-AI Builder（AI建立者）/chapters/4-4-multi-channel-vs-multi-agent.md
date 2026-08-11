# 切模型、開幾個 chat 唔等於 multi-agent：怎樣判斷你有的是工具選擇，還是可交接的 AI team？

很多人同時用 ChatGPT、Claude、Codex、Gemini 或不同 AI channel，便覺得自己已有一隊 AI team。這些工具確實各有強項：有人擅長寫作、有人擅長 code、有人適合查資料；互相切換也能帶來備援和比較。但若每一次交接都要你親自複製貼上、重新講背景、判斷誰該做甚麼，你其實仍是唯一的 project memory 和唯一的 router。

問題不在於多工具沒有價值，而在於名字會影響你的下一步。如果你把「切 model」誤當成「已做 multi-agent」，便可能跳過真正需要補的東西：每個角色的唯一責任、共享但受控的 artifact、handoff contract、reviewer 與停止線。結果只是多了幾個對話視窗，你本人反而成為更忙的訊息中轉站。

Jimmy 的判斷是：multi-channel 是工具／模型的選擇；multi-agent 是多個有清楚責任的工作角色，能透過共享 artifact 和明確 handoff 合作。並行可以增加速度，但不是唯一標準：有些真正的多 Agent workflow 必須順序交接；相反，很多同時開幾個 chat 的做法，沒有共享狀態和 handoff，仍然只是一種人手 model router。

| 你可能有的東西 | 它真正解甚麼 | 還缺甚麼才算可交接 team |
| --- | --- | --- |
| Multi-channel／multi-model | 比較不同模型、備援、按任務揀工具 | 角色、共享 artifact、handoff、review |
| Parallel tasks | 讓互不依賴的工作同時處理 | 合併規則、衝突處理、唯一 owner |
| Sequential agent pipeline | 研究 → 草稿 → review 的順序工作 | 每站清楚 input／output／停止線 |
| Multi-agent workflow | 多個角色在合約下合作 | 仍要治理 shared state、品質與 release |

## 多開幾個 AI chat 或切模型，為甚麼未必等於你有 multi-agent team？

同時使用幾個模型本身很合理。你可以用一個模型 brainstorm、用另一個檢查、用 coding agent 改 working copy；這叫做按能力選工具，亦能降低單一供應商或單一模型的依賴。但若每次都要由你把第一個 chat 的內容摘要給第二個、再由你決定甚麼才是最後答案，工作並沒有變成一個可交接系統。

關鍵不在視窗數目，而在責任是否從你腦內移到可見的工作結構。若「研究 agent」究竟讀甚麼、交甚麼、交給誰，沒有被寫下；「review agent」又只收到一段人手複製的 chat；最後沒有人知道哪份 artifact 是可信版本，這些 AI 只是不同 channel 的助手，不是一個能自己被管理的 team。

**Jimmy 的結論：** 切 model 是換工具，不是自動多了一位同事。真正的 multi-agent 要令角色之間可以透過可讀 artifact 接手，而不是由你充當所有 context、記憶和決定的運輸帶。

可用這張對照快速分辨：

| 問題 | 只是 multi-channel 的常見答案 | 可交接 multi-agent 的答案 |
| --- | --- | --- |
| 誰做研究？ | 「我今次叫 Claude 做」 | Research role 有固定範圍、input、artifact |
| 下一位怎樣知道前一位做過甚麼？ | 「我會 copy 給它」 | 有 source list／brief／receipt／handoff note |
| 兩個模型結果不同怎樣處理？ | 「我自己揀」 | 有 comparison／review rule 和 named owner |
| 工作完成後留下甚麼？ | 幾段 chat history | 可回看的 draft、evidence、decision、next action |
| 你不在時怎樣繼續？ | 很難，因為背景在你腦內 | 另一位 owner 可按 contract 接手 |

若目前只是左邊，並不代表做錯；只代表下一個改善不是加更多模型，而是先做一份最小 handoff artifact。

## Multi-agent workflow 最少要有哪三樣東西，才不會變成失憶接力？

真正的 multi-agent 不一定要同時並行，也不必一開始有複雜 database。最小條件是：每個角色有清楚且不同的工作責任；角色之間有可讀、可追溯的共享 artifact；交接時有明確 contract 說清 input、output、unknown、下一位 owner 和停止線。這三樣令「下一個 agent／人」不用重新猜上一個做過甚麼。

並行是第四個可選能力，而不是硬性門檻。若兩個子任務彼此獨立，例如一個找來源、一個檢查 schema，可以同時跑；若工作本身有次序，例如先 research 再寫 draft，強行並行只會造成衝突和重複。好的 team 設計看依賴關係，不是追求 agent 數量。

**Jimmy 的結論：** Multi-agent 的最小單位不是「多個 AI」，而是「不同角色能以清楚 artifact 接力完成一件工作」。先做到可交接，才看是否值得並行。

三個必要 component 可這樣寫：

| Component | 要寫清甚麼 | 沒有它會怎樣 |
| --- | --- | --- |
| Role contract | 這個角色只負責哪一段、可用甚麼工具、何時停止 | 多個 agent 重覆／越界，沒人知道誰負責 |
| Shared artifact | source list、brief、draft、review receipt、state file 等 | 下一位靠 chat 記憶或人手重講 |
| Handoff contract | 已完成、unknown、check、下一位、未做 action | 交接時丟失 context，或把 draft 當完成 |
| Optional parallelism | 哪些任務可獨立同時處理、怎樣合併 | 為了快而做出衝突輸出 |

一個共享資料夾本身不等於 shared memory；只有檔案有 owner、命名、版本、用途和 handoff 規則時，它才真的幫到 team。

## Agent role 點樣切，才不會把同一件工作叫三個人做？

多 agent 最常見的浪費，是給每個 agent 一個看似不同、實際高度重疊的稱號，例如「研究專家」、「策略專家」、「內容專家」，但三者都讀同一堆資料、都寫同一篇建議、最後要人自己合併。這不是分工，而是把同一個不清楚任務複製幾次，增加成本和衝突。

較好的切法是按 context、工具權限、輸出 artifact 和驗收方式分開。研究角色只整理指定 sources 並標記未知；寫作角色只讀已批准 brief 產生 draft；review 角色只按 rubric 檢查，不能自行 release。角色之間的界線愈清楚，越容易知道哪一格需要改善、哪些工作其實不需要新的 agent。

**Jimmy 的結論：** Agent 角色不是職稱，而是一份 bounded work contract。最好的角色切法，會令每一位有自己不可替代的 input／output 和清楚的停止線，而不是一群都「幫手諗」。

可以用四條問題設計角色：

1. 這個角色只處理哪一類 input？哪些資料不應看到？
2. 它要交哪一個獨特 artifact，而不是泛泛意見？
3. 它有甚麼工具／權限，哪些 action 一定不可做？
4. 它完成後交給誰、何時要標 unknown／needs approval？

如果兩個角色的四條答案幾乎一樣，先合併它們或保留單 agent loop。分工是為了降低不確定，不是為了令架構看起來更先進。

## Shared memory／artifact 怎樣設計，才不會由「共同資料夾」變成另一個混亂來源？

所有 agent 都能看到同一個資料夾，並不代表它們有可用的共同記憶。若檔案沒有來源、版本、owner、更新時間或用途，下一個角色仍要猜哪一份可信、是否可以覆寫、前一位用了甚麼假設。多個 agent 同時寫入時，還可能出現衝突、覆蓋和過期內容被當成最新結論。

第一份 shared artifact 應刻意做得小而可讀。對一條 research → draft → review workflow，可能只需要一份 evidence list、一張 content brief、一份 draft 和一張 review receipt。每一份都注明角色、版本、已知／未知、下一位 owner；不要一開始就把整個私有 vault 變成所有 agent 的共享 context。

**Jimmy 的結論：** Shared memory 的價值不是儲得最多，而是讓正確的下一位在正確時間讀到足夠、可信、受控的 context。愈清楚 artifact 的用途和版本，愈少要靠人腦補洞。

最小 shared artifact pack 可以是：

| Artifact | 由誰寫 | 下一位用來做甚麼 |
| --- | --- | --- |
| Evidence list | Research role | 知道可用 source、原始位置、unknown |
| Work／content brief | Owner／planner | 知道受眾問題、scope、完成線、邊界 |
| Draft／working copy | Creation／builder role | 讓 reviewer 看實際結果，不讀整段 chat |
| Review receipt | Reviewer | 留下 pass／revise／stop、理由、下一步 |
| Run／status receipt | Operator | 追查版本、已做／未做 action、回退點 |

這些 artifact 必須留在批准範圍內；客戶、CRM、付款、合約、credentials、未公開策略或無 owner 的 vault 不應因為「共享」就被打開給所有 agent。

## Agent handoff 怎樣寫，下一位才不會靠你人手重講 context？

一個 handoff 不應只是「我做完了，請繼續」。下一位需要知道前一位接了甚麼任務、用了甚麼 input、交出甚麼、哪些內容仍不確定、哪些檢查已做、它絕對沒有做甚麼 action，以及自己究竟有權做哪一步。若缺少這些，handoff 就會退化成把工作和風險一起交給下一位猜。

handoff contract 同時也是 protection：research role 不應把未確認推論偷偷變成 draft 事實；draft role 不應因為看見資料就自行擴大 scope；review role 不應被期望同時補 research、重寫內容和作 release 決定。每個角色只收它真正需要的 context，才容易追查錯誤在哪一格發生。

**Jimmy 的結論：** 好 handoff 不是愈長愈好，而是讓下一位不開舊 chat 也能安全地決定「我可以繼續甚麼、必須停在哪裡、完成後交回誰」。

每次 handoff 最少寫：

| 欄位 | 內容 |
| --- | --- |
| 任務／版本 | 本次要完成的工作單位和當前版本 |
| 已批准 input | 已讀哪些材料、來源與範圍 |
| Artifact | 已交出甚麼檔案／draft／receipt，位置在哪裡 |
| Check／unknown | 哪些已驗證、哪些仍不確定或衝突 |
| Scope／未做 action | 明確列出沒有外發、覆寫、擴權或補猜甚麼 |
| 下一位 | 指定角色可做的下一步、何時要 escalate／stop |

如果 handoff 需要複製大量 private chat 或敏感資料才能理解，先回到上游收窄 context；不要把資料擴散當作「團隊合作」。

## Parallel agent 幾時真的有價值，幾時只會令你更難收貨？

並行最適合兩個或以上互不依賴的子任務。例如一位 agent 從指定 sources 整理事實，另一位依固定 schema 檢查既有資料是否缺欄；兩者不需要先看對方 output，完成後可由一個 owner 合併。這時並行確實可以減少等待時間，但仍要有合併規則、衝突處理和最終 reviewer。

若工作有必然次序，硬並行通常只會增加返工。寫作角色在 brief 未定前先寫，可能要全部重來；review role 在 draft 未完成前「review」，只會變成泛泛意見；多 agent 同時修改同一份 working copy，更容易覆蓋和產生版本衝突。這些情況用單 agent 或 sequential handoff 反而更快、更容易管理。

**Jimmy 的結論：** Parallelism 是速度工具，不是 multi-agent 的身份證。只有任務真正獨立、輸出能合併、衝突有人處理時，並行才會帶來槓桿。

先用這三條判斷是否並行：

1. 兩個子任務是否不用等對方的 output 才能開始？
2. 它們會否修改同一份資料、作相同判斷或爭奪同一個 source？
3. 完成後誰合併、以甚麼 rule 處理不一致？

任何一條答不到，先做 sequential workflow。能穩定交接的單 agent loop，通常比三個互相干擾的 agent 更有價值。

## 想試第一條 multi-agent workflow，最安全的開始是甚麼？

第一個 multi-agent workflow 不需要自動發佈、不需要大量共享 memory、更不需要一隊 agent 同時改 production。選一件低風險、只產生 internal draft、能清楚切成兩段的工作，例如「已批准公開資料 → evidence list → briefing draft → review receipt」。先由兩個角色開始：research／structure 和 draft／review；必要時由人做 final owner。

成功標準不是 agent 數目，而是你能拿走原本的 chat history，仍然看懂每一格用過甚麼、交了甚麼、未確定甚麼、下一位能做甚麼。若這條 workflow 已能安全接力，再問是否有任何獨立子任務值得並行；若還要你不停轉述背景，先補 artifact 和 handoff，而不是再加模型。

**Jimmy 的結論：** 第一條 multi-agent 的成果是一組可讀、可交接、可 review 的角色合約與 artifact pack；不是一張看似很忙的 agent team 圖。

可以用這五步開始：

1. 選一件只用公開／synthetic input、只交 internal draft 的工作。
2. 切成兩個不重疊角色，為每個寫 input、artifact、stop line。
3. 用一份 evidence list／brief 做最小 shared artifact，不開放整個 vault。
4. 寫一張 handoff receipt，列已知、unknown、checks、未做 action、下一位 owner。
5. 由人 review 兩輪結果；若交接仍靠你重講，先修 contract，不加第三個 agent。

暫時不要把多個 chat 視為已完成 multi-agent；不要把 shared memory 理解成所有 agent 都可讀所有資料；也不要為了有並行而把有依賴的工作硬拆開。想按 context 和驗收判斷該用一條 loop 還是 specialist，可讀 [Loop 和 specialist 的分工](./4-13-loop-or-specialist.md)；想先跑一條穩定單 agent workflow，可讀 [AI Loop 點樣先唔係排咗期嘅 prompt](./4-3-loop-engineering.md)。

← [返回 AI Builder](../README.md) · [按問題瀏覽](../../../README.md)
