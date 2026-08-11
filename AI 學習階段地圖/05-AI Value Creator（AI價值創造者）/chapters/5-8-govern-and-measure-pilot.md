# AI pilot 要量甚麼先有用？用最小治理加一兩個比較，不要製造另一個 dashboard

有 log 不代表可治理；量得多也不代表更客觀。很多 AI pilot 最後有一張很漂亮的 dashboard，卻沒有人知道哪個數字決定甚麼、誰要看、遇到例外怎樣做。結果資料愈收愈多，workflow 本身反而沒被改善。

真正需要的不是監控所有人，也不是為了證明成功而找漂亮 KPI。你需要的是一個最小循環：AI 可以讀甚麼、不能做甚麼、誰 review、出現甚麼例外、以及這條工作相較原本有沒有變。這些資料必須能支援一個實際決定，而不是只留在報告裡。

Jimmy 的看法是：好的 measure 令團隊同時看見價值和風險，而不是製造另一個無人看的 dashboard。為每條 pilot 寫一張 control card，再選一兩個真正回答工作問題的 observation；每次 review 都把結果連回 retain、revise、stop 或小幅 expand。

AI 實戰 · AI Value Creator · governance · measurement · pilot · control card · evidence · exception

| 最小治理與量度的一格 | 要回答甚麼 | 留下甚麼 |
|---|---|---|
| Baseline | 未用 AI 時現在怎樣？ | 可比較的起點 |
| Control card | AI 可讀、可做、不可做甚麼？ | input、action、owner、stop line |
| Run receipt | 本輪實際發生了甚麼？ | artifact、例外、review 結果 |
| Observation | 工作有沒有變？ | 時間、質量或風險痕跡 |
| Review | 問題在 AI、資料、流程還是 check？ | 原因分類 |
| Decision | 下一輪要怎樣做？ | retain、revise、stop 或 expand |

## AI pilot 點解不能只靠 dashboard：有資料不等於有人能作決定

dashboard 能幫你看狀態，但它本身不會治理 workflow。若沒有 owner、decision rule 和例外處理，一堆圖表只會令團隊更難分辨哪些是重要訊號、哪些只是系統活動。看到生成次數增加，未必代表工作更好；看到時間減少，也未必代表 reviewer 沒有承受更多清理成本。

治理的核心是讓每個數字回到一個問題：這個 observation 要決定甚麼？誰看？若異常，誰可以修 input、rule、scope 或停下？當這些答案不存在，收集資料只會增加負擔，也可能不必要地涉及員工或客戶的個人資料。

**Jimmy 的結論：** dashboard 是呈現工具，不是決策系統。先寫清 owner、control、observation 和 decision，再決定需要不需要畫任何 dashboard。

| 看起來很有用的資料 | 為何仍未夠 | 要補的決定問題 |
|---|---|---|
| AI 使用量 | 不知 workflow 有沒有改善 | 哪一條工作因此更可 review？ |
| 完成時間 | 不知 quality／rework 有沒有變 | reviewer 退回原因是甚麼？ |
| 生成內容數 | 不知有沒有被採用 | 哪份 artifact 真正被 owner 使用？ |
| 錯誤次數 | 不知錯在哪一層 | 是 input、rule、AI 還是流程問題？ |
| 個人行為 log | 可能無關且侵入 | 是否真的需要收集？ |

如果一個數字不能改變下一個行動，就先不要收。這是最簡單的資料治理，也是對團隊時間與私隱的尊重。

## Baseline 點樣定：先記一個可比較起點，不把「以前好忙」當證據

沒有 baseline，之後所有改善都只剩印象。你不需要回溯一整年資料；只要在 pilot 前選一個可觀察的起點，例如「資料齊備到第一版可 review draft 需要多久」、「一輪通常有幾個缺欄」、「reviewer 最常退回哪三種問題」。這些要寫清由哪一刻量到哪一刻、誰記、甚麼算一次 rework。

baseline 也不能假裝完全精準。不同週的資料量、複雜度和人手可能不同，所以它是一個比較框架，不是因果實驗。重點是讓團隊在幾次 run 後有共同問題可討論，而不是在沒有資料時硬說 AI 慳了多少。

**Jimmy 的結論：** 一個誠實 baseline 比十個事後 KPI 有用。先定義工作原本怎樣，才知道 AI 帶來的是改善、轉移成本，還是沒有改變。

