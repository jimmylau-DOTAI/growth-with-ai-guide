# 想帶團隊試 AI，第一個 pilot 要點設？先買 evidence，不要急住買成功故事

「試下 AI」聽起來很積極，但如果沒有人說清楚要改善哪一段工作、誰決定可不可以用、何時應停，最後通常只會多一個漂亮 demo。團隊看過示範、開了 account，回到日常工作後仍然不知道哪份資料可用、結果誰收貨、出錯誰負責。

第一個 pilot 不需要承諾 ROI，也不需要同時改整個部門。它要做的是買一份真 evidence：在一條明確 workflow、最小資料和 human review 下，AI 有沒有令一小段工作在質量、時間、重做或風險上值得繼續研究。沒有改善也不是失敗，只要能說清原因並作出 stop 或 revise 決定。

Jimmy 的看法是：pilot 不是叫 AI 表演，而是把一個真工作縮小到可安全觀察。清楚讀乜、出乜、邊個批、邊度停，以及幾時根據 evidence 決定下一步，團隊才會由「試工具」走到真正的 AI adoption。

AI 實戰 · AI Value Creator · AI pilot · adoption pilot · governance · workflow · owner · evidence

| Pilot canvas 的一格 | 它解決甚麼問題 | 留下甚麼 |
|---|---|---|
| 問題 | 不為了試 AI 而試 AI | 目前摩擦與 baseline |
| 範圍 | 不一次做整個部門 | 一手可控制工作 |
| Input | 不亂用資料 | 最小已批准材料 |
| Artifact | 不只看 chat output | 可 review 的 internal result |
| Owners | 不把責任交給工具 | 工作、資料、review、決定 owner |
| Controls | 不讓 AI 越權 | approval、stop line、禁止 action |
| Evidence | 不只靠感覺說成功 | 一兩個 outcome 觀察 |
| Decision date | 不讓試行無限拖延 | retain、revise、stop／小擴大決定 |

## AI pilot 點解唔係 demo：demo 證明一次可行，pilot 要證明一條工作可學習

demo 的價值是讓人看見可能性。它可以在幾分鐘內展示 AI 怎樣寫一段文、整理資料或生成圖片；但 demo 的材料往往很乾淨、任務很短，亦沒有真實 owner、review 或後果。demo 成功不代表同一做法在下星期的工作壓力下仍然可以被安全重複。

pilot 則把焦點放在一條真 workflow。它不假裝一定會成功，而是預先寫好要觀察甚麼、誰收貨、哪種情況不繼續、以及哪一天要作 decision。這讓團隊不需要靠「感覺好像有用」或「已經買了工具」來決定擴大。

**Jimmy 的結論：** demo 用來打開想像；pilot 用來買 evidence。第一個 AI pilot 的成功不是 AI 看起來多厲害，而是團隊知道這條工作下一步應 retain、revise、stop 還是小幅 expand。

| Demo 常見特徵 | Pilot 必須多的一格 | 為何重要 |
|---|---|---|
| 一次漂亮 output | 真實 workflow 摩擦 | 知道要改善甚麼 |
| 示範者自己操作 | 明確 owner 與 reviewer | 知道誰負責結果 |
| 材料已準備好 | input boundary | 知道可讀甚麼 |
| 沒有失敗情況 | stop line 與 escalation | 遇到問題不會猜過去 |
| 結尾叫大家試用 | decision date 與 evidence | 不讓試行無限延長 |

若你不能說明 pilot 在何時做 decision，它很容易變成一個沒有結論的工具試用，而不是一個可學習 experiment。

## Pilot 問題與範圍怎樣選：先解一段真摩擦，不選最炫的 AI 能力

第一個 pilot 應由現在真的重複、容易等待、返工或漏項的工作開始，而不是由最新最炫的 AI capability 開始。團隊若每次活動後都要重複整理批准資料、每週都要把公開內容變成 internal draft、或總是在 review 時補同一類缺口，這些都是比「做一個自主 Agent」更好的起點。

範圍要刻意小：一條流程、一類資料、一個 output、一個 human gate。不要同時接多個工具、部門和權限；否則結果變好或變差都無法知道原因。你可以選擇只讓 AI 起 draft、只標資料缺口、或只做分類，先不要讓它外發、改 production 或代表團隊作任何承諾。

**Jimmy 的結論：** 第一個 pilot 不需要最有野心，只需要最容易判斷。選一段有真痛點、可控制、可 review 的工作，讓 evidence 指出值不值得下一步。

