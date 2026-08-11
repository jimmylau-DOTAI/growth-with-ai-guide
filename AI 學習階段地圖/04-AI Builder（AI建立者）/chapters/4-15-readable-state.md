# 點解 AI 做完你都唔知啱唔啱？先把工作變成可讀 state

AI 交了一段文字、一張圖或一個看似完整的 output，不代表你知道它根據甚麼做、改了哪裡，或者是否略過了重要限制。當你只能望住最後成品說「感覺唔啱」，就很難判斷問題是在輸入資料、指令、製作過程，還是在最後的驗收。

很多人以為多寫一個 prompt 或換一個模型就能解決。其實工作若只存在於腦中、口頭描述或封閉畫面時間線，AI、reviewer 和下一手同事都看不見它現在做到哪、還缺甚麼、誰可以決定甚麼。工具再強，也只能猜一個沒有被外化的工作。

Jimmy 的看法是：AI 真正接得走的，不是任何創作，而是已被外化成可讀 state、可留痕修改、可驗收交付的那一段工作。state 讓人先看清工作，而不是把決定偷偷交給 AI；因此它是協作與安全的開始，不是全自動化的同義詞。

AI 實戰 · AI Builder · state · artifact · change request · verification · human review

| 可讀 state 的一格 | 它解決甚麼問題 | 完成後留下甚麼 |
|---|---|---|
| Source | 不讓輸出失去根據 | 已批准輸入、版本與範圍 |
| State | 讓目前進度可被看見與交接 | outline、table、draft 或 checklist |
| Change request | 不讓本輪修改無限擴張 | 只可改的範圍與不可碰的邊界 |
| Verification | 不只靠「感覺」收貨 | diff、rubric 或 check 結果 |
| Decision | 清楚下一步誰負責 | approve、revise、stop 的 owner |

## AI output 點解難驗收：只有最後成品，沒有中間 state

當 AI 一次過交出一份完整報告、一條影片腳本或一個設計稿，人很容易只針對最後的語氣、外觀或長度給意見。但如果你不知道它讀了哪些資料、哪些內容仍是未知、這一輪到底改過甚麼，就很難提出可執行的 feedback。下一次通常只會得到另一個同樣難驗收的版本。

這也是多步工作特別容易出錯的原因。research、結構、草擬、事實確認和批准本來就不是一件事；它們全部被壓在一個聊天輸出時，錯誤無法被定位。你可能以為 AI「做錯了」，其實是工作從來沒有一個讓大家共同檢查的狀態。

**Jimmy 的結論：** 最後 output 只是工作的一個切面，不是工作本身。若要讓 AI 幫得可靠，先要讓人看得見當前 state、允許的變更和驗收位置。

| 只看成品時的說法 | 真正缺少的是甚麼 | 較好的 state 問題 |
|---|---|---|
| 「呢份唔啱 feel」 | 沒有可指出的結構或版本差異 | opening、例子還是結論哪一格要改？ |
| 「好似漏咗資料」 | source 與未知項目沒有顯示 | 哪個 claim 沒有來源或仍待確認？ |
| 「再幫我整好啲」 | change request 沒有限定 | 這輪只改順序、語氣還是事實？ |
| 「點解改咗咁多？」 | 沒有 diff 或版本記錄 | 這輪實際改了哪些欄位？ |

若你無法把 feedback 指到某一格 state，就先不要要求 AI 再生成。先把「現在有甚麼、要改甚麼、怎樣算完成」寫出來，下一輪才有可靠的開始。

## 可讀 state 是甚麼：把腦內工作外化成下一手可判斷的 artifact

state 不一定是很技術化的 JSON 或資料庫。它可以是一個有標題的 outline、一張表、一份有欄位的 brief、一個 versioned draft，或一張 checklist。它的唯一要求是：另一個人或 Agent 打開後，能夠理解目前的工作根據甚麼、完成到哪裏、仍有甚麼未知，以及下一步能否改動。

可讀不等於把所有資料公開。好的 state 只外化驗收所需的最小資訊；敏感資料、未公開素材或不屬於這次任務的背景，不會因為「方便 AI」而被搬進去。能協作的文件和能安全交接的文件，是同一件事。

**Jimmy 的結論：** state 的作用不是令文件愈長，而是令工作不必靠猜。只要下一手能看見依據、進度、限制和未知，它就足夠可讀。

