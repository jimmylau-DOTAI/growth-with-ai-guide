# AI 每次都犯同一種錯？唔好只改稿，將 feedback 變成下一次可用的 rule

你可能已經很習慣改 AI 初稿：換一個開場、刪一個誇張說法、補回未確認資料、調整格式。問題是改完後，那個原因往往只留在你腦裡或某一段 chat；下一次同類工作來到，AI 又在同一位置猜錯，你又花一次時間重新解釋。

最自然的反應是把所有 feedback 都儲進 memory 或 custom instruction。但這會很快造成另一個問題：今次日期、一次性版面要求、某個人的偏好，被錯當成永遠規則，越積越多互相矛盾的指示，AI 反而更難知道今次真正應聽哪一條。

Jimmy 的判斷是：不是每句 feedback 都值得留下。真正可累積的是反覆出現、講得出 why、知道何時適用也知道何時應退休的判斷。它應以一張小小的 reference card 留給下一次工作，而不是把整段私人 chat 當成 AI 記憶。

| 你看到的 feedback | 它應去哪里 | 留下甚麼 |
|---|---|---|
| 今次才需要的 edit | 本輪 draft／task pack | 一次性修正 |
| 相近工作反覆出現的問題 | Rule 候選 | 可 review reference card |
| 工作要求已經改了 | 更新當前 task | 新的本輪條件 |
| 未確認、私人或敏感意見 | 受控原始紀錄 | 不進公開／長期 context |

## AI feedback 為甚麼不能一改完就全部存進 memory？

每一次修改看起來都好像有用，但它們的壽命不同。「今次把日期改成星期四」只屬於本輪 deliverable；「新手教學要先說讀者的真工作」則可能在多篇相近內容都成立。若不先分辨，你會把短期細節污染成長期指令，未來反而要花時間清理 AI 為何仍在跟舊要求做。

還有一些 feedback 根本不適合離開原來情境，例如私人 reviewer 的語氣意見、未公開客戶背景、尚未確認的方向。它們可以留在受控工作資料裡，但不應被包裝成普遍 rule，更不應因「要令 AI 更懂我」而搬進公開或共享位置。

**Jimmy 的結論：** Feedback 的第一步不是儲存，而是判斷它屬於一次性 edit、重複 pattern、changed requirement，還是根本不應離開原來情境。

| 類型 | 典型例子 | 正確處理 |
|---|---|---|
| 一次性 edit | 今次縮短標題、改某日日期 | 只留本輪 draft |
| 重複 pattern | 無 evidence 的成效主張常被寫成保證 | 收集至少兩次 evidence，才候選為 rule |
| Changed requirement | 課程改了目標讀者或本輪格式 | 更新 task pack，不讓舊 rule 蓋過新需要 |
| 私人／未確認資料 | reviewer 私人看法、客戶內容 | 留在受控紀錄，不存進通用 context |

先做這個分流，才不會把「AI 越用越懂我」誤解成「把所有改動一股腦塞給 AI」。

## AI feedback 至少出現幾多次，才值得由一次 edit 變成 rule？

沒有一個魔法數字能保證 rule 永遠正確，但第一輪至少要看到相近修正出現兩次，並且能說明背後是同一個工作問題。這是很低的門檻，目的不是做統計，而是防止你因為一次不喜歡某句字便把個人當日偏好寫成永久指示。

除了重複，還要看它是否可解釋。你若只記得「這樣不喜歡」，AI 下次只會模仿表面詞句；你若能說「先講讀者要完成甚麼，因為新手要先判斷與自己有何關係」，你才有一條能遷移到相近工作、又能在不適用時被人挑戰的 rule。

**Jimmy 的結論：** 一條 feedback 值得升成 rule，至少要同時有重複 evidence、可說明的 why，和一個能被限定的適用範圍。

| 看到的情況 | 是否候選 rule | 原因 |
|---|---|---|
| 今次要把標題縮短 | 否 | 版面需要可能一次性 |
| 兩篇新手稿都先講工具而忘了工作 | 是，先寫 why | 同一類讀者卡位反覆出現 |
| 一次資料不足卻寫成保證 | 先觀察 | 需看是否屬通用 evidence boundary |
| 多次將 unknown 寫成事實 | 是 | 可直接影響安全與 review |

不要為湊數而硬把兩個不同情況湊在一起。所謂重複，必須是同一類工作、同一類判斷真的再次出現。

## AI feedback 怎樣由「改了甚麼」寫成「為甚麼下次要這樣做」？

只記 edit，通常是「刪走第一段」「語氣不要太闊」「加一個表格」。這些紀錄對當下改稿有用，卻沒有告訴下一位人或 AI：第一段為何不對、語氣會造成甚麼後果、表格其實在幫誰檢查甚麼。沒有 why，AI 只能盲目複製一個表面動作。

