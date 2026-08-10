# AI 話做完、畫面又似樣，為何仍未算完成？你缺的是可重跑的 evidence loop

AI 做完一個改動後，最常見的「證明」是一張 screenshot、一個綠色 test、一個成功 API response，或一句「已完成」。這些都可能有價值，但通常只證明其中一小部分：畫面在某一刻長甚麼樣、某次 request 有回覆、某一組測試通過，或模型覺得自己已做完。它們不會自動證明原本問題真的被解決，也不會證明其他未測範圍沒有被影響。

如果每次驗收都換一種方法，你也無法比較修正前後究竟有沒有改善。你可能先用 screenshot 說有 bug，修完後用一個不相關的 test 說好了；中間沒有一條可重走的路徑連接兩者。結果是工作看起來一直推進，真正的 acceptance、out-of-scope 邊界和後續風險卻沒有人說清。

Jimmy 的判斷是：AI workflow 的可靠性不在於它會說 done，而在於人可以沿同一條證據路徑，重現原本問題、檢查最相關 evidence、做受控改動、再用相同路徑讀回結果，並清楚報告已驗和未驗。這個 reproduce → inspect → patch → verify → report 的 evidence loop，才讓一輪修正變成可比較、可交接、可學習的工作。

| Evidence loop 的一格 | 它要解的問題 | 完成後留下甚麼 |
| --- | --- | --- |
| Reproduce | 「好像有問題」無法被別人重現 | 預期、實際、輸入與重現步驟 |
| Inspect | 收集太多或看錯 evidence | 最相關的資料、狀態、checklist |
| Patch | 改動 scope 不清、順手改太多 | 可比較的 working copy／diff |
| Verify | 修完用另一條路說沒問題 | 同一路徑的前後結果與 check |
| Report | 把局部成功說成整體完成 | 驗證範圍、unknown、owner decision、未做 action |

## Screenshot、綠色 test 或成功 response，為甚麼都未必等於 AI 工作完成？

Screenshot 只捕捉一個畫面，一個綠色 test 只覆蓋它被設計要測的行為，一個成功 response 只代表服務在那次 request 回了資料。它們都是 evidence，但不是所有 evidence。若你不問「它實際覆蓋哪個問題、沒有覆蓋甚麼」，便很容易把一個局部信號升級成「整個 workflow 已經正常」。

這個問題不只在 code。內容 draft 看起來流暢，不代表每個主張有來源；資料表能打開，不代表欄位沒漏或數字可信；Agent 顯示 completed，不代表 owner 已 review 或外部 action 已被批准。不同工作需要不同 evidence，但共同原則是：證據要對應原本聲稱已解決的問題。

**Jimmy 的結論：** 局部成功不是假 evidence；它只是有範圍的 evidence。可靠驗收的第一步，是把「它證明甚麼」和「它完全未證明甚麼」同時說出來。

可用這張對照避免過度宣稱：

| 你手上有的證據 | 它可以支持的說法 | 它不能支持的說法 |
| --- | --- | --- |
| Screenshot | 指定畫面在指定狀態顯示正常 | 整個流程、所有裝置、所有資料已正常 |
| Green test | 被測的 scenario／assertion 通過 | 未覆蓋的功能、外部系統或 production 已安全 |
| 成功 API response | 某次 request 有有效回應 | 資料完整、寫入正確、下游 action 已發生 |
| AI output | AI 生成了一份 artifact | 內容正確、已被人收貨、可對外使用 |
| Reviewer note | 指定 reviewer 在指定 scope 看過 | 所有人、所有風險、所有後續結果都已驗證 |

每次報告只說證據真正支持的範圍，反而更能建立信任。

## Reproduce 怎樣把「好像壞了」變成可重跑的 AI 工作問題？

很多 bug、品質問題或 Agent 失敗，一開始都只是一句感覺：「結果唔啱」、「畫面怪怪地」、「AI 又讀錯」。這些描述足夠提醒你有事發生，卻不夠讓另一位人或 AI 精準調查。沒有明確預期、實際結果、輸入和步驟，下次可能無法重現；就算剛好修好了，也不知道到底修了甚麼。

