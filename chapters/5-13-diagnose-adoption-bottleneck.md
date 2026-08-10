# 帶人用 AI 唔好先加 prompt：先診斷卡在工具、流程、能力、意欲還是治理

「AI 用唔到」只是症狀。有人其實卡在工具不能安全處理所需格式或語言；有人還未拆清 workflow；有人有興趣但沒有 sample、時間或 reviewer；有人擔心出錯；也有人根本沒有資料權限或對外 approval。若把所有問題都當成「不夠識 prompt」，你會將錯的介入加到錯的位置。

這也是為何同一堂培訓、同一份 template，對不同人效果可以完全不同。對一個沒有清楚 input 的人，再好 prompt 都只是猜；對一個怕資料出事的人，更多技巧會增加焦慮；對一個沒有 owner 的團隊，漂亮 output 無處可去。要幫人進步，先要知道工作最早在哪裏斷。

Jimmy 的看法是：帶人用 AI 的第一步，不是給多一個 prompt；是幫他看見哪一段真工作最早斷了，然後只補一個可驗收的下一步。用可行性、workflow、能力、意欲、治理五格診斷，不是為了分類人，而是為了設計一個小而對位的介入。

AI 實戰 · AI Value Creator · AI adoption · bottleneck diagnosis · workflow · governance · coaching

| 最早卡位 | 要問甚麼 | 本輪只補甚麼 |
|---|---|---|
| 可行性 | 工具能否安全處理格式、語言、權限？ | 查技術或換可行小任務 |
| Workflow | input、判斷、output、handoff 清楚嗎？ | 畫工作 map／brief |
| 能力 | 有 context、sample、時間、reviewer 跑一次嗎？ | 低風險可 review 練習 |
| 意欲 | 他知道為何值得改、害怕甚麼嗎？ | 看真痛點、設安全小成果 |
| 治理 | 資料、權限、外發、例外誰負責？ | owner、boundary、approval |

## 為何「AI 用唔到」不是一個答案：同一症狀可能來自五種不同斷點

一個人說「AI 用唔到」，可能是他把一個掃描品質很差的檔案交給工具，這是可行性問題；也可能是他根本未說清想要甚麼 output，這是 workflow 問題；或是他知道想做甚麼，卻沒有時間、例子和 reviewer 在真工作跑一次，這是能力問題。

同一句話背後也可能是意欲或治理。有人怕出錯、怕加班、怕資料外洩，未必是抗拒改變；他可能正在指出合理風險。有人想讓 AI 直接處理客戶資料或外發內容，卻沒有 owner 和 approval，這不是 prompt 能解決的問題。先辨認斷點，才能避免把技術、人的感受和公司責任混在一起。

**Jimmy 的結論：** 「AI 用唔到」是開始診斷的訊號，不是診斷結果。先找最早不成立的格，才知道本輪應做 workflow map、練習、對話、control card，還是乾脆停止。

| 聽到的症狀 | 可能的真正斷點 | 不應立即做甚麼 |
|---|---|---|
| 「個工具唔得」 | 格式、語言、權限可行性 | 強迫學更多 prompt |
| 「每次出嚟都唔同」 | context／workflow 未清 | 立刻換模型 |
| 「我唔敢用」 | 意欲、風險或 owner 缺失 | 說對方不肯學 |
| 「整完都冇人睇」 | artifact／review handoff 不存在 | 加更多生成步驟 |
| 「怕發錯出去」 | governance／approval 未定 | 直接接 send automation |

每次只修一個最早斷點。後面的問題暫時不用全解，否則介入會變成另一個複雜、難以開始的 AI project。

## 可行性卡住時怎樣處理：先問工具、資料格式與權限是否真的可行

可行性是最前面的一格。AI 未必能可靠處理某種檔案、語言、網絡環境、資料格式或權限限制；也可能成本、延遲或準確度根本不適合這件工作。這時候再好的 workflow、training 或激勵都不能令它變成可行。

帶領者應先用一個公開、低風險樣本測試核心動作：工具能否讀到需要的材料？能否產出指定格式？是否可以在不擴大資料存取的情況下完成？若答案不行，正確選擇是換工具、換資料格式、縮小任務或保持人手，而不是把不可行包裝成「同事未適應」。

**Jimmy 的結論：** 技術可行是 adoption 的地基，不是最後才看的細節。不可行時先停，不要用更多 training 蓋過工具與資料的真限制。

