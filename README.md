# 送貨助手：司機手機用的網頁

放在公開的 GitHub repo `pto2tsai/delivery-app`，用 GitHub Pages 發布：`https://pto2tsai.github.io/delivery-app/`

- `index.html`：**整個送貨助手的畫面**（不是外殼、不用框），由 `npm run build:web` 從 `src/App.html` 產生，不要直接改
- 資料都在 Google 試算表：網頁用 fetch 呼叫 Apps Script 的 `doPost`（網址在 `docs/WEB_APP_URL.txt`），密碼一樣檢查 `APP_PIN`
- `manifest.webmanifest`、`icon-*.png`、`apple-touch-icon.png`：手機主畫面的名稱和圖示（貨車＋定位點＋海浪）
- 網頁本身沒有資料、沒有密碼，公開沒關係

## 為什麼不用框包 Apps Script（2026-09-30 改）

用框包起來時：iPhone 從主畫面打開會算錯高度（底部露出一條）、語音和定位常被 Google 的框擋掉、瀏覽器打開上面有 Google 的提示條。
直接放網頁就跟貨櫃系統、崇文海鮮 ERP 一樣，沒有這些問題。

## 改版

1. 改 `src/App.html`，跑 `npm run build:web`（`npm test` 會檢查有沒有跑）
2. 推 `delivery-helper` 的 `main` → Apps Script 自動部署（後端）
3. **部署成功後**，把 `app-shell/` 的檔案複製到 `delivery-app` repo 推上去（前端）。順序不能反：前端要呼叫的新功能，後端要先有
