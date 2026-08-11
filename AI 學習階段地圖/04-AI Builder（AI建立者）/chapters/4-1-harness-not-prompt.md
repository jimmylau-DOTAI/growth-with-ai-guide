# AI Agent 反覆犯同一個錯，唔一定係 prompt 唔夠長：你可能需要的是 harness

你明明已經叫過 AI「一定要輸出 JSON」、「不要超過預算」、「不要改呢個欄位」、「不確定就問」，它卻隔幾次又犯同一個錯。於是你加多幾句「請務必」、換更強模型、把 system prompt 寫得愈來愈長；短期好像有改善，但下一次換 input、換 task 或長對話後，問題又回來。

這種返工令人誤以為自己還未找到完美 prompt。實際上，很多錯不是語言模型應該靠「記得」來避免的事：格式少一欄、數值超出範圍、未帶來源連結、未批准就要執行外部 action。它們是可以被明確檢查的規則；若只把規則放在文字叮囑裏，AI 仍可在壓力、雜訊或 context 不完整時偏離。

Jimmy 的判斷是：Agent 懂得怎樣推理、調工具和產生內容，並不等於它會穩定地把工作交好。能用清楚規則、schema、檢查、停止線和回退機制卡住的錯，不應只靠 prompt 提醒。這一圈在 LLM 外面令結果更可預期的工作環境，叫做 harness；它提升的是可靠下限，不是把 AI 變成永遠不會判斷錯。

| Harness 的一格 | 它要擋甚麼 | 完成後留下甚麼 |
| --- | --- | --- |
| Input boundary | 不合適、未批准或惡意的 input | 允許／拒絕／需確認的資料範圍 |
| Schema／parameter check | 格式少欄、參數不合法、值超範圍 | 可讀的 pass／fail 結果 |
| Output validation | 沒來源、越界主張、未標記未知 | 可 review 的 artifact 與缺口 |
| Exception／retry rule | 失敗後盲目重跑、偷偷補猜 | needs input／revise once／failed safe state |
| Human gate | 外發、覆寫、權限或高責任 action | Draft 與 named approval 決定 |

## AI 同一個錯反覆出現，為甚麼加多幾句 prompt 未必解決？

Prompt 是很好的工作指示方式：它可以提供任務、語氣、例子、背景與判斷原則。但 prompt 屬於可被模型解讀的 context，不是每一次都會像程式規則一樣被確定執行。輸入變複雜、工作變長、不同指示互相競爭，或資料本身不足時，模型仍可能產生一個看似合理、但違反你要求的 output。

尤其當規則本身是可以客觀驗證的，例如「必須有五個欄位」、「日期必須是 YYYY-MM-DD」、「不可讀取未批准資料」、「找不到原始連結便不可作結論」，不停加措辭只是在要求 AI 記得一個本來可以由流程自動檢查的條件。你越依賴文字提醒，reviewer 越要每次重新做同一個檢查。

**Jimmy 的結論：** Prompt 適合描述目的、語境和判斷；反覆而確定的錯應該被移到可檢查的 guardrail。問題不是 prompt 無用，而是你叫它負責了不應只靠記憶承擔的工作。

例如同一個「請勿犯錯」要求，放在不同位置會有不同效果：

| 你想避免的錯 | 只靠 prompt 的做法 | Harness 的做法 |
| --- | --- | --- |
| 少了必填欄位 | 「請務必填齊」 | Schema check，缺欄便不可進下一步 |
| 數值超出範圍 | 「請保持合理」 | 0–100 validator，超過就標 fail |
| 沒有原始來源 | 「請提供引用」 | 每項主張要求 source field；沒有便標 unknown |
| 未批准外發 | 「不要自行發送」 | 工具不授權 send；只可交 draft／release request |
| input 不足 | 「不要亂猜」 | `needs-input` receipt，列出欠項再停止 |

能把錯轉成明確 check，就不應把希望放在下一次 prompt 剛好被記得。

## Harness、prompt 和 AI Agent 各自負責甚麼，先不會把工作交錯？

把三者混在一起，是 AI Builder 最容易走錯的一步。Agent 負責在不確定的工作中拆任務、讀 context、選工具、生成內容或提出選項；prompt 是給 Agent 的語言指示，說明目標、風格、背景與可用資料；harness 則處理那些應該每次都一致、可被確定檢查的邊界和品質閘。

可以用一個簡單比喻：Agent 像會跑的馬，能在不同地形選路；harness 像馬具和欄杆，確保它不會帶著人衝出指定範圍。馬具不能取代馬的判斷，馬也不應被期待自己永遠記得每個安全規則。兩者配合，才可能有既有彈性又可管理的 workflow。

