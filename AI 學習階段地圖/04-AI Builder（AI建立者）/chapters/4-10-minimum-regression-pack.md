# AI workflow 每次一改就怕另一格壞？先把三至五個重複錯變成 minimum regression pack

每次改 prompt、換模型、加一個資料欄、調整 template 或改 workflow，AI output 可能在眼前變好，卻令另一種常見情況悄悄退步。於是你每次都要由頭逐格看：來源有沒有丟、格式有沒有壞、連結有沒有斷、未知有沒有被改成肯定句。這種人手檢查很累，也很難在忙碌時保持一致。

另一個極端是想一次過把所有人的判斷變成一個 AI score 或龐大測試系統。這同樣不實際：很多高價值問題仍需要語境、品牌、專業或責任判斷；一開始追求百分百覆蓋，通常只會產生一堆沒人維護的 checks，而沒有守住真正令你返工的錯。

Jimmy 的判斷是：regression pack 的作用不是移走人，而是把人每次都在捉、又能客觀檢查的高頻錯，變成下次改動也會重跑的驗收記憶。從三至五條真實 failure 開始，分清 hard check、reviewer flag 和 human-only decision；每次改動前後用同一組 fixed case 跑，讓已知品質不會因新改動默默倒退。

| Pack 的一格 | 它要解的問題 | 留下甚麼 |
| --- | --- | --- |
| Failure log | 靠記憶猜甚麼常壞 | 真實重複錯與工作情境 |
| Acceptance rule | 「感覺不對」無法重跑 | 一句可驗證的 pass／fail 條件 |
| Fixed case | 每次用不同 input，結果無法比較 | 公開／synthetic sample 和預期結果 |
| Check route | 所有問題都假裝可自動判斷 | Hard check、reviewer flag、human-only 分工 |
| Run receipt | 改完只記得「好像 OK」 | pass／fail／unknown、scope、owner decision |

## AI workflow 每次一改就怕別處壞，為甚麼不能只靠最後人手看一眼？

最後人手看一眼當然有用，但它容易被時間、疲勞和注意力影響。當 workflow 愈來愈多，reviewer 可能記得這次要看新功能，卻忘了上次曾經被退回的欄位、斷 link 或缺 source。這些小錯未必每次都嚴重，但重覆出現便會吞噬大量返工時間，也令大家不敢相信改動後的 output。

更重要的是，沒有固定 check 時你無法知道新改動是否真的改善。你可能今次看見語氣較好，卻沒發現原本每個 claim 都有來源的規則被破壞；或修了 UI error state，卻不小心令另一個固定 scenario 壞掉。人仍應 review，但不應每次從零記住所有可描述的舊錯。

**Jimmy 的結論：** Regression pack 的價值不是取代人眼，而是把已知、可驗證的風險變成共同記憶，讓人把注意力留給新問題、判斷問題和高責任決定。

看兩種 review 的差別：

| 沒有 regression pack | 有 minimum regression pack |
| --- | --- |
| 每次靠某人記得上次哪裡壞過 | 已知錯由固定 cases 提醒大家 |
| 改完看一看當下 output | 改前後跑同一組 acceptance |
| 所有問題都用同一種「感覺」處理 | 可規則的自動 check，判斷的留 reviewer |
| 出錯後重新研究 | Fail receipt 指向哪個規則、sample、owner |
| 新人／新 Agent 不知舊坑 | Pack 成為可交接品質記憶 |

你不需要把所有事情都測完；先守住那三至五個最常令你退回 output 的地方已經很有價值。

## Failure log 怎樣揀出最值得先守的三至五個重複錯？

第一個 regression 不是選最煩的問題，也不是選最容易寫測試的問題。它應該來自真實 failure：你已經見過它不止一次、它發生會造成返工或誤導、可以用固定 sample 或清楚規則看見、而且下次改動後有機會再出現。這些條件令 check 有實際回報，而不是一份理論上很完整、實際從不跑的清單。

