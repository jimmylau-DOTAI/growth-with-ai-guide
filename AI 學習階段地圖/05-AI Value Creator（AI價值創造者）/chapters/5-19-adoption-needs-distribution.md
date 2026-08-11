# 做好 AI workflow 不等於團隊會用：AI adoption 要被設計、帶過線和回看

一條 AI workflow 可以設計得很好：有 prompt、有資料、有 automation，甚至在 demo 裡跑得很順。但把連結交給團隊後，很多人仍照舊做。有人根本不知道它存在；有人不知道哪一件工作才適合用；有人怕 output 錯了最後責任落在自己；也有人試過一次，見不到好處便不再回來。

問題不一定是同事「抗拒 AI」。當新做法沒有清楚入口、安全例子、完成線和求助位置，對使用者而言，照舊做通常比冒風險學一條未知流程更合理。只再加一場工具分享，未必能解決這些工作摩擦；它可能令大家知道更多功能，卻仍不知何時可以放心開始。

Jimmy 的看法是：AI adoption 不是 deployment 完成後才做的推廣工作，而是 workflow 設計的一部分。要讓第一批人看見、能用安全材料跑一次、知道怎樣收貨、遇到例外有人幫，然後用真實使用 evidence 決定流程、教學還是範圍應該怎樣改。

AI adoption · rollout · AI workflow · employee enablement · pilot · safe outcome · human review · distribution

| Adoption 要過的一格 | 使用者正在問甚麼 | 留下甚麼 |
|---|---|---|
| 明確入口 | 哪一件工作應由這裡開始？ | use-case trigger |
| 安全示範 | 第一輪用甚麼材料、怎樣跑？ | synthetic／approved example |
| 完成線 | output 怎樣才可交給人？ | artifact 與 acceptance rule |
| 求助與例外 | 卡住、資料不足、結果怪時找誰？ | owner 與 escalation |
| 回看 evidence | 有沒有少重做、哪裡停下？ | usage／rework receipt |
| 下一輪 decision | 改流程、改教學、擴大或停止？ | adoption decision |

## 團隊有 AI workflow 點解仍然不用：問題通常不是「抗拒改變」

當有人不用新方法，很容易把原因概括成「他不想改」。但使用者實際面對的往往更具體：他不知道現在手上哪一件工作適合套入；沒有可安全練習的材料；不知道 AI 讀了甚麼；output 出錯後要不要自己負責；或用了之後仍要花更多時間整理和解釋。這些都是合理的工作風險，不是性格問題。

若管理者只用「大家多試」或再辦一場 tool training 回應，會錯過真正卡位。初學者可能連第一個安全 outcome 也未跑過；熟手則可能需要的是 review rule、handoff 或例外處理。把不同 stage 的人放進同一個 agent 教學，通常令新手更害怕、已開始做的人又覺得沒有幫助。

**Jimmy 的結論：** 不採用不等於不願意。先找出使用者卡在入口、能力、信心、review 還是流程價值，才知道應該改 adoption design 還是改 workflow 本身。

| 表面現象 | 可能的真正卡位 | 下一個合理動作 |
|---|---|---|
| 「我不知道怎樣用」 | 不知哪個真工作適合開始 | 給一個 use-case trigger |
| 「我怕出錯」 | 沒有 review／stop line | 用 draft-only 安全例子示範 |
| 「試過但沒用」 | output 未對準 workflow purpose | 回看 artifact 與 rework |
| 「太麻煩」 | 新增 cleanup 多於減少工作 | 縮小 AI 範圍 |
| 「不關我事」 | 沒看見 owner 或自身好處 | 用角色相關的小 pilot |

下次有人說「團隊不用 AI」，不要立刻加工具。先問他最近哪一件工作曾想試、又在哪一格停下，答案通常比滿意度調查更有用。

## AI adoption 第一批人點樣帶過線：不是大 rollout，而是一個最小 adoption bundle

第一輪不需要起龐大 academy、寫完整 AI policy 或向所有人宣布轉型。對一條低風險 workflow 而言，一個最小 adoption bundle 已足夠讓使用者由「知道有這件事」走到「自己完成過一次」。它包括一個明確入口、一個安全例子、一張完成線、一個求助位置和一次約定回看。

這幾件小東西的作用不同：入口幫人判斷何時用；例子把抽象能力變成可跟的動作；完成線防止把 draft 當完工；求助位置避免例外悄悄變成人的負擔；回看則把一次嘗試變成流程學習。少任何一格，使用者都很容易回到自己摸索或放棄。

**Jimmy 的結論：** Adoption 的最小單位不是一次課堂或一個帳戶，而是一個人能安全完成一件真工作、知道結果交給誰、也知道下次如何再做的小循環。

