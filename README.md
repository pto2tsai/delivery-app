# 送貨助手 App 外殼

手機「加入主畫面」用的外殼網頁，放在公開的 GitHub repo `pto2tsai/delivery-app`，用 GitHub Pages 發布：

- 網址：`https://pto2tsai.github.io/delivery-app/`
- 內容只有：入口頁（`index.html`）、App 名稱與圖示（`manifest.webmanifest`、`icon-*.png`、`apple-touch-icon.png`、`splash.png`）
- **沒有任何程式邏輯、資料或密碼**，打開後把 Apps Script 的送貨助手包在裡面
- 跟「生產作業管理」（wens-app）分開：司機只看得到送貨助手

原始檔放在 `delivery-helper` repo 的 `app-shell/`，改完複製到 `delivery-app` repo。

## 要改的地方

- `index.html` 的 `APP_URL`：Apps Script 部署網址（結尾 `/exec`，見 `docs/WEB_APP_URL.txt`）
- 圖示：由蔡阿博提供的 logo（貨車＋定位點＋海浪）裁切產生，圓角外面塗白

## 限制

- 定位（從目前位置出發、記下這家的位置）、語音：外殼已經允許，但 Google 的框架不一定放行；不行的話畫面會提示改用拖的、改按鍵盤麥克風
- 從 App 打開和從瀏覽器打開，手機裡記的東西（密碼、勾選的縣市）是分開的；請固定用同一種方式打開
