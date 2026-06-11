# Meta 廣告預算優化師 · AI 建議器 Prompt 包

> 把資深投手的判斷力，變成你的決策外掛。
> 一套「四層判斷法」提示詞，套上你自己的 7 天廣告數據，5 分鐘跑出可執行的加碼／減碼／關閉清單。

這份 repo 把 [圭話行銷](https://atmarketing.tw) 課程《AI 廣告預算優化師》的核心方法封裝成**可直接複製的提示詞包**。不需要寫程式、不需要 API key，貼進 ChatGPT、Gemini、Claude 或自建 GPTs 就能用。

---

## 為什麼需要它？

每天上午報表整理完，ROAS 下降，但你不知道是受眾、素材還是版位的問題。主管問下一步，你想了 30 分鐘最後只能說「再觀察看看」。

問題不是你不會看報表，是**沒有一套可重複的判斷框架**。

| 沒框架的提問 | 有框架的提問 |
|---|---|
| 「這份數據看起來如何？」 | 「依四層判斷法分析這份數據」 |
| AI 回 5 段抽象觀察 | 結構→表現→趨勢→決策，逐層拆解 |
| 「ROAS 還算穩定，可以繼續觀察」 | 「受眾 A 減碼 30%、受眾 B 加 25%」 |
| 每段都有道理，但沒一句能執行 | 每條建議都有依據和預估影響 |

---

## 四層判斷法

```
第 1 層 結構層   →  錢分得對不對？（受眾／素材／版位佔比）
第 2 層 表現層   →  哪些指標偏離健康區間？（CTR / CVR / CPA / ROAS）
第 3 層 趨勢層   →  3／7／14 天訊號是否同向？
第 4 層 決策層   →  哪組加、哪組減、哪組關？
```

完整說明見 [`framework/four-layer-method.md`](framework/four-layer-method.md)。

---

## 30 秒上手

1. 複製 [`prompts/system-prompt.md`](prompts/system-prompt.md) 全文，貼到 ChatGPT／Claude／Gemini 對話開頭。
2. 複製 [`prompts/user-prompt-template.md`](prompts/user-prompt-template.md)，把你自己的 7 天廣告 CSV 填進去，送出。
3. 收 AI 回的行動清單，從高優先級往下執行。

想要每天打開就能用、不必每次重貼？把提示詞封裝成 GPTs → 見 [`gpts/gpts-setup-guide.md`](gpts/gpts-setup-guide.md)。

---

## 資料怎麼準備

從 Meta 廣告管理員「廣告報告」匯出 CSV，**以廣告組合為單位**，區間選近 7–30 天。只留這 8 個基本欄位（少即是多，欄位太多 AI 反而給廢話）：

| 欄位 | 說明 |
|---|---|
| 活動名稱 | 識別哪組廣告 |
| 花費 | 本期投了多少錢 |
| 曝光 | 被顯示的總次數 |
| 點擊 | 引起多少興趣 |
| 轉換 | 帶來購買或名單的次數 |
| 轉換金額 | 創造多少收入 |
| 目標客群 | 受眾設定 |
| 版位 | 動態消息／Story／Reels |

CTR、CVR、CPA、ROAS 不必自己算，AI 會幫你算。範例資料見 [`examples/`](examples/)。

---

## 檔案結構

```
meta-ad-advisor/
├── framework/
│   ├── four-layer-method.md        # 四層判斷法完整說明（含健康區間與決策準則）
│   ├── benchmarks.md               # Meta 廣告指標基準（台灣實務值 + 全球中位數）
│   └── related-projects.md         # 同類專案地圖：本 repo 在生態系的位置與升級路徑
├── prompts/
│   ├── system-prompt.md            # 資深投手 System Prompt（直接複製就跑）
│   ├── user-prompt-template.md     # User Prompt 四段資料模板
│   └── my-standards-template.md    # 我的標準範本（先填一次，之後沿用）
├── gpts/
│   ├── gpts-instructions.md        # GPTs Instructions 完整版
│   ├── gpts-setup-guide.md         # 5 步建立你的專屬 GPTs
│   └── conversation-starters.md    # GPTs 對話起始句範例
├── examples/
│   ├── sample-ads-7days.csv        # 範例 7 天廣告數據（25 組廣告）
│   ├── sample-ads-14days-trend.csv # 範例 14 天逐日趨勢
│   └── sample-output.md            # 套範例資料跑出來的行動清單長相
├── LICENSE
└── README.md
```

---

## ⚠️ 使用前先認清界線

AI 是加速器，不是自動駕駛。判斷權留在你手上：

- **AI 會編造數據（幻覺）** → 任何結論回原始報表逐筆核對。
- **資料隱私** → 廣告 CSV 含客戶與營收資訊，上傳前用代號取代品牌／客戶名，只餵分析所需欄位。
- **短期波動造成誤判** → 單日假訊號需用 3／7／14 天多週期交叉驗證。
- **AI 給方向，人做決策** → 最終加碼／減碼／關閉由你拍板，負最終成敗。

---

## 延伸學習

- **想看同類工具？** [`framework/related-projects.md`](framework/related-projects.md) 整理了 GitHub 上的 Meta 廣告 AI 專案（分析 skill、接 API 的 MCP server、行銷組合模型 MMM），並畫出從本 repo 入門到專家級的升級路徑。
- 課程《AI 廣告預算優化師》與《廣告五門 × 四大受眾》補充教材：[atmtut.com/廣告五門](https://atmtut.com)
- 圭話行銷：https://atmarketing.tw

## 授權

[MIT](LICENSE) — 自由使用、修改、散布。歡迎 fork 改成你自己的版本。
