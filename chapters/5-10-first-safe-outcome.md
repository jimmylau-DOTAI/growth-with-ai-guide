# 教 AI 唔好先派工具清單：用第一個安全成果帶人開始

工具介紹很容易做：逐個按鈕示範、派一張 prompt 清單、叫大家回去試。可是學員一回到真工作，通常仍不知道第一件可以交給 AI 的事是甚麼，也不敢判斷結果是否可用。於是課堂很熱鬧，日常工作卻沒有改。

第一個 AI 成果不應是 demo、證書或一段看起來很厲害的聊天答案。它應是一件學員本來會做、錯了仍可安全修正、又有人可以 review 的工作 artifact。這令他第一次親手看見 AI 工作不是 prompt 本身，而是 input、context、邊界、artifact 和 check 的組合。

Jimmy 的看法是：AI 教育唔係塞工具清單，而係帶人安全地交出第一件真工作，然後由 review 決定下一步。第一個成果越小、越真、越可回看，越容易讓學員知道自己下一步應補 context、workflow、quality gate，還是根本先不應交給 AI。

AI 實戰 · AI Value Creator · onboarding · first safe outcome · AI learning · review · workflow

| 第一個安全成果的格 | 它解決甚麼問題 | 留下甚麼 |
|---|---|---|
| 熟悉小工作 | 不由抽象工具開始 | 一件本來就要做的任務 |
| 安全 input | 不為了真實感用敏感資料 | 公開、已批准或 synthetic 材料 |
| 最小 context | 不令 AI 自己猜邊界 | 目標、格式、未知與限制 |
| Review artifact | 不只在 chat 看一次 | 可保存的 draft、table 或 map |
| Feedback decision | 不只說好／不好 | 下一步補甚麼的 evidence |

## 第一堂點解不應先派工具清單：知道功能不等於知道第一件真工作

工具清單可以讓新手知道市場上有很多選擇，但它很少解答他最需要的問題：我明天返工／上堂，哪一件工作適合先試？工具愈多，初學者反而愈容易在選擇、帳號和功能之間打轉，最後沒有完成任何能留低的東西。

第一個工作成果會反過來告訴他需要甚麼工具與能力。若他想把公開文章整理成 brief，便會知道 source、unknown、格式和 review 比模型名字更重要；若他連這些都未能說清，現在最需要的可能是工作設計，而不是另一個 app。

**Jimmy 的結論：** 初學 AI 的第一個問題不應是「用哪個工具」，而應是「我可以安全交出哪一件小工作」。完成一個可 review artifact，比收藏十個工具更能建立真能力。

| 工具清單式開始 | 容易發生甚麼 | 成果式開始 |
|---|---|---|
| 先介紹十個 app | 學員不知哪個適合自己 | 先選一件熟悉小工作 |
| 先示範功能 | 看完沒有可交付物 | 設一份可 review artifact |
| 先給萬用 prompt | 不知可用甚麼資料 | 寫安全 input 與 context |
| 先叫大家自行試 | 出錯沒人知道怎修 | 定 reviewer 與 feedback |
| 先追 output 漂亮 | 忽略未知與邊界 | 留 source／unknown receipt |

一個安全成果不排斥工具地圖；它只是把工具放到正確位置：完成第一件真工作後，再根據實際卡點補工具和 Skills。

## 「小而真」的工作怎樣選：熟悉、低風險、可修正，比大而炫更適合起步

好的第一個任務通常是學員本來就會做的工作，例如整理一段公開資料、起一份 internal brief、做一張 FAQ draft、準備會議議程草稿，或畫出一條 workflow。這些工作有清楚目的，完成後也容易知道是否真的幫到手；它們不需要一開始就連接外部系統或改變他人的資料。

不要因為想證明 AI 很強，就挑一個最大或最高風險的任務。新手若第一次就要處理客戶資料、對外回覆、付款、人事或 production 資料，會同時面對工具、資料、權限、責任和情緒壓力；即使 output 出問題，也很難知道該修哪一格。

**Jimmy 的結論：** 第一個成果不是愈大愈有說服力。選一件小而真、錯了可修、有人可 review 的工作，才會讓學員真正學到怎樣把 AI 放進 workflow。

