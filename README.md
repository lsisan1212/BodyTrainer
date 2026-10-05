# BodyTrainer 💪

居家健身訓練入口（portal）+ 各項單檔訓練頁。

**開站：** https://lsisan1212.github.io/BodyTrainer/

## 結構

```
index.html          # 入口主頁（portal，自動列出所有訓練）
trainings.json      # 訓練清單（標題／emoji／描述／標籤／強調色）
PlankTrainer.html   # 平板支撐訓練（單檔 HTML，離線可用）
.nojekyll           # 關閉 Jekyll 處理
```

## 加新訓練

1. 把 `XxxTrainer.html` 放到 repo **根目錄**（檔名要含 `Trainer`）。
2. 在 `trainings.json` 的 `trainings` 陣列加一項：

```json
{
  "file": "SquatTrainer.html",
  "title": "Squat Trainer",
  "titleZh": "深蹲",
  "desc": "下肢 · 深蹲計時與組數訓練",
  "emoji": "🦵",
  "accent": "#60a5fa",
  "tags": ["下肢", "力量"]
}
```

3. Commit + push。主頁會即刻更新（GitHub Pages 約 1 分鐘內生效）。

> 如果漏咗加 JSON，主頁仍會透過 GitHub API 自動偵測根目錄嘅 `*Trainer.html`，用檔名推導標題同 emoji；但補上 JSON 才有中文名、描述同標籤。

## 設計

- 單檔 HTML，零依賴、零建置。
- 手機優先（max-width 600px 訓練頁 / 820px 入口頁）。
- 4 套主題（dark / light / ocean / sunset），入口頁與訓練頁一致。
- 所有記錄只存瀏覽器本機（localStorage / IndexedDB），不上傳。