| 可行性問題 | 可以做的小測試 | 若不成立怎樣做 |
|---|---|---|
| 工具能讀所需格式嗎？ | 用公開／synthetic 樣本 | 換格式或保持手動 |
| 工具能處理所需語言嗎？ | 檢查指定輸出與理解 | 換工具或縮 scope |
| 權限是否足夠且安全？ | 只看最小 approved input | 不要求更多 access |
| 成本／時間可接受嗎？ | 比較小 run 的延遲與後手 | 不做該 hand-off |
| 輸出是否能被驗收？ | 用固定 rubric review | 先設 quality bar |

可行性過關不代表可以自動擴大；它只代表可以進下一格，開始把真工作說清楚。

## Workflow 卡住時怎樣處理：input、output 與 handoff 未清，就先畫 map

很多人以為 AI 不好用，其實是工作本身沒有被說清。文章已選好嗎？要交一頁 brief 還是十個點？哪個 claim 不可用？結果交給誰？若這些問題答不清，模型只能猜，人類也無法決定結果是否合格。

這一格的介入很少是新 prompt。先把 input → task → artifact → review → handoff 畫出來，指定 current state 和完成線。小小一張 workflow map 已經能讓大家看出究竟缺資料、缺格式、缺 owner，還是其實這件工作沒有真正重複。

**Jimmy 的結論：** workflow 不清時，先畫 map，不要加 template。把工作入口和出口說清，AI 才有一個可以安全幫手的位置。

| Workflow 問題 | 要補甚麼 | 最小 artifact |
|---|---|---|
| 文章／資料未選好 | approved input scope | source list |
| output 不清 | 完成線與格式 | one-page brief template |
| 下一手不明 | handoff owner | current-state note |
| review 只靠感覺 | quality bar | checklist |
| 任務太大 | bounded hand-off | AI 只起 internal draft |

如果最早問題是 workflow，本輪不需要加 Agent、接 CRM 或自動發送。先讓人能看懂工作怎樣開始、怎樣交、怎樣停。

## 能力與意欲卡住時怎樣分：一個是做不到，一個是未想安全地做

能力問題是「想做但在真工作做不到」。可能缺 context、sample、時間、練習範圍或 reviewer；課堂上看過 demo，不等於能在自己的工作壓力下跑一次。這時候需要的是一個低風險、可 review 的練習，讓人完成一份小 artifact 並得到具體 feedback。

意欲問題則是「還未看到為何值得改，或有合理擔心」。有人可能怕 AI 令工作更麻煩、怕資料出事、怕出錯由自己負責。這不是要用更多口號壓過去；先聽他正在面對哪條真 workflow 摩擦，再設一個可停、可修、沒有外部後果的小成果。若反對指出工具真的不可行或治理未定，回到前面格處理。

**Jimmy 的結論：** 不要把做不到當不願意，也不要把不願意當懶。能力要靠安全實作與 review 培養；意欲要靠真痛點、可見價值和可信邊界建立。

| 聽到的說法 | 較可能的問題 | 對位介入 |
|---|---|---|
| 「我想試但不知道從哪開始」 | 能力／workflow | work brief 加 sample |
| 「課堂識，返工做不到」 | Ability | 小 run 加 reviewer |
| 「我怕出錯／洩漏」 | 意欲／governance | 低風險 scope、stop line |
| 「這件事本來唔需要改」 | Awareness／意欲 | 一起看 workflow 摩擦 |
| 「我冇時間再學」 | 工作負擔／意欲 | 選能減少一手重做的任務 |

帶領者的工作不是一次修好所有人，而是讓下一輪多一個可見 artifact。當能力或意欲改善後，再重新診斷，才知道下一個斷點。

## 治理卡住時怎樣處理：資料、權限、外發與例外要有人承擔

治理問題常被誤當成「大家太保守」。實際上它問的是非常具體的責任：AI 可讀哪些資料？可否起草、改檔、外發？發現未知或敏感內容誰處理？誰可以批准下一步？沒有這些答案，團隊就算有能力也不應把 workflow 推向高權限或不可逆行動。

首輪最好的做法通常是停在 public／approved input 和 internal draft；把 output 交給 human owner review。若需要加資料或權限，先寫 control card、action boundary、approval 和 rollback，再跑新的小範圍。治理不是為了阻止創新，而是讓團隊知道哪些低風險工作可以放心開始。