**Jimmy 的結論：** Agent 解決「怎樣做這份工作」；harness 解決「哪些事必須每次守住、何時要停、錯了怎樣留下狀態」。只升級模型或只拉長 prompt，都不能取代這個分工。

把工作放回正確位置：

| 類型 | 最適合放在哪裡 | 例子 |
| --- | --- | --- |
| 目的、受眾、語氣、取捨 | Prompt／brief | 用香港初學者語言解釋一個 AI workflow |
| 探索、摘要、草擬、選方案 | Agent | 從已批准文章抽出相似與相異觀點 |
| 欄位、格式、權限、上限 | Harness／rule | 輸出需有 source、unknown、reviewer 三欄 |
| 不確定、衝突、高責任 action | Exception／human gate | 來源矛盾時交 owner；外發前停住 |

這張分工不是要消滅 AI 的彈性，而是把「有彈性」和「不越界」同時保留下來。

## 哪些 AI 錯可以寫成確定性檢查，哪些仍然需要人或模型判斷？

不是所有錯都適合寫成 code 或硬規則。有些事情可以明確說對或錯，例如檔案是否存在、必填欄位是否齊、日期格式是否合規、是否超過預算、某種外部 action 是否已批准。這些規則每次都由人重新看，既慢又不一致；它們正是最值得先變成 validation 的地方。

另一些事情本質上需要判斷：這段文字是否真正有說服力、哪個策略最適合目前市場、兩個可信來源衝突時應如何取捨、某個畫面是否符合品牌品味。AI 可以幫你列理由、對照 evidence、做初稿，但不能因為你寫了一個很長 prompt 就變成可以自動承擔這些責任的規則引擎。

**Jimmy 的結論：** Harness 應卡住確定性錯誤，讓人和 AI 把注意力放回真正需要判斷的地方。把所有事情卡死會失去 AI 的價值；甚麼都不卡又會把已知錯反覆交給人補救。

先用這個分類表：

| 問題 | 較合適做法 |
| --- | --- |
| 必填欄位、schema、日期、數值範圍 | 自動 validation／quality gate |
| 只可讀／只可寫的資料範圍 | Access boundary、allowlist、sandbox |
| 已知會重覆的格式錯 | 固定 check + revise once |
| 缺資料、來源矛盾、scope 改變 | Exception state + owner approval |
| 內容質素、策略、語氣、優先次序 | AI draft + human／rubric review |
| 新奇、一次性、尚未理解的問題 | 先探索，不急著寫死 rule |

若你說不出一條可檢查的規則，就先不要假裝它可以靠 harness 完美解決；把它留在 review 或判斷層。

## Input、parameter 和 output guardrail 怎樣在一條 Agent workflow 裏運作？

很多人將 LLM 想成 workflow 的全部：用戶給 prompt，模型回 output，就完成了。實際上，一條可靠工作往往有幾個不同位置可以看清和擋住問題。先限制 input，可以避免 AI 一開始就看錯資料；再檢查參數／工具呼叫，可以避免它把含糊語句變成危險 action；最後驗證 output，才不會把看似流暢、其實缺證據或越界的結果交出去。

這些 guardrail 不一定要是大型工程。對第一個 AI Skill 而言，它可以只是一個表格 schema、一段 check list、一個不授予外發權限的 draft folder，加上一個「找不到來源就標 unknown」的停線。重要的是它們放在 Agent 以外，令 pass／fail 不靠同一個模型自己宣稱。

**Jimmy 的結論：** 模型只是中間一格；可靠性來自每一格都知道可進、不可進與要交回誰。越接近真資料或外部 action，越需要讓 validation 和 human gate 看得見。

一條簡化 workflow 可以是：

```text
approved input
→ input boundary（只讀指定資料）
→ Agent 生成 draft／提出 tool parameters
→ schema + parameter check（不合格不往下）
→ bounded tool action／working copy
→ output validation（evidence、format、unknown）
→ human review／release
→ receipt + feedback rule
```

以 research brief 為例：Agent 可整理指定公開來源；schema check 要求每個主張有原始位置；沒有就標 unknown；工具只准寫入 internal draft；owner review 後才決定採用。這比在 prompt 裏重覆十次「請勿亂猜」更容易驗證。

## 同一個錯犯第三次時，怎樣由「補 prompt」變成可重跑的品質規則？

同一種錯第一次出現時，未必急著寫 code。它可能只是 input 特別差、你未講清目的，或問題本身屬於判斷。第二次、第三次開始出現時，才值得停下來問：這個錯能否用一句客觀規則描述？若可以，便把它從「下次記住」升級為 workflow 的 check；若不可以，就應改 brief、rubric、資料品質或 review 方法。