相反，一次性偶發、原因未明、每次情境完全不同的問題，未必適合立刻進 pack。它們仍值得記錄，但可能應先變成 reviewer flag、assumption 或需要更多 evidence 的調查。過早把不理解的問題硬寫成 check，容易產生假安全感或阻擋合理的變化。

**Jimmy 的結論：** 第一條 regression 應由真實返工長出來。高頻、傷害高、可觀察、可重現的錯先守；其餘問題保留在人手判斷或 failure log，等待模式變清楚。

為每個候選錯打四格：

| 問題 | 高分代表甚麼 | 暫時不進 pack 的訊號 |
| --- | --- | --- |
| 發生頻率 | 每次或常常要人手捉 | 只出現一次、原因未明 |
| 傷害 | 會誤導、跨 scope、要大返工 | 只是不合個人口味 |
| 可觀察性 | 可用欄位、link、sample、rubric 看見 | 要讀心才知對不對 |
| 可重現性 | 同類 input 可穩定看到 pass／fail | 每次目標、資料完全不同 |

四格大多高的，先選三條。若只傷害高但無法客觀 check，例如敏感策略取捨，先交 named reviewer，不要假裝一個 script 可以替你承擔。

## Regression acceptance rule 怎樣寫，才不會變成「做得好」「專業啲」？

「內容要專業」、「畫面要靚」、「分析要深入」是好期望，但不是 regression rule。它們沒有說明甚麼狀況算失敗、固定 sample 跑出來應如何判斷，也沒有指定誰能在不同 run 之間用同一把尺比較。把模糊品味硬寫成 yes／no test，往往只會產生誤判或迫 output 變得僵化。

好的 acceptance rule 從反面開始：出現甚麼事情，這次就不算過關？它最好能對應一份 evidence，例如「每個具體 claim 必須有 source 或明確標 unknown」、「指定連結不可失效」、「必填欄位不可缺」、「AI 不可在 draft workflow 中觸發外發 action」。這些不等於所有品質，但它們是可重跑的品質底線。

**Jimmy 的結論：** Regression rule 不是描述理想 output，而是守住已知不可接受的失敗。規則愈清楚，AI 和 reviewer 愈能把心力留給真正需要判斷的部分。

將常見句子改寫：

| 模糊要求 | 可重跑 acceptance rule |
| --- | --- |
| 「資料要可靠」 | 每個具體事實要有指定 source，否則標 `unknown` |
| 「不要漏資料」 | Schema 中所有必填欄位均存在且非空 |
| 「不要亂改」 | Diff 只可觸及 change request 列出的 working copy 範圍 |
| 「不要太誇張」 | 未驗證成效不可用保證式語句；交 reviewer flag |
| 「不可以自動外發」 | 試跑 output 只可寫到 draft queue，不能觸發 send／publish |

若你寫不出可判斷的規則，不要強迫自動化。先把它寫成 reviewer 的問題或補充 brief／rubric。

## Hard check、reviewer flag 和 human-only decision 點樣分，才不會把所有判斷假裝成自動化？

不是所有品質問題都該用同一種 check。硬規則適合格式、必填欄、連結、範圍、數值等可以明確判定的條件；它們可以 block 或 `revise once`。有些事情雖然重要，但仍需要人看語境，例如語氣、讀者是否聽得明、某個 claim 是否容易被誤會；這些更適合變成 reviewer flag，而不是讓系統假裝已完全通過。

還有一類是 human-only decision：對外承諾、品牌立場、法律／財務／人事責任、付款、權限、客戶資料、production release。AI 可以整理 evidence、產生 draft、提示風險，但不能因為所有 automated checks 通過就自行決定。把這三類分開，才不會令「全數 pass」被誤讀成「可以做任何 action」。

