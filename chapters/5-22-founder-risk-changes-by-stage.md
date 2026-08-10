# AI founder 每一階段怕的事不同：先找最可能令價值斷掉的一格

剛開始做 AI 產品、服務或課程時，大家很容易把風險理解成「選錯模型」或「技術很快過時」。技術當然會變，但真正令一件事失敗的原因會隨階段改變：早期可能根本沒有人需要；做出 demo 後可能沒有人願意把它放進 workflow；開始有客戶後，可能是交付、權限、支援和維護撐不住。

如果每個階段都用同一個答案，例如更快 build、再加更多 tools、再加一個 Agent，便很容易解錯問題。你可能在市場還未確認時花太多時間做介面；在 pilot 尚未受控時急著賣成效；在團隊未採用時不斷擴大 access。看似前進，實際讓風險越堆越高。

Jimmy 的看法是：AI founder 的工作不是永遠追最快技術，而是在每個階段先找出最可能令價值斷掉的一格。先用最低成本驗證最大的未知，讓產品、服務、教育或 adoption 的下一步由 evidence 決定，而不是由工具熱潮決定。

AI founder · AI product · AI service · founder risk · product validation · pilot · adoption · scale

| 你在甚麼階段 | 最可能斷掉的價值 | 先留下甚麼 evidence |
|---|---|---|
| 想法 | 沒有真工作痛點 | problem interview／workflow map |
| Pilot | demo 不可靠或不安全 | approved input、review、run receipt |
| 交付 | 每次都要由零客製 | service card、template、owner boundary |
| 採用 | access 多但沒人用 | safe outcome、repeat use、卡點 |
| 擴大 | 權限、例外、維護失控 | governance、measurement、rollback |
| 長期 | 內容／產品方向散開 | canonical decision 與 evidence path |

## AI idea 最早期應怕甚麼：不要把新能力的興奮誤認成真需求

看見一個新模型或 Agent 能力時，很自然會立刻想到一個產品。可是「做得到」和「有人正在為它痛」是兩件不同的事。若你還不知道目標使用者今天怎樣完成這個工作、哪一步最慢、最常重做或最難交接，漂亮 demo 很可能只解了你自己覺得有趣的問題。

早期最需要的不是完整平台，而是一個清楚 workflow pain。找一件重複、低風險、有人願意一起驗證的工作，問它不存在時對方現在怎樣辛苦地完成這一手。這把討論由「Agent 可以做甚麼」拉回「這個人真正需要哪個改變」。

**Jimmy 的結論：** 想法期最大的風險不是模型選錯，而是 build 了沒有人願意改做法的東西。先找到真工作痛點，才值得投入更多建造。

| 早期常見衝動 | 它忽略甚麼 | 較好的最低成本驗證 |
|---|---|---|
| 先砌完整 agent team | 使用者是否真有這個痛點 | 畫現在 workflow，找重做位 |
| 先做漂亮介面 | 誰會每週重複使用 | 用手動／draft 版跟一人試 |
| 先比較所有模型 | output 要服務哪個決定 | 定一份可驗收 artifact |
| 先講市場很大 | 一開始誰願意改做法 | 找一個明確 owner |
| 先承諾轉型 | 邊界與風險是否可管理 | 選一條低風險 routine |

若你仍答不到「誰在甚麼工作最痛」，不要用更大 build 掩蓋。先做 discovery，讓下一步建立在真工作而不是想像上。

## AI demo 變 pilot 時應怕甚麼：一次成功不等於可靠交付

第一個 output 很好看時，風險會由「有沒有人需要」轉成「這是否只在理想情況成功」。它用了甚麼資料？換一個 input 會否失準？誰有權說這份結果可用？出錯時能否找回原因、停止下一步？若沒有答案，demo 還未變成可以交給別人使用的 pilot。

小範圍 pilot 的目的不是證明 AI 很神，而是找出它在甚麼條件下真的值得繼續。它需要已批准 input、明確 artifact、human review、run receipt 和 stop line。這些元素讓你看見問題是出在資料、規則、模型、workflow 還是 owner，而不是將每一個失敗都誤解成技術不夠好。

**Jimmy 的結論：** Pilot 階段最大的風險是把一次成功當成可交付承諾。先讓工作在受控條件下重複跑，才有資格談品質、ROI 或擴大。

