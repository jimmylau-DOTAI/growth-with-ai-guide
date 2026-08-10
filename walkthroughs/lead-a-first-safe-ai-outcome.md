# 45 分鐘完成第一個安全 AI 成果：帶新手由聊天紀錄走到可 review 工作

剛開始用 AI 的人很容易帶走一段聊天紀錄：問過、答過、看起來有用，但回到工作後不知道能否交給人、哪裡要自己核對、下一次怎樣再做。若第一堂就展示很複雜的 agent、automation 或 integration，新手通常只會覺得自己追不上，而不是建立真正使用習慣。

第一個成果不需要大，也不應由 AI 自己完成所有事。它要用已批准、非敏感的材料，產出一份 internal draft；未知被標記；懂工作的人 review；最後留下下一輪只改善一格的記錄。這一小循環讓人第一次感到：AI 可以幫我起一版，而我知道自己仍要在哪裡負責。

Jimmy 的看法是：安全完成一次可 review 的真工作，比驚險地自動十次更能令 AI 變成習慣。45 分鐘的目標不是教晒工具，而是讓一個人由「我不知道怎樣開始」走到「我有一份可收貨 artifact，也知道下次怎樣跑」。

first safe outcome · AI training · AI adoption · human review · AI User · internal draft · facilitator · Hong Kong

| 45 分鐘的一格 | 要完成甚麼 | 留下甚麼 |
|---|---|---|
| 5 分鐘選工作 | 小而真、低風險、有 reviewer | work statement |
| 10 分鐘定 context | input、格式、不可猜、不可做 | context pack |
| 15 分鐘起草 | AI 做一份完整 internal draft | first artifact |
| 10 分鐘 review | 核對來源、unknown、scope、handoff | pass／revise／stop |
| 5 分鐘回看 | 找一個最常退回點 | next-run rule |
| 安全邊界 | 不外發、不接敏感資料、不寫 production | trust boundary |

## 第一個 AI 成果點解要「安全」：不是最小 demo，而是一個可收貨小循環

安全成果不是叫 AI 生成一段文字就算，也不是把 AI 接到所有系統。它是一段有頭有尾的工作：已批准、非敏感 input 進來；AI 起一份 internal draft；不知道的地方明確標記；有工作 owner review；最後記下下一輪要改善的地方。每個環節都讓學員看見 AI 的責任與人的責任。

把第一輪限定在 internal draft 很重要。新手還未學會 context、review 和 stop line，若直接要求對外發送、寫入 CRM、處理個人資料或作高後果決定，會把學習變成風險。安全不是降低標準，而是讓人有空間看見錯誤、提出問題、把 feedback 變成下一次方法。

**Jimmy 的結論：** 第一個 AI 成果不是「AI 做得最多」，而是「使用者能安全完成、有人能收貨、下次能再跑」。有這三樣，才是 adoption 的真正起點。

| 只是 demo | 安全成果 | 為何差很遠 |
|---|---|---|
| 一段漂亮 output | 可 review internal artifact | 有工作完成線 |
| AI 自己說完成 | owner accept／revise／stop | 有責任關口 |
| 沒說資料從哪裡來 | approved input boundary | 有安全範圍 |
| 錯了再算 | unknown／stop rule | 可從錯誤學習 |
| 做完便散 | 留 feedback rule | 下次不用從零猜 |

如果一個任務不能限制在 internal、draft-only、可 review 的範圍，先不要選它做第一個成果。縮小到整理三份公開資料，也比冒險大做更適合學習。

## 第一步怎樣揀工作：小而真、有完成線、錯了會知道

請參與者填一句：「我想把＿＿整理成＿＿，但只作 internal draft，完成後由＿＿review。」這句會迫使大家先定工作目的、artifact 和 owner，而不是一開始問 AI 可以做甚麼。適合的是公開資料整理、FAQ draft、brief、重點清單或分類表；它們有較清楚 input，也容易在 review 前發現問題。

不適合的是對外訊息、報價、合約、付款、客戶記錄、醫療／法律／財務判斷、未經批准公開發布，或「幫我做完整轉型計劃」這種沒有完成線的任務。這些不代表永遠不能用 AI，但不是讓新手第一次練責任分工的地方。

**Jimmy 的結論：** 第一個任務不必容易，但必須真、低風險、可驗收。若錯了連自己也不知道，便不是學習 AI workflow 的安全入口。

| 工作候選 | 是否適合第一輪 | 原因 |
|---|---|---|
| 已批准公開資料 → FAQ draft | 適合 | input 清楚、可 internal review |
| 固定格式 briefing | 適合 | artifact 與 owner 可定 |
| 對外客戶回覆 | 暫不適合 | 語氣／承諾風險高 |
| CRM 更新 | 暫不適合 | 私人資料與 production action |
| 合約／付款建議 | 暫不適合 | 高後果、需專業 judgment |
| 「幫我改善所有東西」 | 不適合 | 沒有 bounded artifact |