**Jimmy 的結論：** Regression pack 守住的是可規則化下限，不是把所有決定交給機器。硬 check 擋已知錯，reviewer flag 提醒判斷，人類 owner 保留高責任 release。

| 類型 | 例子 | 不通過／出現時怎樣處理 |
| --- | --- | --- |
| Hard check | 缺欄、斷 link、格式錯、超範圍 | Block／`revise once`／`needs input` |
| Reviewer flag | 語氣、疑似無根據 claim、讀者理解 | Named reviewer 看 evidence、採用或退回 |
| Human-only decision | 外發、品牌承諾、付款、權限、production | `needs approval`／`human release`，不自動繼續 |

這張分工表應跟著每條 workflow 保存。新 Agent 看到它，也知道自己不是要把所有問題「解決掉」，而是要把正確問題交給正確 owner。

## Fixed regression case 怎樣設計，才可以比較改動前後而不碰真客戶資料？

同一條 regression 若每次用不同 input，就很難知道 fail 是因為改動、還是因為資料本身變了。fixed case 的角色是提供一組穩定、可安全重跑的前提：一份 synthetic sample、一組公開 URL、去識別化 test records、固定 schema 或 sample working copy。它不需要模擬所有世界，只需要讓你重現最常見、最值得先守的 failure。

對第一個 pack 而言，避免用真實客戶、CRM、付款、合約、credentials、production data 或未公開資料。這些不只是私隱／權限風險，也會令測試結果難以重跑，因為資料可能很快改變。若日後真的需要接近 production 的驗證，應另設受控環境、approval 與最小資料範圍，而不是把正本拿來當 test fixture。

**Jimmy 的結論：** Fixed case 的價值不是像真度最高，而是能在安全範圍內穩定告訴你：這個已知錯有沒有再次出現。先守住可重現的真問題，才有資格慢慢擴大。

一個 public-safe research brief pack 可有：

1. 三個指定公開 URL 或 synthetic source snippets。
2. 一份固定 input schema，包含一個缺欄／矛盾／unknown 情況。
3. 預期 artifact 的欄位：source、claim、unknown、review status。
4. 三條 hard check：link 存在、必填欄齊、未知不被補成結論。
5. 一條 reviewer flag：語氣是否把未驗證內容說得太肯定。

每次改 prompt、template 或 rule 前後都用同一包跑；若要新增 test case，另外記錄它解哪個新 failure，避免 pack 變成無目的雜物箱。

## Regression pack 每次應該幾時跑、跑完要留下甚麼 evidence？

pack 不需要在任何微小改動後都變成阻塞部署的大儀式，但它應在會影響相同 workflow 的改動前後執行：改 prompt、模型、template、schema、connector mapping、quality rule、working copy 邏輯時，都值得跑一次。若改動完全不涉及這條 workflow，無需假裝每個 test 都相關；檢查應跟 scope 走。

跑完後不要只寫「all passed」。至少記下哪個 pack、哪個 input version、甚麼改動、hard check 結果、reviewer flag、未驗範圍和 owner decision。這份 receipt 令下次發現 regression 時，可以比較哪個版本開始出問題，也讓團隊不會把自動 checks 通過誤讀成已對外發佈或已驗證全部環境。

**Jimmy 的結論：** Regression run 是一次 evidence loop：同一組 case、同一組 acceptance、清楚結果和範圍。它不只找 bug，也把「這個 workflow 曾經怎樣被守住」留下來。

一張最小 run receipt：

| 欄位 | 要留甚麼 |
| --- | --- |
| Pack + version | 哪一組 cases／rules 被跑過 |
| Change scope | 本輪改了 prompt、schema、template 還是 integration？ |
| Input fixture | 使用哪份公開／synthetic fixed case |
| Results | 每條 hard check pass／fail，flags 有甚麼 |
| Out of scope | 未測的外部系統、真實資料、release action |
| Owner decision | 誰採用、要求 revise、停止或決定下一步 |

