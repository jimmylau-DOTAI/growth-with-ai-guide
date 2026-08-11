# AI 改文件、網站或資料前，點樣先劃一個可回退 workspace，唔怕它直接掂正本？

想讓 AI 幫你改文件、網站、小工具或資料整理時，真正令人不敢放手的，通常不是它會改錯一個字，而是你不知道它讀過甚麼、碰過甚麼、原本有沒有保留、改完又怎樣證明沒有破壞其他東西。當 AI 說「我幫你改好」，如果你只得一個最後版本，便很難分辨它做對了甚麼、做錯了甚麼、該從哪裡回去。

很多人以為解法就是「先 backup」。backup 當然重要，但它沒有回答本輪 AI 到底只可讀哪些檔、只可改哪一小段、不能做哪些外部 action、要用甚麼驗收、出了問題由誰決定放棄或重跑。沒有這些邊界，副本也可能很快變成另一個無人知道狀態的正本。

Jimmy 的判斷是：第一次交 AI 改東西，目的不是最快把正本改完，而是先建立一個人和 AI 都看得懂的改動場地。source of truth、working copy、change request、verification 和 recovery 分開後，AI 才能在一個可檢查、可撤回的 workspace 裏真正幫到你。

| 改動場地的一格 | 它要解的問題 | 完成後留下甚麼 |
| --- | --- | --- |
| Source of truth | 不知哪一份才是準確基準 | 指定正本／資料來源與只讀範圍 |
| Working copy | AI 容易直接覆寫或混入實驗改動 | 可丟棄的副本、sample 或 feature slice |
| Change request | 「幫我整好」的範圍太闊 | 本輪要改與明確不改的清單 |
| Verification | 改完只憑感覺看一眼 | Diff、checklist、test 或人手 scenario |
| Recovery | 出事後不知哪版可信、誰可回退 | 回退點、已做／未做 action、owner |

## AI 改正本時最危險的是甚麼，為甚麼不只是「改錯字」？

AI 的改動可以很快跨過很多檔案、欄位或步驟。即使原意只是改一個 FAQ，它也可能因為看到相似資料而改動其他 section、補入未確認資訊、移走本來有用途的內容，或在沒有清楚要求時重組整份文件。若這些變更直接落到正本，reviewer 往往先要花時間找回「原本是甚麼」，才有可能判斷新版本是否好。

對 code、資料或網上系統而言，改動還可能牽涉連鎖影響：一個 schema、設定或連結被變更，未必立即在畫面上出錯，但可能在下次使用、同步或發布時才出現問題。這不是說 AI 不能改，而是要承認「看起來完成」不等於「其他地方沒有被影響」。

**Jimmy 的結論：** 可回退 workspace 的第一個價值，是令改動不會跟正本混在一起；第二個價值，是讓人有證據看見 AI 實際改過甚麼，而不是被一個最後版本迫著相信它。

在交 AI 前，先分辨以下幾種風險：

| 風險 | 若直接改正本會怎樣 | 可回退 workspace 怎樣減少它 |
| --- | --- | --- |
| Scope 漂移 | 多改了不在本輪的內容 | 只開一個 feature slice／draft copy |
| 資料猜測 | 未確認內容被寫成事實 | 只讀指定 source，未知要標記 |
| 舊內容消失 | 無法知道被刪了甚麼 | 保留正本與 diff／變更預覽 |
| 檢查不足 | 局部看似好，全局出問題 | 指定 checklist、scenario 或 test |
| 外部影響 | 改動被同步、發佈或通知別人 | 第一輪不接外發／production action |

這不是要你怕改動；它是把「可以試」和「直接影響正本」分成兩件事。

## Source of truth 同 working copy 點樣分，AI 才不會讀錯或改錯版本？

很多 workspace 出事，不是因為檔案不存在，而是因為同一份資料有多個版本：舊草稿、下載副本、同事改過的 copy、未同步文件、甚至名稱相近的資料夾。若 AI 沒有被告知哪一份是 source of truth，它可能選到最容易讀的版本，而不是你真正要依據或保留的版本。

working copy 的角色則不是「另一份正本」，而是本輪讓 AI 試改的受控地方。它可以是一份新建 draft、一個本機 sample、專案的一個 feature branch／slice，或一個不會自動同步回正式系統的 sandbox。重點是你可以清楚說「它只可在這裡寫」，不合格便可丟棄或重開。

**Jimmy 的結論：** Source of truth 告訴 AI 甚麼可以參考；working copy 告訴 AI 哪裡可以動手。兩者分開，才不會把「讀對」和「改錯正本」混成同一個風險。