| 想比較甚麼 | Baseline 怎樣寫 | 要避免甚麼 |
|---|---|---|
| 速度 | 資料齊到可 review draft 的時間 | 只記 AI 生成時間 |
| 品質 | 缺欄／缺 source 次數 | 把不同複雜度硬比較 |
| Rework | reviewer 退回原因與次數 | 把正常 review 當失敗 |
| 風險 | unknown／stop 出現原因 | 把正確停止當壞結果 |
| 使用 | owner 實際採納哪一格 | 用登入數代替工作結果 |

baseline 不需要多，但必須在跑 pilot 前寫下。這樣結果不如預期時，你仍能看出到底哪一格沒有改變。

## Control card 怎樣保護 workflow：把 input、action、review 與 stop line 放在同一張卡

control card 是一張半頁到一頁的工作契約。它寫明 AI 今輪只可讀哪些 input、只可做甚麼 action、artifact 放在哪裏、誰 review、哪些情況必須 stop，以及誰有權決定下一步。它不是合規文件的替代品，而是讓 pilot 的日常治理可以被大家看見。

特別是 action boundary 很重要。一般首輪可以讓 AI 讀已批准材料、起 internal draft、在指定可回退檔案留下結果；不應讓它對外發送、讀私人或客戶資料、改公開設定或寫入 production。當資料不足或遇到不在 scope 的要求，control card 要把「停下並交 owner」當成正確 output。

**Jimmy 的結論：** control card 不是限制 pilot，而是令團隊知道可以放心試哪一手。邊界愈清楚，低風險工作愈容易跑出可靠 evidence。

| Control card 欄位 | 要寫甚麼 | 安全示例 |
|---|---|---|
| Input | 已批准最小材料 | 指定公開頁與 brief |
| Action | AI 只做哪一手 | 起 internal draft |
| Artifact | 結果放哪、長甚麼樣 | FAQ table 加 source |
| Review | 誰按甚麼收貨 | owner 用 checklist |
| Stop line | 何時不可繼續 | 缺 evidence、敏感資料、外發請求 |
| Decision owner | 誰改 scope 或作取捨 | workflow owner |

每次想加新資料或新權限，都應回到 control card 更新並重新 review；不要因為上一輪「好像不錯」而偷偷擴大。

## Observation 點樣選：一個時間類加一個質量或風險類，已足夠開始

量度太多通常會令團隊失焦。首輪 pilot 最實用的組合是一個時間類 observation，加一個質量或風險類 observation。例如：由資料齊到 reviewer 可接手的時間，加上被退回補資料的原因；或者起草時間，加上缺 source／unknown 是否正確標示。

關鍵是每個 observation 都要有定義。甚麼算「資料齊」？哪一刻叫「可 review」？甚麼算一次 rework？誰負責記錄？這些小定義令同一組數字可以被同一個人以外的人理解，也避免團隊為了好看而只量自己最有利的一面。

**Jimmy 的結論：** 一兩個能支援決定的 observation 已經夠。量度的目標不是看盡一切，而是讓工作改善與風險都不能被忽略。

| Observation 類型 | 可用問題 | 怎樣支持決定 |
|---|---|---|
| 時間 | 資料齊到可 review 要多久？ | 是否真的減少等待 |
| 質量 | 哪類缺欄／缺 source 最常退回？ | input 或 rubric 要否修正 |
| Rework | 退回後重做了幾次？ | AI 是否只轉移工作 |
| 風險 | unknown／stop 是否正確出現？ | governance 是否足夠 |
| 採納 | owner 保留了哪些結果？ | artifact 是否真正有用 |

不要用 KPI 合理化監控員工，也不要把客戶內容、原始敏感資料或無關的個人表現放進 review log。只記改善這條 workflow 所需的最小 evidence。

## Run receipt 與 review 怎樣分辨問題在哪：不要把所有錯都算在 AI 頭上

當 pilot 結果不好，最容易的說法是「AI 不準」。但問題可能在 input 不完整、規則未寫清、workflow 選錯、reviewer 標準不同，或本來就不適合用 AI。若所有例外只記作「AI error」，團隊不會學到下一輪要修哪一格。

