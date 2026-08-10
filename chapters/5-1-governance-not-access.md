# 公司買咗 AI account，點解仲未算 AI transformation？治理唔等於開咗權限

一間公司買了幾個 AI account、開了課程、同事也開始用 chatbot，不代表 AI 已經進入公司運作。最常見的情況是：管理層看到使用量和示範，覺得公司正在轉型；前線卻只是在原有流程外多了一個工具，資料仍然散、責任仍然不清、最後仍要人手重做。

問題不是同事不夠努力，也不只是 prompt 寫得不好。只要 AI 沒有被接到一條真 workflow、沒有清楚知道可用哪些 context、誰驗收結果、出事交給誰，以及如何量度改變，團隊就無法分辨「偶然幫到手」與「真的改善了工作」。開 access 只是開始，並不會自己形成 governance。

Jimmy 的看法是：AI transformation 的分水嶺不是有沒有工具或 training，而是 AI 有沒有在一條真實 workflow 裡被治理和量度。治理不是設更多限制，而是讓每個人知道 AI 可以做哪一手、不能做哪一手、結果由誰負責；量度則讓團隊誠實判斷應保留、修正還是停止。

AI 實戰 · AI Value Creator · AI adoption · governance · workflow · integration · measurement · pilot

| 由工具走向轉型的格 | 真正要問的問題 | 完成後留下甚麼 |
|---|---|---|
| Access | 誰可用甚麼工具？ | 基本可用帳戶與培訓 |
| Workflow | 哪件真工作由 AI 協助哪一手？ | 狹窄、可重複的工作卡 |
| Context | 它可讀甚麼資料？ | 已批准的最小材料包 |
| Governance | 誰 review、何時停、誰批准？ | owner、approval、stop line |
| Measurement | 到底改善了甚麼？ | quality、cycle time、rework 或風險觀察 |

## AI access 點解唔等於 AI adoption：多一個工具，未必改變任何真工作

當團隊有了 ChatGPT、Gemini、Claude 或其他工具，最早看到的通常是個人效率提升：有人快些起草、有些人更快整理筆記、有人可以問技術問題。這些都是有用的起點，但它們仍可能只停留在每個人的個人桌面，沒有改變任何交接、品質檢查或團隊的共同做法。

若一份工作仍然由不同人自己找資料、自己判斷哪版可信、最後靠另一人救火，工具多了只代表產出速度可能加快，並不代表 workflow 更可靠。真正 adoption 是 AI 進入一條工作時，大家能說清楚它接了哪一段、輸入從哪來、結果怎樣驗收，以及沒把握時誰接手。

**Jimmy 的結論：** access 是讓人開始試；adoption 是讓一條工作有新的、可重複的做法。不要用 account 數量或使用次數，代替「上星期哪一件工作真的因此交得更好」這個問題。

| 你看到的現象 | 還未代表甚麼 | 要再問的 workflow 問題 |
|---|---|---|
| 同事都有 AI account | 工具已被接入工作 | 上星期哪一手工作有用到？ |
| 有人說節省時間 | 團隊已減少 rework | 結果誰 review、漏項少了嗎？ |
| 上過 prompt 課 | 有共同 context 與規則 | 哪份資料可用、哪些不可用？ |
| 做過漂亮 demo | 可在真流程穩定重複 | demo 之後的 owner 與 stop line 是甚麼？ |

從第一條真 workflow 開始，比要求所有人「多用 AI」更能讓團隊看見下一步。

## AI workflow integration 是甚麼：把工具放進已有 owner、input 和交付的工作

integration 不是把 AI 接到所有系統，而是選一條已有真實 owner、相對穩定 input、可見交付和可 review 的工作，讓 AI 先協助其中一手。這一手可能是整理資料、起內部 draft、標記缺口、生成 checklist 或預備 review queue；它不必一開始就是最終決策或外部發送。

最常被跳過的是 context 與 hand-off。AI 若不知道哪份資料是 current、哪些內容可讀、哪些是未知，便很容易把舊資料或推論寫進 output。當它完成後，下一手也要看得出哪些地方由 AI 起草、哪些地方仍要人確認，否則 integration 只是在原有流程旁邊多加一段難追查的文字。

**Jimmy 的結論：** integration 的價值不在「接了多少工具」，而在 AI 能否被放進一段有 owner、有 input、有 artifact 的真工作。先整合一手，再決定是否值得接更多。