| 適合起步的任務 | 為何適合 | 暫時不應選 |
|---|---|---|
| 公開文章變 internal brief | source 可回看、可標未知 | 客戶建議書或合約 |
| 已批准 FAQ 變 draft table | 格式固定、可 review | 直接對外 customer reply |
| 會議議程草稿 | 可由 owner 修正 | 代替人作關鍵決策 |
| workflow map | 不需動真資料 | 直接連接 production 系統 |
| 公開內容 outline | 可保留在 internal draft | 自動公開／排程發文 |

如果學員想做的工作很大，先把它拆到一個人類可以在五至十分鐘內 review 的 artifact。這會比一次「AI 大專案」更快讓人獲得正確 feedback。

## 安全 input 與最小 context 點樣令新手敢試：不靠敏感資料製造真實感

很多人以為一定要用真實公司或客戶資料，AI 練習才有意思；其實第一輪最需要的是安全和可學習，不是最大真實感。公開、已批准或去識別化材料已足夠讓學員練習 source、格式、unknown 和 review；而且即使 output 出錯，也不會讓他因恐懼而不敢嘗試。

最小 context 要說清目標、可用材料、輸出格式、不能猜甚麼和誰 review。它不是把 prompt 寫得很長，而是讓 AI 不必自行推測範圍。資料不足時，AI 應標 unknown，學員也因此學會「不知道」是正確的工作狀態，不是失敗。

**Jimmy 的結論：** 安全 input 加最小 context，令新手可以在不冒不必要風險下看見 AI 的真限制。第一輪的成功不是生成最像真人的答案，而是能正確留低未知與邊界。

| Context 格 | 你要寫甚麼 | 安全起點 |
|---|---|---|
| 目標 | 要交甚麼小 artifact | 一頁 internal brief |
| Input | 只可用哪些材料 | 一篇公開文章 |
| 格式 | 人怎樣 review | 主張、link、unknown、問題 |
| 不可做 | 不能猜、不能外發甚麼 | 不補事實、不寫客戶建議 |
| Owner | 誰會看結果 | 同事、老師或 content owner |

第一輪不要用客戶、學生、人事、付款、CRM、未公開 offer、credentials 或 production data 來測試「AI 夠不夠真」。那些資料需要另行權限、治理與高得多的 review 門檻。

## Review artifact 點樣令學習留下來：不要只在 chat 視窗看一眼

一段聊天可以很快消失，也難以讓下一手比較。當學員把結果存成一頁 brief、一張 FAQ table、一份議程 draft 或 workflow map，reviewer 才可以逐格指出哪裏可用、哪裏需要來源、哪裏不該猜。artifact 令他第一次接觸真正的交付與 revision，而不只是得到一段答案。

review 要有具體問題。不是只說「幾好」或「再執下」，而是檢查 input 有沒有被正確使用、格式是否齊、未知是否標出、是否超出 scope。這些 feedback 會告訴學員下一輪要補 context、例子、rule 還是手動 review，而不是讓他以為只要換 prompt。

**Jimmy 的結論：** 不是有 output 就代表學會；當一份 artifact 能被人按標準收貨、退回和修正，學員才開始理解 AI 工作的完整形狀。

| Artifact | Reviewer 可怎樣看 | 能學到甚麼 |
|---|---|---|
| Public-source brief | claim 是否有 link、未知有否標示 | source 與 evidence |
| FAQ draft | 每題是否對應批准資料 | 格式與內容邊界 |
| Meeting agenda draft | 議題是否符合目標與時間 | task contract |
| Workflow map | owner、handoff、stop 是否清楚 | 工作設計 |
| Review receipt | pass／revise／unknown／stop | 如何處理不確定 |

把 artifact 和 feedback 留下來，下一次練習才不會由零開始。它也可成為 AI Super User、Operator 或 Builder 下一步要用的 context 和 workflow evidence。

## Feedback 怎樣決定第二步：找出是 context、workflow、quality gate 還是工具不適合

第一個成果 review 完後，不要只把結果分成好／不好。更有用的是找出問題在哪一層：是否沒有足夠 context？輸出格式和 quality bar 是否未定？任務是否其實有很多 handoff 要先畫 workflow？AI 是否在未知時沒有停？又或者工具在這個資料格式或語言情境下根本不適合？

不同答案帶來不同第二步。context 不足，就加例子、source rule 或 feedback；工作重複但交接混亂，就寫 current state 和 handoff；AI 容易越界，就加 stop line 和 review；若技術不可行或治理成本太高，停止或換方案也是成熟選擇。