若學員帶來的工作太大，請幫他縮小，不是叫他換成純假題目。保留真摩擦、縮小 action，才會既貼近工作又安全。

## Context pack 怎樣令新手不靠猜：目標、approved input、格式和不可做要先寫清

很多新手覺得 AI 不穩，是因為每次只給一句任務，卻沒有說明給誰看、可用甚麼資料、要甚麼格式、哪些事絕不能猜或做。這些不需要寫成很長 prompt；四格 context pack 已足夠讓第一次 run 有清楚邊界。

目標讀者／使用情境告訴 AI artifact 為何存在；approved input 防止它用不該用的資料；輸出格式令 reviewer 知道怎樣收貨；不可猜／不可做則保護未知和 action boundary。學員也會從中學到：prompt 不是魔法句，而是一份小型工作合約。

**Jimmy 的結論：** Context pack 的目的不是把 AI 控制到完美，而是讓第一版錯得可見、邊界清楚、review 有地方開始。

| Context 格 | 要寫甚麼 | 安全例子 |
|---|---|---|
| 目標 | 誰為何要看這份 artifact | internal owner review FAQ |
| Approved input | 已獲批准的資料 | 兩頁公開活動資料 |
| 輸出格式 | 必有欄位／段落 | 問題、draft、source、unknown |
| 不可猜 | 缺資料時怎樣處理 | 標待確認，不補事實 |
| 不可做 | 本輪不能做的 action | 不外發、不讀私人檔案 |

如果一格答不到，先停在這裡和 owner 補清楚。這不是拖慢課堂，而是讓學員第一次知道安全使用 AI 本來就要先問哪些問題。

## AI 起第一版時要看甚麼：目標是讓未知可見，不是立即寫到完美

15 分鐘起草時，不要中途逐句搶回工作。先讓 AI 按 context pack 交一份完整 artifact，才看得到問題到底來自 input、格式、模型理解還是完成標準。可要求它列出用過的 input 和最不確定的地方，令未知不會藏在流暢語句裡。

第一版的責任不是「正確到可以直接用」，而是讓工作有一個可被 review 的形狀。若學員一看到不自然句子就不斷改 prompt，容易跳過更重要問題：來源足不足、未知有沒有標、scope 有沒有越界、下一手能否接。把文筆留到 review 之後，學習才會聚焦工作判斷。

**Jimmy 的結論：** 第一版不是 final answer；它是把真工作攤出來讓人看、讓人問、讓人修的 artifact。看得見未知，已經是成功的一半。

| AI 應交甚麼 | 為何重要 | 不應當成甚麼 |
|---|---|---|
| 完整 internal draft | reviewer 有可檢查對象 | 可直接外發的 final |
| 使用 input 清單 | 可回看材料邊界 | 所有資料都可信 |
| Unknown／待確認 | 不確定可被處理 | AI 失敗證明 |
| 格式化 artifact | 下一手可接 | 一段聊天紀錄 |
| 自我列出限制 | 方便 reviewer 問問題 | 自動 approval |

若 AI 補造資料或越界，先不要責怪學員。把它當 review 的實例：回到 context pack，補一條「不可猜」或縮小 input，下一輪再測。

## Human review 怎樣做才不是只改文筆：用 pass、revise、stop 判斷工作可否交接

reviewer 應先對照五件事：每項有沒有 approved evidence；不知道的地方有沒有清楚標記；有沒有越過本輪 scope 或新增 unsupported claim；格式是否讓下一手接得到；有沒有任何不應留在 draft 的資料或 action。這些問題把 review 由「寫得自然嗎」拉回工作責任。

review output 只選 pass、revise 或 stop，並寫一個具體理由。pass 代表這份 internal artifact 可供下一手使用，不代表已公開或已驗證商業結果；revise 代表知道要改哪一格；stop 代表 input、風險或 owner 條件未成立。三個選項讓學員知道停止也是成熟的工作決定。

**Jimmy 的結論：** Review 不是幫 AI 潤色，而是確認這份 artifact 能否安全接到下一手。清楚的 pass／revise／stop，令新手第一次看見 human judgment 放在哪裡。

| Review 問題 | Pass 的意思 | 不合格時怎樣做 |
|---|---|---|
| 有 approved evidence 嗎？ | 可回到來源 | 標 unknown／補資料 |
| 有沒有越界 claim？ | 只在本輪 scope | revise prompt／縮 scope |
| 格式可交接嗎？ | 下一手知道怎樣用 | 補 schema／checklist |
| 有敏感或不應留的內容嗎？ | 沒有越過 boundary | stop／移除 |
| owner 可接受嗎？ | internal draft 可收貨 | accept／return decision |

若沒有合適 reviewer，第一輪仍可以由學員自己對照 checklist，但不要假裝這等於對外批准。下次可找真正的工作 owner 加入。