| Bundle 格 | 你要提供甚麼 | 使用者完成後知道甚麼 |
|---|---|---|
| 入口 | 「當你要＿＿＿時，從這裡開始」 | 何時值得使用 workflow |
| 安全例子 | approved／synthetic input 到 review 的 run | AI 做了甚麼、沒做甚麼 |
| 完成線 | 一張可交的 artifact 標準 | 何時不是只停在聊天 output |
| 求助位置 | named owner 或 issue channel | 例外怎樣升級，不用硬猜 |
| 回看 | 一週後的 short review | 哪一格卡住，是否值得再跑 |

第一批最好不是隨機挑最熱心的人，而是挑最接近該 workflow 的 3–5 位使用者。他們的問題最能告訴你流程是否真的貼近工作，而不是只在 demo 裡好看。

## AI training 點解未必帶來 adoption：課堂要接回真工作、材料與完成線

工具介紹可以讓人知道 AI 有甚麼可能，但它未必能令使用者在星期二下午面對一份真工作時知道怎樣開始。若課堂用的是泛用 prompt、沒有自己的工作材料、也沒有 output 如何交接的標準，學員回到崗位後很快忘記。這不是因為他學得不夠努力，而是 learning 沒有接到 daily workflow。

較有效的做法是由真工作出發：讓學員帶一件低風險、可公開或 approved 的材料；一起把它切成 AI 可以先處理的一手；產出一份可 review artifact；最後由 owner 或同儕對照完成線。這會令 training 不只是「知道模型能做甚麼」，而是第一次演練如何安全地用它完成自己的工作。

**Jimmy 的結論：** AI training 的完成線不是學員聽完工具功能，而是他能用安全材料做出一份可 review 的工作成果，並知道下一次怎樣開始。

| 只講工具的 training | 接真工作的 training | 留下甚麼 |
|---|---|---|
| 示範很多功能 | 選一條使用者真 workflow | use-case decision |
| 用泛用 prompt | 用 approved／synthetic 材料 | context boundary |
| 看一次漂亮 output | 交一份可 review artifact | draft、card、checklist |
| 講「要小心」 | 演練 review 與 unknown | stop line |
| 課後自行摸索 | 約定一次回看 | adoption evidence |

若你仍未有適合的真材料，不要急著接敏感資料進去。先用 synthetic 情境把完整循環跑通，讓使用者先學會分工與 review，再逐步擴大。

## 不同 AI stage 的人點樣有不同入口：stage 是導航，不是考牌

AI User 可能仍在學怎樣把 context 給足、把 output 變成自己的工作；AI Super User 已開始比較工具、留下 context 與 feedback；AI Operator 需要處理重複流程、狀態和例外；AI Builder 需要設計 guardrail 與驗收；AI Value Creator 則要帶人跑 pilot、判斷值不值得擴大。這些不是高低身份，而是使用者在同一條工作路上卡的位置不同。

若把每個人都當作準備建 Agent 的人，會跳過最重要的採用基礎。相反，先從他正在做的一件工作診斷下一小步：初學者先完成一個安全小成果；熟手先把常用做法變成可交接 routine；owner 則先看 evidence 和治理。Stage 讓教學與 distribution 有正確入口，而不是把人困在標籤裡。

**Jimmy 的結論：** 不同 stage 需要不同下一步。Adoption 成功不是所有人學同一堆功能，而是每個人都能向自己的下一個可驗收工作移動。

| 使用者現在的情況 | 不要逼他做甚麼 | 較好的下一步 |
|---|---|---|
| 剛開始用 AI | 直接建 agent 或 automation | 完成一件有 context 的小工作 |
| 已熟 prompt | 永遠停在聊天視窗 | 留下 reusable context 與 feedback |
| 常做重複工作 | 只再學更多 tool | 定 routine、artifact、review |
| 想 build workflow | 直接接高風險 action | 先做 draft-only guardrail |
| 負責團隊／決定 | 只看工具 demo | 用 pilot evidence 判斷 scale／stop |

如果你不確定對方在哪個 stage，不用叫他填很長問卷。請他展示最近一次用 AI 做的真工作，再看他缺的是 context、交接、review 還是 outcome judgment。

## AI adoption 要量度甚麼：不要量「興趣」，要看有沒有完成與重複使用

「大家很有興趣」「很多人來了課堂」「每個人都有帳戶」都可能是真的，但不等於 adoption 已發生。真正要知道的是：有多少人用自己的工作完成第一個安全 outcome？他們在哪一格停止？哪一個 template、案例或 review rule 令 rework 少了？同一條 workflow 有沒有被第二次、第三次自發使用？