| Workflow 組件 | 要寫清楚甚麼 | 安全起點 |
|---|---|---|
| Owner | 這條工作由誰負責結果 | 內容或營運 owner |
| Input | 只可用哪類已批准資料 | 公開 FAQ、已批准 brief |
| AI hand-off | AI 只做哪一手 | 起 internal draft、標缺口 |
| Artifact | 人要 review 甚麼 | 表格、draft、receipt |
| Next hand-off | 下一手怎樣接 | checklist review 或 human decision |

若一條工作沒有 owner、input 或 artifact，先不要急著連接更多系統。那代表 workflow 本身仍未準備好交給 AI。

## AI governance 不是阻止使用：把權限、驗收與 stop line 放回正確位置

有些團隊把 governance 理解成一大堆禁止規則，結果大家怕用 AI；另一些則反過來，因為怕拖慢速度就讓工具自行找資料、改內容或推進下一步。兩個極端都令 adoption 難以持續：前者沒有可試的路，後者沒有可收的風險。

實用治理要回答幾條具體問題：AI 只可讀甚麼？這一輪可草擬還是可改檔案？結果誰用哪個 checklist review？遇到缺資料、私人資料、對外承諾或不可逆動作時，要停在哪裡、交給誰？當這些答案在 workflow 裡可見，團隊便不需要每次由零猜規則。

**Jimmy 的結論：** governance 不是「有權或無權」的開關；它是把 read、draft、write、send、publish 和 human approval 分開。清楚的邊界會令低風險工作更容易開始，高風險工作更容易正確停下。

| 行動層級 | 可以先怎樣用 AI | 必須補上的治理 |
|---|---|---|
| Read | 整理已批准公開資料 | 最小 reference scope |
| Draft | 起內部文件與 review queue | source rule、owner review |
| Write | 改指定可回退檔案 | action boundary、diff |
| Send | 準備對外訊息 | human approval、收件範圍 |
| Publish／production | 公開或改 live 系統 | 明確權限、最後確認、rollback |

當你未能說明誰可以批准下一級 action，最安全也最有進度的做法是停在 draft 或 review queue。這不是做少了，而是在建立可擴展的信任。

## AI measurement 點樣避免假轉型：由「用咗幾多」改問工作有冇變好

只量 account 使用量、prompt 次數或培訓完成率，很容易讓公司覺得 adoption 做得不錯，卻看不見真工作有沒有改善。這些是 activity 指標，不是 workflow outcome。它們可以告訴你有人在試，不能告訴你流程的質量、速度或風險是否真的變好。

量度不需一開始很複雜。選一條 pilot workflow，只觀察一兩個可回看的痕跡：資料齊備到可 review 的時間、被 reviewer 退回的次數、漏欄或錯誤率、正確標記 unknown 的個案，或某個風險是否少了。這些 evidence 會幫 owner 判斷是 retain、revise 還是 stop，不會迫使團隊在未驗證前承諾 ROI。

**Jimmy 的結論：** 不要只問「大家有冇用 AI」，要問「這條工作交付的質量、速度或風險有冇實際改變」。量度是為了學習和決定，不是為了製造漂亮數字。

| 只量 activity | 更接近 outcome 的觀察 | 可以支持的決定 |
|---|---|---|
| 帳戶登入數 | 資料齊備到可 review 的時間 | 值不值得保留 pilot |
| prompt 次數 | draft 被退回／重做次數 | input 或 rubric 要否修正 |
| 課程出席率 | 漏項、錯誤或 unknown 處理 | workflow 是否更可靠 |
| 生成內容數 | owner 實際採納比例與原因 | job 範圍是否合適 |
| 工具連接數 | 正確 stop 的個案 | 是否需要補治理 |

如果沒有可觀察的 workflow outcome，就先不要把試用稱為 transformation。保留為 experiment，反而能更誠實地走到下一步。

## 管理層與前線為何常有成熟度落差：用真工作取代印象分數

一份面向知識工作者的全球調查曾發現，決策者對公司 AI 能力的信心明顯高於實際使用者；同一研究也把 integration、governance 和 measurement 視為較成熟組織常見的特徵。這類資料的價值不是替香港公司打分，而是提醒我們：管理層的「我們已經有 AI」與前線的「我仍要自己救流程」可以同時存在。

因此，不要把成熟度當成一條公司口號，也不要急著用外部比例來判定自己公司。更有用的方法是讓兩邊各自說出一條上星期的真工作：哪一手由 AI 協助？用了甚麼 context？誰 review？最後結果比以前有甚麼改變？若答不出來，代表是印象，不是 evidence。

**Jimmy 的結論：** 成熟度落差不是用一份問卷取勝，而是用同一條真 workflow 對齊。當管理層和前線都能指向同一份 artifact、同一個 owner 和同一個 outcome，才有共同的 adoption 事實。

