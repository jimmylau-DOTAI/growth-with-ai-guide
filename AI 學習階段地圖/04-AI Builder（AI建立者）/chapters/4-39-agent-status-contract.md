# Agent 一直顯示 Loading，係未壞咗？先寫清 status contract，令人知道何時等、何時介入

當 AI 開始做多步或較長工作，使用者最常遇到的畫面就是「Loading」：它可能正在讀材料，也可能卡在工具、等你補資料、等你批准，甚至早已失敗。若所有狀態只留在對話內，下一位同事無法知道該繼續等、重新叫一次、找 owner，還是其實不能再讓它繼續。

這種不確定會令團隊走向兩個極端：有人一看沒有回覆就不斷 retry，令舊狀態被覆蓋；有人以為 AI 沒出錯就等於已完成，錯過了需要 review 或 release 的一步。問題不在於 UI 顏色不夠漂亮，而在於 workflow 沒有共同語言說清楚「現在在哪裡、已做甚麼、尚未發生甚麼、下一位誰負責」。

Jimmy 的判斷是：status 不應只是 Loading／Done 的視覺標籤，而是一份責任合約。每個狀態要同時帶出 current step、可見 artifact、下一位 owner 和可做 action；當 AI 不能安全自行繼續時，人便能用最少資訊接回工作，而不是靠猜或靠重問整段 chat。

| 狀態 | 它真正代表甚麼 | 人應看見甚麼 |
| --- | --- | --- |
| Queued | 已收到任務，尚未開始處理 | 工作單位、排隊原因、預計起點 |
| Running | 在指定 scope 內執行 | current step、已讀 input、最後更新 |
| Needs input | 缺必要材料或答案 | 缺甚麼、由誰補、未做了甚麼 |
| Needs approval | 已到責任／外部 action 門檻 | 選項、影響、誰可 approve／reject |
| Failed safe | 未完成，但有可信狀態可回看 | 成功部分、錯誤、回退點 |
| Ready for review | 有 draft artifact，仍未可對外使用 | 輸出位置、check、unknown、review owner |
| Completed | Owner 已就本輪結果作決定 | 采用／修訂／停止決定與下一步 |

## Agent 顯示 Loading 很久時，為甚麼不應只靠「再試一次」處理？

一個長工作沒有即時回覆，原因可以完全不同：它真的正在處理、指定 input 缺失、工具連線中斷、已到 approval gate，或其實已交了一份 draft 等人 review。若全部都被叫成「Loading」，使用者無法用正確動作回應，常見結果就是重開一次，令原本可用的狀態、已讀材料和錯誤訊息都混在一起。

無限制 retry 特別危險，因為它把「暫時等候」誤當成「應該再做一次」。如果工作正在等待 owner 批准，重跑不會解決問題；如果工具中斷，重跑前至少要知道最後成功位置；如果 input 不足，AI 多跑幾次只會多猜幾次。正確的下一步取決於狀態，而不是取決於畫面多久沒有動。

**Jimmy 的結論：** 當 Agent 看起來沒反應，第一個問題不應是「它壞了嗎」，而是「它現在屬於哪個可交接狀態，誰有權做下一步」。有名字的狀態，才有可管理的處理方法。

把不同情況拆開：

| 你看到的表面情況 | 不應直接做甚麼 | 應先確認甚麼 |
| --- | --- | --- |
| 很久沒有新訊息 | 不斷開新 run | 是否仍是 running、最後一步與最後更新 |
| Output 不完整 | 叫 AI 硬補結論 | 是否 needs input、unknown 或 failed safe |
| 要寫入／發送前停住 | 當成工具故障 | 是否已進 needs approval／human release |
| 工具報錯 | 立即覆蓋舊 output 重跑 | 是否有可用 receipt、回退點與錯誤類型 |
| 出現 draft | 當成已交付／已發布 | 是否仍在 ready for review，誰應收貨 |

這個分辨令速度不再靠催 AI，而是靠每個人都知道正確的下一手。

## 一套最小 Agent status contract 要有哪幾個狀態，才不會把所有未完成混在一起？

不需要一開始就做很複雜的監控系統，但至少要把「未完成」拆成不同責任。缺資料不等於等批准；等批准不等於工具失敗；有草稿不等於已完成。若它們都只顯示一個灰色 icon，使用者和 owner 都無法知道工作應該由誰接手，或是否仍在安全範圍內。

status 名稱可以按你的工具與團隊習慣調整，但每個名稱要有固定含義。更重要的不是叫法，而是 status 轉換時有沒有留 evidence：甚麼觸發轉換、AI 已做甚麼、尚未做甚麼、下一步需要哪個角色。這令 status 成為 workflow 的可讀 state，而不是漂亮 dashboard 裏的裝飾。

**Jimmy 的結論：** 最小 status contract 的目的不是追蹤每一下 AI 動作，而是讓每一個「不能安全自行繼續」的時刻，都有清楚 owner、artifact 和下一步。

可以從這七格開始：