若 hard check fail，先修最小原因再重跑；若 reviewer flag 未清，維持 draft／review 狀態；若涉及 human-only action，pack 通過亦不會取代 approval。

## 用「公開資料 → internal brief」跑一次 minimum regression pack，會怎樣發生？

假設一條 workflow 根據三篇公開資料起 internal brief。團隊曾經遇過四種重覆錯：某個具體說法沒有 source、未知被寫成肯定句、固定欄位漏失、連結有時失效。這些都適合先放進 pack，因為它們常見、傷害明顯、可用指定 sources 和 schema 檢查；語氣和策略則仍交 reviewer。

每次改 prompt 或 brief template，Agent 都用同一份 public-safe fixture 產生 draft。hard checks 檢查 source、unknown、欄位和 link；任一 fail 就不進下一格。reviewer 再看是否有誇大語氣，最後只決定是否內部採用／退回。整個 run 不會發文、寫 CRM、發 DM 或改 production，因為 regression pack 的目標是守住已知品質，不是偷步擴大 action。

**Jimmy 的結論：** 一個小 regression pack 讓你把「每次都要人手捉」變成「每次改動會主動報」，人因而可以更集中看真正需要判斷的內容。

| Rule | Case 內怎樣測 | 結果去向 |
| --- | --- | --- |
| 每個具體 claim 有 source／unknown | 固定 source 欄對照 draft | 缺失則 block／revise |
| 未驗證內容不可保證式表述 | fixture 含一個不完整 evidence case | reviewer flag／改寫 |
| 必填欄不可漏 | 固定 schema 驗證 | 缺欄則 revise once |
| Link 必須存在 | 逐個指定 URL check | 失效則 needs input／標 unknown |

跑完後留下 pack version、結果、unknown 和 owner decision。這些資料可在下一次變更時直接比較，不需靠人記住上次哪個坑最痛。

## 想建立第一個 regression pack，最安全的開始是甚麼？

不用追求全自動覆蓋，也不用從最敏感 workflow 開始。挑一條低風險、只交 internal draft 的 AI 工作，回看最近三個「每次都要人手捉」的錯。只選能寫成一句規則、能用公開／synthetic case 重現、錯了能在 draft 層收回的那幾個；其餘仍放在 reviewer flag 或 human-only decision。

第一輪可以只有三條 hard check、一份 sample、一次 run receipt。重要的是你每次改 prompt、template 或 workflow 相關部分時，真的用同一組 case 重跑，並根據結果決定 revise、review 或 stop。這比寫一份很長但從不執行的 QA 文件更能累積品質。

**Jimmy 的結論：** 第一個 regression pack 的成功，不是測得最多，而是把三個真實、重覆、可驗證的錯，從人腦變成每次改動都會提醒你的工作記憶。

可以跟這六步開始：

1. 揀一條低風險、draft-only workflow，不接客戶／production action。
2. 列最近三個重覆 failure，按頻率、傷害、可觀察、可重現篩選。
3. 將每個改成一句 pass／fail acceptance rule。
4. 用公開／synthetic input 建一份固定 case，不讀私有資料。
5. 將規則分成 hard check、reviewer flag、human-only decision。
6. 下次改 prompt／template／schema 時，跑 pack，留 receipt，再決定是否擴大。

暫時不要把品味、策略、品牌承諾或高責任決定偽裝成硬規則；不要把 test fixture 變成客戶／CRM／credentials 備份；也不要因為 pack 通過就說 workflow 已 production-ready 或可以自動外發。若你未有一條可比較的修正路徑，先讀 [AI 話做完、畫面又似樣，為何仍未算完成？](./4-9-evidence-loop.md)；要為例外寫清止步與交接，讀 [AI 一遇資料不足就繼續猜？Skill 要先寫好 exception ladder](./4-34-skill-exception-ladder.md)。

← [返回 AI Builder](../README.md) · [按問題瀏覽](../../../README.md)