| 工作原本藏在哪裏 | 可轉成的 state | 下一手因此能做甚麼 |
|---|---|---|
| 口頭講的內容方向 | 有段落目的的 outline | 只調整某一段敘事順序 |
| 散落的資料連結 | source table 加狀態欄 | 看見哪些內容已確認、哪些未知 |
| 腦中的質量要求 | review checklist | 用相同標準驗收兩個版本 |
| 一次性的聊天結果 | versioned draft 加變更記錄 | 比較本輪實際修改 |
| 不確定的決定 | decision log 加 owner | 交回有權的人判斷 |

當你把 state 做得可讀，AI 不再是「幫你猜腦內想法」，而是可以在一個看得見的工作面上協助整理、比較和提出下一步。

## Change request 點樣限制 AI 修改：每一輪只交一個清楚範圍

AI 最容易失控的情況，不一定是它能力太強，而是人給了一句沒有邊界的要求，例如「幫我整好」「再 professional 啲」或「全部優化」。這些說法混合了內容、語氣、結構、事實與批准權；AI 必須自行猜哪一樣才是重點，亦很容易一併改掉本來不應碰的部分。

change request 是把本輪容許的改動寫得很小很明確。例如「只調整三段順序，保留所有已批准 claim」、「只補三個標記為未知的問題，不新增外部事實」，或「只把長段拆成 checklist，不改內容立場」。範圍小不代表價值小；它令 diff、review 和 rollback 都變得容易。

**Jimmy 的結論：** 每輪 AI 工作都應有一個可驗收的 change request。清楚說明「只改甚麼」與「絕不改甚麼」，比加十句形容詞更能改善結果。

| 模糊指令 | 可讀 change request | 不可跨越的線 |
|---|---|---|
| 「幫我優化份稿」 | 只重排三段的敘事順序 | 不新增外部 claim |
| 「整到更加有說服力」 | 為每段補一個已批准例子 | 不改價格、承諾或立場 |
| 「幫我執好啲資料」 | 將已提供資料放入固定欄位 | 不自行補缺失欄位 |
| 「改晒成專業版」 | 只統一標題與列表格式 | 不刪人類尚未 review 的內容 |

先把 change request 寫成一行也可以。只要 reviewer 能在完成後對照「有沒有只做這一件事」，你就已經由聊天走向可控制的 AI 工作。

## Diff 與 verification 怎樣令 reviewer 知道改了甚麼、仍差甚麼

沒有 diff 的修改，reviewer 只能重新讀一遍全文，靠記憶比較哪裏不同；沒有 verification，則只能看格式漂不漂亮。這兩種做法都很耗人，而且容易漏掉重要問題，例如一個來源被移除、一個未知被悄悄改成肯定句，或一個本不該動的段落被重寫。

diff 是把「這輪改了甚麼」展示出來；verification 是把「這輪是否符合規則」展示出來。它們不需要很複雜：一張修改前後表、已勾選／未勾選的 checklist，或清楚列出資料不足的 receipt 已足夠。關鍵是 reviewer 不再要猜，而是能按預先同意的條件作決定。

**Jimmy 的結論：** 人類 review 不是在最後憑感覺按 approve；它需要看得到變更、依據和未解決問題。diff 與 check 令責任重新回到看得見的工作面。

| Review 問題 | 可用的 state 機制 | reviewer 可作的決定 |
|---|---|---|
| 這輪到底改了甚麼？ | before／after diff 或 change log | 接受、退回某一格 |
| 有沒有加入未確認事實？ | claim-source check | 要求補 link 或標 unknown |
| 是否仍符合原本範圍？ | change request 對照表 | 拒絕越界改動 |
| 哪些問題未解？ | needs-human-review 清單 | 指派 owner 或停止 |
| 哪個版本可用？ | version／decision record | approve 或保留舊版 |

有 checklist 不等於自動過關。checklist 要對準真正重要的內容、權利、風險或用途；如果它只量標題格式，便不能取代人對意思與後果的判斷。

## 一個公開安全例子：用 state 協作整理 60 秒教學短片 draft

假設你要把已批准的公開課綱和三個 key point 整理成 60 秒教學短片的 internal draft。若直接叫 AI「寫條短片」，它可能自行加未經確認的 claim、把原本順序改掉，或混入不屬於這次工作的素材。當結果不對，團隊只能說「重做」，卻不知道該重做哪一層。

把工作拆成可讀 state 後，source 是已批准的公開課綱；state 是一張文字 outline，列出 opening、三段內容、每段 key point 和待確認 claim；本輪 change request 只可調整敘事順序並提出 caption draft。reviewer 對照原意、來源和未知欄位；human owner 未批准前，不 render、不發佈、也不使用未批准 asset。

