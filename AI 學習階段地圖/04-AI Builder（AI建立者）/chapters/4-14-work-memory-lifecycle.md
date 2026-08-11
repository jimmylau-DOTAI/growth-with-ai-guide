# AI 記憶唔係儲得愈多愈好：要有 evidence、召回、驗收同退休

你可能已經儲了很多筆記、chat、SOP、提示詞和 Agent memory，但每次開始一件新工作，AI 仍然會問回相同問題，或者引用一條不知道何時寫下、也不知道是否還有效的舊規則。於是人又把更多文件塞進 context，希望它「記得更多」；最後卻發現答案變慢、變散，還會混入過期做法。

真正的困難不是保存，而是判斷哪段經驗值得在下一件工作出現。歷史對話可以保留，卻不等於它能作 current instruction；AI 讀到一條規則，也不代表它有用對。若無來源、無適用範圍、無實際交付物檢查，所謂 memory 只是一個愈來愈大的檔案堆。

Jimmy 的看法是：工作記憶不是資料倉，而是一個小型 lifecycle。它由可檢查的 evidence 開始，變成有適用範圍的判斷；只在對的任務被召回，最後要看結果是否真的改善工作。無效、過期或被新證據推翻的規則，應保留歷史，但退出 active context。

`AI 實戰 · AI Builder · AI memory · work memory · context · evidence · retrieval · lifecycle`

| 工作記憶的一格 | 它解決甚麼問題 | 完成後留下甚麼 |
|---|---|---|
| Evidence | 不把一句印象當事實 | 來源、日期、決定或可檢查 artifact |
| Reusable judgment | 由一次經驗抽出可用做法 | 一句有條件的工作判斷 |
| Targeted recall | 不讓每個任務讀所有舊資料 | 觸發條件和可讀範圍 |
| Applied check | 分清「提過」與「用對」 | 新 artifact 的 check 結果 |
| Lifecycle | 防止舊規則長期污染新工作 | active、待修正、retired 狀態 |

## AI memory 最常見的問題：存了很多資料，下一次仍然用錯

把資料存下來很容易；讓下一次工作只拿到相關、可信而仍然有效的資料，才是難處。若一個 Agent 每次都把整個 vault、全部舊 chat 或所有 SOP 放進 context，它不是擁有更好記憶，而是被迫從大量互相無關的材料中猜哪一條才是現在的規則。

另一個風險是把「曾經成功」誤認為「永遠正確」。工具、資料格式、政策、課程定位和工作 owner 都可能改變。一條舊做法可以有參考價值，卻不能因為被存進 memory 就自動獲得現在的授權。歷史與 active instruction 需要分開，否則 AI 很容易以舊 context 回應新問題。

**Jimmy 的結論：** 不是所有資料都應成為 AI 的工作記憶。只有能說清來源、適用任務、驗收方式和更新狀態的經驗，才值得在下一輪被自動召回。

| 你看到的情況 | 它真正代表甚麼 | 較安全的處理 |
|---|---|---|
| 每次都要重新講背景 | 沒有為任務寫好可召回的判斷 | 抽出一張有觸發條件的記憶卡 |
| AI 引用舊規則但結果不對 | 規則可能過期或被用錯範圍 | 保留 evidence，從 active context 移走 |
| context 愈長答案愈亂 | 不同任務的材料被混在一起 | 限制每次只讀相關 bundle |
| 有很多 SOP 但無人知哪份可信 | 缺少 owner 和最後驗證日 | 標註 current、review 或 retired |

一條好的記憶應讓人一眼看見「它是由甚麼得出、何時可用、何時不應用」。寫不到這三件事，就先當它是 reference，而不是讓它指揮下一件工作。

## Evidence 如何令 AI 記憶可信：先保留能被回看的工作事實

evidence 不必是一大包文件。它可以是一條公開來源連結、一份已批准的 brief、一個經過人 review 的 artifact，或一個清楚記錄決定的工作紀錄。重點不是資料量，而是下一個人或 AI 能否回看：這條規則從哪裏來？它是作者主張、已做決定，還是暫時推論？

