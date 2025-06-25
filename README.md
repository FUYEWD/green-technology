# green-technology# 環保戰士碳足跡計算器 - GitHub 專案設置指南

## 📁 專案結構

建議的資料夾結構：
```
carbon-footprint-calculator/
├── index.html              # 主要網頁檔案
├── README.md               # 專案說明文件
├── LICENSE                 # 授權檔案
├── assets/                 # 資源檔案夾
│   ├── css/
│   │   └── style.css      # 分離的樣式檔案（可選）
│   ├── js/
│   │   └── app.js         # 分離的 JavaScript 檔案（可選）
│   └── images/            # 圖片檔案
├── docs/                  # 文件資料夾
│   └── screenshots/       # 應用程式截圖
└── .gitignore             # Git 忽略檔案
```

## 📝 README.md 模板

```markdown
# 🌍 環保戰士：碳足跡計算器

一個簡單易用的碳足跡計算器，幫助用戶記錄和計算日常生活中的碳排放量。

## ✨ 功能特色

- 🚗 **交通記錄**: 支援多種交通方式的碳排放計算
- 🍽️ **餐點記錄**: 詳細的三餐碳足跡追蹤
- 📊 **即時統計**: 即時顯示今日總碳足跡
- 🏆 **環保等級**: 根據碳排放量給予環保等級評定
- 📱 **響應式設計**: 支援桌面和行動裝置

## 🚀 在線體驗

[點擊這裡體驗應用程式](https://yourusername.github.io/carbon-footprint-calculator/)

## 📱 本地運行

1. 克隆此專案：
```bash
git clone https://github.com/yourusername/carbon-footprint-calculator.git
```

2. 進入專案資料夾：
```bash
cd carbon-footprint-calculator
```

3. 使用瀏覽器打開 `index.html` 或使用本地伺服器：
```bash
# 使用 Python 3
python -m http.server 8000

# 使用 Node.js (需安裝 http-server)
npx http-server
```

4. 在瀏覽器中訪問 `http://localhost:8000`

## 🛠️ 技術棧

- **前端**: HTML5, CSS3, JavaScript (ES6+)
- **框架**: Bootstrap 5
- **字體**: Google Fonts (Press Start 2P, Orbitron)
- **圖標**: Unicode Emoji

## 📊 碳排放係數參考

### 交通工具 (kg CO₂/km)
- 步行/腳踏車: 0.0
- 捷運: 0.03
- 公車: 0.05
- 機車: 0.12
- 汽車: 0.25
- 計程車: 0.30

### 食物類別 (kg CO₂/份)
- 素食類: 0.3-1.5
- 一般餐點: 1.5-4.0
- 肉類料理: 3.0-6.2

## 🤝 貢獻指南

歡迎提交 Issue 和 Pull Request！

1. Fork 此專案
2. 創建你的特性分支 (`git checkout -b feature/AmazingFeature`)
3. 提交你的更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 打開一個 Pull Request

## 📄 授權協議

此專案基於 MIT 授權協議 - 查看 [LICENSE](LICENSE) 檔案了解詳情

## 📞 聯絡方式

- 專案連結: [https://github.com/yourusername/carbon-footprint-calculator](https://github.com/yourusername/carbon-footprint-calculator)
- 問題回報: [Issues](https://github.com/yourusername/carbon-footprint-calculator/issues)

## 🙏 致謝

感謝所有為環保事業貢獻力量的開發者們！

---
⭐ 如果這個專案對你有幫助，請給個星星支持一下！
```

## 🔧 GitHub Pages 設置步驟

### 方法 1: 直接上傳檔案
1. 在 GitHub 上創建新的 repository
2. 將 `index.html` 重新命名並上傳
3. 在 Settings > Pages 中啟用 GitHub Pages
4. 選擇 `main` 分支作為來源

### 方法 2: 使用 Git 命令
```bash
# 初始化 Git repository
git init

# 添加檔案
git add .

# 提交更改
git commit -m "Initial commit: Carbon footprint calculator"

# 添加遠端 repository
git remote add origin https://github.com/yourusername/carbon-footprint-calculator.git

# 推送到 GitHub
git push -u origin main
```

## 📱 轉換成 App 的方案

### 選項 1: Progressive Web App (PWA)
添加以下檔案來創建 PWA：

**manifest.json**
```json
{
  "name": "環保戰士碳足跡計算器",
  "short_name": "碳足跡計算器",
  "description": "計算日常生活碳足跡的工具",
  "start_url": "/",
  "display": "standalone",
  "background_color": "#3a7bd5",
  "theme_color": "#00d2ff",
  "icons": [
    {
      "src": "icons/icon-192x192.png",
      "sizes": "192x192",
      "type": "image/png"
    },
    {
      "src": "icons/icon-512x512.png",
      "sizes": "512x512",
      "type": "image/png"
    }
  ]
}
```

**service-worker.js**
```javascript
const CACHE_NAME = 'carbon-calculator-v1';
const urlsToCache = ['/', '/index.html'];

self.addEventListener('install', event => {
  event.waitUntil(
    caches.open(CACHE_NAME)
      .then(cache => cache.addAll(urlsToCache))
  );
});

self.addEventListener('fetch', event => {
  event.respondWith(
    caches.match(event.request)
      .then(response => response || fetch(event.request))
  );
});
```

### 選項 2: 使用 Cordova/PhoneGap
```bash
# 安裝 Cordova
npm install -g cordova

# 創建新專案
cordova create CarbonCalculator tw.carbon.calculator "碳足跡計算器"

# 添加平台
cordova platform add android
cordova platform add ios

# 構建應用
cordova build
```

### 選項 3: 使用 Capacitor
```bash
# 安裝 Capacitor
npm install @capacitor/core @capacitor/cli

# 初始化
npx cap init

# 添加平台
npx cap add android
npx cap add ios

# 同步檔案
npx cap sync

# 打開 IDE
npx cap open android
npx cap open ios
```

## 🎯 後續優化建議

1. **程式碼分離**: 將 CSS 和 JavaScript 分離到獨立檔案
2. **資料持久化**: 添加本地存儲功能記錄歷史數據
3. **圖表功能**: 使用 Chart.js 添加數據可視化
4. **多語言支援**: 添加英文等其他語言版本
5. **API 整合**: 連接真實的碳排放數據 API
6. **社交分享**: 添加分享功能鼓勵環保意識

## 🔍 SEO 優化

在 `<head>` 中添加：
```html
<meta property="og:title" content="環保戰士碳足跡計算器">
<meta property="og:description" content="計算你的日常碳足跡，成為環保戰士！">
<meta property="og:image" content="https://yourdomain.com/og-image.png">
<meta property="og:url" content="https://yourdomain.com">
<meta name="twitter:card" content="summary_large_image">
```