| 不適合作首輪的選法 | 較好的 bounded 範圍 | 為何較安全 |
|---|---|---|
| 「全面自動化 customer service」 | 整理公開 FAQ 成 internal draft | 不涉及對外回覆 |
| 「讓 AI 管整個專案」 | 整理指定資料成一頁 brief | artifact 與 owner 清楚 |
| 「接所有公司資料」 | 只讀已批准公開／內部資料包 | context 可被審查 |
| 「做一個 AI team」 | 一個 worker 做一手分類或草擬 | hand-off 成本較低 |
| 「先看能省多少錢」 | 比較可 review 前時間與 rework | 早期 evidence 更可信 |

若你選不到一條低風險真工作，先做 workflow discovery。這不是慢，而是在避免把不清楚的工作直接交給 AI。

## 八格 pilot canvas 應怎樣填：把成功、邊界與結束時間在開始前說清

一張 pilot canvas 不是 project 文件的裝飾，而是將關鍵假設放在桌面。問題說明現在摩擦；範圍說明 AI 只做哪一手；input 界定可讀材料；artifact 讓 reviewer 有東西收貨。這四格令團隊知道「正在試甚麼」。

owners、controls、evidence 和 decision date 則保護 pilot 不會越走越大。owners 分開工作、資料、review 和最後決定；controls 寫明禁止 actions 和 stop line；evidence 只選一兩項 outcome；decision date 逼團隊在指定時間面對結果，而不是因為已投入就永遠繼續。

**Jimmy 的結論：** 有一格空白就先不跑。首輪 pilot 的價值不在文件很完整，而在每個人都能回答 AI 可以做甚麼、不能做甚麼、做完誰會看、何時決定。

| Canvas 欄位 | 你要填甚麼 | 一個安全示例 |
|---|---|---|
| 問題 | 現在最常等待、返工或漏項 | FAQ 資料分散、review 常漏題 |
| 範圍 | 只做哪一手，刻意不做甚麼 | 只起 internal draft，不更新、不外發 |
| Input | 已批准最少資料 | 指定公開頁與 approved brief |
| Artifact | 可 review output | 有來源與 unknown 的 FAQ table |
| Owners | 工作、資料、review、決定誰負責 | content owner、data owner、reviewer |
| Controls | 不可做與 stop 條件 | 敏感資料、外發、缺 evidence 即停 |
| Evidence | 一兩項 outcome | 可 review 前時間、退回原因 |
| Decision date | 何時作取捨 | 跑三次後 review |

canvas 不一定要很長，但每一格必須可執行。若只寫「用 AI 提升效率」，它仍然沒有告訴團隊怎樣安全跑第一輪。

## Owners、controls 與 stop line 點樣保護團隊：pilot 不應把責任外包畀 AI

pilot 最容易出事的地方，不是 output 不漂亮，而是責任不清。誰確認資料可用？誰決定內容正確？誰可以批准下一步？若這些角色未定，AI 的 output 很容易被下一手誤當完成品，或被人用在未被授權的地方。

controls 要寫得具體：AI 可否只讀？可否起草？可否改指定本機 draft？絕不可直接做甚麼？一般首輪應停在 internal artifact 和 human review；凡涉及私人資料、客戶資料、價格／法律承諾、外部發送、公開設定或 production 寫入，都應停止並交 owner。

**Jimmy 的結論：** governance 不是為 pilot 加麻煩，而是令團隊敢於安全地試。當 human gate 和 stop line 清楚，AI 才可在低風險範圍內真正幫到手。

| 情況 | Pilot 可否自行繼續 | 正確處理 |
|---|---|---|
| 已批准資料要整理成 internal draft | 可以 | 依 contract 起草 |
| 發現缺少公開 source | 不可猜 | 標 unknown，交 owner |
| 需要讀未列出的資料夾 | 不可自行擴大 | 問 data owner |
| draft 看似完成要外發 | 不可 | 交 human approval |
| 要改 live FAQ 或 production 系統 | 不可首輪直接做 | 先保留 draft 與 review receipt |

清楚停下不是 pilot 失敗。相反，正確 stop 是最有價值的 evidence，因為它揭示了資料、流程或權限哪一格仍未準備好。

## Evidence 與 decision date 點樣令 pilot 有結論：不只收集好評，也收集停止理由

pilot 常見的問題是最後只收集「大家覺得好用嗎？」的感想。感想有價值，但很容易受新鮮感、個人偏好和一次結果影響。更可靠的做法是加上一兩個工作痕跡，例如第一版可 review 前所需時間、漏項或缺 source 次數、reviewer 退回原因、rework 次數或正確 stop 的個案。