Reproduce 的目的不是把問題寫成很長的 technical ticket，而是把摩擦變成一條可走的路：在甚麼 input／情境下，預期看到 X，實際卻看到 Y；這個差異對哪個 acceptance 有影響。對內容和資料工作同樣適用，例如「指定來源缺失時，預期標 unknown，實際卻生成了確定結論」。

**Jimmy 的結論：** 能被重現的問題，才可以被可靠地修正。若你只能說「上次好像不對」，AI 最多只能猜一個改善；若你能寫清 X 和 Y，下一輪才有可比較的驗收線。

一張最小 reproduce note 可包括：

1. **工作單位**：哪一個頁面、run、brief、資料表或 Agent task？
2. **Input／前提**：用了哪個 sample、URL、欄位或狀態？
3. **步驟**：由哪個 action 開始，按甚麼順序走？
4. **預期 X**：原本應出現甚麼 output／state？
5. **實際 Y**：實際看見甚麼差異、error 或缺口？
6. **影響範圍**：這是 draft、local sample、internal workflow，還是未驗的外部系統？

若問題無法穩定重現，先記錄不確定性和最後可見 state，不要叫 AI 在沒有證據下「修到看起來好」。

## Inspect evidence 時怎樣只看最相關資料，又不因為驗證而擴大敏感範圍？

發現問題後，很容易想「把所有 log、所有資料、所有對話都給 AI 看」。這通常令調查變慢，也可能把客戶、CRM、付款、私有 vault 或不必要的敏感材料暴露給一個本來只需看小範圍的 workflow。更多資料不一定帶來更好判斷；更重要的是先知道這個問題需要哪一種 evidence。

例如 UI 問題可能只需看指定狀態、DOM／render 結果或 user scenario；資料問題可能只需看 source、schema、欄位值和 transformation rule；內容問題則應看 brief、原始來源、主張與 unknown。把 inspection 限定在最相關的 source，不但守住資料邊界，也讓後面 patch 和 verify 的因果更清楚。

**Jimmy 的結論：** Inspect 的目的不是收集最多資料，而是找到足以解釋 X 和 Y 差異的最小證據。Evidence 越精準，AI 越不需要用無關 context 猜原因。

可用問題類型選 evidence：

| 問題類型 | 優先看甚麼 | 不應因此自動打開甚麼 |
| --- | --- | --- |
| UI／文件呈現 | 指定頁面狀態、render、欄位／文字 | 全部使用者資料、所有 production log |
| 資料／schema | 指定 source、欄位、轉換規則、sample | CRM、付款、未相關資料表 |
| AI content／brief | Approved brief、原始來源、draft、unknown | 私訊全文、未公開策略、客戶材料 |
| Agent run | Run receipt、input class、status、工具錯誤 | 整個 vault、所有 chat history |
| Integration | 指定 request／response、queue state、schema | 完整帳戶憑證、其他系統所有記錄 |

如果最小 evidence 都不能解釋問題，先寫成 `needs input`／`needs approval`，由 owner 決定是否擴大調查；不要讓 AI 自行取得更多存取權限。

## Patch AI workflow 或 working copy 時，怎樣避免修一格卻改壞其他地方？

當你知道可能原因後，AI 很容易提出一大串改動：改 prompt、換模型、加資料、重寫整份檔案、加 connector、再加一堆保護規則。這種「一次全部改好」的方式看起來積極，卻令你無法知道哪個改動真正解決問題，也增加 scope 漂移和 regression 的機會。最終若結果仍不好，你只能重新調查整堆變更。

較可靠的 patch 應針對已 inspect 到的假設，放在 working copy／sandbox，並清楚記錄本輪只改甚麼、不改甚麼。若問題是缺欄位，先修 schema／validator；若問題是 brief 不清，先修 brief；若資料來源不足，先補 input 而不是重寫 output。每輪只改最可能的因，才能讓 verify 真正比較前後。