| Demo 看似成功 | Pilot 必須再問 | 第一輪要留甚麼 |
|---|---|---|
| output 很漂亮 | input 是否有邊界 | approved source list |
| 講者即時補救 | 誰平日 review | named owner |
| 一次跑通 | 不同例外如何處理 | stop／fallback rule |
| 速度很快 | 是否少了真重做 | outcome receipt |
| 能做很多 action | 哪一手最值得先做 | bounded scope |

未有 evidence 前，不應接敏感資料、直接外發或把成效寫成客戶保證。把 AI 保持在 draft、整理、提示層，反而能更快學到真實限制。

## AI service 開始交付後應怕甚麼：不要把客製化忙碌誤認成可 scale

開始有人願意付錢或找你協助時，最危險的狀況是每一個 project 都從零開始：你要靠自己腦內補 context、改 prompt、處理例外、解釋 scope、追 owner。你會很忙，也可能收到正面 feedback，但沒有任何部分能被同事接手、被客戶理解或在下一次較快交付。

這不是服務沒有價值，而是它還未產品化。你要找出哪一段已跑過、可被說清：為誰解甚麼問題、用甚麼 input、交甚麼 artifact、誰 review、哪些不在 scope、何時停止。把這些寫成 service card、template 或 Skill，才是讓交付逐步穩定的開始。

**Jimmy 的結論：** 交付期的風險不是客製化本身，而是所有價值都只存在你腦中。先把一條已跑通的 workflow 變成可管理承諾，再談 scale。

| 你很忙但仍危險的訊號 | 它代表甚麼 | 要留下的資產 |
|---|---|---|
| 每次都重寫同類說明 | scope 未標準化 | service card |
| 客戶不知買到甚麼 | artifact 不清楚 | deliverable checklist |
| 只有你可修正問題 | rule 未外顯 | workflow／review template |
| 一加人品質便變 | owner 與 acceptance 不清 | handoff／rubric |
| 每次都承諾很多 | evidence boundary 消失 | in-scope／out-of-scope |

如果每一次都還靠即場判斷十種例外，先不要把它叫成熟產品。繼續收集 pattern、縮小承諾、留下 reusable assets，才是更健康的成長。

## AI adoption 擴大時應怕甚麼：access 不等於團隊真正會用

當更多人得到帳戶、工具或 workflow 連結時，很容易以為 adoption 正在發生。其實使用者可能不知道何時用、怕負責 output、找不到安全材料，或用了之後發現 cleanup 比原本更多。若只看開通數或課堂人數，你看不見最重要的問題：有沒有一條工作被第二次、第三次自發使用。

擴大前要設計不同入口、onboarding、support 和回看 evidence。AI User 需要第一個安全成果；AI Operator 需要交接與例外；owner 需要看到工作是否值得繼續。把所有人塞進同一條工具 training，通常只會令 adoption 看起來很熱鬧，實際沒有改變日常 workflow。

**Jimmy 的結論：** 擴大期的風險不是人數不夠，而是 access 被誤當成 adoption。只有可重複使用、有 owner、有 evidence 的 workflow 才值得帶到更多人。

| 表面擴大 | 真正要看 | 先補甚麼 |
|---|---|---|
| 更多 account | 完成過幾個安全 outcome | use-case trigger |
| 更多課堂 | 學員能否回到真工作再跑 | safe example／completion line |
| 更多 workflow | 哪一條真正被重複用 | adoption receipt |
| 更多資料 access | boundary 是否仍成立 | governance／approval |
| 更多 automation | cleanup 是否反而增加 | rework review |

若你未能說出一條 workflow 的 repeat use、卡點和 owner，先不要全面 rollout。先把最接近真工作的幾位使用者帶過第一個小循環。

## AI 產品開始 scale 時應怕甚麼：例外、權限與維護會比能力更快放大

當一條 workflow 開始接更多資料、更多 action 或更多團隊，例外也會一起放大。原本由 founder 手動補救的小錯誤，可能變成權限不清、資料越界、品質不一致、沒人知道 agent 做過甚麼。此時最大的風險通常不再是模型能力，而是沒有 governance、state、rollback 與維護 owner。

scale 不一定代表技術更複雜，它代表責任必須更清楚。每加一種 access 或 action，都要重問 input boundary 是否仍合理、review 是否仍跟得上、receipt 是否足以回看、stop line 是否可行。若答案不是肯定，暫停或縮小範圍是成熟決定，不是失敗。