1. **Queued**：任務已收到，尚未讀任何 input；可看見工作單位與排隊原因。
2. **Running**：正在指定 scope 內處理；顯示 current step、已讀 input class、最後更新。
3. **Needs input**：缺少必要材料／答案；列出缺項與指定 owner。
4. **Needs approval**：遇到矛盾判斷、外部 action、scope 改變；列選項與影響。
5. **Failed safe**：執行未完成；保留成功部分、錯誤、最後可信版本與回退點。
6. **Ready for review**：有 draft／artifact；保留 check、unknown、reviewer，仍未 release。
7. **Completed**：owner 已作出采用、修訂或停止的本輪決定；不是自動等於已發佈。

若一個工作仍只分「跑緊／做完」，先補 `needs input`、`needs approval`、`failed safe` 和 `ready for review`；它們通常最能防止誤解和無效 retry。

## Status 裏要留低哪些 evidence，人才可以不打開全部 chat 也能接手？

Status 只有一個字仍然不夠。看到 `needs-approval`，人還要知道 AI 在問哪個決定、已經做了甚麼、哪個 input 導致這個問題、若拒絕又怎樣處理。若這些只藏在長對話或工具 log 裏，狀態雖然有名字，實際仍然無法交接。

Evidence 的目標也不是把所有私人材料、tool call 或對話全文塞進 dashboard。它只需保留足夠讓下一位 owner 做決定的最小資訊：這是甚麼工作、目前在哪一步、用了哪類 input、交了甚麼 artifact、觸發了甚麼 check／例外、下一個 action 是甚麼。敏感內容可用受控連結或摘要，不應因為要 observability 而擴大曝光。

**Jimmy 的結論：** Status 要連住 evidence，不是連住華麗 UI。只要另一個人能在不重讀全部歷史下判斷要等、補、批、重跑或停止，這個 status contract 已經有用。

每個狀態更新可包含以下六欄：

| 欄位 | 讓接手者知道甚麼 |
| --- | --- |
| 工作單位／run ID | 這次在處理哪一件工作，避免混淆多個 run |
| Current step | 已進到哪一格，不只「進度 60%」 |
| Input class／範圍 | 它讀了哪些指定材料，沒讀甚麼 |
| Artifact／state 位置 | draft、receipt、diff 或結果可在哪裡查看 |
| Check／exception | 哪個規則通過、哪個觸發 needs input／approval／failed safe |
| Owner + next action | 誰要做甚麼，AI 現在刻意不做甚麼 |

若任何一格需要披露客戶、CRM、付款或私有內容，先將它留在受控內部位置；公開指南與一般 status 摘要只需記工作狀態，不需複製敏感資料。

## AI research brief 由 running 走到 review，status 會怎樣幫人作正確決定？

假設 AI 要把三篇已批准的公開文章整理成一頁 internal briefing。這是一個低風險、適合測試 status contract 的工作：它只讀指定 URL、只交 internal draft、不會自動發布。即使這樣，過程仍可能由 running 轉 needs input、needs approval、failed safe 或 ready for review；不同狀態代表完全不同的下一步。

若第三個 URL 無法開啟，AI 不應繼續把 brief 寫成三篇都讀過；它應列 `needs-input`，說清楚欠哪個 URL、需要替代來源還是 owner 允許跳過。若 draft 裏一項主張無法核對，應轉 `needs-approval`，列出選項；若工具中斷，應 `failed-safe`，保留已讀兩篇和最後可信 artifact。這些狀態讓 owner 不必猜 AI 是否「還在努力」。

**Jimmy 的結論：** Status contract 令 workflow 的慢變成可解釋：不是「Agent 很慢」，而是「它正確地等某個 input、某個決定或某個 recovery action」。

這個 run 可以這樣呈現：

| Status | 可見 state | 下一位 owner／動作 |
| --- | --- | --- |
| Running | 已讀兩個 URL；正在抽第三篇；尚未生成結論 | AI 繼續；若超時，回報最後更新 |
| Needs input | 第三個 URL 失效；列出欠項 | 研究 owner 補來源或批准跳過 |
| Needs approval | 兩項說法矛盾；列出原始位置 | 內容 owner 選擇刪除、補證據或保留 unknown |
| Failed safe | 工具中斷；保存兩篇摘要與錯誤時間 | Workflow owner 決定重跑或停止 |
| Ready for review | Draft、來源、unknown、check 已齊 | Reviewer 檢查；不可直接發布 |
| Completed | Owner 選擇 internal 採用／修訂／停止 | 留決定與下一步，不等於對外 action |

跑完後可回看：每一次卡住是否走到正確 owner、是否保留了正確 evidence、是否有任何 draft 被誤當成 completed。

## Needs approval 點樣由一個模糊「幫手睇下」變成真正可管理的 gate？

「麻煩睇下」看似有 human-in-the-loop，實際卻未說明 reviewer 應看甚麼、誰有權 decide、拒絕後如何回到 workflow。若 team 很忙，這種模糊 gate 很容易變成 AI output 在沒有人真正收貨的情況下被採用，或者每個人以為另一些人會看。

