# AI 有冇真價值點樣證明：用 value proof card 分開已觀察、未證明和下一步

一次 AI output 很好看，或者一個小 pilot 跑得順，很容易令人想說「AI 已經創造價值」。但這種說法通常太快：可能只跑了一次、input 剛好很乾淨、owner 剛好有時間 review，或者真正省下的時間被後面的 cleanup 吃掉。若不把 evidence 拆開，團隊很容易把 demo 變成 ROI claim，之後也不知道應保留、修正還是停止。

value proof card 的目的不是製造成績表，也不是把私有工作變成公開 case。它只把一輪或幾輪有限工作說清：原本哪一手有摩擦、AI 今次只做哪一段、用了甚麼 input、交甚麼 artifact、誰 review、實際看到甚麼、還未證明甚麼，以及下一輪應作哪個 decision。

Jimmy 的看法是：真 proof 不是講 AI 有幾勁；是坦白講清楚它幫哪一段工作、交了甚麼、邊個 check，同埋仍有甚麼未證明。當 evidence、boundary 和 next decision 都可回看，AI 價值才可以被安全討論。

AI value proof · AI ROI · pilot evidence · workflow outcome · review · retain revise stop · AI Value Creator

| Value proof card 一格 | 它要回答甚麼 | 防止甚麼誤會 |
|---|---|---|
| Work pain／scope | 原本卡哪裡，AI 只做哪一手？ | 把整個流程都算成 AI 功勞 |
| Input／artifact | 讀甚麼，交甚麼？ | 只有 screenshot 沒交付 |
| Review／control | 誰按甚麼收貨？ | AI 自己說 done |
| Observation | 今次實際看到甚麼？ | 把感覺當事實 |
| Unknown／exception | 哪些未證明、何處退回？ | 把一次 run 當 ROI |
| Next decision | retain、revise 還是 stop？ | evidence 沒有下一步 |

## AI value proof 點解不是 screenshot：一張 output 看不出工作有冇變好

Screenshot 很適合展示某個工具可以產生甚麼，但它通常看不見前後的工作設計：原本哪一手慢、AI 只參與哪一段、是否用了已批准 input、誰 review、output 有沒有被退回、下次能否再跑。缺少這些，旁人無法分辨這是一次漂亮結果、可運作 pilot，還是已有可比較 evidence 的 workflow。

Value proof card 不需要放所有原始材料，也不應為了證明而複製客戶、學員、CRM、合約或未批准數字。它只保留另一個人理解本輪判斷所需的最小 evidence。這既保護私隱，也迫使你將「感覺有用」轉成可說清的工作觀察。

**Jimmy 的結論：** Screenshot 可以是 artifact 的一部分，但不是 value proof。要談價值，必須同時看到 work pain、scope、review、observation 和下一步。

| 只有 screenshot | 讀者仍不知道 | Value proof 要補甚麼 |
|---|---|---|
| AI 出了一份內容 | 原本問題與使用情境 | work pain |
| 有一張漂亮表格 | 是否可被 owner 接受 | review result |
| 有一次快的 run | 是否少了整體重做 | observation／exception |
| 有工具畫面 | input 是否安全 | boundary |
| 有一個成功例子 | 能否第二次使用 | next decision |

若你只有一次 output，先把它留成 run receipt 或 internal draft。等你有 owner review 和一個可比較觀察，再寫 value proof card。

## Value proof card 的 scope 怎樣寫：AI 只做哪一手，不要把整條流程都算成成果

第一格先寫原本工作摩擦：例如公開 FAQ 散在幾頁，初稿常漏題；或資料齊後仍要人反覆整 format。再寫本輪 AI 只處理哪一手：把指定公開資料整理成分類 draft。最後寫清不做甚麼：不更新網站、不外發、不讀私人資料、不處理任何高後果決定。

這種 scope 看似保守，但它能讓 team 誠實地討論 AI 到底幫了哪裡。若一份 draft 是 AI 起草、人補資料、owner 改策略、另一人外發，就不能把最終結果全歸功 AI。寫清分工，才不會令 future decision 建立在錯誤期待上。

**Jimmy 的結論：** Value proof 的第一個品質標準是 scope 誠實。AI 做哪一手就記哪一手，不把整個 workflow、團隊成果或商業結果一口吞進去。

