# AI Coding 愈快，人愈要識砍 scope 同驗收

AI 可以很快幫你起一個網站、做一個小工具、加一個功能。這種速度很容易令人誤會：以前做不出，是因為不懂技術；現在做得出，就代表問題已經解決。

其實 AI coding 把最大的樽頸推回人身上：你是否說得清楚要解決甚麼、今次不做甚麼，以及怎樣才算真的完成？

Jimmy 的判斷是：AI coding 的速度不會代替 product judgment。先把需求砍成一個可驗收切片，寫清 scope、不可改部分、check 和回退點，AI 才能幫你把畫面變成可 review 的工作，而不是更快地造出錯的東西。

| Build 格 | 要回答甚麼 | 留下甚麼 |
|---|---|---|
| Problem／scope | 誰在哪裡卡住、今次只解甚麼 | 最小價值切片 |
| Boundary／plan | 哪些檔案、資料、功能不可碰 | 可批准的改動範圍 |
| Acceptance／rollback | 怎樣驗收、錯了怎樣回退 | evidence 與安全出口 |

> **AI 可以把模糊想法更快變成畫面；但只有清楚的 scope 和 acceptance，才可以把畫面變成可交付的產品。**

## 「簡單、方便、好用」不是 requirement

人講需求時很常說：想整得簡單一點、好用一點、有一個 dashboard。這些方向沒有錯，但它們不是 AI 可以直接驗收的工作。

一個可 build 的要求要再走一步：誰在哪個情況遇到甚麼問題？做完之後他能完成哪個動作？今次故意不做甚麼？如果這些仍然未定，AI 只會很有效率地替你猜一個版本。

例如你想做一個簡單的工作追蹤頁。與其說「整個 dashboard」，不如先說：

```text
使用者：一位每週要回看工作的人
這次要做到：看見三個進行中的工作及其下一步
資料來源：一份指定的本機 sample data
不做：登入、多人協作、外部同步、通知
完成條件：能新增、更新、重新開啟資料後仍看見同一狀態
```

這不是令創意變少，而是讓第一版有一條可以判斷的完成線。

**Jimmy 的結論：** 「簡單、好用」只是方向；可 build requirement 必須寫出使用者、動作、資料、明確不做和可驗收完成線。

## Plan 不是拖慢 AI 的程序

當 AI 很快能開始寫，你更需要一個小 plan gate：先說明它理解了甚麼、會碰哪些檔案、預計改哪一層、怎樣驗收。這不是要你看每一行 code；而是讓你在改動發生前，仍然有機會發現範圍被誤解。

好的 plan 應回答：

- 這次只解甚麼問題？
- 哪些東西明確不碰？
- 先做哪一個最小切片？
- 完成後用甚麼方法檢查？
- 如果結果不對，怎樣回到上一個可用狀態？

若這些答不到，就不應讓速度代替判斷。

**Jimmy 的結論：** Plan gate 不是拖慢 AI，而是在改動發生前確認 scope、最小切片、check 和 rollback 沒有被模型自行猜走。

## 第一版不是縮水版，是可學習版

MVP 的意思不是隨便少做一些功能。它是保留最小但完整的價值切片：有人真的能用它完成一件原本做不到或很麻煩的事，而你能從他的使用中學到下一步。

所以砍 scope 時，不只是刪功能。你要說清楚：今次不做甚麼、為甚麼不做、甚麼 evidence 出現後才值得再做。這條界線讓 AI 和團隊都不會把每個新想法偷偷塞進第一版。

> **真正的 AI Builder，不是最快叫 AI 造出功能的人；是能把一個問題砍到可驗收，又知道下一次應根據甚麼擴大的那個人。**

**Jimmy 的結論：** MVP 不是縮水版；它是一個可學習、可驗收的完整價值切片，未有 evidence 前不把新想法偷偷塞進第一版。

| 想加的東西 | 第一版怎樣處理 | 何時才回來考慮 |
|---|---|---|
| 登入／多人協作 | 明確不做 | 單人切片已被真使用者驗收 |
| 外部同步／通知 | 保留人手動作 | 有清楚 trigger、owner、失敗處理 |
| 更多 dashboard 功能 | 只留最初要完成的動作 | evidence 顯示原切片仍不足 |

## Build 完，仍然不等於畢業

畫面出來、網站 deploy 了、程式跑得起，都只是新的 feedback 開始。你仍要分開看：它有沒有解決最初的問題？資料是否真的安全保留？錯誤會不會被看見？使用者是否知道下一步？

先讓一個小切片跑通，再根據真實 feedback 改第二格，比一開始把所有功能交給 AI 更快走到可用結果。

**Jimmy 的結論：** Build 完只是 feedback 的開始；只有用原本問題、資料安全、可見錯誤和使用者下一步驗收，才知道這一版是否值得擴大。

| Build 後要問 | 可見 evidence |
|---|---|
| 有沒有解決原始使用者動作？ | 走一次指定 scenario 的 read-back |
| 資料和變更是否在 scope 內？ | changed-file／data-boundary review |
| 錯誤有沒有被看見？ | check output、known limitation、receipt |
| 值不值得加第二格？ | reviewer／使用者的具體 feedback |

想先把一個工作寫成清楚範圍，讀：[workbench contract](./4-19-workbench-contract.md)。想在真正 build 前檢查是否準備好，讀：[五個 build gate](./4-12-ready-to-build.md)。

---

## 下一步

第一步只在可回退 workspace／公開或 synthetic sample data 做一個最小切片；先 review plan，再改，最後用 acceptance test 和 receipt 收貨，不 deploy、不接 production、不擴到其他功能。

**Jimmy 的結論：** 第一版的完成線是證明一個切片可用並留下下一輪 evidence，不是讓 Codex 一次改大半個 project。

| 第一輪 | 要交甚麼 | 不可做甚麼 |
|---|---|---|
| Sample-data work card | scope、plan、diff、check、rollback | production deploy、敏感資料、未批准擴 scope |

留低一個最小 scope、不可改部分、驗收 test 和回退點。暫時不要讓 Codex 一次改大半個 project；先讀 [minimum regression pack](./4-10-minimum-regression-pack.md)。

← [返回 AI Builder](../README.md) · [按問題瀏覽](../../../學習地圖.md)
