# 黑糖饅頭 - 公廁巡檢系統 🚀

專為外勤公廁巡檢拍照打造的極速、多人協同上傳系統。採用深藍質感與立體卡通按鈕風格，支援 iOS/Android 手機一次選取 100~200 張照片流暢載入，並可直接加入手機主畫面以全螢幕 App 方式運作。

---

## 📁 檔案結構說明

```text
public-restroom-inspection/
├── index.html               # 【核心前端】GitHub Pages 主要網頁 (深藍卡通風格、內建後端網址)
├── icon.png                 # 【App 圖示】192x192 專屬黑糖饅頭圖示 (iOS 主畫面使用)
├── icon-512.png             # 【App 圖示】512x512 高解析度圖示
├── icon.jpg                 # 【原始圖檔】黑糖饅頭 3D 卡通巡檢員高清圖
├── manifest.json            # 【PWA 設定】手機加入主畫面設定檔 (名稱：黑糖饅頭)
├── Code.gs                  # 【後端代碼】Google Apps Script API (分塊快取、極速建立資料夾)
├── appsscript.json          # 【後端設定】Google Apps Script 專案設定
├── README.md                # 本專案說明文件
│
├── capacitor.config.json    # (可選) Capacitor 原生 App 設定檔
├── package.json             # (可選) Capacitor 依賴套件管理
├── README_CAPACITOR.md      # (可選) Mac / Xcode 打包原生 iOS App 指南
└── www/                     # (可選) Capacitor 專用網頁資源目錄
    ├── index.html
    ├── icon.png
    ├── icon-512.png
    └── manifest.json
```

---

## 🚀 如何更新至 GitHub Pages (3 步驟)

1. **上傳檔案到 GitHub**：
   * 將本壓縮包解壓縮後的 `index.html`、`icon.png`、`icon-512.png`、`manifest.json` 與 `README.md` 上傳或推送到您的 GitHub 儲存庫（Repository）的 `main` 分支。
2. **確認開啟 GitHub Pages**：
   * 在 GitHub 進入專案的 **Settings** ➔ **Pages**。
   * **Source** 選擇 **Deploy from a branch**，分支選擇 **`main`** / **`/ (root)`**，點擊 **Save**。
3. **取得網址並使用**：
   * 稍等 1 分鐘，GitHub 就會產生專屬網址（例如：`https://ysm2238304-hue.github.io/public-restroom-inspection/`）。
   * 直接將該網址發送給同仁即可使用！

---

## 📱 如何在 iPhone 手機上加入主畫面 (像 App 一樣使用)

1. 用 iPhone 的 **Safari 瀏覽器** 打開 GitHub Pages 網址。
2. 點擊畫面底部的 **「分享（方形帶向上箭頭 ⎋）」** 圖示。
3. 往下滾動找到並點擊 **「加入主畫面 ➕」**。
4. 點擊右上角 **「新增」**。
5. 手機桌面上就會出現可愛的 **「黑糖饅頭」App 圖示**，點開即可全螢幕極速巡檢！