run receipt 可以很簡單：本輪用了哪個版本的 control card、交了甚麼 artifact、出現哪些 unknown／stop、review 結果如何、時間與質量 observation 是甚麼。review 時再把問題分類為 input、AI output、workflow、rule、owner 或技術可行性。這讓 revise 是有方向的，而不是叫模型「再做好一點」。

**Jimmy 的結論：** 一張 run receipt 讓 pilot 變成學習 loop。它不需要追究誰錯，而是讓團隊看見問題在哪一層、下一輪應改甚麼。

| 發現的問題 | 可能在哪一層 | 下一輪先試甚麼 |
|---|---|---|
| 缺很多資料 | input／source | 補 source boundary 或欄位 |
| 格式每次不一致 | rule／template | 更新 quality bar |
| reviewer 意見不同 | owner／rubric | 對齊 review rule |
| AI 猜未知內容 | stop line／prompt | 強化 unknown receipt |
| 工具不支援必要資料格式 | 技術可行性 | stop 或換方案 |

正確的 stop 與 unknown 也是 receipt 的好結果。它們表示控制生效，避免一個未解問題被包裝成完成品。

## 一個公開安全例子：internal FAQ draft pilot 的最小治理與比較

假設一條 internal FAQ draft pilot 只處理已批准公開資料。control card 寫明：AI 只讀指定公開頁與已核對 brief；只起 FAQ table；每題附 source、未知標待確認；不能對外發送、不能更新 live FAQ，遇到缺 evidence 或敏感資料即 stop，交 content owner。

團隊只記兩個 observation：從材料齊到 reviewer 可接手的時間，以及每次被退回的原因。每次 run 留下一份 receipt，記錄 source、artifact、unknown、review 結果和這兩個 observation。若速度快了但退回大增，答案可以是 revise input 或 stop，無需硬說 AI 慳了時間。

**Jimmy 的結論：** 這個例子顯示最小治理與量度可以很輕，但仍足以同時看見價值和風險。重要的是每個數字最後都能連回一個具體 workflow decision。

| Pilot 格 | 例子中的做法 | 可見 evidence |
|---|---|---|
| Control | 只讀批准資料、只起 internal table | control card |
| Human gate | owner review 後才推進 | review receipt |
| Time | 材料齊至可 review | 時間記錄 |
| Quality | 退回補資料原因 | reason tags |
| Stop | 缺 evidence／敏感資料 | unknown／stop record |
| Decision | 三次 run 後檢討 | retain／revise／stop |

這個例子是公開安全的 synthetic workflow，不代表任何實際團隊已有相同成效，也不授權 AI 接觸私人／客戶資料、外部發送、公開設定或 production 系統。

## 今日怎樣治理及量度一條 pilot：先寫半頁 control card，再選兩個 observation

為你的一條 pilot 寫一張半頁 control card：input 類別、允許／禁止 action、artifact、review owner、stop line、決定日期。接著選一個時間類和一個質量或風險類 observation，先定義從哪刻量到哪刻、誰記、甚麼算 rework。這些設定要在跑前完成，不要做完才找正面故事。

每次 run 後用一份簡單 receipt 回看 artifact、exception 和 observation，再把問題分類。到 decision date 時，根據 evidence 作 retain、revise、stop 或小擴大；若要擴大資料、權限或外發範圍，重新寫 card，不要沿用首輪授權。

**Jimmy 的結論：** 好的 measure 令你同時看見價值和風險，而不是製造另一個無人看的 dashboard。最小治理加一兩個比較，已經足夠讓 pilot 有方向地學習。

| 今日第一步 | 你要完成甚麼 | 安全起點 |
|---|---|---|
| 寫 control card | input、action、review、stop、owner | 只讀公開資料、只起 draft |
| 定 baseline | 一個可比較起點 | 過往可 review 時間 |
| 選兩個 observation | 時間加質量／風險 | 時間加退回原因 |
| 留 run receipt | artifact、exception、review 結果 | 一張每次更新的表 |
| 定 decision date | 何時作決定 | 三次 run 後 review |

未有 control card、owner 和 stop line 前，不要收集不必要個人資料，也不要把 AI 接到外部發送、客戶資料、公開設定或 production。下一步可看 [pilot 跑完後應 scale 還是 stop](./5-9-scale-or-stop.md)。

> 好的 measure 令你同時看見價值和風險，而不是製造另一個無人看的 dashboard。

← [AI Value Creator 入口](../README.md) · [按問題瀏覽](../../../README.md)