沒有 evidence 的記憶，最容易由一句聊天結論慢慢變成「公司一直是這樣做」。特別是涉及外部事實、公開安全、工作權限或品質要求時，AI 不應把未核對說法自動升格成固定規則。若來源不明，最好的狀態不是假裝完整，而是標記 unknown，交回 owner。

**Jimmy 的結論：** 記憶的可信度不是由語氣決定，而是由它能否回到一個可檢查的來源或 artifact 決定。沒有 evidence 的內容，可以保留作靈感，但不應自動驅動工作。

| Evidence 類型 | 可以支持甚麼 | 不應偷步支持甚麼 |
|---|---|---|
| 公開原文與連結 | 作者明確講過的主張 | 未被原文支持的延伸結論 |
| 已批准的工作 brief | 這次工作可用的範圍與欄位 | 其他未批准任務的權限 |
| 人 review 過的 artifact | 某個格式和 checklist 曾經可用 | 所有未來情況都保證成功 |
| 明確 decision record | 當時由誰作了哪個決定 | 把舊決定當成永久政策 |

實際做法很小：在記憶卡旁邊留下來源、日期和「這是事實、決定還是推論」。下次 AI 需要它時，就能知道要引用、要驗證，還是要停下來問人。

## 可重用 judgment 怎樣由一次工作長出來：不要只把整段 chat 存低

一次工作留下的資料很多，但真正可重用的往往只是一個有條件的判斷。例如「公開 research brief 裡，每個 external claim 要有可開啟的原文 link；推論要另標待驗證」。這不是把整段討論濃縮成口號，而是把下一次會影響輸出的規則說清楚。

好的 judgment 必須有範圍。它不應寫成「永遠要這樣做」，而是寫出在甚麼任務、哪種輸出和哪個風險下適用。若資料格式、工具或 owner 已換，AI 就不應照搬；它應該把這條記憶當成一個需要重新確認的起點。

**Jimmy 的結論：** 一次經驗不是一條永久命令。把它寫成「在某個情境下，為了避免某個失誤，要留下某個檢查」的 judgment，才真正能被重用。

| 原始經驗 | 不夠好的記憶 | 可重用的 judgment |
|---|---|---|
| brief 把作者主張和推論混在一起 | 「research 要小心」 | 「公開 brief 要把原文主張和內部推論分欄，推論標待驗證」 |
| 草稿漏了批准日期 | 「記得檢查日期」 | 「活動相關 draft 在 review 前要核對日期、時區和來源版本」 |
| AI 猜了缺失資料 | 「AI 不可靠」 | 「輸入缺欄時，AI 要標 `needs-human-review`，不可自行補事實」 |
| 舊工具步驟已失效 | 「工具更新很快」 | 「工具操作規則要附最後驗證日，過期後只作 reference」 |

當一條 judgment 已包含情境、風險和 check，它便不再只是筆記；它開始像一個可以放進 Skill 或工作卡的 quality gate。想看這種寫法如何變成可用合約，可接著看 [由 Prompt 變成 Skill 的工作合約](./4-23-skill-is-a-work-contract.md)。

## Targeted retrieval 如何避免長 context：每次只召回這件工作的最小 bundle

AI 不需要每次都「記得你所有事情」。它需要在目前任務裡讀到足夠而相關的 context：這次目標是甚麼、可用哪些資料、輸出格式如何、哪些規則不能跨過。把這幾樣東西組成最小 bundle，比把所有舊內容貼進 prompt 更容易驗收，也較不容易污染答案。

targeted retrieval 的重點不是檔案路徑，而是觸發條件。你可以規定「只有當任務是公開 research brief，並且要處理 external claim 時，才讀這條 claim／inference 分欄規則」；若現在是在寫內部會議紀錄，這條規則未必有用，甚至可能造成干擾。記憶要被任務邀請，而不是自己闖進來。