要找 why，可以問：這個 edit 原本保護哪個讀者、哪個 evidence 邊界、哪個完成線？它若不適用時又會怎樣？答案通常讓 rule 變短而更準，因為你由「我改過這句」走到「我正在避免哪一種工作失敗」。

**Jimmy 的結論：** 可重用 rule 不應只描述改法；它要說清這個改法保護甚麼判斷，才知道何時適用、何時不適用。

| 只記 edit | 寫成有 why 的 rule |
|---|---|
| 刪走第一段 | 新手教學先說讀者要完成的工作，再介紹工具；因為讀者要先判斷此事是否與自己有關 |
| 不要誇張 | 沒有可核對 evidence 時，不把推測寫成成效或保證；因為 reviewer 不能為它負責 |
| 加待確認 | 資料不足會改變結論時，標 unknown 並 ask owner；因為 AI 不應自行補授權或事實 |

```text
原本改了甚麼：＿＿＿＿＿＿＿＿＿＿
這個 edit 避免了甚麼失敗：＿＿＿＿＿＿＿＿＿＿
下次在甚麼工作可先檢查它：＿＿＿＿＿＿＿＿＿＿
```

這個三行轉換，讓你把一次文字修改變成一條人與 AI 都能理解的工作判斷。

## AI rule 的 scope 要怎樣定，先不會把一個偏好硬套全部工作？

同一條 rule 在不同工作可能完全不適用。新手 teaching opening 先說工作摩擦很有用，技術排錯紀錄卻可能要先列故障現象和 evidence；「保持親切」適合某類對外草稿，未必適合需要精確責任分界的內部文件。沒有 scope 的 rule 很容易由好習慣變成噪音。

寫 scope 時，不必列盡每一個例外，只要能說清它針對哪類讀者、哪種 artifact 或哪個風險。再加一個 owner，表示誰有權確認、修改或退休這條 rule；這樣它不是一段無主的 AI 指令，而是可被現實工作更新的判斷。

**Jimmy 的結論：** Rule 愈能說清適用與不適用，愈不會在其他工作裡變成僵硬模板。

| Rule 部分 | 應怎樣寫 | 例子 |
|---|---|---|
| 適用於 | 讀者／artifact／情境 | 新手 AI 教學的 internal briefing 開場 |
| 不適用於 | 明顯不同的工作 | 技術 incident report、熟手操作手冊 |
| Owner | 誰能修訂或拒絕 | 內容／課程 owner |
| Evidence | 哪幾次已 review 情況支持它 | 兩份已改稿的 reference |

```text
適用於：＿＿＿＿＿＿＿＿＿＿
不適用於：＿＿＿＿＿＿＿＿＿＿
Owner：＿＿＿＿＿＿＿＿＿＿
Evidence：＿＿＿＿＿＿＿＿＿＿
```

若你還說不出 scope，先把它保留在本輪 memo；它可能仍只是一次性 edit，而不是尚未寫好的長期 rule。

## AI rule 為甚麼要有 expiry，舊 context 何時應退休？

工作會變：讀者換了、產品改了、流程改了、公司決定也會變。一條昔日有用的 rule 若沒有重看時間，很容易變成過期 context；AI 還在引用它，人卻忘了它是為何、何時、替哪個問題而寫。這是很多「AI 好像一直照舊做」的真正來源。

Expiry 不一定是一個死日期。它可以是下一次 campaign 前、讀者定位改變時、產品／課程版本更新後，或三個月 review 一次。重點是 rule 有一個合理的機會被 owner 問：「它仍然解決同一個問題嗎？還是應修改、拆開或退休？」

**Jimmy 的結論：** Rule 不是收藏品；它是一個有生命週期的工作判斷，若環境變了就應被重新驗證或退休。

| Trigger | 要問甚麼 | 可能結果 |
|---|---|---|
| 讀者改變 | 原來的開場仍適合嗎？ | 修改 scope 或新建 rule |
| 產品／課程更新 | Evidence 和禁忌是否已過期？ | 更新／退休 |
| 三個月回看 | 它有沒有真的被用、是否仍減少錯誤？ | Keep、縮短或刪除 |
| Owner 更換 | 誰現在對這條判斷負責？ | 重新確認 ownership |

```text
Recheck date／trigger：＿＿＿＿＿＿＿＿＿＿
如果不再適用：更新／退休／回到一次性 task detail。
```

有 expiry 的 context 反而更可信，因為它承認工作判斷不是永恆事實，而是需要隨 evidence 更新的選擇。

## 把 AI feedback 寫成 reference card，最少要包括哪五格？