| Scope 寫法 | 可驗收版本 | 不應怎樣寫 |
|---|---|---|
| Work pain | 公開 FAQ 分散、初稿常漏題 | 「公司效率太低」 |
| AI action | 分類 approved data 成 draft | 「AI 處理所有 FAQ」 |
| Out of scope | 不外發、不更新網站 | 不寫任何邊界 |
| Owner role | reviewer 判斷可否使用 | 叫 AI 自己驗收 |
| Risk | 個人資料／未知即停 | 假設全部資料可用 |

若 scope 仍大到無法一句講完，先不要寫 proof card。回到 work card，把 workflow 縮成一段可 review 的工作。

## Input、artifact 和 review 點樣令 evidence 可追：不靠長 transcript 也可收貨

card 第二格記 AI role、approved input 類別和 artifact／版本。你不需要把所有原文和聊天紀錄貼進去；記得來源類型、檔名、版本或可回看的位置已足夠。重點是 reviewer 能知道這份 evidence 是否來自允許材料，和 AI 最後確實交了一份甚麼可被檢查的東西。

第三格是 review 和 control。不要寫「已 QA」，而要寫 reviewer 實際檢查的 rule：每項是否能回到原資料、unknown 有否標示、格式是否能交下一手、是否越過 scope。review 結果可為 accept、revise 或 stop；三者都比一句「看起來好」更有資訊。

**Jimmy 的結論：** 可追溯 evidence 不是保留所有細節，而是讓另一個人能重建本輪的資料邊界、artifact 與收貨判斷。少而清楚，比多而模糊更有用。

| Card 格 | 要記甚麼 | 不應變成甚麼 |
|---|---|---|
| AI role | 整理、分類、起 draft | 「AI 做晒」 |
| Approved input | 公開 URL／已批 schema | 私有 raw transcript |
| Artifact | 檔名、版本、可 review 內容 | 一句 done |
| Review rule | source、unknown、format、scope | 模糊「已 QA」 |
| Decision | accept／revise／stop | AI 自動批准 |

若 artifact 涉及敏感資料，card 只記其類型與保管位置，不能因為要證明價值而複製內容進公開或廣泛可見記錄。

## AI value 怎樣寫才不誇大：已觀察到、仍未證明和例外必須分開

最有價值的一格，是將已觀察到和仍未證明拆開。已觀察到可以是「本輪由材料齊到可 review draft 的時間可被記錄」「owner 可用固定 checklist 收貨」「三條資料不足已被標 unknown」。仍未證明可以是「是否長期節省工時」「是否改善客戶體驗」「是否能擴到其他資料類型」。這個分法能阻止一次順利 output 被誤讀成全面成果。

例外與 rework 也要如實記下。若三條題目原資料不足、某一欄常漏、reviewer 每次都退同一種問題，這不是 card 的尷尬內容，而是下一輪最有價值的 evidence。沒有例外記錄，你只能繼續猜要不要加工具、改 prompt 或停止。

**Jimmy 的結論：** 不誇大的 value proof，不是把效果說小；是把已看到、尚未知、需要修正的事情分開。這令下一輪可以用 evidence，而不是用氣氛決定。

| 寫法 | 例子 | 它不代表甚麼 |
|---|---|---|
| 已觀察到 | 可記錄到可 review 的時間 | 固定節省 X 小時 |
| 已觀察到 | owner 能按 checklist review | 已全公司 adoption |
| 仍未證明 | 是否適用更多資料類型 | 不能先宣稱可 scale |
| Exception | 三條題目資料不足 | 不等於 AI 全部無用 |
| Rework pattern | 常漏 source link | 指向下一條 rule／template |

不要為了讓 card 漂亮而刪走 exception。透明的例外，正好顯示你知道怎樣管理真工作，而不是只展示最順的一次。

## Retain、revise、stop 怎樣揀：next decision 應由 evidence，不由工具熱度決定

proof card 最後不是一句「繼續優化」，而是選一個明確 decision。retain 代表 input、artifact、review 和 observation 已足以再跑一次；revise 代表有問題但知道應補 source、format、review rule 或 scope 哪一格；stop 代表風險、rework 或 owner 成本已超過目前值得學到的東西。stop 不是失敗，它避免團隊把資源投在錯的 workflow。

decision 後只改一格。若同時換模型、加 integration、重寫 prompt、擴大人數，就很難知道是甚麼令結果改變。證據不足時，保持 pilot 小而清楚，通常比很快宣布 scale 更成熟。