**Jimmy 的結論：** 最好的 context 不是最多，而是剛好足以完成此刻工作、同時能指出未知與邊界。每條記憶都應寫明「何時讀」和「何時不要讀」。

| 任務訊號 | 可召回的最小 bundle | 不必一併載入的東西 |
|---|---|---|
| 整理公開文章成 brief | source rule、claim/inference 格式、公開安全 checklist | 所有課程草稿和舊聊天 |
| 草擬 internal template | 已批准欄位、輸出格式、owner review rule | 外部研究資料庫 |
| 重跑一條穩定 workflow | 目前版本的 skill、輸入契約、例外規則 | 已 retired 的舊步驟 |
| 發現資料衝突 | evidence link、最後驗證日、escalation owner | 自行補完的假設 |

若你無法說明一條記憶在甚麼訊號下才該出現，先不要讓它自動載入。把它留在 reference library，等到它有清楚的工作觸發點才升級。

## Applied check 怎樣證明記憶有用：看新 artifact，不是看 AI 有沒有提過它

AI 在回答裡提到一條規則，並不代表它已遵守。真正的檢查要落在新交付物：這次 brief 是否每個 external claim 都有連結？推論是否真的分欄？資料不足時是否停下而非猜測？若 artifact 看不出這些痕跡，所謂 memory 可能只是被引用，沒有改變工作。

這也讓你分清一條記憶是否值得保留。若它幫助 reviewer 更快看出缺口、減少 rework、或令交接更清晰，就有證據支持它仍有用；若每次都被略過、造成誤讀或已不合現況，便應修正或退休。記憶的 KPI 不是條數，而是它是否令下一次的工作更可靠。

**Jimmy 的結論：** 一條 memory 只有在新 artifact 上留下可檢查改變，才算真的被用對。沒有 applied check，就不能分辨它是經驗、裝飾，還是風險。

| 想驗證甚麼 | 在 artifact 上看甚麼 | 結果如何處理 |
|---|---|---|
| claim 規則有否被用 | 每個 claim 有原文 link，推論另標 | 漏項則回到 draft 補證據 |
| stop line 有否有效 | 資料不足處有 `needs-human-review` | 有猜測則修正 loop／prompt |
| 格式規則有否減少 rework | reviewer 可按 checklist 快速驗收 | 重複出錯則更新 judgment |
| 規則是否仍合現況 | owner 確認日期、工具和權限仍一致 | 不一致則轉為待修正或 retired |

先由一個低風險 artifact 開始做這種 check。不要一開始就讓 memory 驅動外部發送、客戶資料處理或 production 寫入；那些工作需要另外的授權、監控與 human approval。

## AI memory 何時應退休：保留歷史，不讓過期規則繼續指揮現在

retire 並不是刪除一切。舊 memory 有時仍能解釋為何以前採用某個做法，對 audit 或學習很有價值；問題是在新的任務裡，它會否被誤當成 current instruction。把記憶標成 retired，代表它可回看、不可自動召回。

退休的常見原因包括：工具界面或能力已改、資料格式已換、權限或 owner 已變、原本的 evidence 被新資料推翻，或者它其實只適用於一次性的情境。當你未能判斷是否過期，也不需要假裝它仍有效；標成 `needs-review` 比靜靜讓 AI 照做安全得多。

**Jimmy 的結論：** 可信的記憶系統一定容許規則退出。保存歷史是為了理解，不是讓舊做法永遠自動生效。

| 記憶狀態 | 何時使用 | AI 應怎樣處理 |
|---|---|---|
| active | evidence、owner 和條件仍被確認 | 在對應任務的最小 bundle 召回 |
| needs-review | 有可能變更，但未重新驗證 | 提醒 owner，不把它當硬規則 |
| superseded | 有新版本明確取代 | 指向新規則，不再載入舊版 |
| retired | 保留歷史價值但不再適用 | 只供回看，不進 active context |