這個轉換很重要，因為它令 feedback 不會只留在某段 chat 裏。每次修正可以慢慢變成 Skill 的一部分：甚麼輸入不足要停、甚麼欄位必須存在、甚麼 output 不能 release、甚麼錯只允許 revise once。久而久之，AI 和人都不用在同一件小事上重新耗神。

**Jimmy 的結論：** 反覆錯誤是 workflow 設計的資料，不是單純 prompt 技巧不足。可描述的錯變 check；不可描述的錯變成更好的判斷題、source 或 review，而不是無限加叮囑。

可跟這五步處理：

1. 記下最近三個「明明叮囑過仍再犯」的錯，連同工作情境。
2. 問每一個錯能否寫成 yes／no 規則或明確 schema。
3. 可以的，加入 input／parameter／output check，並定 revise once 或 stop。
4. 不能的，標記它屬於 context、策略、品味或責任判斷，補 rubric／review。
5. 用公開或 synthetic input 跑一次，確認 check 真的捕捉到錯，而不會亂擋合理工作。

若檢查本身需要大量人工猜，先不要自動化。你的第一份 harness 可以很小，但每一條都要解一個真實、重覆、可驗證的錯。

## Harness 有甚麼邊界，幾時不應為一次工作過度建置？

Harness 有建置和維護成本。一件只做一次、錯了即時看得到、風險又低的工作，未必值得花很多時間寫一層又一層 validation；直接用好的 brief、人工 review 和 working copy 已經足夠。可靠性不是堆最多控制，而是用剛好的控制處理剛好的風險。

另一個風險是把規則包得太死。若所有未預期的 input 都被拒絕、所有內容只准一種形式、AI 不可提出任何新選項，系統可能避開了一些錯，也同時失去探索、適應與創意。Harness 應保護確定性的邊界，不應假裝可以替你把所有複雜判斷預先寫死。

**Jimmy 的結論：** Harness 提升的是下限，不是上限。它能更早發現已知問題、減少可預防錯誤，卻不能令做不到的模型突然有專業判斷，也不能代替 owner 對高責任決定負責。

決定是否值得建置前，先看：

| 情況 | 較適合的做法 |
| --- | --- |
| 一次性、低風險、容易人手看出錯 | 好 prompt + human review 即可 |
| 重複、可描述、錯後常返工 | 加小型 check／schema／receipt |
| 會讀敏感資料、改正本、對外 action | 先縮 scope、加 access boundary／human release |
| 結果全靠專業取捨或關係語境 | 保留 human runbook，AI 只協助 draft |
| 模型能力本身不足 | 收窄任務或換方法，不要用更多 guardrail 假裝能做 |

若要把例外處理寫成共同語言，可讀 [AI 一遇資料不足就繼續猜？Skill 要先寫好 exception ladder](./4-34-skill-exception-ladder.md)；要把已知錯收進固定檢查，可讀 [最小 regression pack](./4-10-minimum-regression-pack.md)。

## 想為第一條 AI Agent 加 harness，最安全的起點是甚麼？

第一個 harness 不需要是一套 production platform。挑一件低風險、重複、只交 draft 的工作，例如把三篇指定公開文章整理成固定 briefing。先不要接 CRM、付款、客戶資料、production 系統或自動發佈；只測一兩個你真的看過的錯，例如缺少來源、少了必填欄位或超出指定資料範圍。

成功標準也不是「AI 從此不會出錯」，而是它遇到這些已知錯時會被明確攔下、留下可讀 result、知道要 revise 還是停，reviewer 因此不用每次由零再抓同一個問題。這是一條可靠 Agent loop 的開始，不是一次性 demo。

**Jimmy 的結論：** 第一份 harness 的成功，是把一個重覆、可描述的錯從 prompt 裏移到 workflow 規則裏，令下一次不必靠你再記得叮囑。

可以由這五步開始：

1. 選一項公開安全、可回退、只產生 draft 的重複任務。
2. 找出一個近來反覆出現、可用 yes／no 描述的錯。
3. 為它定一條 schema／範圍／格式 check，並指定 fail 時的 receipt。
4. 只准 AI 在 working copy 交 draft，不可外發、覆寫或擴大讀取。
5. 跑幾次後才問：這條 check 是否真減少返工？要不要多加第二條？

暫時不要把所有 prompt 都改成 code；不要把判斷、策略、品味或人際責任硬寫成假規則；也不要因為有 harness 就授予外部 action。想先設計一條可停、可 review 的 Agent loop，可讀 [先跑一條可停的 Agent loop](./4-25-first-agent-loop.md)；若你的工作仍混合了人手判斷與可重跑部分，讀 [唔係每條 SOP 都應該變成 AI Skill](./4-37-human-runbook-or-ai-skill.md)。

← [返回 AI Builder](../README.md) · [按問題瀏覽](../../../學習地圖.md)