Needs approval 應在會改變責任、外部狀態、敏感資料範圍或核心判斷的門檻出現。它需要把選項、影響、已知 evidence、unknown 和未做 action 清楚交給 named owner。Owner 選 approve、revise 或 stop 後，status 才能合法轉到下一格；不是 AI 等了一段時間就自動當作默許。

**Jimmy 的結論：** Approval gate 的作用不是拖慢 Agent，而是將「應否繼續」的責任放回應承擔的人手上；沒有清楚 owner 的 approval，不是 gate，只是一個容易遺漏的訊息。

每個 `needs-approval` state 應問清：

1. 哪個問題令 AI 不能安全繼續？
2. 已有哪些證據、哪一些仍不確定？
3. Owner 有哪幾個可選 action，各有甚麼影響？
4. AI 在收到決定前刻意不做甚麼？
5. 誰是唯一可以 approve／reject／要求 revise 的 owner？
6. 多久後若無決定，應維持等待、提醒還是正式 stop？

這樣人手 review 不再是一個不確定等待，而是 workflow 內可被看見、可被收尾的狀態。

## Completed 到底代表甚麼，為甚麼不等於已發佈、已交付或已證明有效？

「Completed」是最容易被誤用的狀態。AI 完成生成、workflow 完成一次 run、reviewer 完成檢查、內容已發佈、客戶已收到、成果已產生價值，這些其實是不同事件。若全部寫成 completed，團隊就會以為一個內部 draft 已經產生外部結果，或以為一輪 test 成功等於 workflow 已 production-ready。

較好的定義是：completed 只代表本輪有 owner 根據指定 checks 作出一個可記錄的決定，例如內部採用、要求 revise 或正式 stop。後續若需要發佈、交付、量度結果，應該有它們自己的 status／receipt／owner，而不是偷偷包含在同一個字裏。

**Jimmy 的結論：** 清楚的完成狀態不是冷冰冰的行政工夫；它保護你不會把「AI 做完一段工作」誤讀成「世界已經因而改變」。

可將結果分開記：

| 狀態／事件 | 真正含義 |
| --- | --- |
| Ready for review | AI 已交 artifact，仍未有人收貨 |
| Completed (internal decision) | Owner 已採用、退回或停止這一輪 output |
| Released／published | 有權的人完成對外或寫入正本 action |
| Delivered | 指定對象已收到，並有送達證據 |
| Outcome reviewed | 有足夠資料評估 workflow 有沒有幫到工作結果 |

先把這些詞用對，即使你暫時只用一張文字 task note，也比一個永遠顯示「Done」的 dashboard 更可靠。

## 想為第一條 AI workflow 加 status contract，最安全的開始是甚麼？

不用先建 dashboard、monitoring stack 或完整 Agent platform。挑一條仍然靠 chat 跟進、但只產生 draft 的低風險工作，例如把指定公開文章整理成 internal briefing，或把一組 sample 資料填入固定模板。用文字、表格或 task note 記 status 已足夠驗證這套共同語言有沒有幫到人。

第一輪只要先做好最容易被混淆的三格：`needs-input`、`needs-approval` 和 `failed-safe`。你要能看見缺甚麼、等誰、哪一版可信、下一步何時可以重新開始；其餘 queued、running、ready for review、completed 可隨 workflow 成熟慢慢加。這比先做一個顯示很多數字的 dashboard 更接近可用的治理。

**Jimmy 的結論：** 第一份 status contract 的成功，不是追到每一下 AI 動作，而是當 AI 不能自己安全繼續時，任何指定 owner 都能看懂現在發生甚麼，並作出正確下一步。

可以跟這五步開始：

1. 選一條只交 internal draft 的工作，勿接客戶、CRM、付款或自動外發。
2. 為 `needs-input`、`needs-approval`、`failed-safe` 定義觸發條件、receipt、owner 和未做 action。
3. 加入最少 `running` 和 `ready-for-review`，讓人看見 AI 是否仍在 scope 內。
4. 每次 status 轉換都留下工作單位、current step、artifact、check／exception 和下一位 owner。
5. 先 review 三次真實試跑中有沒有少 retry、少誤解、易接手，再考慮 dashboard 或更多 automation。

暫時不用把所有 tool call、私人對話、客戶資料或秘密材料塞進 status log；不用為 status 先造 dashboard；也不要把 completed 當成已發佈、已交付或已證明價值。若你還未定義何時必須停下來等人，讀 [AI 一遇資料不足就繼續猜？Skill 要先寫好 exception ladder](./4-34-skill-exception-ladder.md)；若需要讓 AI 交出可 review 的工作狀態，讀 [先把工作變成可讀 state](./4-15-readable-state.md)；第一次接真 workflow 前，再讀 [第一個 AI live run 唔係直接按掣](./4-36-dry-run-before-live-run.md)。

← [返回 AI Builder](../README.md) · [按問題瀏覽](../../../學習地圖.md)