每次工作規則被更新，不必急著清空舊檔；只需把「現在哪一版有效、誰最後看過、舊版去哪裏」寫清楚。這比大規模刪除更安全，也令下一個人知道變更的來由。

## 一個公開安全例子：由 research brief 經驗變成可召回的工作記憶

假設你每星期把公開文章整理成一頁 internal research brief。某次 reviewer 發現草稿把作者已說的主張和 AI／人自己的延伸推論混在一起，讀者無法知道哪一部分能夠核對。這不是要記住整段 chat，而是一個可以改善下一次 artifact 的具體問題。

你可以先保存原文章連結和該次草稿的 review 結果，然後抽出一條 scoped judgment：在「公開 research brief」這類任務中，每個 external claim 留原文 link，推論另標 `待驗證`。下次只有在同類 brief 開始時才帶入這條卡；reviewer 再檢查新 draft 是否真的分開兩者。若原文格式改變或規則不再適用，就把它標記 review／retired。

**Jimmy 的結論：** memory 在這裡不是讓 AI 愈做愈神，而是讓一個曾出現的可驗收失誤，下次有正確的 evidence、正確的觸發點和正確的 check。

| Lifecycle 一步 | 這個例子怎樣做 | 可回看的結果 |
|---|---|---|
| Evidence | 保留公開文章 link 和 review note | 可確認哪個 claim 出問題 |
| Judgment | claim 與推論要分欄，推論標待驗證 | 一句 scoped rule |
| Recall | 只在公開 research brief 開始時帶入 | 小型 task bundle |
| Check | reviewer 對照新 brief 的 link／標記 | pass 或 needs-rework receipt |
| Lifecycle | 格式變了便標 needs-review 或 retired | 不污染下一次 context |

這個例子只處理公開、低風險的草稿工作。它不授權 AI 讀取私人資料、自己對外發送訊息，或把任何內容寫進 production 系統；那些動作需要獨立的 approval 和控制。

## 今日怎樣建立第一張 memory card：由一個重複工作開始，而不是搬整個 vault

你今天不需要整理全部歷史。選一項一星期內會再做、輸入較穩定、而且可以由人 review 的低風險工作，例如把已批准的公開資料整理成內部 brief。這種小工作既容易驗收，又足以看見記憶是否真的幫到下一輪。

先寫最少四行：可重用 judgment、它的 evidence、何時才召回、怎樣在新的 artifact 檢查。跑過一次後才加最後驗證日與 lifecycle 狀態。這個順序能防止你在還未驗證用途前，就把很多舊資料提升成「AI 應該記得」的規則。

**Jimmy 的結論：** 第一張好的 memory card，比一千段未分類 chat 更有用。它讓人與 AI 都知道下一次該讀甚麼、要交甚麼、出錯時如何修正。

| Memory card 欄位 | 你要填甚麼 | 一個安全示例 |
|---|---|---|
| Judgment | 哪條做法能避免甚麼錯誤 | claim 與推論必須分欄 |
| Evidence | 它從哪裏得出 | 公開原文 link 加 review note |
| Trigger | 哪類任務才讀它 | 整理公開 research brief 時 |
| Applied check | 如何知道有沒有用對 | reviewer 查 link 與標記 |
| Status | 現在是否仍有效 | active，附最後驗證日 |

先把卡用在一條公開、可回看的 draft workflow，保留 input、輸出、check 和停下原因。未做完這個小驗證前，不要把整個 vault 當作 active memory，不要讓它自動存取私人或客戶資料，也不要接到任何外部發送或 production 寫入。接著可看 [AI 工作要有可讀 state，否則下一手無法接](./4-15-readable-state.md)，了解 memory 如何在交接時變得可見。

> AI 記憶的價值，不是保存更多對話；而是令對的工作經驗，在下一件對的工作被找回、被驗收，過期時亦退出場。

← [返回 AI Builder](../README.md) · [按問題瀏覽](../../../README.md)
