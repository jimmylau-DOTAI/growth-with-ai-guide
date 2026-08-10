# AI 課程不只是教 prompt：要教人知道何時相信、何時停下、怎樣交付

一堂 AI 課最容易得到的場面，是所有人輸入同一條 prompt，幾秒後拿到一段漂亮回答。這會帶來「我識了」的感覺；但回到真工作，很多人仍然不知道資料不完整時怎樣問、AI 猜了時怎樣發現、交付前哪一部分要自己承擔，於是又回到聊天式試錯。

工具技巧當然重要，但只教答案會令學員更快把不確定的東西交出去。學員可能懂得叫模型重寫、換語氣、出格式，卻不懂定 input boundary、檢查 evidence、處理例外或把一次 feedback 變成下次可重用的規則。這不是他不夠聰明，而是教學完成線定得太低。

Jimmy 的看法是：AI education 的成果不是人人有一條 prompt；是每個人多了一個能在真工作中判斷、留下證據、安全前進的反射。好的課堂要由一件真工作走到可 review artifact，再把判斷留成可以帶走的 context、checklist 或 stop line。

AI education · prompt engineering · AI training · AI judgment · human review · context · workflow · Hong Kong

| 一堂 AI 課要完成的一格 | 學員要學會問甚麼 | 最後留下甚麼 |
|---|---|---|
| 真工作 | 我究竟想交甚麼？ | problem 與 artifact |
| 材料邊界 | 哪些資料可給、哪些不能給？ | approved input rule |
| AI 一手 | AI 只先做哪一段？ | draft／整理範圍 |
| Review | 怎樣分辨可用、未知或錯誤？ | acceptance checklist |
| Feedback | 今次發現的問題怎樣不再重複？ | reusable rule／context |
| 下一步 | 下次回到工作怎樣自己再跑？ | safe repeatable routine |

## AI 課程只教 prompt 點解不夠：漂亮答案不等於可負責的工作

一條 prompt 在示範時成功，未必代表學員下次面對不同資料也知道怎樣做。真工作有空白、矛盾、敏感內容、不同 owner 和時間壓力；模型若給出流暢但錯的答案，學員需要知道如何發現、如何標記、如何退回，而不是只懂再按一次生成。

若課程把完成定義成「成功用到某功能」，它自然會把注意力放在 output，而非判斷。學員很快能說出工具功能，卻未必說得出 input 是甚麼、誰會 review、甚麼情況不可照用。這會令 AI 看似令人更快，實際令錯誤更快進入下一手工作。

**Jimmy 的結論：** Prompt 是入口，不是完成線。AI 課程要讓人帶走一套能處理不確定、可交付、可回看的工作判斷。

| 課堂只做到甚麼 | 回到真工作會卡在哪裡 | 要加回哪一格 |
|---|---|---|
| 輸入 prompt 出答案 | 不知答案可否直接用 | review checklist |
| 學很多功能 | 不知哪個工作適合開始 | real-work trigger |
| 模仿講師例子 | 不知自己的資料能否給 AI | input boundary |
| 看到一次成功 | 不知錯了怎樣處理 | unknown／stop line |
| 改過一次 output | 下次又從零猜 | reusable context／rule |

課程設計時先問：學員離開後，遇到一件資料不完整的工作，會否知道安全第一步？若答案是否定，先補工作判斷，不是再加一條萬用 prompt。

## AI training 怎樣由真工作開始：先定 artifact、材料與完成線

不要先問「大家想學哪個工具」。請學員帶一件最近真的要完成的低風險工作：整理公開資料、準備 internal briefing、比較方案、起草常見回覆，或交接一段 routine。這件工作有真實摩擦，學員才知道為何要改變，也能分辨哪一個 AI output 真正幫到自己。

然後先定 artifact：最後要交甚麼讓別人可以打開、核對、退回或接手？再定哪些材料可以使用、哪些不能使用、AI 只先處理哪一手。當完成線在動手前講清，學員不會把一段聊天內容誤當成完成，也較容易在 output 出來後做有方向的 review。

**Jimmy 的結論：** 真工作不是讓學員把所有私人資料丟進 AI；它是讓學員用安全材料，完整練一次由目的到 artifact 的工作循環。

