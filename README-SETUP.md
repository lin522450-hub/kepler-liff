# LIFF 設定指南

## 你需要手動做的步驟

### 1. 建立 LINE Login Channel
1. 到 LINE Developers Console (https://developers.line.biz)
2. 選擇 Provider: Frank52071
3. 新增 Channel → 選 "LINE Login"
4. 填入:
   - Channel name: 克卜勒獵才LIFF
   - Channel description: LIFF applications for 克卜���獵才Copilot
   - App types: 勾選 Web app
5. 記錄 Channel ID

### 2. 建立 LIFF App (人選資料表單)
1. 在剛建的 LINE Login Channel 頁面 → LIFF tab → Add
2. 設定:
   - LIFF app name: 人選資料填寫
   - Size: Full
   - Endpoint URL: (你的 hosting URL)/candidate-form.html
   - Scopes: 勾選 profile, openid
3. 記錄 LIFF ID (格式: 20xx-xxxxxxxx)

### 3. ���立 LIFF App (預約諮詢)
1. 同上，再 Add 一個
2. 設定:
   - LIFF app name: 預約諮詢
   - Size: Full
   - Endpoint URL: (你的 hosting URL)/booking.html
   - Scopes: 勾選 profile, openid
3. 記錄 LIFF ID

### 4. 更新 LIFF ID
在兩個 HTML 檔案中，把 `__LIFF_ID__` 替換成實際的 LIFF ID:
- candidate-form.html → 人選資料表單的 LIFF ID
- booking.html → 預約諮詢的 LIFF ID

### 5. Hosting 方式 (選一)
- **GitHub Pages**: push 到 GitHub repo，開啟 Pages
- **Netlify**: 拖入 liff 資料夾即可部署
- **Cloudflare Pages**: 連接 GitHub 或直接上傳

## Webhook URLs (已設定)
- 人選表單: https://unsuppressible-loriann-undeliciously.ngrok-free.dev/webhook/liff-candidate
- 預約���詢: https://unsuppressible-loriann-undeliciously.ngrok-free.dev/webhook/liff-booking
- 注意: Cloudflare tunnel URL 重啟會變，需同步更新

## n8n Workflow IDs
- LIFF 人選資料表單: O8QncdQHKwXUtPMc (active)
- LIFF 預約諮詢: oiexAqxr6dnkE7cY (active)
