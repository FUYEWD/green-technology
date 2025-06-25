# 🌍 環保戰士：碳足跡計算器

一個簡單易用的互動式碳足跡計算器，幫助使用者記錄和計算日常生活中的碳排放量。

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)
![Bootstrap](https://img.shields.io/badge/Bootstrap-7952B3?logo=bootstrap&logoColor=white)

## 🚀 線上體驗

[點擊這裡體驗應用程式](https://yourusername.github.io/carbon-footprint-calculator/)

## 📁 專案結構

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

## 📖 專案簡介

這是一個以環保為主題的碳足跡計算器，採用遊戲化設計，讓使用者能夠：
- 🚗 記錄日常交通方式和距離
- 🍽️ 詳細記錄三餐的食物消費
- 📊 即時計算碳排放量
- 🏆 根據碳足跡獲得環保等級評定
- 💡 獲得個人化的環保建議

## ✨ 主要功能

### 🚗 交通記錄
- 支援多種交通方式：步行、腳踏車、公車、捷運、汽車、機車、計程車
- 實時碳排放係數顯示
- 自定義距離輸入

### 🍽️ 餐點記錄
- **早餐選項**：吐司、三明治、早餐店套餐、粥品、豆漿燒餅等
- **午餐選項**：便當、炒飯、湯麵、漢堡、披薩、沙拉等
- **晚餐選項**：家常菜、火鍋、燒烤、牛排、海鮮等
- 支援自定義食物和碳排放係數
- 彈性份量設定

### 📊 結果分析
- 詳細的碳足跡分解報告
- 環保等級評定系統（5個等級）
- 個人化環保建議
- 視覺化的結果展示

## 🎮 等級系統

| 等級 | 碳足跡範圍 | 稱號 | 星級 |
|------|------------|------|------|
| 🌟 | ≤ 3.0 kg CO₂ | 環保大天使 | ★☆☆☆☆ |
| 🌱 | 3.1-7.0 kg CO₂ | 綠能天兵 | ★★☆☆☆ |
| ♻️ | 7.1-12.0 kg CO₂ | 環保中隊長 | ★★★☆☆ |
| 🌿 | 12.1-18.0 kg CO₂ | 綠能小騎士 | ★★★★☆ |
| 💨 | > 18.0 kg CO₂ | 碳汙染惡魔 | ★★★★★ |

## 🚀 快速開始

### 📱 本地運行

1. **克隆專案**：
```bash
git clone https://github.com/yourusername/carbon-footprint-calculator.git
```

2. **進入專案目錄**：
```bash
cd carbon-footprint-calculator
```

3. **運行應用程式**：
   - **方法一**：直接在瀏覽器中打開 `index.html`
   - **方法二**：使用本地伺服器：
```bash
# 使用 Python 3
python -m http.server 8000

# 使用 Node.js (需安裝 http-server)
npx http-server
```

4. **訪問應用程式**：在瀏覽器中打開 `http://localhost:8000`

## 🛠️ 技術架構

### 前端技術
- **HTML5**: 語義化標記結構
- **CSS3**: 現代化樣式設計
  - CSS Grid 和 Flexbox 佈局
  - CSS 自定義屬性（CSS Variables）
  - 響應式設計
  - 動畫和過渡效果
- **JavaScript (ES6+)**: 核心計算邏輯
- **Bootstrap 5.3.0**: UI 組件和響應式網格系統
- **Google Fonts**: Press Start 2P, Orbitron 字體

### 設計特色
- **遊戲化介面**: 賽博朋克主題設計
- **響應式佈局**: 支援桌面和行動裝置
- **無障礙設計**: 符合 ARIA 標準
- **模組化架構**: 易於維護和擴展

## 📱 裝置支援

- ✅ 現代瀏覽器 (Chrome, Firefox, Safari, Edge)
- ✅ 行動裝置 (iOS, Android)
- ✅ 平板電腦
- ✅ 桌面電腦

## 🔧 自定義配置

### 修改碳排放係數
在 `script` 標籤中找到 `CARBON_DATA` 物件：

```javascript
const CARBON_DATA = {
    transport: {
        walk: 0.0,
        bike: 0.0,
        bus: 0.05,
        // 修改或新增係數...
    },
    food: {
        toast: 0.8,
        sandwich: 1.5,
        // 修改或新增係數...
    }
};
```

### 新增食物選項
在對應的 `<select>` 元素中新增選項：

```html
<option value="new_food">新食物 (X.X kg CO₂/份)</option>
```

並在 `CARBON_DATA.food` 中新增對應係數。

## 📊 碳排放參考數據

### 交通工具（每公里）
| 交通方式 | 碳排放係數 (kg CO₂/km) | 圖標 |
|----------|------------------------|------|
| 步行 | 0.0 | 🚶 |
| 腳踏車 | 0.0 | 🚴 |
| 捷運 | 0.03 | 🚇 |
| 公車 | 0.05 | 🚌 |
| 機車 | 0.12 | 🏍️ |
| 汽車 | 0.25 | 🚗 |
| 計程車 | 0.30 | 🚕 |

### 食物類別（每份）
| 食物類型 | 碳排放係數 (kg CO₂/份) | 範例 |
|----------|------------------------|------|
| 素食類 | 0.3-1.5 | 水果、沙拉、素食便當 |
| 一般餐點 | 1.5-4.0 | 三明治、便當、炒飯 |
| 肉類料理 | 3.0-6.2 | 火鍋、燒烤、牛排 |

## 🤝 貢獻指南

歡迎貢獻！請遵循以下步驟：

1. Fork 專案
2. 建立功能分支 (`git checkout -b feature/AmazingFeature`)
3. 提交變更 (`git commit -m 'Add some AmazingFeature'`)
4. 推送分支 (`git push origin feature/AmazingFeature`)
5. 開啟 Pull Request

### 開發建議
- 保持代碼風格一致性
- 新增功能時請更新文件
- 確保響應式設計相容性
- 測試多種瀏覽器相容性

## 📝 更新日誌

### v1.0.0 (2024-12-XX)
- ✨ 初始版本發布
- 🚗 交通碳足跡計算功能
- 🍽️ 三餐記錄功能
- 🎮 遊戲化等級系統
- 📱 響應式設計支援
- 🌟 環保建議功能

## 🚀 未來規劃

- [ ] 多語言支援
- [ ] 資料匯出功能
- [ ] 歷史記錄追蹤
- [ ] 社群分享功能
- [ ] PWA 支援
- [ ] 更多食物選項

## 📄 授權條款

本專案採用 MIT 授權條款 - 詳情請見 [LICENSE](LICENSE) 檔案。

## 🙏 致謝

- 感謝所有提供碳排放數據的環保組織
- Bootstrap 團隊提供的優秀 UI 框架
- Google Fonts 提供的字體資源

## 📧 聯絡資訊

- 作者：[Your Name]
- Email：your.email@example.com
- 專案連結：https://github.com/yourusername/carbon-footprint-calculator

## 🔗 相關連結

- [碳足跡相關知識](https://example.com)
- [環保生活指南](https://example.com)
- [氣候變遷資訊](https://example.com)

---

⭐ 如果這個專案對你有幫助，請給個星星支持！

📢 讓我們一起為地球環保盡一份力！