## 5 分鐘回看怎樣讓學習留下：每次只改善一格，不要課後再加十個工具

最後請每位參與者只寫三行：這輪最有用的是甚麼；最常退回的原因是甚麼；下一輪只改善 context、format、review rule 或 handoff 的哪一格。保留 input 清單、instruction、draft 和 review note，這四樣已足夠成為下一次可靠的起點。

這一步把一次課堂由 demo 變成 learning loop。若你課後立刻加 API、agent 或新工具，學員反而會忘記最重要的 evidence。先讓同一條小工作再跑一次，看一條 feedback rule 有否減少重做，才知道應繼續、修正或換下一個 workflow。

**Jimmy 的結論：** 第一次安全成果的真正交付，不只是一份 draft，而是一條下一次不用從零開始的 feedback rule。每輪只改善一格，習慣才會長出來。

| 回看格 | 寫甚麼 | 下一輪只改甚麼 |
|---|---|---|
| 最有用 | 哪一手真的少了負擔 | 保留有用 template |
| 最常退回 | 來源、格式、unknown、scope？ | 一條 rule／context |
| Artifact | input、draft、review note 在哪 | 讓人可再跑 |
| Next move | context／format／review／handoff | 不同時加所有工具 |
| Decision | retain／revise／stop | 有 evidence 的下一步 |

若下一輪仍無法完成，不代表 AI 不適合。請用卡位診斷找最早出問題的格，而不是不斷增加教學內容。

## 一個公開安全例子：三份公開活動資料變成可 review FAQ draft

假設一位學員想把兩頁公開活動資料和一份公開 FAQ 整理成 internal FAQ draft。context pack 指定：只可使用三份公開資料；輸出是問題、建議答案、來源位置、待確認欄；不可補造資料、不可對外發送、不可讀私人檔案。AI 先交第一版並標出三個最不確定地方。

reviewer 發現兩題資料不足，要求保留 unknown；其餘題目格式可用，狀態是 revise 而不是 pass。回看時學員決定下一輪只改善 source mapping，不加新工具。這一次的成功不是 AI 寫了一篇完美 FAQ，而是學員、AI 和 reviewer 一起跑通了可安全改進的工作循環。

**Jimmy 的結論：** 這個例子讓新手看見：AI 的第一個價值是把工作攤出來、讓未知可見、讓人可以負責收貨，而不是取代最後決定。

| 時間 | 做甚麼 | 留下甚麼 |
|---|---|---|
| 5 分鐘 | 選 FAQ draft task | bounded work statement |
| 10 分鐘 | 寫 context pack | input／format／boundary |
| 15 分鐘 | 起 internal draft | first artifact＋unknown |
| 10 分鐘 | reviewer pass／revise／stop | review note |
| 5 分鐘 | 選一格改進 | next-run rule |

這是 synthetic 教學情境，不代表任何客戶、活動或 DotAI training 已有特定效果。它示範的是如何帶人安全完成第一次 AI 工作。

## 今日怎樣帶一個人完成第一個安全成果：不要追求炫，先讓他有一份可收貨 draft

邀請一位同事、學生或自己，選一件已反覆出現、可限制在 45 分鐘內的低風險工作。先寫工作句子與四格 context pack，再讓 AI 起第一版；最後用 pass／revise／stop 做 review，留下四份材料：input 清單、instruction、draft、review note。這就是一次完整 first safe outcome。

未完成這一輪前，不要急著教 automation、API、team agent 或 production integration。這些可能是後面的路，但新手首先要建立的是「我知道怎樣安全交出一件工作」的信心和方法。第一個 artifact 有 owner、有邊界、有下一輪，才值得往 AI Super User 或 Operator 走。

**Jimmy 的結論：** 帶人學 AI 的第一步不是讓他驚嘆工具，而是讓他安全完成一次真工作、看懂自己要 review 甚麼、並帶走下一次更穩的開始。

| 開始前自查 | 合格訊號 | 不合格時怎樣縮小 |
|---|---|---|
| Task | internal、低風險、可驗收 | 只整理公開三頁資料 |
| Input | 已批准且非敏感 | 改 synthetic example |
| Artifact | 可交給 reviewer | 定一張固定格式 |
| Review | 有 owner／checklist | 暫不外發 |
| Next run | 只改一格 | 留 feedback note |

想在一次練習後設計下一輪 pilot，讀 [設計一個真的學到東西的 adoption pilot](../chapters/5-6-design-adoption-pilot.md)；若學員卡住，讀 [AI adoption 點解推唔郁](diagnose-an-ai-adoption-bottleneck.md)。

> 安全完成一次可 review 的真工作，比驚險地自動十次更能令 AI 變成習慣。

← [返回 AI Value Creator](../05-ai-value-creator.md) · [按問題瀏覽](../BROWSE.md)