| 問法 | 只得到甚麼 | 改成甚麼才可行動 |
|---|---|---|
| 「公司 AI 成熟嗎？」 | 印象分數與口號 | 上星期哪條 workflow 有實例？ |
| 「大家有冇用？」 | 個人使用感受 | input、artifact、review 是甚麼？ |
| 「投資值不值？」 | 大而模糊的 ROI 期待 | pilot 的質量、時間或風險有冇變？ |
| 「誰要負責 AI？」 | 空泛職位討論 | 每條 workflow 的 owner 是誰？ |

外部調查只能提供問題框架，不能取代你自己公司的工作證據。不同規模、行業、資料風險和客戶責任都會令最合適的 adoption 路線不同。

## 一個公開安全例子：活動後 follow-up briefing pilot 怎樣接 workflow、治理和量度

假設一個團隊每次活動後都要整理已批准活動資料，起一份 internal follow-up briefing，再由人 review 後才寫入下一步系統。它不是先問「有沒有 ChatGPT」，而是找出每次誰在整理資料、哪裏最常漏欄、從資料齊備到可以 review 要多久。

pilot 可以把 AI 放在一個小位置：只讀已批准的活動 brief、公開 FAQ 和欄位 schema，起 internal follow-up draft，標出缺資料和待確認位置。內容 owner 決定資訊是否準確；CRM owner 核對可否寫入；所有對外發送仍要 human approval。初期不讓 AI 自己寄出、不讓它自行讀客戶資料或改 production。

**Jimmy 的結論：** 這才是 adoption：一條工作接好 context、權限、驗收和指標，讓團隊看見它有沒有創造價值，而不是演示一個看似 autonomous 的 Agent。

| Pilot 格 | 在例子裡怎樣做 | 可觀察 evidence |
|---|---|---|
| Workflow | 活動資料到 internal briefing draft | 可 review 前的時間 |
| Context | 批准 brief、FAQ、schema | 資料來源清單 |
| Governance | content／CRM owner、外發 approval | review 與 stop receipt |
| Artifact | internal follow-up draft | 缺欄與修正記錄 |
| Measurement | cycle time、漏欄、rework | retain、revise 或 stop 決定 |

這是一個 synthetic、低風險例子；它不代表任何特定客戶或團隊已得到相同成效，也不授權把未公開資料、客戶資料或對外發送交給 AI。

## 今日怎樣開始第一條 AI governance card：不要由公司政策或新工具開始

如果你想帶領團隊用 AI，不必先寫一份很大的 AI policy，也不必先買更多工具。選一條重複、低風險、已有 owner 的工作，填五格：可用 context、AI 只做哪一手、artifact、approval／stop、以及本輪要觀察甚麼。這張 card 會迫使你把 governance 變成工作上的可見選擇，而不是抽象口號。

開始時可以只問管理層和前線各一條問題：「上星期哪一件工作，因為 AI 而真的交得更快、更準或更安全？」如果答法不同，就把兩邊說的工作畫成同一張卡；若沒有具體工作，就先跑一個小 pilot，而不是用感覺宣布公司已轉型。

**Jimmy 的結論：** AI adoption 的下一步不是推人用多一個工具，而是把一條真 workflow 接好 context、權限、驗收和指標。先讓一條工作有 evidence，團隊才知道應如何擴大。

| Governance card 欄位 | 你要寫甚麼 | 安全起點 |
|---|---|---|
| Workflow | 一件重複、低風險工作 | 已批准資料整理成 internal draft |
| Context | 可讀的最小材料 | 公開／已批准 brief 與格式 |
| AI hand-off | 只幫哪一手 | 起草、分類、標缺口 |
| Approval／stop | 誰 review，何時停 | owner review、缺 evidence 即停 |
| Measurement | 一兩個 outcome 痕跡 | cycle time、漏欄、rework |

未完成這一輪小 pilot 前，暫時不要以為 access、training 或 dashboard 已等於 transformation；亦不要讓 AI 自行外發、寫入 production、讀取私人／客戶資料或作高後果決定。下一步可看 [如何設計一條安全 adoption pilot](5-6-design-adoption-pilot.md)。

> AI transformation 不是公司買咗幾個 account，而是 AI 有冇接到一條真 workflow，讀到需要的 context，知道甚麼不能做，出來的結果有人驗收，最後你量到質量、速度或風險有冇變。

← [返回 AI Value Creator](../05-ai-value-creator.md) · [Start Here](../README.md)