| 開始前要定的格 | 學員應回答 | 安全預設 |
|---|---|---|
| 工作目的 | 這份 output 幫誰作哪個決定？ | 選低風險 internal task |
| Artifact | 最後交甚麼可核對東西？ | brief、draft、checklist、card |
| Input | 哪些材料可用？ | approved／public／synthetic |
| AI scope | AI 只先做哪一手？ | 整理、分類、起 draft |
| Review | 誰按何標準收貨？ | named owner／同儕檢查 |
| Stop | 不確定時怎樣辦？ | 標 unknown，勿猜或外發 |

未有安全材料時，請用 synthetic 情境做練習。先學識工作分工與 review，比急著讓學員接觸真客戶資料更有價值。

## AI 學習怎樣練出判斷：由一次 output 走到比較、質疑與 feedback

一個完整練習應不只生成 output。它要讓學員主動找到一個可能錯誤、來源不足、格式不合或超出 scope 的位置，並問：這是 input 問題、模型推論、規則不足，還是人還未給足 context？這一段比較與質疑，才是把「AI 似乎答對」變成「我知道怎樣判斷它」的關鍵。

最後把發現留下來。可以是一條 context 說明、一個 source check、一張 checklist、一個命名規則，或一條 stop line。下次同類工作出現時，學員不用靠記憶重做同一個修正；他有一個可重用的工作記憶。這也是 AI Super User 走向 Operator 的核心變化。

**Jimmy 的結論：** 真正的學習在 output 之後：看出不確定、說出原因、留下下一次的規則。沒有 feedback artifact 的練習，通常只是一場 demo。

| 練習回合 | 學員做甚麼 | 留下甚麼 |
|---|---|---|
| 1. 講清工作 | 目標、範圍、完成線 | work statement |
| 2. 交一小手給 AI | 只做低風險 draft／整理 | first artifact |
| 3. 比較與質疑 | 找錯誤、unknown、缺來源 | review note |
| 4. 回到原因 | 分 input、rule、model、owner 問題 | diagnosis |
| 5. 留 feedback | 寫進 context／checklist／stop line | reusable rule |
| 6. 再跑一次 | 檢查規則有否減少重做 | learning receipt |

若學員只需說「答案好不好」，練習仍太淺。請他指出哪一句能被來源支持、哪一句是推論、哪一句必須交回 owner，判斷才會變成可教的能力。

## AI 導師點解不能只靠自己很熟：教人要看見不同 stage 的下一步

一個人自己很熟 AI，不代表他知道新手在哪一格會害怕。導師可能已習慣自己補 context、自己判斷 output、自己修正例外，因而不自覺地跳過了學員真正需要的中間步。結果新手覺得內容太快、太抽象或太危險；熟手又覺得只有基礎功能，無法前進。

Stage 的作用是幫教學者判斷下一步：AI User 先完成一件有 context 的小工作；AI Super User 學會留下 reusable context 與 feedback；AI Operator 學會將 routine 交接、留 state、處理例外；AI Builder 學 guardrail；AI Value Creator 則學帶人跑 pilot 和看 evidence。這不是考牌，而是不同工作卡位的導航。

**Jimmy 的結論：** 好導師不是把自己最熟的招數一次教晒，而是讓每個人由現在的工作位置，完成剛好下一個可驗收成果。

| 學員現況 | 不要跳去教甚麼 | 較好的完成線 |
|---|---|---|
| 剛開始用 AI | Agent、automation、production access | 一件有 context 的小工作 |
| 已會問 prompt | 無止境更花巧 prompt | reusable context 與 feedback |
| 常做重複工作 | 只比較更多 tools | routine、artifact、review |
| 想 build | 直接交高風險 action | draft-only guardrail |
| 帶團隊的人 | 只看 demo 影片 | pilot evidence 與 decision |

當你不知道學員在哪個 stage，請他拿出最近一次用 AI 的真工作。看他卡在 context、review、交接、例外還是價值，便比問「你懂不懂 AI」更接近教學需要。

## AI 課堂怎樣示範 human review：讓學員親手看見 AI 的邊界

一個安全而有效的課堂示範，可以讓全班從三份指定公開資料做一頁 briefing draft。每人都要標出：哪一句可直接對照來源、哪一句是合理推論、哪一句因資料不足要交回 owner 確認。這讓 AI 的速度和它的邊界同時變得可見。

示範後，不要只比較誰的 output 寫得漂亮。讓小組比較不同 output，討論哪一條規則能避免下次同樣錯誤，例如「未有來源不可補數字」「不確定客戶意圖要標 unknown」「先出 internal draft，不直接對外發送」。學員因此看到 review 不是 AI 失敗後的懲罰，而是讓工作可安全交接的設計。