**Jimmy 的結論：** 第一個安全成果的最大價值，不是一定要好用，而是令你知道第二步應補甚麼。review 把新手的「AI 好像不行」變成可修正的工作判斷。

| Review 發現 | 最可能缺少甚麼 | 下一步 |
|---|---|---|
| 每次格式不一 | context／template | 補例子與 output rule |
| claim 沒有來源 | source boundary | 加 link／unknown checklist |
| 另一個人接不到 | workflow／handoff | 寫 current-state note |
| AI 擅自補事實 | stop line／review | 要求 unknown receipt |
| 產出後仍要大改 | task 太大或 quality bar 不清 | 縮小 scope、定 rubric |
| 工具根本不支援 | 技術可行性 | stop、換工具或保持手動 |

好的 feedback 不會令學員覺得「我用錯工具」，而是讓他看見 AI 協作本來就包含 input、artifact、review 與改進。

## 一個公開安全例子：由一篇公開政策文章完成第一份 research brief

假設一個團隊想練習 AI research，但不接觸任何內部資料。每人選一篇公開政策文章，AI 只可產出一頁 internal brief：主要主張、來源連結、未知和三條待確認問題。它不能補造事實、寫客戶建議或對外發送。

reviewer 檢查每個 claim 是否能回到文章、unknown 有沒有標示、是否超出作者原意。然後不只評分，而是問：問題是材料不足、格式不清、還是學員還未把推論與事實分開？下一輪才根據 evidence 決定加 context pack、加 review rubric，還是把同類工作 map 成 workflow。

**Jimmy 的結論：** 這件成果很小，但讓人第一次看到：AI 工作不只得一段 prompt，而是 input、邊界、artifact 和 check。學員完成的不是一份漂亮摘要，而是一份可以被真正 review 的工作。

| 成果格 | 例子中的做法 | 留下甚麼 |
|---|---|---|
| 小工作 | 公開文章整理成 brief | 一頁 draft |
| 安全 input | 一篇公開政策文章 | source link |
| Context | claim、link、unknown、問題格式 | task card |
| Artifact | internal research brief | 可保存文檔 |
| Review | source／unknown checklist | feedback receipt |
| 下一步 | 補 context、workflow 或 rule | 下一輪調整 |

這個例子是公開、低風險的學習情境，不代表任何研究、政策或客戶建議已被獨立驗證，亦不允許 AI 接觸私人資料、對外發送或 production 系統。

## 今日怎樣帶人開始：四句清楚，就做一個 draft；四句未清楚，就先補工作設計

找一位想開始用 AI 的人，請他填四句：我本來會做的低風險工作、今次只可用的安全材料、我要交的 artifact、誰會 review以及甚麼情況要停。四句清楚，就做一個小 draft；四句任何一格答不到，就先補清楚，毋須急著教第二個工具。

完成後只做一次短 review：哪一格最需要修？讓學員自己說回 input、artifact、unknown 和 review。這比讓他展示十個 prompt 更能看出是否真的開始建立能力，也更容易決定他應讀 AI Super User、AI Operator、AI Builder 還是繼續多跑一次相同小工作。

**Jimmy 的結論：** AI 教育唔係塞工具清單；係帶人安全地交出第一件真工作，然後由 review 決定下一步。四句清楚，就有安全起點；四句未清楚，就先做工作設計。

| 今日四句 | 你要回答甚麼 | 安全起點 |
|---|---|---|
| 小工作 | 本來會做的低風險任務 | 公開文章 brief |
| 安全材料 | 今次只可用甚麼 | 一篇公開原文 |
| Artifact | 要交甚麼給 reviewer | claim／link／unknown 表 |
| Review／stop | 誰看、何時不能繼續 | 老師／owner，缺 evidence 即停 |
| Feedback | 從結果學到甚麼 | context 還是 rule 不足 |

未完成第一個可 review artifact 前，不要以為必須學晒所有工具，也不要把新手直接帶到外部發送、客戶／私人資料、公開設定或不可逆 production 工作。下一步可看 [如何判斷下一個 stage readiness](5-11-next-stage-readiness.md)。

> AI 教育唔係塞工具清單；係帶人安全地交出第一件真工作，然後由 review 決定下一步。

← [返回 AI Value Creator](../05-ai-value-creator.md) · [按問題瀏覽](../BROWSE.md)
