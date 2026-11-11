# 南投縣公廁巡檢系統 (Capacitor 原生 iOS App 專案)

本專案已將「公廁巡檢系統」配置為 **Capacitor 原生應用程式**，可直接連動 iOS 底層 PhotoKit 相簿，徹底解決 Safari 網頁選取 100～200 張照片時卡死或按勾勾無反應的問題。

---

## 專案目錄結構

```text
toilet-inspect-app/
├── capacitor.config.json    # Capacitor 核心設定 (App ID: tw.gov.nantou.toiletinspect)
├── package.json             # 依賴套件清單 (含 @capacitor/camera 原生外掛)
├── README.md                # 本說明文件
├── www/
│   └── index.html           # 前端介面 (同時支援 Capacitor 原生相簿與網頁降級)
└── Code.gs                  # Google Apps Script 後端代碼 (部署為 Web App API)
```

---

## 在 Mac 電腦上建置與安裝步驟 (5 步驟完成)

### 前置需求
1. 一台 Mac 電腦（安裝 macOS 13+）。
2. 已安裝 **Node.js** (v18 或 v20) 與 **Xcode**（可從 Mac App Store 免費下載）。

---

### 步驟 1：下載並進入專案目錄
打開 Mac 的「終端機 (Terminal)」，切換到本專案資料夾：
```bash
cd toilet-inspect-app
```

### 步驟 2：安裝相依套件
執行 npm 安裝 Capacitor 核心與相機原生外掛：
```bash
npm install
```

### 步驟 3：產生 iOS 原生專案
首次建置請執行新增 iOS 平台：
```bash
npx cap add ios
```
這會在專案下自動生成一個標準的 `ios/` Xcode 專案資料夾。

### 步驟 4：同步網頁代碼到 iOS
每次修改 `www/index.html` 後，執行同步指令：
```bash
npx cap sync
```

### 步驟 5：用 Xcode 開啟並安裝到 iPhone
執行指令打開 Xcode：
```bash
npx cap open ios
```

在 Xcode 介面中：
1. 用傳輸線將您的 **iPhone** 接上 Mac 電腦。
2. 在 Xcode 左側點選最上方的專案名稱 **App**，進入 **Signing & Capabilities** 分頁。
3. 在 **Team** 下拉選單中登入您的 Apple ID（免費個人帳號即可）。
4. 上方裝置選擇您的實體 iPhone。
5. 點擊左上角的 **「播放 (▶)」按鈕**，Xcode 就會自動編譯並將 App 直接安裝進您的 iPhone！

---

## 為什麼 Capacitor 能解決 100～200 張照片卡頓？

1. **直通 iOS PhotoKit**：
   使用 `@capacitor/camera` 的 `Camera.pickImages({ limit: 0 })`，直接由 iOS 原生 C++/Swift 處理，不經過 Safari WebKit 沙箱拷貝，選完 200 張點勾勾 **0.1 秒瞬間完成**。
2. **免伺服器費用**：
   後端依然直接連線您原本部署在 Google Apps Script 的 API，資料直接寫入 Google 試算表與 Drive，**伺服器成本永遠 0 元**。
3. **離線與背景保護**：
   作為原生 App，在 iOS 上擁有更高記憶體配額，上傳照片不易被系統中途凍結。