**Jimmy 的結論：** Scale 的基礎不是更大架構，而是例外可見、權限可控、責任可追。沒有這三樣，能力越強，風險放大得越快。

| 擴大變化 | 必問治理問題 | evidence 未足時怎樣做 |
|---|---|---|
| 加新資料來源 | 是否已批准且最小必要？ | 不加 access，先試 public input |
| 加新 action | 誰批准、能否 rollback？ | 保持 draft-only |
| 加新使用者 | onboarding 與 support 夠不夠？ | 限在小 cohort |
| 加新 workflow | exception 是否能分類？ | 先寫 work card |
| 加 automation | output 是否仍被收貨？ | 補 owner 與 receipt |

「先停一下」在這個階段可以保護信任和學習。比起把未成熟系統推到更多地方，留住可回看的 evidence 更有價值。

## 一個 AI founder 安全例子：由公開資料 briefing 找出現在最該驗證的風險

假設一位 founder 想做一個幫團隊整理公開資料的 AI service。想法期，他先不砌完整平台，而是找三位每週真的要做 internal briefing 的人，了解他們在哪一手重做。Pilot 期，他限定 Agent 只讀 approved public sources、起 internal draft、標 unknown，由內容 owner review，並留下每次 rework 的 receipt。

如果三次後大家發現 template 穩定、owner 容易收貨、重做真的減少，交付期才把流程寫成 service card；若使用者不知道何時用，則先做 adoption bundle，而不是加新功能。當有更多人想用，再檢查權限、support、state 和 rollback 是否足以承擔，而非把成功 demo 直接複製到所有人。

**Jimmy 的結論：** 同一個 AI 想法，在不同階段需要不同問題。Founder 的成熟不在於一直 build，而在於能把下一週投資放在當下最大的未知。

| 階段 | 現在要驗證 | 暫時不急著做 |
|---|---|---|
| 想法 | 有沒有重複真工作痛點 | 完整產品介面 |
| Pilot | input、review、stop 是否有效 | 高權限 automation |
| 交付 | artifact 與 scope 能否重複 | 無限量客製承諾 |
| Adoption | 是否有 repeat use | 全公司 rollout |
| Scale | governance 與維護能否承擔 | 盲目加 access |

這是 synthetic 教學情境，不代表任何特定 founder、服務或客戶已有相同結果。它示範的是如何用階段風險，決定下一個最小、最誠實的行動。

## 今日怎樣找出你最值得驗證的 founder risk：選一個階段，只寫一個斷點

看一看你現在最投入的 AI 產品、課程、服務或內容計劃，先選它真正所處的階段：想法、pilot、交付、adoption 還是 scale。然後只寫一個句子：「如果＿＿＿未被證明／解決，這件事便不值得擴大。」不要一次列二十個風險，因為那會令下一步失焦。

接著選一個最低成本驗證：做一次 workflow discovery、跑一個 draft-only pilot、寫一張 service card、帶三位使用者完成安全成果，或補一張治理卡。若你未能寫出這個最小 action，通常代表階段還未判清；回去看真工作，而不是看下一個工具發佈。

**Jimmy 的結論：** AI founder 的下一步不應由新技術決定，而應由目前最可能令價值斷掉的風險決定。先驗證一格，才能更穩地走去下一階段。

| 今天先問 | 對應的下一步 | 完成後留下甚麼 |
|---|---|---|
| 有沒有人真需要？ | workflow discovery | pain／owner map |
| Pilot 是否可靠？ | controlled run | receipt／stop rule |
| 是否可交付？ | service card | scope／artifact |
| 有沒有人真使用？ | adoption bundle | first／repeat use evidence |
| 是否可安全擴大？ | governance review | access／owner／rollback decision |

想先分清一個 idea 是否值得 build，讀 [先用過，再決定建不建](5-24-use-before-build.md)；如果你現在已跑出一條 workflow，想知道何時能對外交付，讀 [由 AI Builder 走到服務](5-14-builder-to-service.md)。

> AI founder 的工作不是永遠追最快技術，而是在每個階段先找出最可能令價值斷掉的一格。

← [返回 AI Value Creator](../05-ai-value-creator.md) · [按問題瀏覽](../BROWSE.md)
