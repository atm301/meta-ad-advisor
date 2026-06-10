# 5 步建立你的專屬 GPTs 建議器

封裝成 GPTs 後，每天打開直接貼資料，不必每次重貼 Prompt。決策時間從 1–2 小時壓縮到 5–10 分鐘。

> 需要 ChatGPT Plus（GPTs 建立功能）。沒有 Plus 也沒關係——直接用 [`../prompts/`](../prompts/) 的兩段 Prompt 手動貼也能跑。

---

## 步驟

| # | 動作 | 怎麼做 |
|---|---|---|
| 1 | 建立新的 GPT | ChatGPT → 左側「探索 GPT」→ 右上「建立」→ 切到「設定（Configure）」分頁 |
| 2 | 貼入 Instructions | 把 [`gpts-instructions.md`](gpts-instructions.md) 的整段程式碼框內容，貼到「Instructions」欄位 |
| 3 | 上傳知識庫 | 在「Knowledge」上傳 `four-layer-method.md`、`benchmarks.md`，以及**你自己填好的** `my-standards-template.md`。AI 會越用越懂你的帳戶 |
| 4 | 設定對話起始句 | 把 [`conversation-starters.md`](conversation-starters.md) 的 4 句填到「Conversation starters」，幫使用者快速上手 |
| 5 | 試跑驗收 | 用 [`../examples/sample-ads-7days.csv`](../examples/sample-ads-7days.csv) 跑一次，比對 [`../examples/sample-output.md`](../examples/sample-output.md)，確認輸出格式對了再分享給團隊 |

---

## 封裝後的 4 個好處

1. **一次設定**：System + User Prompt 鎖進建議器，打開直接用，省下每次設定的 5 分鐘。
2. **知識庫累積**：把產業特性、歷史成效塞進知識庫當背景，AI 越用越懂你的帳戶。
3. **標準化輸入**：固定資料格式，避免每次格式不一造成輸出不穩。
4. **可複製給團隊**：驗收 OK 後分享連結，全隊用同一套判斷標準。

---

## 投手的新工作流：5 分鐘決策日常

| 時間 | 動作 |
|---|---|
| 9:00 | 用 7 天篩選，從廣告後台匯出當日報表 CSV |
| 9:02 | 打開你的 GPT 建議器，貼上 CSV 內容，送出 |
| 9:03 | AI 給的行動清單按優先級從上往下看 |
| 9:04 | 依清單一行一行勾，沒共識的標問號等下午再看 |
| 9:05 | 進廣告後台依建議調整預算、暫停或加碼 |

> 原本花 1–2 小時做的決策，壓成 5 分鐘的標準流程。

---

## 其他封裝路徑

- **Claude Project**：在 Claude 建一個 Project，把 Instructions 放進 Project 的「Custom Instructions」，知識庫檔案上傳到 Project Knowledge。用法與 GPTs 幾乎相同。
- **Gemini Gem**：Gemini 的「Gems」也能貼 Instructions + 上傳檔案，邏輯相同。
- **不想封裝**：每次手動貼 [`../prompts/system-prompt.md`](../prompts/system-prompt.md) + [`../prompts/user-prompt-template.md`](../prompts/user-prompt-template.md)，一樣有效，只是每次多花 1 分鐘。
