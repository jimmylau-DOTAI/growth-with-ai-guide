# AI 做到一次唔等於可以交付：Skill 點樣用 quality gates 令結果過到收貨線？

AI 可以很快完成一個任務：起草一份內容、整理幾份資料、改一段程式、填一張表。可是「有 output」和「可以收貨」中間，往往差了很多：資料是否齊、來源是否可追、格式是否對、未知有沒有被標示、原本不應碰的地方有沒有被改、需要人承擔的決定有沒有被偷偷跳過。

若這些問題每次都靠你最後憑感覺看一遍，AI 就不是一個可管理的工作幫手，而是一個不停交半成品給你重做的人。看似 workflow 已跑起來，實際上完成的定義仍在你腦內；換一個人、隔一個月或 task 稍為變形，大家又要重新猜「到底怎樣才算做好」。

Jimmy 的判斷是：Skill 不應被理解成更長、更完整的 prompt，而是一份有完成線的工作合約。quality gate 就是把收貨標準放進流程：AI 每完成一格，才知道要交甚麼、怎樣被檢查、不過關應修一次、等待人還是停止。這令「做完」不再由 AI 自己宣佈。

| Quality gate | 它在檢查甚麼 | 不通過時怎樣處理 |
| --- | --- | --- |
| Input gate | 材料是否已批准、足夠且在 scope 內 | needs input／停在範圍外 |
| Process gate | 是否按必要步驟產生可讀 state | 留 receipt、補缺失步驟 |
| Output gate | schema、來源、格式、未知是否符合 | revise once 或標記未通過 |
| Review gate | 人是否能判斷主張、風險和適用性 | ready for review，等 named owner |
| Release gate | 是否可對外、寫正本、升級權限 | human approval／stop |

## AI 有 output 了，為甚麼仍未等於這個工作可以收貨？

AI 產生一段看起來流暢的文字，或成功跑完一個工具 call，只能證明它完成了一次生成／執行。它沒有自動證明輸入正確、沒有漏掉關鍵欄位、沒有把不確定內容當成事實、沒有改錯地方，更沒有證明對外發布或寫入正本是合適的下一步。

這個分別在多步工作特別重要。假設 AI 根據三篇資料寫 briefing：它可能成功交出一頁摘要，卻漏了一篇來源、把二手說法寫成原始事實，或沒有標記兩個來源之間的矛盾。若你只看「文字順不順」，這些錯會被帶到下一步，最後由人花更多時間補救。

**Jimmy 的結論：** Output 是一個中間物，不是完成證明。真正可交付的工作，要能說清它根據甚麼、過了哪些 checks、仍有哪些未知、誰已經為下一步負責。

可以用這個對照分清：

| 「AI 做完」的說法 | 收貨時仍要知道甚麼 |
| --- | --- |
| 「我已經整理好資料」 | 讀了哪些 source？欠了哪些？主張可否追溯？ |
| 「我已寫好內容」 | 有沒有答中指定讀者問題？有沒有越過事實邊界？ |
| 「我已改好檔案」 | 改了甚麼、沒改甚麼、diff／test 是否通過？ |
| 「我已經同步」 | 寫到哪裡、是否真的成功、能否回退？ |
| 「我已完成任務」 | 這是 draft、review-ready，還是 owner 已批准的 release？ |

quality gate 就是把這些不應靠猜的問題，放回 workflow 每一格去回答。

## AI Skill 為甚麼唔係一段好長 prompt，而係有完成線的工作合約？

一段長 prompt 可以說明任務、風格、背景和希望避免的錯；它對一次性協助很有用。但若同一件工作要多次重跑、由不同人啟動、接不同 input，單靠一段文字很難令每次都遵守相同邊界。特別是當 AI 要讀資料、寫 artifact、調工具、遇到例外或交接 review 時，prompt 很容易變成一份難以檢查的願望清單。

Skill 則把這段工作變成合約：它有清楚 goal、trigger、已批准 input、處理步驟、可見 output、quality gate、exception 和 acceptance。這不代表每個 Skill 都要寫成很複雜的程式；就算是一份 markdown 指引，只要人和 AI 都知道何時用、怎樣跑、做到哪一步才算交得出，它已經比「一段好 prompt」更可管理。

**Jimmy 的結論：** Prompt 決定一次對話怎樣開始；Skill 決定一個工作單位怎樣反覆交付。沒有 acceptance 和 gate 的「Skill」，通常只是一份換了名字的指示。

一份最小 Skill 合約可有：