Reference card 是讓下一次可直接取用的最小形態。它不需要保存整個 conversation，也不需要收進所有改稿截圖；它只要保留能讓另一位人理解 rule、why、scope、owner 和 expiry 的資訊。這五格令 rule 可被質疑、更新和安全地帶到相近工作。

卡片越短越好，但短不等於模糊。若「Rule」只寫成「寫得專業一點」，它沒有可執行內容；若「Evidence」只寫「我覺得」，也無法分辨是穩定 pattern 還是當日偏好。讓每一格都回到真實 review 的觀察，才算可用 context。

**Jimmy 的結論：** Reference card 不是 AI 的永久命令；它是下一次開始前可快速檢查的一條、有邊界的工作判斷。

```markdown
# Reference card：＿＿＿＿＿＿＿＿＿＿

**Rule**
＿＿＿＿＿＿＿＿＿＿

**Why**
＿＿＿＿＿＿＿＿＿＿

**Scope**
適用於：＿＿＿＿＿＿＿＿＿＿
不適用於：＿＿＿＿＿＿＿＿＿＿

**Owner and expiry**
Owner：＿＿＿＿＿＿＿＿＿＿
Recheck：＿＿＿＿＿＿＿＿＿＿

**Evidence**
來自哪幾次已 review 的 draft：＿＿＿＿＿＿＿＿＿＿
```

完成卡片後，只把它放在下次同類任務確實會讀到的位置；不要連同完整 chat、私人 reviewer 評語、客戶資料或未批准背景一起複製。

## 用 internal workshop briefing 示範：怎樣把三個 feedback 分流？

假設一份 internal workshop briefing 收到三個修改：不要說「一定慳到時間」；把今次活動日改成星期四；開頭先說讀者要完成的工作。三句看起來都是 feedback，但它們的壽命、風險和去處完全不同。

若把它們全部塞進 AI memory，下次它可能在不相關稿件仍避免任何時間主張、甚至硬套星期四。但若先分流，你會留下真正能保護未來稿件的 evidence boundary，同時讓單次細節留在本輪，不污染新的工作。

**Jimmy 的結論：** 好 feedback routing 不是儲得最多；而是每一條都去到正確層：本輪 task、reference rule，或只是受控原始紀錄。

| Feedback | 分流結果 | 原因 |
|---|---|---|
| 不要說「一定慳到時間」 | Rule 候選 | 可寫成：無 evidence 不承諾效果 |
| 今次放星期四 | 一次性 task detail | 只屬本輪日程 |
| 開頭先說讀者工作 | Rule 候選，限新手 teaching briefing | 有清楚讀者與 artifact scope |

```text
Rule：沒有可核對 evidence 時，不把推測寫成效果或保證。
Why：owner 無法為未驗證主張負責。
Scope：適用於面向外部／新手的內容 draft；技術實測需另列方法和數據。
Expiry：每次 evidence policy 或讀者定位變更時重看。
```

這樣留下來的不是一條「寫作口味」，而是一條知道自己為何存在、何時應重新檢查的工作判斷。

## 把 feedback 變成 rule 後，AI Super User 下一步應怎樣用？

下一次相近工作開始前，先讀一兩張仍在 scope 內的 reference card，連同本輪最新 materials 和 completion criteria 放入 task pack。不要把所有 card 全部貼進 prompt；規則太多而沒有關聯，AI 和人都只會忽略。跑完 draft 後，再用 reviewer 的 pass／revise／stop 決定檢查這條 rule 是否真的幫到手。

當同類工作已經有穩定 input、rule、review 和例外，才值得升成 AI Operator 的 SOP 或 Skill；若每次工作仍差異很大，保留 task pack 加 reference card 已經足夠。這種耐心不是退步，而是避免把未成熟的偏好假裝成可以自動化的系統。

**Jimmy 的結論：** Feedback 變成 rule 的完成線，是下一次相近工作少猜一次；不是建立一個愈來愈大的 memory 庫。

| 你現在卡住的位置 | 接著讀甚麼 | 會留下甚麼 |
|---|---|---|
| 今次工作仍未交代清楚 | [五格組一個 AI task pack](./練習-build-an-ai-task-pack.md) | task、材料、邊界、review |
| 不知改稿後應 pass、revise 還是 stop | [AI 第二稿 review loop](./2-11-review-loop-next-draft.md) | revision memo |
| 想先分清 source 與自己的判斷 | [一篇 source 怎樣變成工作判斷](./練習-turn-a-source-into-your-own-decision.md) | source-to-decision note |
| 同類工作已開始穩定交接 | [AI Operator stage](<../../03-AI Operator（AI工作操作者）/README.md>) | SOP、state、exception |

可返回 [AI Super User stage](../README.md) 看其他入口。本文只用公開／synthetic 情境；reference card 不構成資料存取、外發、系統寫入或 production action 的批准。
