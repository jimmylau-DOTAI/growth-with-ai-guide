# AI workflow 點樣由逐句指令變成可驗收循環：第一條 loop 要有檢查、狀態和停止線

你可能每天都在用 AI：叫它寫、整理、比較、起草。可是每做一件事仍要在旁逐句補資料、確認下一步、看有沒有出錯。看到別人用同一類工具卻快很多時，差距通常不只是 prompt 寫得更靚；他已經把一件重複工作設計成會自己推進、留低狀態、最後交給人驗收的循環。

AI 能執行不等於 AI 有 workflow。一次指令只解當下問題；一次 execution 可以讀資料和做 action；loop 則會根據結果檢查、修正或停下，再決定下一步。若缺少檢查，流程只是定時重複輸出，壞結果也會同樣重複。若缺少狀態與停止線，使用者就不敢真的放手。

Jimmy 的看法是：AI workflow 的分水嶺不在「有冇 Agent」，而在你能否講清這一輪的完成標準、何時要修正、何時要交回人、以及下一輪怎樣知道上一輪發生過甚麼。第一條 loop 不要挑最酷的，挑一條重複、低風險、錯了會知道的工作。

AI workflow · AI loop · automation · agent workflow · validation · state · stop line · AI Builder

| 一條可驗收 loop 的一格 | 要回答甚麼 | 留下甚麼 |
|---|---|---|
| Trigger／purpose | 何時開始、今輪要完成甚麼？ | work statement |
| Input | 讀甚麼已批准材料？ | source boundary |
| Action | AI 只做哪一手？ | bounded task |
| Check | 甚麼結果才算合格？ | acceptance rule |
| State | 下次怎樣知道已做過甚麼？ | artifact／receipt |
| Stop／handoff | 何時停、交回誰？ | escalation／owner |

## AI workflow 同 prompt 有咩分別：逐句餵 AI 會令你的注意力成為瓶頸

當你每一步都要說「現在讀這份資料」「再整理成這個格式」「這一句改掉」「下一步做甚麼」，你其實是在親自做流程控制。AI 只是在每個小步幫手，沒有承擔如何由開始走到完成。這種用法對探索很靈活，但一件工作每週重複時，你的注意力會很快成為瓶頸。

Workflow 則先把工作目的、input、artifact、review 與下一步寫清。AI 未必會做得更多，但它知道自己只需處理哪一手、完成後交甚麼、甚麼情況不可繼續。人由「每一步都在」轉成「設計與驗收」，才是真正省回注意力。

**Jimmy 的結論：** prompt 解決一次問題；workflow 管理一次工作。你想交出去的不是幾句指令，而是一段能由 input 走到可驗收 artifact 的路徑。

| 層次 | 它做到甚麼 | 人仍要做甚麼 |
|---|---|---|
| 指令 | 問一次、答一次 | 每一步決定下一步 |
| Execution | 讀資料、用工具、產生 output | 開頭與結尾大量補救 |
| Workflow loop | 按標準檢查、留下 state、決定 handoff | 設計規則與驗收 |
| Scale-ready loop | 有 owner、exception、measurement | 決定是否擴大 |

若你還未能說出一件工作的 artifact 和完成線，先不要叫它 loop。先把工作切清，這比加更多 agent 功能重要。

## AI loop 為何一定要有檢查：沒有 feedback 的重複執行只是定時器

每朝八點叫 AI 出一份摘要，有 trigger、有輸出，但若它漏資料、格式錯或引用了不可靠來源，下一天仍會照樣做。這叫重複執行，不叫 loop。loop 的分界線是 output 會被某個標準檢查，檢查結果會影響下一步：合格才交付，不合格則修正、標 unknown、退回或停止。

檢查不必一開始很複雜。可以是必填欄位、source link、日期格式、一個 owner checklist，或人手對照關鍵事實。它的作用不是令 AI 完美，而是令「完成」有定義，並讓錯誤在進下一手前被看見。

**Jimmy 的結論：** 沒有 check 的 automation 只是排了期的輸出風險。能根據結果改變下一步，才是 workflow loop。

| 每日自動做甚麼 | 若無 check 會怎樣 | 加一個最小 check |
|---|---|---|
| 整理新聞 | 可能混入舊／不可靠來源 | 只讀 approved source list |
| 起內容 draft | 可能漏 CTA／越界 claim | checklist 加 owner review |
| 分類名單 | 可能誤判或缺欄 | schema validation |
| 摘要會議 | 可能把 unknown 寫成事實 | unknown label／human review |
| 更新狀態 | 可能重複或漏掉 action | receipt／idempotency rule |

若 check 本身需要策略、語氣或高風險判斷，請留給 owner，而不是假裝可以用硬規則完全取代人。