| 部分 | 需要回答的問題 |
| --- | --- |
| Goal | 它要替哪個重複工作交甚麼結果？ |
| Trigger | 甚麼條件下才應啟動，而不是每次都用？ |
| Input boundary | 可讀甚麼、不讀甚麼、資料不足怎樣處理？ |
| Workflow | 中間需要留下哪些可讀 state／artifact？ |
| Quality gates | 每一格怎樣判斷 pass、revise、unknown 或 stop？ |
| Acceptance／release | 誰能收貨、誰能外發／寫正本、完成代表甚麼？ |

若缺少其中的 quality gate，AI 可以跑得很勤力，團隊卻仍無法比較這次和下次結果是否真的可靠。

## Quality gate 應該放在哪些步驟，才不會變成最後才找錯？

很多人只在最後加一句「請 review」。這會令問題太遲才被發現：一開始讀錯資料，到最後才發現全部分析都要重做；一開始 scope 已越界，到最後才發現不應該改正本；一開始沒有保留來源，到最後只剩一段無法追溯的文字。最後 review 當然需要，但它不應是唯一一關。

較穩的流程會把 gate 放在風險真正出現的地方：input 前確認範圍，處理中確認中間 artifact，output 前檢查可描述的品質標準，外部 action 前由人 release。這不是每一步都要停下來，而是讓已知的高成本錯不要一路流到最後。

**Jimmy 的結論：** Quality gate 最有價值的地方，不是在最後挑錯，而是在錯誤仍然便宜、容易回退的時候把它擋住。

一條小 workflow 可以這樣排：

```text
approved input
→ input gate：資料是否足夠、可讀、在 scope 內？
→ AI 產生中間 artifact
→ process gate：必要來源／欄位／state 是否存在？
→ AI 起 draft
→ output gate：schema、evidence、unknown、格式是否通過？
→ human review gate：主張、語境、風險是否可採用？
→ release gate：是否真的要外發、寫入或擴大？
→ receipt：留下決定與下一步
```

不是每個任務都要全部七格。一件低風險草稿可以只要 input、output、review；一件高責任 workflow 才需要更明確的 release 和 recovery。重點是 gates 對應實際風險，而不是為了流程而流程。

## 內容、資料、程式三種 AI 工作，各自可以怎樣寫可驗收標準？

「做得好」、「專業啲」、「符合我要求」不是可驗收標準，因為另一個人或另一個 AI 不知道如何檢查。這不代表所有標準都要變成死板分數；而是要先找出這份工作最不能接受的失敗，以及哪些東西可以用 evidence、schema、checklist 或 reader scenario 看出來。

不同工作需要不同 gates。內容工作要看讀者問題、主張和 evidence boundary；資料工作要看來源、欄位、缺失與計算；程式／文件改動要看 scope、diff、已知 scenario 和回退。把它們全部寫成一樣的「quality 80 分」不會有幫助，反而會掩蓋真正要收貨的東西。

**Jimmy 的結論：** 好 acceptance criteria 不是形容詞清單，而是把「不合格長甚麼樣」和「人可以怎樣驗證」寫清楚；它應跟工作類型走，而不是跟 AI 熱門詞走。

可以由以下反面標準開始：

| 工作類型 | 不合格的樣子 | 可檢查的 gate |
| --- | --- | --- |
| 公開內容 draft | 答非所問、主張無支持、把假設講成事實 | 讀者問題、evidence／unknown、review owner |
| Research／briefing | 缺 source、混合二手與原始說法、未標矛盾 | 每條重點有原始位置、未知欄、diff／review |
| 資料整理 | 少欄、格式錯、數字來源不明 | Schema、必填欄、範圍／合計 check |
| Code／文件改動 | 改到不在 scope、既有東西壞了 | Change request、diff、最小 test／scenario |
| Automation draft | 沒有停止線、直接外發、無法追查 | Exception state、draft queue、human release |

先寫三條「出現就不算完成」的條件，已經比一句「要專業」更能幫 AI 和 reviewer 對齊。

## Quality gate 不通過時，AI 應該 revise、問人，還是停止？

Gate 的價值不只在判斷 pass／fail，而是在失敗時把工作帶到正確地方。若所有 fail 都叫 AI 再生成一次，它可能在缺 input、矛盾資料或越界 scope 下反覆猜；若所有 fail 都交給人，workflow 又變得太重，連固定格式錯都要人工處理。不同錯誤需要不同去向。