**Jimmy 的結論：** Human review 必須被演練，不能只在最後提醒一句「要小心」。學員親手發現一次邊界，才懂得下次如何保護自己和團隊。

| 示範格 | 做法 | 學員學到甚麼 |
|---|---|---|
| Input | 指定公開、有限材料 | 不是所有資料都可亂放 |
| AI output | 起一頁 internal draft | AI 只做一手 |
| Evidence check | 對照哪句有來源 | 流暢不等於正確 |
| Unknown | 標出資料不足處 | 不要補猜測 |
| Review | owner／同儕按標準收貨 | 誰負責最後決定 |
| Feedback | 留一條下次規則 | 學習可累積 |

這種示範同時適合公開攻略和企業訓練，因為它不依賴敏感資料，卻保留了真工作需要的判斷。

## AI education 怎樣避免只產生答案：把課堂完成線改成可重用的工作能力

課堂如果只以「學員成功用到某功能」作結，通常無法知道他回到工作後會否再用。把完成線改成「學員完成一件甚麼工作、知道甚麼要人手確認、並留下甚麼 feedback artifact」，課堂的設計就會自然由功能演示轉向工作能力。

這也會讓你更容易回看教學是否有效：學員帶走的 work card 是否有用？哪一個 review rule 最常被忽略？哪種材料仍讓人不敢開始？下一次應改例子、改流程還是增加一段練習？AI education 因此不只是把知識傳出去，也會隨著使用 evidence 逐步改善。

**Jimmy 的結論：** AI 課程最值得交付的，不是一份 prompt pack，而是一個人能在真工作中安全重複使用的判斷循環。

| 舊完成線 | 改成工作完成線 | 可回看的證據 |
|---|---|---|
| 學員用到某個功能 | 完成一份可 review artifact | accepted／returned output |
| 學員記得 prompt | 留下一條 reusable context | next run 是否少重做 |
| 學員看懂 demo | 能指出 AI 的 unknown／boundary | review note |
| 學員說很有用 | 願意在真工作第二次使用 | repeat-use receipt |
| 課堂結束 | 有下一輪改良決定 | revise／retain／stop |

未有安全第一個成果前，不應把學員推去高風險自動化、外發或 production action。先讓他能判斷和收貨，才有基礎走向 Builder 或 Value Creator。

## 今日怎樣把一個 AI 單元改好：由「學功能」改成「完成一件可 review 工作」

揀你現有一個 AI 課程單元，先刪走「學員成功用到＿＿功能」這種完成定義，改為：學員完成一件＿＿工作；AI 只處理＿＿；＿＿要人手確認；本次 feedback 留成＿＿。接著安排一段讓學員實際找 unknown、比較 output、寫下一條下一次規則的時間。

如果你暫時只能用工具 demo，也不代表內容無用；先把它標為認識工具，而不要假裝已完成能力訓練。當你加回真工作、review 和 feedback artifact，這個單元才會變成一個能帶進工作現場的學習循環。

**Jimmy 的結論：** 好 AI 教學不是教學員更快得到答案，而是教他在答案出來後仍能清楚判斷、負責交付、帶走下一次更穩的做法。

| 今日先改的一格 | 寫成甚麼 | 為何重要 |
|---|---|---|
| 真工作 | 學員要完成的具體 routine | 有真實採用入口 |
| AI 範圍 | 只交出一個低風險小步 | 不把 output 當完成 |
| Review | 誰按哪個 checklist 收貨 | 令品質與責任可見 |
| Feedback | 一條可重用 rule／context | 不用下次從零猜 |
| 邊界 | 不給甚麼資料、不做甚麼 action | 保持安全與信任 |
| 下一步 | 完成後可再讀哪一篇 | 連到下一個 stage |

想先設計新手的安全成果，讀 [第一個安全成果](5-10-first-safe-outcome.md)；要把 feedback 留成更穩的工作判斷，讀 [把 feedback 變成判斷](2-9-feedback-into-judgment.md)。

> AI education 的成果不是人人有一條 prompt；是每個人多了一個能在真工作裏作判斷、留下證據和安全前進的反射。

← [返回 AI Value Creator](../05-ai-value-creator.md) · [按問題瀏覽](../BROWSE.md)