## AI loop 的六步怎樣設計：目的、計劃、受控 action、check、修正、交接

第一步是定今輪目的，不是定工具：例如把已批准公開來源變成 internal briefing draft。第二步定 action plan，列 input、output 和限制；第三步讓 AI 做一個受控 action；第四步按 acceptance rule check；第五步若不合格便修正、補資料或停止；第六步交出 artifact、記下 state 或送到下一個 owner。下一輪由這份 state 繼續，而不是由零猜。

六步讓 workflow 有因果：不是因為排程到了就繼續，而是因為前一步留下的 evidence 符合標準才繼續。這也讓你較容易 debug：是 input 不好、action 不對、check 不夠、還是 owner 的完成定義沒講清？

**Jimmy 的結論：** Loop 不是一堆自動 action；它是一個會看結果、留下 state、按規則改變下一步的工作系統。

| 六步 | 要做甚麼 | 必須留下甚麼 |
|---|---|---|
| 1. Purpose | 今輪要解甚麼真工作 | work statement |
| 2. Plan | input、scope、artifact、owner | work card |
| 3. Action | AI 做 bounded task | draft／structured output |
| 4. Check | 對照 acceptance rule | pass／return／unknown |
| 5. Repair／stop | 補資料、改規則或交回人 | exception note |
| 6. Handoff／state | 交付並記錄本輪結果 | receipt／next trigger |

剛開始時不用讓 AI 自己設計六步。你先把六步寫成 card，再選其中一兩個低風險 action 交出去，才是安全的 builder 練習。

## AI loop 同傳統 automation 有咩不同：不用想齊所有情況，但要講清楚甚麼叫完成

傳統 automation 很擅長固定規則：若條件 A，便做 action B。它可靠，但對沒有預設過的情況通常只會停止或報錯。AI loop 可以在一些不完整情況下整理、比較、提出選項，甚至嘗試修正；代價是它需要更清楚的 acceptance standard 和人手邊界。

這不是說 AI 取代傳統 automation。客觀計算、欄位比對、固定格式應優先交給 deterministic rule；理解語意、起草、歸納、處理半結構材料才適合讓 AI 幫忙。好的 loop 往往同時有兩者：AI 提供彈性，規則和 review 負責可靠性。

**Jimmy 的結論：** AI loop 的成本不在於把所有例外預先寫完，而在於先定義「甚麼叫可交付」和「甚麼情況不可由它自己決定」。

| 工作部分 | 較適合甚麼 | 原因 |
|---|---|---|
| 日期／數值／必填欄位 | deterministic check | 可客觀判對錯 |
| 公開資料摘要 | AI draft 加 source review | 需要理解但可核對 |
| 語氣與策略 | AI options 加 human decision | 高度依賴情境 |
| 對外發送／付款／設定 | approval gate | 高風險不可逆 |
| exception routing | rule 加 escalation owner | 不能靜靜失敗 |

當你把所有事情都交給 AI，loop 很容易不可靠；當你把所有事情都硬規則化，又會失去 AI 的彈性。邊界設計正是 Builder 要練的能力。

## 第一條 AI loop 應揀甚麼：重複、低風險、錯了會知道比「容易」更重要

第一條 loop 的目的不是即刻慳最多時間，而是讓你學會工作設計。因此它應該重複出現、風險低、而且有清楚驗收方法。適合的例子包括：已批准來源的每週摘要、內部內容選題整理、會議 action draft、固定 FAQ 分類、或一份由人 review 的 briefing。

不適合第一條的，是報價、合約改動、未審核的對外貼文、敏感客戶資料、付款、production deployment，或「幫我改善所有東西」這種沒有完成線的任務。這些未必永遠不能用 AI，但它們不是學 loop 的安全起點。

**Jimmy 的結論：** 第一條 loop 不要揀最容易做，而要揀「即使它錯了，你也會在傷害前知道」的工作。可驗收，先有資格自動推進。

| 適合第一條 | 為何適合 | 暫時不應做甚麼 |
|---|---|---|
| 每週 public-source brief | input 與 source 可限定 | 不將 AI 當唯一事實來源 |
| internal content draft | 可由 owner review | 不自行公開發佈 |
| meeting action draft | 可對照原記錄 | 不直接 assign 高風險 action |
| FAQ 初步分類 | 低風險、可抽樣檢查 | 不直接對客外發 |
| fixed-format checklist | rule 清楚、容易驗收 | 不接 production system |

若你不知道工作錯了怎樣驗收，先不要開 loop。你缺的不是 automation 工具，而是 completion standard。

## AI loop 要有哪七條上線前檢查：trigger、source、rule、proof、state、handoff、cost

