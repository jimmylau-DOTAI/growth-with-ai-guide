# AI adoption 點解推唔郁：用五格診斷真卡位，唔好每次都叫人再學 prompt

當同事、學生或團隊說「AI 用唔到」「試過但冇用」「大家唔肯用」，最容易的反應是再教 prompt、再買工具、再安排一場分享。但同一句「用唔到」背後可能是五種完全不同的問題：技術條件不成立、workflow 未拆清、使用者未能安全完成、看不到改變理由，或者根本沒有治理和 owner。

如果不先找最早壞掉的一格，介入很容易越做越多、越做越不對。資料格式根本無法處理，卻叫人多練 prompt；工作沒有 artifact，卻起 agent；人不知道誰收貨，卻怪他抗拒改變。這不只浪費時間，也會令團隊誤以為 AI adoption 很複雜或不可靠。

Jimmy 的看法是：AI 用不動不是結論，先找出它最早卡在可行性、workflow、能力、意欲還是治理，再只設計一個最小介入。五格不是用來給人貼標籤，而是幫你把下一步拉回真工作、真 evidence 和安全範圍。

AI adoption · adoption diagnosis · workflow bottleneck · AI training · governance · AI Value Creator · pilot · Hong Kong

| 診斷五格 | 真正要問甚麼 | 最小介入留下甚麼 |
|---|---|---|
| 可行性 | 資料、語言、權限、工具是否能處理？ | input test |
| Workflow | input、artifact、handoff 是否清楚？ | work map |
| 能力 | 有沒有 context、sample、reviewer？ | first safe outcome |
| 意欲 | 使用者為何值得改、最怕甚麼？ | low-risk choice |
| 治理 | 可讀甚麼、誰 review、何時停？ | control card |
| Decision | 最早卡位是否已移動？ | next review receipt |

## AI adoption 診斷點解一定要用真工作：沒有工作只會變成人格測驗

不要先問「你對 AI 有沒有興趣」「你是不是抗拒改變」。這些問題太大，也很容易令使用者覺得被評價。請他選一件最近真的卡住、重做、退回或不敢交出去的工作：原本 input 是甚麼？想交甚麼 artifact？最後在哪一手停下？誰原本要收貨？

真工作會把討論由抽象態度拉回可觀察 evidence。有人可能很有興趣，但手上沒有可用材料；有人可能懂工具，但工作根本未拆；也有人 output 沒問題，只是沒有 owner 承擔下一步。只有看到工作，才能知道下一個小實驗應改甚麼。

**Jimmy 的結論：** Adoption 不是人格測驗。先拿一條最近失敗或停住的真工作，才有可能診斷到真正卡位。

| 不要只問 | 改問甚麼 | 為何較有用 |
|---|---|---|
| 你喜不喜歡 AI？ | 最近哪件工作想試但沒完成？ | 有具體 evidence |
| 你會不會 prompt？ | input、artifact、review 是甚麼？ | 看 workflow 是否成立 |
| 你抗不抗拒改變？ | 最怕哪種錯／後果？ | 看意欲與治理 |
| 工具夠不夠強？ | 哪一手最常重做？ | 找值得介入的範圍 |

如果對方未能提出一件低風險工作，先不用做 adoption diagnosis。先找一個公開或 synthetic safe task，讓他有一段可討論的 workflow。

## AI 可行性卡住時怎樣處理：先驗證條件，不要用更多 prompt 掩蓋

可行性是最早的一格：必要資料格式、語言、網絡、權限、工具能力是否真的能處理？若 input 是掃描得很差的圖片、資料根本無法取得、或系統沒有任何合法讀取方法，再長 prompt 也不能令 workflow 可靠。這不是使用者能力不足，而是基本條件未成立。

最小介入應是受控 input test：用一份已批准公開或 synthetic 資料，驗證工具能否讀、能否保留關鍵欄位、是否需要人轉換格式。結果若不行，就改資料條件、換方法或停止；不要因為已買了工具而強行繼續。

**Jimmy 的結論：** 可行性未成立時，下一步是驗證 input 和權限，不是教更花巧 prompt。先知道能不能做，才值得討論怎樣做得好。

| 可行性警號 | 不要做 | 最小介入 |
|---|---|---|
| 資料格式亂／不可讀 | 直接開 automation | 用 approved sample 測一次 |
| 沒有合法 access | 叫人找方法繞過 | 定 data owner 與 permission |
| 語言／欄位不一致 | 假裝模型會自動修好 | 定 input schema／轉換 |
| 工具能力未測 | 先承諾 workflow | 做 draft-only proof of fit |