開始前可寫一張小型 workspace card：

| 欄位 | 要寫清楚甚麼 |
| --- | --- |
| 正本在哪裡 | 哪個檔案、資料夾、系統或版本是本輪唯一基準 |
| 只讀範圍 | AI 只可讀哪些檔案、欄位或已批准材料 |
| 可寫位置 | AI 只可新建／改動哪個 draft、sample 或 sandbox |
| 不可碰位置 | 不讀、不改的 vault、CRM、production、帳戶或資料夾 |
| 版本標記 | 本輪副本如何命名、怎樣認出是 test output |

當 source 不清楚時，先叫 AI 列出它看見的候選檔案並停下，不要讓它「估哪一份最新」。

## Change request 要寫到幾清楚，AI 才不會把「幫我整好」變成範圍失控？

「幫我整好」、「做得簡單啲」或「照上次改」都很自然，但它們不是可驗收的改動要求。人聽到這些話會從關係、歷史和眼前畫面補足意思；AI 則需要根據有限 context 猜一個最像的方向。它猜得愈主動，越可能把本來不在 scope 的功能、資料或視覺調整加進來。

好的 change request 不需要寫成厚重 specification，但至少要讓人看見本輪要改哪個工作問題、只碰哪個 slice、哪些東西明確不改、完成後如何收貨。這個範圍也幫 AI 在發現需要多一格資料、設定或權限時及早停下，而不是先做了再說。

**Jimmy 的結論：** Change request 的目的不是限制 AI 創意，而是令 AI 的主動性只在你已批准的範圍內發揮；超出範圍時，它應交問題而不是自行擴大。

一張好用的 request 可以有：

1. **工作問題**：這次想改善哪一個使用情境或摩擦？
2. **最小改動**：只改哪一頁、哪個檔案、哪個 feature slice？
3. **完成線**：人打開後要能看見／做到甚麼？
4. **不做清單**：不改 schema、不加登入、不接外部工具、不部署等。
5. **驗收方式**：用 diff、checklist、測試或真人 scenario 怎樣檢查？
6. **停止條件**：發現缺 source、需新增權限、需改正本時要怎樣處理？

如果這些未清楚，先寫 [Build 前先寫 assumption ledger](./4-35-assumption-ledger-before-build.md)，不要叫 AI 以更多改動來替你找答案。

## AI 改完工作副本後，怎樣用 diff、checklist 或 scenario 驗收？

「看起來無問題」是最容易漏東西的驗收方法。你可能只看了新加的區域，卻沒有看 AI 是否刪掉既有內容、改了不該改的欄位、令某個連結失效，或把未確認文字放進可見位置。驗收不是要你在每次小改動做一套企業 QA，而是要為這次 change request 定一個能抓住主要風險的可見機制。

不同工作用不同驗收：Markdown／文件可看前後 diff 和 source 對照；小網站可以跑一個指定使用情境；資料整理可核對欄位、筆數與未知標記。AI 也可以協助產生 checklist 或指出變更，但最終 check 要能讓人找到具體 evidence，而不只是接受 AI 的自我報告。

**Jimmy 的結論：** Verification 的完成線不是 AI 說「我已檢查」，而是人能根據 request 看見甚麼改了、甚麼沒改、關鍵條件有沒有通過。

以一份 local sample briefing 轉成 FAQ draft 為例：

| 驗收項 | 人怎樣檢查 | 不通過時怎樣處理 |
| --- | --- | --- |
| 只用了指定 briefing | 每條 FAQ 可回到原資料段落 | 標 unknown 或退回重做，不補猜 |
| 沒新增 offer／日期／價格 | 用 source 對照與 diff | 刪除未支持內容 |
| 正本未被覆寫 | 確認只有 `faq-draft.md` 有變更 | 停止，回到 working copy |
| 問題結構可讀 | 用 2–3 個讀者情境看答案 | 修正結構，不擴大 scope |
| 未知已標記 | 檢查待確認欄位 | 交給 owner 補資料或決定不寫 |

若有已知會重覆出現的錯，才值得把它變成 [最小 regression pack](./4-10-minimum-regression-pack.md)；第一輪先把最重要的驗收線看清便足夠。

## Recovery 點樣設計，才不會出錯後只剩「再試一次」？

可回退不等於只在開始前複製一份檔案。真正需要的是：當 output 不合格、AI 中途停下、發現 scope 錯了或工具改了太多時，團隊知道哪一版仍可信、可以丟掉哪一份 working copy、要由誰決定重跑、是否需要先改 request 或 input。若這些沒有寫下，大家通常只會不斷叫 AI 再試，令狀態愈來愈難追。