decision date 令團隊知道 evidence 何時會被看。到期時，不必只有成功或失敗兩種選擇：可以 retain 原範圍、revise input／quality bar、stop，或只 expand 已被證明可靠的一小手。這避免了因為已買工具或做了宣傳而硬撐一條不合適流程。

**Jimmy 的結論：** pilot 的終點不是一份好評，而是一個有 evidence 的下一步決定。明確的 stop 選項，會令團隊更誠實也更快學習。

| Evidence 問題 | 可回看的指標 | 到 decision date 可作的決定 |
|---|---|---|
| 第一版有沒有更快可 review | 資料齊備到 draft 的時間 | retain 或修 workflow |
| quality 有沒有更穩 | 缺欄、缺 source、退回原因 | revise input／rubric |
| 人手成本有沒有轉移 | reviewer 清理與 rework | stop 或縮小範圍 |
| governance 有沒有有效 | unknown／stop receipt | 補 owner 或 action boundary |
| 值不值得下一步 | 多輪 evidence 加 owner 判斷 | 小幅 expand 或不擴大 |

如果 evidence 不足，也是一個結果：先延長觀察或補資料，而不是急著用一個漂亮故事填滿空白。

## 一個公開安全例子：已批准資料到 internal FAQ draft 的小 pilot

假設小組想改善「已批准資料 → internal FAQ draft」。問題是資料散在指定公開頁和已核對 brief，每次都由人手整合，review 後常要補資料。範圍只限產生一份 draft，不直接更新 FAQ、不對外發送，也不讀未被列出的資料。

AI 只讀指定公開或已批准資料，交有來源、待確認欄的 FAQ table。工作 owner 看內容，資料 owner 確認 input 範圍，reviewer 按 quality bar 收貨。團隊跑三次後，看看第一版可 review 的時間和被退回補資料原因；再決定補 context、維持手動 review、縮小範圍或只擴大整理那一步。

**Jimmy 的結論：** 這是一個 pilot，不是已部署成果。沒有改善也可以 stop；真正有價值的是團隊知道問題是在 input、quality bar、AI hand-off 還是根本不適合用 AI。

| Pilot 格 | 例子中的做法 | 留下甚麼 |
|---|---|---|
| 問題 | 資料分散、review 常漏題 | baseline／退回原因 |
| 範圍 | 只起 internal FAQ draft | action boundary |
| Input | 指定公開頁、approved brief | source list |
| Artifact | FAQ table 加來源與 unknown | review queue |
| Controls | 不更新、不外發、不碰敏感資料 | stop receipt |
| Evidence | 時間與退回補資料原因 | 三輪 comparison |
| Decision | 三次 run 後 review | retain／revise／stop |

這個例子是公開安全的 synthetic workflow，不代表任何特定團隊已有同樣成效，也不授權 AI 接觸私人或客戶資料、公開內容或 production 系統。

## 今日怎樣開第一個 AI pilot：先選一條低風險 workflow，再定一日作決定

找一條團隊現在真的重複做、但不涉及外發或敏感資料的工作。不要先選工具；先把八格 canvas 填好，尤其是 owner、stop 和 decision date。若其中一格只能答「到時先算」，就先補清楚再跑。

第一輪最多一條流程、一類資料、一個 output 和一個 human gate。跑完後不要急著擴大，先看 evidence：結果是否真的更易 review？工作量是否只是轉移？有沒有正確停下？把答案留在 canvas，才會知道下一輪要改哪一格。

**Jimmy 的結論：** Pilot 唔係叫 AI 表演；係揀一段真工作，講清楚讀乜、出乜、邊個批、邊度停，同埋完咗之後用乜 evidence 決定值唔值得行下一步。

| 今日第一步 | 你要完成甚麼 | 安全起點 |
|---|---|---|
| 選問題 | 一個重複摩擦 | 公開資料整合常漏欄 |
| 縮範圍 | 一手可控制工作 | 只起 internal draft |
| 定資料 | 最小 approved input | 指定公開頁 |
| 定人 | owner、reviewer、決定者 | human review gate |
| 定 evidence | 一兩個 outcome | 可 review 時間、rework |
| 定日期 | pilot 何時結束 | 三次 run 後 review |

在未跑過這個小 pilot 前，暫時不要把 AI 接到外部發送、私人／客戶資料、公開設定、production 寫入或不可逆 action。下一步可看 [demo 與價值有甚麼分別](5-7-demo-versus-value.md)。

> Pilot 唔係叫 AI 表演；係揀一段真工作，講清楚讀乜、出乜、邊個批、邊度停，同埋完咗之後用乜 evidence 決定值唔值得行下一步。

← [由五段地圖選下一步](../CURRENT-JOURNEY.md) · [按問題瀏覽](../BROWSE.md)