可行性 test 通過也不代表 adoption 已完成。它只代表你可以走到下一格：這件工作本身是否被拆得清楚。

## AI workflow 卡住時怎樣處理：先畫 input、artifact、handoff，唔好急住建 Agent

很多人說「AI 做不到」，其實是任務只被說成「幫我做好」。沒有清楚 input、決策、output 和 handoff，AI 和人都不知道完成是甚麼。你可能得到一段看似合理文字，但沒有 artifact、owner 或下一步，任何人都難以判斷它有沒有幫到真工作。

workflow 診斷的最小介入很小：只畫三格，input → artifact → handoff。例如已批准公開資料 → internal briefing draft → content owner review。這張圖會立刻暴露哪些材料未定、哪一手其實仍需人判斷、以及甚麼位置可安全先交 AI。

**Jimmy 的結論：** workflow 未拆清時，加 prompt、template 或 Agent 都太早。先畫出一條人和 AI 都看得見的工作路徑，才能知道哪一手值得改善。

| Workflow 警號 | 真正缺甚麼 | 最小介入 |
|---|---|---|
| 「幫我做好」 | 沒有完成定義 | 寫 artifact 名稱 |
| output 被反覆退回 | handoff 不清 | 指定 reviewer 與 checklist |
| 每次 input 都不同 | source boundary 未定 | 列 approved input |
| AI 做完沒下一步 | owner 未定 | 寫 accept／revise／stop |

若三格圖仍畫不出，先不要建 Agent。請工作 owner 先說明目標和交付，因為這一部分不能由模型替人發明。

## AI 能力卡住時怎樣處理：先帶人完成一個安全成果，而不是派工具清單

workflow 已經清楚，但使用者可能仍不知怎樣給 context、怎樣選材料、怎樣看 output，或找不到 reviewer。這不是他不願意用，而是還未完成過一次安全小循環。若你此時只派一堆 tool list 或萬用 prompt，他回到工作仍不知第一步怎樣做。

最小介入是一個 first safe outcome：用已批准、非敏感 input，讓他只起一份 internal draft；unknown 要標記，由懂工作的人 review，最後留下下一輪只改一格的 note。這讓使用者第一次看見自己可以安全完成、可以被收貨，也知道錯不等於失敗。

**Jimmy 的結論：** 能力不足不是「不懂很多 AI 功能」，而是未能安全跑完一條工作。先給第一個可 review outcome，才能讓學習進入真採用。

| 能力警號 | 不要做 | 最小介入 |
|---|---|---|
| 不知怎樣開始 | 再講十個功能 | 給 use-case trigger |
| 不敢交 output | 叫他直接外發 | internal draft 加 reviewer |
| 每次從零猜 | 只給一條 prompt | context pack／template |
| 不知錯在哪 | 只說多試 | review checklist／feedback note |

第一輪不接私人資料、production 或高後果 action。學會一個安全循環，比讓人表面上「用了 AI」更有價值。

## AI 意欲卡住時怎樣處理：不要叫人接受改變，先讓他選一個值得試的低風險痛點

意欲不是「這個人懶不懶」或「喜不喜歡新科技」。有人看不到改變的理由，可能因為現有流程雖慢但可預測；有人怕一旦出錯責任落在自己；也有人已經很忙，無法負擔學一條看不到成果的新做法。若只說 AI 很重要，通常只會增加壓力。

先問他最煩、但又低風險的一手是甚麼，以及最怕哪種後果。讓他自己選一個可退出的小試行，保留 human review 和明確 stop line。當第一輪確實少了一次重做、或至少讓未知更可見，意欲才有可能由外在要求變成自己的工作動機。

**Jimmy 的結論：** 意欲不是靠說服出來，而是靠安全、相關、可退回的小成果建立。先讓人選一條自己的痛點，而不是逼他接受一個大計劃。

| 使用者說法 | 可能在保護甚麼 | 較好的介入 |
|---|---|---|
| 「我沒時間學」 | 看不到短期工作價值 | 選一件最常重做小任務 |
| 「出錯誰負責？」 | 沒有 review／stop | draft-only + named owner |
| 「以前都做到」 | 改變成本大於預期好處 | 比較一個重做成本 |
| 「這不關我事」 | 沒有角色相關入口 | 選他自己 workflow 的 pain |

不要把意欲問題當心理或 HR 診斷。它只是在問：這個人是否有一條安全、值得、可掌握的工作路徑開始。

## AI 治理卡住時怎樣處理：涉及敏感或不可逆 action 時，責任不能留白

只要 workflow 涉及對外訊息、敏感資料、金錢、不可逆 action 或 production system，治理不是最後才加的文件。使用者即使願意用、工具也做得到，仍需要知道可讀甚麼、不可做甚麼、誰 review、甚麼情況停、誰處理例外。這些空白會令最願意嘗試的人也不敢真的把工作交出去。