開始跑前，請回答：何時觸發？讀甚麼資料？跟甚麼規則？甚麼 output 證明它做對？狀態寫在哪裡？何時交給人或停止？成本／重試上限是多少？這些不是企業大工程，而是保護第一條 workflow 不會在無人看見時失控。

最難的通常是「output 怎樣才算對」。因為它逼你先定義好，而不是讓 AI 自己宣布完成。寫不出時，最好的決定是縮小 scope、把 artifact 做得更具體，或先保留人手 review；不要用更長 prompt 假裝已解決。

**Jimmy 的結論：** 七條上線前問題不是拖慢 loop，而是讓你有資格放心交出第一段工作。任何一條答不到，都應縮小而不是硬推。

| 上線前問題 | 合格答案例子 | 答不到時怎樣做 |
|---|---|---|
| Trigger | 每週一、approved input 齊才開始 | 先手動觸發 |
| Source | 固定公開來源清單 | 不讀不明／敏感資料 |
| Rule | 必有 source、unknown、owner | 寫 output schema |
| Proof | owner accepted checklist | 加 review step |
| State | run receipt 存在 work folder | 留簡單 log |
| Handoff／stop | 缺來源即交 data owner | 設 escalation |
| Cost／retry | 最多一次重跑，超過即停 | 不讓無限 loop |

這些檢查仍不代表可以開高權限 access。第一輪以 internal、draft-only、human-approved 為預設，先拿到可回看的 evidence。

## 一個公開安全例子：每週 briefing 怎樣由定時 prompt 變成可驗收 loop

假設團隊每週要把三份公開來源變成 internal briefing。定時 prompt 的做法，是每週一叫 AI「整理一下」，結果可能時有 source、時沒有 source，沒人知道上次是否已完成。loop 的做法則先定固定 trigger、approved source list、brief schema、owner review 和 receipt。

AI 只整理與起草；每項必有 source、unknown、owner 三格，缺一格就 flag，不自行外發。content owner review 後才標 accepted；receipt 記下資料缺漏、退回原因和本輪用時。若連續幾次都在同一處退回，才改 template 或 source rule；若 owner 缺席或材料未批准，loop 停止。

**Jimmy 的結論：** 這個例子沒有比定時 prompt 更花巧，但它多了 completion standard、state 和 stop line。正因如此，團隊才知道何時可以信、何時應改、何時不能推進。

| 原本 | Loop 設計 | 留下的證據 |
|---|---|---|
| 每週叫 AI 整理 | trigger＋approved sources | input receipt |
| 一段聊天 output | fixed briefing schema | reviewable artifact |
| 看到錯才手動救 | check 缺欄／unknown | returned reason |
| 沒人知是否完成 | owner accept／return | completion state |
| 下週重新猜 | receipt 指向下一輪 rule | repeatable workflow |

這是 synthetic 教學情境，不代表任何特定團隊已有同樣效果。它要展示的是 loop 如何把「AI 幫我做」變成「AI 在受控條件下完成一手工作」。

## 今日怎樣設計第一條 AI loop：先畫六步，再只自動化一個安全 action

揀一件本週已經重複做過的低風險工作，依序寫目的、input、AI action、check、修正／stop、handoff／state。寫到 check 時若你答不到「甚麼叫合格」，停在這裡；找 owner 一起定 artifact，不要急著開 automation。

接著只挑一個安全 action 交給 AI，例如把 approved material 整成 fixed draft。其餘包括 approval、外發、敏感決定仍由人保留。第一輪完成後，留一張 receipt，再看下一次是否少了重做、是否有人能接手、是否值得調整或繼續。

**Jimmy 的結論：** 第一條 AI loop 的成果不是一個會自己跑的 Agent，而是一段你不必逐句看著、但仍知道何時完成、何時出錯、誰會接手的工作。

| 今日動作 | 先寫甚麼 | 安全邊界 |
|---|---|---|
| 選工作 | 重複、低風險、可驗收 | 不用客戶／production task |
| 畫六步 | purpose 到 handoff | 不跳過 check |
| 定一個 rule | 甚麼叫合格 | 不把 judgment 硬卡死 |
| 指定 owner | 誰 review／stop | 不要「有人會看」 |
| 跑一次 | draft-only action | 不自行外發 |
| 留 receipt | pass／return／unknown／next fix | 下次不從零猜 |

想更深入理解 feedback loop 的設計，讀 [Loop 是回饋系統設計](./4-3-loop-engineering.md)；想先為重複錯建立可靠檢查，讀 [AI 點解反覆犯同一個錯](./練習-ai-repeats-the-same-mistake.md)。

> 你唔係 AI 用得少；你係由逐句餵 AI，走去設計一條有 check、有 state、可交接的工作循環。

← [返回 AI Builder](../README.md) · [按問題瀏覽](../../../學習地圖.md)