**Jimmy 的結論：** 治理不是最後一道合規關卡；它是 AI adoption 可以安全開始的條件。未有 owner、boundary 和 approval，先不要接外發、敏感資料或 production。

| 治理問題 | 要寫清楚甚麼 | 安全起點 |
|---|---|---|
| 資料 | 可讀哪些、不可讀哪些 | 公開／已批准材料 |
| Action | 可 draft、write、send 哪一層 | draft only |
| Review | 誰收貨、用甚麼 rule | human owner checklist |
| Exception | unknown／敏感資料怎處理 | stop 並 escalation |
| Change | 要擴大怎樣回退 | rollback plan |

若帶領者自己無權決定資料或外發，正確動作是找相應 owner；不要讓 AI 或學員用「先試下」繞過責任線。

## 一個公開安全例子：internal briefing 反覆重改，先補 workflow 而不是換工具

假設同事每星期想用 AI 整理公開文章成 internal briefing，但每次都要重改。不要立刻換工具。先問：文章已選好嗎？output 是一頁 brief 還是十個點？有沒有來源欄、unknown 標記和 reviewer？若答案都未清，最早問題就是 workflow／能力，而不是模型。

本輪只畫 input → draft → review → handoff，並做一個 brief template：主張、link、推論、unknown、下一步問題。先讓 AI 在指定公開文章上產生 internal draft；reviewer 檢查 source 和未知。只要這一格未穩，不接 CRM、不自動發送、不加更多 Agent；下一輪再根據退回原因決定補 context、sample 或 quality rule。

**Jimmy 的結論：** 這個例子說明最好的介入不是最複雜，而是最對位。先修 workflow，工具才有可能在正確位置真正幫到手。

| 診斷問題 | 例子答案 | 本輪介入 |
|---|---|---|
| 可行性 | 公開文章可被整理 | 維持現有工具 |
| Workflow | output／handoff 未清 | 畫 map、定 template |
| 能力 | 沒有固定 sample／review | 跑小 draft 練習 |
| 意欲 | 怕重改浪費時間 | 用低風險單一 hand-off |
| 治理 | 未碰敏感／外發 | 維持 draft-only |

這個例子只使用公開資料與 internal artifact，不允許 AI 接觸客戶／私人資料、CRM、外部發送、公開設定或 production 系統。

## 今日怎樣做一次 bottleneck diagnosis：只寫症狀、最早卡位、本輪 artifact、下次 reviewer

找一件最近失敗或一直沒有開始的 AI 工作。先寫症狀，不急著解釋；然後依五格找最早答不清的一項。最後只決定本輪要做的一個 artifact，以及下次由誰 review。這會把「AI 用唔到」由一個模糊抱怨變成一個可觀察、可改善的小 experiment。

下次 review 時，不要先問「大家係咪覺得 AI 好用咗」。先問最早卡位有沒有被清楚化：source scope 是否已定？workflow map 是否可走？學員有沒有跑出 artifact？owner 是否接得住？若答案仍然不行，留在同一格修，不要跳去更多工具。

**Jimmy 的結論：** 帶人用 AI 的第一步，不是給多一個 prompt；是幫他看見哪一段真工作最早斷了，然後只補一個可驗收的下一步。

| Bottleneck card | 你要寫甚麼 | 安全示例 |
|---|---|---|
| 症狀 | 甚麼一直不順 | internal brief 每次重改 |
| 最早卡位 | 五格中哪格先不成立 | workflow |
| 本輪 artifact | 只補甚麼 | input→draft→review map |
| Reviewer | 誰看下一輪 | content owner |
| Stop line | 何時不能繼續 | source／權限不清即停 |
| 下次 evidence | 怎樣知道有改善 | 退回原因是否減少 |

先從公開、低風險的 workflow 開始。未有清楚 evidence、owner 與 control 前，不要用一個好看的 demo 掩蓋 bottleneck，也不要將 AI 接到外部發送、客戶／私人資料、公開設定或 production。下一步可看 [如何由 AI Builder 走向可以服務他人的能力](5-14-builder-to-service.md)。

> 帶人用 AI 的第一步，不是給多一個 prompt；是幫他看見哪一段真工作最早斷了，然後只補一個可驗收的下一步。

← [返回 AI Value Creator](../05-ai-value-creator.md) · [查看五段地圖](../CURRENT-JOURNEY.md)