最小介入是一張 control card：read、draft、review、stop。它不需先包含所有企業政策，只要把第一輪範圍守住。例如只讀 approved public sources、只出 internal draft、由 content owner review、任何個人資料或需要外發的情況一律停止。這樣你才能安全判斷 workflow 是否有價值。

**Jimmy 的結論：** 治理不是等 scale 才做；一旦有敏感性或不可逆後果，它就是 adoption 的前提。責任未寫清，就不要提高 AI 的 action scope。

| 治理警號 | 不要做 | 最小介入 |
|---|---|---|
| 想接 CRM／私人檔案 | 先開所有 access | approved input boundary |
| 想自動外發 | 以「之後有人看」代替 approval | draft-only + owner |
| 出錯不知找誰 | 讓 Agent 自己 retry 到成功 | stop／escalation owner |
| 沒有 run evidence | 只靠 screenshot 交代 | receipt／audit note |

治理不等於不能開始。它反而讓你能在小範圍、更低風險地開始，並知道何時值得擴大。

## 一個公開安全例子：AI 整理資料「不準」其實先卡在 workflow，不是模型

有人說：「AI 整理資料不準，所以我不用。」你先問：資料是否有固定格式？它要整理成甚麼 artifact？誰知道怎樣收貨？他最擔心錯甚麼？若錯了會否涉及敏感資料或外發？假設答案是資料散、沒有固定欄位，也沒有 reviewer，最早壞掉的一格其實是 workflow。

此時最小介入不是換模型或再買工具，而是選三份已批准公開資料，定一張欄位表，讓 AI 只起 internal draft，再由 owner 看一次。若這一輪可被收貨，才往能力、意欲和治理走；若連三格 workflow 都未能成立，就沒有理由把問題推給 AI。

**Jimmy 的結論：** 「AI 不準」常是一個症狀，不是一個診斷。先找到最早不成立的一格，才知道該修資料、工作、學習、意欲還是治理。

| 問到的答案 | 最早卡位 | 下一步 |
|---|---|---|
| 資料格式工具讀不到 | 可行性 | sample input test |
| 沒人講得出交付是甚麼 | workflow | input → artifact → handoff |
| 沒人敢 review | 能力 | safe outcome 練習 |
| 使用者覺得不值得 | 意欲 | 選自己低風險 pain |
| 涉及私人資料／外發 | 治理 | read／draft／review／stop card |

這是 synthetic 教學情境，不代表任何特定團隊或工具已有相同問題。它示範的是診斷次序，讓你不會每次都用「再學 prompt」當預設答案。

## 今日怎樣做 adoption diagnosis：只寫最早卡位和一個最小介入

選一件最近失敗、被退回或一直沒有被使用的工作，依次走五格。每格只記你實際看到的 evidence，不要猜人性格或假設工具一定做不到。找到最早一格後，下一步只寫一個最小介入：input test、三格 work map、safe outcome、低風險選擇或 control card。

然後指定 owner 和 review 日期。下一次回看時只問：最早卡位有沒有移動？若沒有，再檢查該格的 evidence；若已移動，才走到下一格。不要一次把五格全變成巨大轉型計劃，因為那會失去最重要的診斷焦點。

**Jimmy 的結論：** AI adoption diagnosis 的交付不是一份大報告，而是一條真工作、一個最早卡位、一個安全最小介入和一次回看。這才令團隊能由問題走到可驗證的改變。

| 診斷記錄 | 寫甚麼 | 為何留下 |
|---|---|---|
| Work symptom | 最近哪一件工作卡住 | 保持在真情境 |
| Earliest blocker | 五格中最早不成立的一格 | 防止解錯問題 |
| Evidence seen | 你看到／聽到甚麼 | 不靠假設 |
| One intervention | 只改一個小地方 | 控制風險 |
| Owner／review date | 誰跟進、何時回看 | 形成 learning loop |
| Decision | retain／revise／stop／next gate | 有下一步而非空談 |

想帶人完成第一個安全 AI 成果，讀 [45 分鐘完成第一個安全 AI 成果](lead-a-first-safe-ai-outcome.md)；想更深入理解五格背後的判斷，讀 [先診斷 adoption 卡位](../chapters/5-13-diagnose-adoption-bottleneck.md)。

> AI 用唔到不是結論；先找出它最早壞在哪一格，才知道下一步值得修甚麼。

← [返回 AI Value Creator](../05-ai-value-creator.md) · [按問題瀏覽](../BROWSE.md)