**Jimmy 的結論：** Retain、revise、stop 是 value proof 的真正交付。card 不只是記錄過去，而是讓團隊用 evidence 決定下一步投資在哪裡。

| Decision | 何時選 | 下一輪只做甚麼 |
|---|---|---|
| Retain | workflow 在本輪 scope 可再跑 | 用同樣 rule 跑第二次 |
| Revise | 問題可定位到一格 | 補 source／format／review rule |
| Stop | 風險或成本不值得 | 留下原因，不硬推 |
| Limited scale | 多輪 evidence 與 owner 都穩 | 只加小範圍／一個 cohort |

如果你尚未有任何 run receipt，不要直接寫 proof card。先記一次具體 execution，否則 evidence 很容易退化成回憶和印象。

## 一個公開安全例子：FAQ draft pilot 怎樣寫成不誇大的 value proof card

假設團隊每週要整理公開 FAQ，原本資料散在幾頁，初稿常漏題。今輪 AI 只把指定公開資料分類成 internal draft；不可更新網站、不可處理客戶資料、不可對外回覆。artifact 是一份 FAQ draft，包含來源位置、重複題和待確認欄；content owner 按「每項可回原資料、unknown 有否標示、格式可否接手」review。

card 可以記：已觀察到從材料齊到可 review draft 的時間可被記錄，且三條資料不足題目被正確標出；仍未證明是否節省長期工時、是否提升客戶體驗、是否適用其他 FAQ 類型；例外是 source mapping 不夠清晰。decision 選 revise，下一輪只改善 source mapping，不加新工具。

**Jimmy 的結論：** 這張 card 沒有承諾 ROI，卻給出了有用下一步：workflow 有可用 artifact、例外可見、owner 有 decision。這比一個「AI 很有效」的說法可靠得多。

| Card 格 | 例子內容 | 邊界 |
|---|---|---|
| Pain／scope | FAQ 分散 → internal category draft | 不更新網站 |
| Input／artifact | approved public FAQ → draft＋source | 不讀客戶資料 |
| Review | content owner + checklist | 不自行公開 |
| Observation | 可記錄 review time／unknown | 不代表長期 ROI |
| Exception | source mapping 不清 | 不補猜 |
| Decision | revise source mapping | 不一次擴大 |

這是 synthetic 教學情境，不代表任何特定 FAQ、客戶或 DotAI pilot 已有相同成果。它展示的是 evidence 如何被誠實整理。

## 今日怎樣寫第一張 value proof card：留一個小 evidence，而不是發一個大 claim

選一輪已有 reviewer 的低風險 AI 工作，填六格：work pain／scope、AI role／approved input／artifact、review rule、已觀察到、仍未證明／exception、next decision。每格只需一句，但要具體到另一人可以追問、核對或在下一輪使用。

若沒有 owner review、artifact 或清楚 input，先不要填成 value proof。回到 work card 或 run receipt 補設計；若有 evidence 但還不足以 scale，保留在 private decision record。公開內容只可展示清洗後的工作方法，不能把未驗證數字或私有資料包裝成案例。

**Jimmy 的結論：** 第一張 value proof card 的成功，是你可以誠實回答：「AI 今次幫了哪一手？我看到甚麼？還未知道甚麼？因此下一步做甚麼？」答到，已經比宣稱 ROI 更接近價值。

| 今日先填 | 合格訊號 | 未合格時回到哪裡 |
|---|---|---|
| Work pain／scope | AI 只做一個 bounded action | work card |
| Artifact／review | 有 reviewer 可收貨 | run receipt |
| Observation | 一個具體 workflow change | 再跑一次 pilot |
| Unknown／exception | 不確定可見 | 不要假裝結果 |
| Decision | retain／revise／stop | 定一個最小下一步 |

想先設計一條可驗收 AI 工作，讀 [將一件重複工作寫成 AI work card](write-an-ai-work-card.md)；想記錄每一次 run 的收貨證據，讀 [AI 話做完時點樣先收貨](write-an-ai-run-receipt.md)。

> 真 proof 不是講 AI 有幾勁；是坦白講清楚它幫邊一段工作、交咗乜、邊個 check，同埋仲有乜未證明。

← [返回 AI Value Creator](../05-ai-value-creator.md) · [按問題瀏覽](../BROWSE.md)