這些數字不是為了監控員工或製造排名，而是幫 team 判斷下一輪應改哪裡。若多人在 input 卡住，要補材料界線；若多人在 review 卡住，要補 acceptance rule；若用了但沒有減少重做，也許 workflow 本身不值得推。沒有這種 evidence，launch 再漂亮也只是一次活動。

**Jimmy 的結論：** Adoption evidence 不是 account 數或興趣，而是人有沒有把一條 workflow 用到可收貨，並在下一次願意再用。量度應服務改善，不是服務監控。

| 只看甚麼 | 為何不足 | 較有用的 adoption evidence |
|---|---|---|
| Account 開通數 | access 不等於使用 | completed safe outcome |
| 課堂出席率 | 聽過不等於會做 | first workflow run |
| 正面 feedback | 沒有說明卡點 | stop／rework category |
| Output 數量 | 多不等於可用 | owner accepted artifact |
| 一次 launch | 未知是否持續 | second／third voluntary use |

回看時請使用者用工作語言描述，而不是問「你喜不喜歡 AI」。問他哪一手少了、哪一手變多了、下次敢不敢自己再跑，答案會更接近真實 adoption。

## 一個公開安全例子：用五格 bundle 讓第一批人開始 internal briefing workflow

假設一個小團隊希望改善每週公開來源的 internal briefing。第一輪找四位本來就要整理資料的同事，不宣稱要全公司 rollout。入口寫成「當你要把 approved sources 變成 internal update 時，用這張 work card」；例子用公開資料跑一次；完成線是一份有 source link、unknown 標記和 owner review 的 brief。

遇到例外時，同事可以把問題留在指定位置，不必自行把敏感資料交給 AI 或強行完成。每週回看四件事：是否完成了一份可 review brief、最常卡在 input／format／review 哪裡、重做有否減少、以及哪位 owner 願意第二次使用。三次後才決定要改 bundle、改 workflow 或小範圍擴大。

**Jimmy 的結論：** 這不是把 AI 傳給更多人，而是設計一條讓第一批人安全學會、留下 evidence 的 adoption 路。Distribution 由此開始有價值。

| Bundle 格 | 例子怎樣做 | 邊界 |
|---|---|---|
| 入口 | 有 approved sources 才用 work card | 不處理私人資料 |
| 例子 | 公開來源 → internal draft | 不自行對外發送 |
| 完成線 | source／unknown／owner review 齊 | 不把 draft 當最終事實 |
| 求助 | named owner 收集例外 | 不靠同事私下救火 |
| 回看 | completion、卡點、rework、repeat use | 不用來評分員工 |

這是 synthetic 教學情境，不代表任何特定團隊已取得相同成效。它要展示的是 adoption 如何與 workflow、review 和 evidence 一起設計。

## 今日怎樣開始設計 adoption：找最接近工作的人，跑一次完整小循環

如果你已經有一條值得試的 workflow，暫時不要問「怎樣全公司 rollout」。先找 3–5 位最接近該工作的人，為他們準備一個安全案例、一張完成線、一位能回應例外的 owner，以及一次一週後回看。這已經足夠讓你看見 adoption 的真資料。

若目前沒有完整 workflow，也可以先由一件小工作開始：讓人用 approved／synthetic input 產出一份 internal draft，再練習對照完成線 review。不要跳過這層，直接把 production、外發或高風險 action 交給新手。可重複的小安全成果，比一次全公司宣佈更能建立習慣。

**Jimmy 的結論：** AI adoption 的第一步是讓最接近真工作的人，安全地完成一次、被人看見一次、再願意做第二次。這比「全面推廣」更接近真正的價值。

| 本週可做的事 | 完成訊號 | 未準備好時怎樣縮小 |
|---|---|---|
| 選 3–5 位最接近 workflow 的人 | 有真工作使用者 | 先找一個 owner 與 routine |
| 寫一個 use-case trigger | 大家知道何時開始 | 不要只發工具連結 |
| 跑一個安全例子 | 有可 review artifact | 先用 public／synthetic input |
| 定完成線與求助位置 | 例外有人處理 | 不要要求同事硬猜 |
| 一週後回看 | 有卡點與 repeat-use evidence | 決定 revise、stop 或下一輪 |

完成第一輪後，可讀 [第一個安全成果](./5-10-first-safe-outcome.md) 來設計新手的完成線；如果你要用真工作診斷每個人的下一步，讀 [由真工作診斷 AI stage](./5-12-diagnose-stage-from-work.md)。

> 一個工具被開通，只代表 access；一個做法被人重複採用，才代表它開始創造價值。

← [返回 AI Value Creator](../README.md) · [按問題瀏覽](../../../README.md)
