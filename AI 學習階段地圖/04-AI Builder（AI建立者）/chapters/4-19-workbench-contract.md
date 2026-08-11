# 唔好淨係叫 AI 做嘢：先寫一張 workbench contract

你可能已經識得寫一份 task brief：目標是甚麼、要交甚麼、怎樣算合格。但當工作不止一句回答，而是牽涉一個 project、幾份參考資料、幾次修改或不同權限時，AI 還需要知道：它今次正在一個甚麼範圍內工作。

一句「幫我整好呢個 project」聽起來很清楚，實際上留了很多空位。它可讀哪份檔案？現行版本是哪份？可否改動？遇到資料不足時是否可自行找更多？完成是交一個 draft、做一個 diff，還是直接推進下一步？這些空位若不由人填，AI 只能猜。

Jimmy 的看法是：workbench contract 不是把 brief 寫得更長，而是把一輪工作可以在哪裏發生、可以碰甚麼、何時算交到和何時必須停講清楚。它令 AI 由「幫我搞掂」變成在一個可回退、可驗收的工作場內協作。

AI 實戰 · AI Builder · workbench · task contract · scope · authority · verification · human review

| Workbench contract 的一格 | 它解決甚麼問題 | 完成後留下甚麼 |
|---|---|---|
| 目的 | 不讓 AI 只追求表面整好 | 今輪 artifact 與成功條件 |
| 現行 state | 不用舊 chat 或錯版本開工 | 可信起點與版本 |
| 可讀 references | 不讓 context 無限擴散 | 已批准的最小材料包 |
| 允許 actions | 不讓 scope 靜靜擴大 | 可讀、可改與不可做清單 |
| 驗收與 handoff | 不把「做完」當自我聲稱 | diff、check、未知與下一步 |
| Stop line | 不把不確定當成默許 | escalation owner 與停下原因 |

## 一句「幫我整好」點解不夠：AI 不知道它正在甚麼工作場做事

task brief 可以清楚說明結果，例如「起一份一頁 brief」；但它未必說明 AI 可以在哪裏找資料、可以改哪一份檔案、哪些檔案只是參考、以及有沒有權處理下一步。對一件小而獨立的工作，這些可能不重要；對多步 project、資料夾或需要反覆 review 的工作，它們就是最常出事的地方。

如果 AI 沒有一個清楚工作場，它可能讀了過期檔案、把草稿當最終版、修改不屬於本輪的內容，或因為找不到資料而嘗試擴大搜尋。每一個動作可能看似合理，累積起來卻會令你很難知道它為何那樣做、又有沒有越界。

**Jimmy 的結論：** Task brief 回答「今次要交甚麼」；workbench contract 補上「在甚麼範圍、按甚麼限制、交給誰」。兩者缺一不可，尤其當 AI 開始觸及檔案、版本和多輪工作。

| 只得 task brief 時 | Workbench contract 補上的問題 | 風險怎樣被減少 |
|---|---|---|
| 「寫一份 brief」 | 哪份 outline 是 current state？ | 不用舊版起稿 |
| 「研究這個 topic」 | 今次只可讀哪幾份來源？ | 不任意取用無關材料 |
| 「優化文件」 | 哪些區域可改、哪些不可改？ | 不誤改已確認內容 |
| 「做好後交我」 | 要交 diff、未知還是 final draft？ | 完成線可被驗收 |
| 「有問題再問」 | 甚麼問題必須立即 stop？ | 不確定不會被猜過去 |

當工作場被寫清楚，AI 不需要知道你所有事情；它只需要能安全地完成此刻這一小段工作。

## Task brief 與 workbench contract 有甚麼不同：一個講成果，一個講可工作的範圍

task brief 是一張任務說明：目標、輸入、輸出和完成標準。workbench contract 則是環境說明：現行 state 是甚麼、哪些 references 可讀、哪些 actions 被允許、誰驗收，以及甚麼時候不能再自動前進。兩者一起才形成一份可操作的工作協議。

這個分別很實際。假如 brief 說「把三篇公開文章變成 research brief」，但沒有 contract，AI 仍可能不知該用哪個版本、可否下載其他資料、可否覆蓋既有草稿、或整理完是否已可發出。contract 的目的不是管得很死，而是讓每個選擇與限制都能被回看。

**Jimmy 的結論：** brief 定義成果；contract 定義這一輪的工作環境。當工作有檔案、資料、權限或多次 hand-off，先寫 contract 才談自動化。

| 比較項 | Task brief | Workbench contract |
|---|---|---|
| 最主要回答 | 要完成甚麼？ | 可以怎樣完成、在哪裏完成？ |
| 起點 | 目標與輸入 | current state 與版本 |
| 邊界 | 任務範圍 | 可讀資料、可做 action、不可做事項 |
| 完成 | 一個 expected output | output 加 check、handoff 與 owner |
| 適合 | 小而獨立工作 | project、資料夾、多輪修改與 review |