原則是：清楚、低風險、可回退的規則問題可以 `revise once`；缺資料要 `needs input`；涉及取捨、矛盾主張、範圍或外部責任的要 `needs approval`；工具／狀態不可信時要 `failed safe`；任何外發、覆寫、付款、權限 action 仍要 human release。這令 AI 不會把「通過不了」誤解成「再努力生一版」。

**Jimmy 的結論：** Gate 不是一個分數，而是一條路由器：它決定錯誤應該由規則修、由人補、由 owner 決定，還是應該停下來保留狀態。

可用這個簡單 routing：

| Gate 不通過的原因 | 下一步 |
| --- | --- |
| 缺必填欄、格式錯、已知 schema 問題 | `revise once`，交 diff 和 check 結果 |
| 指定 input 少了、來源找不到 | `needs input`，列欠項，不自行補猜 |
| 兩個可信說法矛盾、要改 scope | `needs approval`，列選項與影響 |
| 工具中斷、版本不明、不能信任已跑狀態 | `failed safe`，保留最後可信 artifact |
| 要對外發送、寫正本、付款、改權限 | `human release`，只交 draft／預覽 |

想把這些狀態寫成 Skill 語言，可讀 [AI 一遇資料不足就繼續猜？Skill 要先寫好 exception ladder](./4-34-skill-exception-ladder.md)。

## 一條 Skill「能跑」同「可重複交付」，實際上差在哪裡？

能跑，通常指 AI 在某一次合適 input 下完成了工作。這已經是很好的探索起點，但仍可能靠運氣、靠當時在場的人補 context、靠 reviewer 默默修正。下次換一批資料、換一個人或多跑幾次時，工作是否仍能收貨，還未有證據。

可重複交付則多了幾樣可見資產：人知道何時啟動、AI 知道只讀甚麼、每一步有可檢查 artifact、已知錯有 gate、例外有 status、外部 action 有 owner、結果可追查並能用 feedback 改善。它不要求全自動，也不要求零錯；它要求錯時仍然不會失去責任和可讀 state。

**Jimmy 的結論：** Production-grade 不是一個工具標籤，而是一條 workflow 的證據：它多次在指定邊界內交到可驗收結果，而不是剛好有一次成功 demo。

| 能跑一次 | 可重複交付 |
| --- | --- |
| AI 交出 output | AI 交出有來源、狀態、check 的 artifact |
| 主要靠 prompt 和當時的人 | 有 trigger、input boundary、skill contract |
| 出錯就再試 | Gate 將錯路由到 revise／input／approval／stop |
| review 靠感覺 | 有可見 acceptance 和 named owner |
| 下一次重新解釋 | 保留 receipt、規則和可改進 feedback |

不要因為一條 workflow 還未到最右邊就否定它；先把最常重覆、最可描述的品質問題補成第一個 gate，便已是在由 User 走向 Builder。

## 想為第一份 AI Skill 加 quality gate，最安全的開始是甚麼？

第一個 gate 不需要從最重要、最複雜的工作開始。選一件重複、低風險、只產生 draft 的任務，例如把指定公開文章整理成固定 briefing，或把 sample 資料填入一張 schema 明確的表。你應該已看過它在哪裡容易出錯，例如缺 source、少欄位、超出 scope，這些正好是第一條最值得寫下的驗收線。

開始時不要急著把所有「好」都量化。先用反面寫法：列三條「出現以下任何一項，這次就不算完成」的條件。每條都要能由人看見、最好能用簡單 check 驗證；跑幾次後再看哪一條值得自動化、哪一條其實是需要更好 brief 或 human judgment。

**Jimmy 的結論：** 第一個 quality gate 的成功，不是令 AI 從此完美，而是令一個你本來每次都要親自捉的重覆錯，變成 workflow 會主動指出的事情。

可以跟這五步開始：

1. 選一條只交 draft、可回退的重複工作，避免客戶／production action。
2. 寫下最近三次最常令你退回 output 的同一種錯。
3. 將它改寫成「出現即不通過」的具體條件。
4. 決定不通過時是 revise once、needs input、needs approval 還是 stop。
5. 用 sample／公開安全 input 跑幾次，保留 check 結果和 reviewer feedback。

暫時不要把所有創作結果寫成硬規則；不要因為有 gate 就跳過 human review；更不要把一次通過當成 production-ready。若你需要先判斷哪段 SOP 值得做成 Skill，可讀 [唔係每條 SOP 都應該變成 AI Skill](./4-37-human-runbook-or-ai-skill.md)；要將已知錯做成更可重跑檢查，可讀 [最小 regression pack](./4-10-minimum-regression-pack.md)。

← [返回 AI Builder](../README.md) · [按問題瀏覽](../../../README.md)