Recovery 也讓你避免把一次失敗錯誤歸咎於「AI 不行」。如果 receipt 顯示是 input 少了一份、request 太闊、check 不清楚或外部 dependency 中斷，你便知道下一輪要補哪一格；若只是重跑而不留狀態，失敗不會變成任何可用規則。

**Jimmy 的結論：** Recovery 的核心不是回到舊版本，而是保留一個人能理解的決定點：這次跑到哪裡、甚麼可保留、甚麼要丟、下一步先修規則還是重跑。

每個改動後，留一張簡單 recovery receipt：

| 要留甚麼 | 用途 |
| --- | --- |
| 正本／起點版本 | 知道回退基準是甚麼 |
| Working copy 位置 | 知道哪些輸出可保留或丟棄 |
| 實際改動摘要／diff | 找到 scope 有沒有漂移 |
| 驗收結果 | 分清哪一項通過、哪一項失敗 |
| 已做／未做 action | 不把 draft 誤認為已寫入、已發送或已部署 |
| 下一位 owner | 決定修 request、補 input、重跑或停止的人 |

當你找不到這些資訊時，先不要加更多 AI 權限或更大 scope。先讓一個小改動可以被安全理解和撤回。

## 可回退 workspace 為甚麼仍然不是完整安全保證？

一份副本或 sandbox 主要減少「改壞正本」的風險，但它不會自動處理敏感資料、網絡 action、錯誤判斷、權限管理、惡意 input 或工具供應商行為。若你把客戶、CRM、付款、合約或 credentials 複製進測試 workspace，風險仍然存在，只是多了一個位置存放它們。

同樣地，working copy 不會令 output 自動正確。AI 仍可能誤解內容、錯引來源、生成不適合的文字或改錯邏輯。因此 workspace 要配合最小資料範圍、明確 change request、human review 和 release gate；越接近刪除、覆寫、外發或影響別人的 action，越應留在 draft／approval 層。

**Jimmy 的結論：** 可回退 workspace 是可靠改動的地板，不是安全的終點。它令錯誤更容易被收回，但不取代資料邊界、品質判斷和人類責任。

這些東西應同時存在：

1. 只給 AI 這輪真正需要、已批准的材料。
2. 把正本與 working copy 分開，避免直接覆寫。
3. 用 request、assumption ledger 寫清 scope 和未知。
4. 以 diff、checklist 或 scenario 做 human verification。
5. 對外發送、production write、付款、權限和敏感資料維持 human release。

少了其中一格，不要用「反正有 backup」來跳過。先把 workflow 收窄到你能真正管理的程度。

## 想第一次交 AI 改東西，最安全的 workspace 試跑怎樣設計？

第一個試跑最好選一份已批准的 local sample 或 public-safe draft，而不是正在使用的客戶文件、production 系統或整個 project。任務也應是單一、可驗收的 slice，例如把一份 sample briefing 重排成 FAQ draft、在一個 sample 頁增加一個純顯示欄位，或在副本中修正指定格式；不要求 AI 連接外部資料、部署或直接發布。

成功標準不是「AI 幫我改了很多」，而是它只讀了指定 source、只寫進 working copy、改動可用 diff／checklist 驗收、不通過時不會碰正本、你能清楚說出怎樣重開。能跑好這種小改動，才值得慢慢增加資料範圍、功能或頻率。

**Jimmy 的結論：** 第一個可回退 workspace 的成果，是一個你敢交、敢檢查、也敢丟掉的 working copy；不是讓 AI 第一次就處理最重要的正本。

可以按這五步開始：

1. 選一份本機 sample、公開安全內容或 synthetic 資料，避開真客戶／production。
2. 寫清唯一 source of truth、AI 只讀範圍和 working copy 位置。
3. 寫一個只包含單一 feature slice 的 change request，加上不做清單。
4. 在 AI 動手前定好 diff、checklist 或 scenario；完成後由人執行驗收。
5. 留下 recovery receipt；不通過便丟 working copy／回到正本，不讓 AI 直接「修到好」。

暫時不要把真客戶資料、production data、credentials 或內部 vault 複製進測試 workspace；不要一次交整個 project；亦不要因為有副本就跳過 review。若你需要把 workspace 的目的、可讀材料和驗收寫成工作合約，可讀 [先寫一張 workbench contract](./4-19-workbench-contract.md)；改動開始前仍有未確認問題時，回到 [AI 一遇資料不足就繼續猜？Skill 要先寫好 exception ladder](./4-34-skill-exception-ladder.md)。

← [返回 AI Builder](../README.md) · [按問題瀏覽](../../../學習地圖.md)