**Jimmy 的結論：** Patch 不是「AI 幫我整好所有東西」，而是一個可被驗證的假設：我改這一格，預期 X 和 Y 的差異會消失，而其餘邊界保持不變。

Patch 前可寫這張小卡：

| 項目 | 要說清楚甚麼 |
| --- | --- |
| 問題假設 | 根據哪個 evidence，相信哪一格是主因？ |
| 本輪只改 | Prompt、schema、欄位、working copy、check 等哪一項？ |
| 明確不改 | 不加權限、不接外部資料、不改正本、不部署等 |
| 預期差異 | 同一條 reproduce path 修後應看到甚麼？ |
| 回退點 | 不通過時丟哪個副本、回哪個版本？ |

若 patch 需要越過既有 scope，例如讀敏感資料、改 CRM、外發或部署，先停在 approval，不要把「修 bug」變成未批准的擴權。

## Verify 為甚麼要走回同一條證據路徑，才算真正比較到修正前後？

修正後用不同 input、不同畫面或不同 checklist 做驗證，很容易得到一個看似好的結果，卻無法證明原本問題被解決。例如原本某個 sample 會令欄位缺失，修完後你只用一個乾淨 sample 測試；或原本內容因來源不足出錯，修完後你只看語氣變順。這些可能證明別的事情，但不能回答「同一個 X／Y 差異有沒有消失」。

走回同一條 path 的意思是：用相同前提、相同步驟、相同 acceptance／check，再讀回相同 artifact 類型。你可以額外測別的 scenario，但那應被清楚列作另外的 evidence。這讓 AI 修正不再靠感覺，而是可以被人比較、被下一輪回歸測試重用。

**Jimmy 的結論：** Verify 不是再看一次結果，而是用同一把尺比較修改前後。只有同一路徑，才能證明這次 patch 對應到原本問題，而不是剛好在另一個情境看起來沒事。

可按這個順序 verify：

1. 重用原本的 input／sample／狀態。
2. 重走同一組步驟和 action。
3. 檢查同一個預期 X 和實際 Y 是否已對齊。
4. 對照本輪 patch 是否只改了已聲明範圍。
5. 記錄結果：pass、partial pass、revise、needs input、failed safe。
6. 如需新 scenario，另開一條 evidence，不把它偽裝成原問題已解。

當一條 check 反覆用來驗證同一類問題，才值得把它收進 [最小 regression pack](4-10-minimum-regression-pack.md)。

## Evidence report 應該點樣寫，才不會將本機驗證誤講成已上線或已交付？

驗收完成後，最危險的溝通不是說「還有 unknown」，而是把範圍講大了：本機 preview 通過被說成已 deploy、draft 生成被說成已發佈、API response 被說成已寫 CRM、reviewer 看過被說成客戶已收到。這些事件各有不同 owner 和證據；混在一句「done」裏，團隊便很容易在錯誤假設下繼續下一步。

一份好 evidence report 不必很長，但要清楚分開已驗、未驗、未做 action 和 owner decision。它讓下一位知道本輪到底交付了甚麼，也保護 AI workflow 不會因為過度宣稱而被要求承擔未被設計的責任。這同樣適用於公開指南、內部工具、內容 draft 和 integration 測試。

**Jimmy 的結論：** 報告 verification 範圍不是保守措辭，而是工作本身的一部分。能講清「這次證明了甚麼、未證明甚麼、下一步誰決定」的團隊，才真的能安全擴大 AI 使用。

一份 receipt 可以只有這六項：

| 欄位 | 要寫甚麼 |
| --- | --- |
| Reproduce path | 原本怎樣重現問題，X 和 Y 是甚麼 |
| Inspected evidence | 看了哪些最小資料／artifact |
| Patch scope | 本輪改了、沒改甚麼 |
| Verify result | 同一路徑重跑後 pass／partial／fail 的 evidence |
| Out of scope | 未測的系統、外部 action、資料範圍、情境 |
| Owner + next action | 誰採用、退回、擴大、部署或停止 |