如果你只需要一段一次性的文字，brief 通常已足夠；一旦你希望 AI 反覆在同一個工作面協作，contract 才會幫你防止 context 和 scope 漸漸失控。

## 六格 workbench contract 應怎樣寫：把 scope、權限與完成線放在動手之前

一份最小 contract 不需要很複雜。先寫清今輪目的，指出唯一可信的現行 state，列出可以讀的資料，然後界定可做與不可做的 actions。最後才寫交付時要留下的 check 和遇到不確定時的 stop line。這六格足以令一輪工作被理解、被執行和被驗收。

特別是 actions 與 stop line，很多人會省略。可實際上「只可起草，不可外發」、「只改這一份 local draft，不碰其他資料夾」、「資料不足就標 unknown，交 owner」正是防止 AI 把合理推論變成越權動作的護欄。

**Jimmy 的結論：** contract 的好處不在細節愈多愈好，而在每一格都能讓下一手回答「現在能做甚麼、不能做甚麼、做完交甚麼」。答不到就先補清楚，別叫 AI 猜。

| Contract 欄位 | 你應填甚麼 | 一個安全示例 |
|---|---|---|
| 目的 | 今輪問題與 artifact | 一頁公開 research brief 草稿 |
| 現行 state | 唯一可信起點 | brief-outline.md，附日期 |
| References | 今輪可讀材料 | 三個已批准公開 URL 摘要 |
| Actions | 可讀、可改、不可做 | 可改本機 draft，不可外發 |
| Handoff | 交甚麼與誰 review | diff、來源、未知，交 editor |
| Stop line | 何時不應繼續 | 需要私人資料或缺 evidence 時 |

把這張表放在工作檔案頂部也可以。最重要的是它在 AI 動手前已存在，而不是出事後才補一段解釋。

## 現行 state 與 references 點樣防止 AI 讀錯版：先給最小、可信的起點

AI 最常見的失誤之一不是能力不足，而是它從錯的 state 開始。資料夾內可能有舊版、備份、不同格式的 notes；若沒有指明哪份是 current，AI 可能選了一份看起來完整但已過時的材料。之後即使它寫得好，整個輸出仍然建立在錯誤起點。

同樣地，references 不應等於整個 vault 或所有雲端資料。列出這次准看的最小材料，能讓 AI 和 reviewer 知道它的依據；不在清單內的資料不會因為「可能有用」而被偷偷帶入。當 references 本身不足，正確下一步是 stop，不是擴大 access 或補造事實。

**Jimmy 的結論：** 一個可信起點加一個最小 reference bundle，比一個很大的資料夾更有用。AI 要的是對的 context，不是全部 context。

| 常見混亂 | Contract 應怎樣寫 | 正確結果 |
|---|---|---|
| 有多份相近的 draft | 指出唯一 current file 與版本日期 | AI 不會任選舊版 |
| 資料散在不同位置 | 列出本輪允許讀的三至五份材料 | evidence 可回看 |
| source 不完整 | 在 contract 標記未知與 stop line | 不會自行補資料 |
| 有敏感檔案混在資料夾 | 明確不在可讀 references 內 | 不因方便而被載入 |
| 現行方向未決 | 指定 owner 與 decision state | AI 等待決定，不猜方向 |

如果你發現自己說「你自己睇下邊份啱」，這通常不是 AI 的問題，而是 workbench 尚未有一個可靠的 current state。

## Allowed actions 與 stop line 怎樣避免 scope creep：把不應做的事也寫出來

scope creep 很少由一個很明顯的錯誤開始。它常由「順手幫你改埋」「我找不到資料，所以看看另一個資料夾」「草稿完成了，所以直接下一步」累積。沒有 action boundary 時，AI 很難知道哪個延伸仍屬幫忙，哪個已經改變了工作授權。

allowed actions 要寫得具體，例如可讀指定本機檔案、可起草、可修改一份 draft、可運行不改資料的 check；不可下載附件、不可接觸其他資料夾、不可對外發送、不可修改 production 或公開設定。stop line 則寫明：遇到資料不足、需要外部動作、看到私人資料或工作超出本輪範圍時，標問題交 owner。

**Jimmy 的結論：** 一輪 AI 工作的安全，不只靠它知道要做甚麼，也靠它清楚知道不能做甚麼。寫出 stop line，代表你容許系統在不確定時正確地停。

| 情況 | 可否繼續 | 正確處理 |
|---|---|---|
| 需要在 current draft 補已批准欄位 | 可以 | 依 change request 修改 |
| 找不到一個公開來源的日期 | 不可猜 | 標 unknown，交 owner |
| 想讀另一個未列出的資料夾 | 不可自行做 | 問是否加入 reference bundle |
| draft 看似完成，想直接外發 | 不可 | 交 review／approval |
| 發現可能涉及敏感資料 | 不可繼續處理 | stop 並通知 owner |

當 stop line 被當成正常輸出，而不是失敗，AI 才能安全在更大的工作面協作。

## 一個公開安全例子：將已批准資料整理成本機 research brief 草稿