**Jimmy 的結論：** 這個例子裡，AI 的價值不是自行完成影片，而是把可見 state 變成較好 review 的 draft。所有會影響發佈、權利或對外承諾的決定仍然留在人手。

| State 一格 | 在例子裡放甚麼 | 誰用它作判斷 |
|---|---|---|
| Source | 已批准公開課綱、三個 key point | AI 與 reviewer |
| Outline state | opening、三段內容、待確認 claim | content owner |
| Change request | 只調整順序與 caption draft | AI worker |
| Verification | 原意、來源、未知項目 checklist | reviewer |
| Decision | revise、approve 或 stop | human owner |

這個例子故意保持在公開、低風險的 internal draft。它不代表 AI 已被授權處理客戶素材、未公開 script、外部發送或 production 發佈；那些工作需要另一套權限、review 和 approval。

## State 怎樣令多人或多 Agent 交接不失焦：先交 artifact，再交口頭解釋

一項工作由一個人轉交另一個人，最常見的問題不是能力不足，而是只有口頭背景，沒有可讀 artifact。下一手可能重新做一次、重複問同樣問題，或在不知道舊決定的情況下改掉已確認內容。多 Agent 工作更容易放大這個問題，因為每次 hand-off 都可能令 context 被壓縮、遺漏或誤解。

所以交接的單位不應是「你自己理解」，而應是目前 state：使用了哪些 source、現在是甚麼版本、本輪改過甚麼、哪些事項未決、下一手有沒有權處理。這樣就算不同 specialist 參與，大家仍然在同一個可回看的工作面上合作，而不是各自帶著一段隱形記憶工作。

**Jimmy 的結論：** 可以交接的不是一句 summary，而是一個有來源、有版本、有未知和有 owner 的 artifact。先把 hand-off 寫清楚，才談多 Agent 或 parallel。

| Hand-off 要帶的東西 | 沒有它會怎樣 | 可見 state 的寫法 |
|---|---|---|
| 目前輸入與版本 | 下一手重複找資料或用錯版 | source list 加版本日期 |
| 已完成與未完成 | 以為工作已交完 | status 欄：done／blocked／review |
| 變更範圍 | 下一手誤改已確認內容 | 本輪 change request |
| 未知與風險 | AI 或人自行猜測 | needs-human-review 項目 |
| 決定 owner | 卡住時無人負責 | escalation owner 與下一步 |

若你現時只有一人和一個 AI，也值得先這樣做。它會令你日後加入 reviewer、specialist 或新工具時，不必重新發明整個交接規則。

## 今日怎樣做第一個可讀 state：先寫五格，不急著叫 AI 生成

選一件最近要 AI 幫手、但仍可在內部 review 的低風險工作。先不要叫它生成，也不要把敏感資料搬進 context；只把工作外化成五格：可用 source、現在可讀 state、本輪只准改甚麼、誰用甚麼 check、哪個人決定下一步。

若你寫不到「現在可讀 state」，就先把它轉成 outline、table 或 checklist。這通常代表工作還未準備好被交出去，不是 prompt 不夠長。當五格都有答案，才把一個小而可驗收的 change request 交給 AI，並保留完成前後的差異。

**Jimmy 的結論：** 先做一個可讀 state，比先做一個很厲害的生成更重要。它令你能看見工作、限制 AI、驗收結果，亦知道甚麼時候應該停下交人。

| 第一次 state card | 你要寫的內容 | 安全起點 |
|---|---|---|
| Source | 已批准且與任務直接相關的輸入 | 公開課綱或 synthetic brief |
| State | 現在的 outline／table／draft | 一頁文字 outline |
| Change request | 本輪唯一要改的事 | 只調整三段順序 |
| Check | 怎樣看出合格或不合格 | 原意與來源 checklist |
| Decision | 誰有權批准下一步 | content owner review |

完成後保留 state、change request、diff 和 review 結果。暫時不要把這種流程接到外部發送、production 寫入或未公開／客戶資料；先在可回看的 draft 工作證明它有用。下一步可看 [AI Agent 要有 loop，而不是一次性回答](./4-3-loop-engineering.md)，再把這張 state card 放進一條有 stop line 的工作 loop。

> AI 真正接得走的，不是任何創作；而是已被外化成可讀 state、可留痕修改、可驗收交付的那一段工作。

← [返回 AI Builder](../README.md) · [按問題瀏覽](../../../學習地圖.md)