例如「local sample 的 heading、form schema 和 error state 已用指定 scenario 驗證；未測外發、真實資料寫入和 live publish；本輪僅是驗收 report，未構成上線批准」就是完整而有用的結論。

## 用一個本機公開資訊頁 draft 跑 evidence loop，完整過程會怎樣發生？

假設 AI 在一個 local working copy 做了一頁公開資訊頁 draft。Reviewer 發現指定情境下表單欄位沒有正確顯示 error state。這個例子適合 evidence loop，因為它可以用 sample input 重現、改動可留在本機 working copy、驗收只針對指定 UI／schema，不需接客戶資料、真實寫入或 live publish。

先寫 reproduce：用 sample input S，按步驟 A → B，預期 error message X，實際沒有顯示 Y。再 inspect 指定欄位 schema 和 render state，而不是把整個 app 資料都交給 AI。Patch 只在 working copy 加上所需 validation／render rule；verify 時再用 sample S 走 A → B，確認 X 出現，同時檢查其他既有欄位未被改。最後列出 live publish、外發、真實資料寫入仍未驗。

**Jimmy 的結論：** Evidence loop 的力量不在於這是一個 UI 問題，而在於任何人都能看見「原本問題 → 最小證據 → 受控改動 → 同路徑驗證 → 範圍清楚的 report」這條因果鏈。

| 階段 | 本輪做甚麼 | 留下甚麼 |
| --- | --- | --- |
| Reproduce | 用 sample S 重走 A → B，記 X／Y | 可重跑 scenario |
| Inspect | 只看 schema、欄位和 render state | 最小相關 evidence |
| Patch | 在 working copy 補 validation rule | Diff／變更預覽 |
| Verify | 用同一 sample／步驟讀回 X | Pass／fail check 結果 |
| Report | 列已驗、未驗、未做 action、owner | Evidence receipt |

跑完後，這個 receipt 不但能讓 reviewer 收貨，也能在同類問題再次出現時成為回歸檢查的起點。

## 想建立第一個 evidence loop，最安全的開始是甚麼？

選一個最近「看起來完成」但你其實不太肯定的低風險 output：一個本機 draft、一張 sample 資料表、一份 internal brief 或一個受控 UI change。不要從 production、客戶資料、付款或已發布內容開始。目標不是證明所有東西都對，而是學會將一個具體 X／Y 差異變成可重跑的驗證路徑。

第一輪只需要寫預期、實際、最小 evidence、單一 patch、同路徑 verify 和未驗範圍。跑幾次後，你會開始分辨哪些 check 值得收進 regression pack、哪些問題其實是 brief／source／owner 未清、哪些 output 不能因為有 screenshot 就被標 completed。這才是 AI Builder 能把「做了」變成「證明了」的能力。

**Jimmy 的結論：** 第一個 evidence loop 的成功，不是交出最漂亮 report，而是下一次任何人都能沿同一條路徑看見修正前後差甚麼，並知道這次結果不能被誤說成甚麼。

可以跟這六步開始：

1. 挑一個 local／sample／internal draft 的具體問題，不接 production。
2. 寫下 input、步驟、預期 X、實際 Y。
3. 只 inspect 能解釋 X／Y 的最小 evidence，守住資料範圍。
4. 在 working copy 只改一個假設，不順手擴大 scope。
5. 用完全同一條 path verify，記 pass／partial／fail。
6. 留 evidence receipt，清楚列未驗、未做 action 與下一位 owner。

暫時不要把 screenshot、綠色 test 或「已完成」訊息當成所有事情的證明；不要為了 debug 擴大到整個 vault、CRM 或敏感資料；也不要把本機驗證說成已部署、已發佈或已交付。若你想把同一類檢查變成每次都跑的回歸保護，可讀 [最小 regression pack](4-10-minimum-regression-pack.md)；需要寫清改動前提時，讀 [Build 前先寫 assumption ledger](4-35-assumption-ledger-before-build.md)。

← [返回 AI Builder](../04-ai-builder.md) · [按問題瀏覽](../BROWSE.md)