假設你要把幾篇已批准的公開資料整理成一份本機 research brief 草稿。這不是客戶交付、不會發送、也不會寫入其他系統。目的只是交一頁有三個觀察、來源和未知的 draft，供 editor 之後 review。

contract 可以指出 brief-outline.md 是唯一可修改 state；可讀材料只有資料夾內三個公開 URL 摘要和已批准 style checklist；AI 只可讀這些內容及修改本機草稿。handoff 要交代這輪改了甚麼、每個觀察對應哪個 URL、哪些說法仍待核對；若遇到需要私人資料、無法支持的 claim 或有人要求發布，必須 stop。

**Jimmy 的結論：** AI 在這個例子裡不需要「知道你所有事情」。它只在一個明確、小而可 review 的工作場內起草，未知與決定都留給人，因而更容易做得好。

| Contract 格 | 例子中的內容 | 交付後怎樣看 |
|---|---|---|
| 目的 | 一頁 research brief draft | 三個觀察、source、未知 |
| State | brief-outline.md 是 current | 只改這一份檔案 |
| References | 三個公開 URL 摘要與 style checklist | 每個 claim 可回指 |
| Actions | 可讀、可起草、可改 local draft | 沒有外部動作 |
| Handoff | diff、source mapping、unknown | editor 可 review |
| Stop line | 缺 evidence、私人資料、發佈請求 | needs-human-review |

這個例子刻意保持公開和低風險。它不授權 AI 開其他資料夾、下載檔案、讀取客戶或私人資料、外發訊息、改 visibility 或做任何 production 寫入。

## Workbench contract 有咩常見誤會：不是把整個 vault 餵給 AI，也不是一次綠燈

最常見誤會是「畀晒整個 vault，它就會更聰明」。資料多不等於 context 對；過期、無關或敏感資料反而令 AI 容易用錯。第二個誤會是「tests 或 checklist 綠色就可以放行」。check 只證明某些項目已被檢查，不代表事實、風格、權利、商業選擇或外部承諾都已由正確 owner 承擔。

還有人覺得 local draft 可以任改，因為還未公開。事實上本機也可能有重要檔案或被其他工作依賴。清楚 scope、小批次變更和可回退狀態，能讓人知道一輪 AI 工作究竟做了甚麼；這比一次「全 project 優化」可靠得多。

**Jimmy 的結論：** workbench contract 的目的不是限制創作，而是保護可用 context、可驗收改動和 human decision。它愈能正確地拒絕越界工作，愈值得信任。

| 誤會 | 為何有風險 | 正確替代 |
|---|---|---|
| 整個 vault 都可讀 | context 污染與私隱擴散 | 最小 approved reference bundle |
| 綠色 check 等於放行 | quality gate 不是最終責任 | human owner approval |
| Local draft 可任改 | 仍可能破壞重要 work state | 明確可改檔案與 diff |
| AI 可自行找更多資料 | 會擴大 scope 與 access | source 不足即 stop |
| 合約愈長愈好 | 反而令真正限制被埋沒 | 六格最小可操作 contract |

一份好的 contract 可以很短。只要它令 AI 和 reviewer 不再要猜本輪的邊界、依據與完成線，就已經比一份很長的泛泛說明更有效。

## 今日怎樣寫第一張 workbench contract：先包住一件低風險多步工作

下一次要 AI 處理多步工作前，先選一件可在本機、內部 review 的低風險任務。不要一開始給整個 project，也不要讓它接觸私人資料或外部動作。把六格填完後，讓 AI 只做一個小 change request，例如整理一個 outline 或把已批准資料放入固定欄位。

完成時要求它交回改動、對應 references、未知與 stop reason；然後由人 review。你會很快看見哪一格仍要補：可能是 current state 未清楚、reference 太大、check 不具體，或 owner 還未定。這些發現本身就是下一輪 contract 的改善證據。

**Jimmy 的結論：** 你不是把一個願望交給 AI；你是在設計一個它可以安全完成、亦可以被人檢查的工作場。先讓一件小工作跑穩，再擴大 scope。

| 第一張 contract | 你要填甚麼 | 安全起點 |
|---|---|---|
| 目的 | 一件小而可驗收的交付 | 一頁 internal draft |
| Current state | 唯一可信檔案與版本 | 一個本機 outline |
| References | 三至五份已批准材料 | 公開資料摘要 |
| Actions | 可做與不可做 | 可改 draft，不可外發 |
| Handoff | 要留下甚麼 | diff、unknown、review request |
| Stop line | 何時交人 | 缺 source 或需外部 action |

未跑過這種低風險 contract 前，暫時不要讓 AI 自己擴到整個 project、所有資料夾、客戶／私人資料、公開設定或 production 系統。下一步可看 [如何把工作寫成一張 AI work card](./4-20-ai-work-card.md)，將這張工作場再變成可重用的最小契約。

> 你不是把一個願望交給 AI；你是在設計一個它可以安全完成、亦可以被人檢查的工作場。

← [返回 AI Builder](../README.md) · [按問題瀏覽](../../../學習地圖.md)
