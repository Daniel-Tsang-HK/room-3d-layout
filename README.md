# 房間 3D 佈局方案（單一離線檔）

一個**單一 HTML 檔**的 3D 房間佈局檢視器：內嵌 three.js r180，**不需連網、不需安裝任何東西**，用瀏覽器打開即可。

## 檔案

| 檔案 | 說明 |
|---|---|
| `index.html` | 完整互動 3D（單一離線檔，851 KB，內嵌 three.js 與靜態預覽圖） |
| `room-3-static-preview.pdf` | 靜態預覽 PDF（3D 圖＋尺寸表），適合用 WhatsApp／郵件直接傳送 |
| `publish_to_github.ps1` | 一鍵發佈到 GitHub Pages 的 PowerShell 腳本（不用手動上傳） |

## 方法 A：一鍵發佈（建議，不用找 GitHub 上傳按鈕）

1. 到 https://github.com/settings/tokens → **Generate new token (classic)**
   - Note 隨便填，Expiration 選 7 days
   - 勾選 scope **repo**
   - 產生後複製 token（只顯示一次）
2. 在本資料夾按右鍵 →「在終端機中開啟」→ 執行：

   ```powershell
   powershell -ExecutionPolicy Bypass -File .\publish_to_github.ps1
   ```

3. 依提示輸入：使用者名稱、repo 名稱（直接按 Enter 用 `room-3d-layout`）、貼上 token。
4. 腳本會自動：建立 repo → 上傳 `index.html`／`README.md`／PDF → 啟用 GitHub Pages → 開啟網址。
5. 網址格式：`https://<你的帳號>.github.io/room-3d-layout/`（約 1–2 分鐘生效）

> 不需要時記得回到 GitHub → Settings → Developer settings → Tokens 把該 token 刪除。

## 方法 B：手動用網頁上傳

1. 開 https://github.com/new → Repository name：`room-3d-layout` → **Public** → **勾選 Add a README file** → Create repository
2. 進入 repo 後，檔案列表右上角按 **Add file ▾** → **Upload files**
   （也可直接開 `https://github.com/<帳號>/<repo>/upload/main`）
3. 把 `index.html`（及 PDF、README）拖進去 → **Commit changes**
4. **Settings → Pages** → Source：Deploy from a branch → Branch：`main`、資料夾 `/ (root)` → **Save**
5. 網址：`https://<帳號>.github.io/<repo>/`

## 功能

- 旋轉：單指拖曳／滑鼠左鍵；縮放：雙指／滾輪；平移：雙指／右鍵拖曳
- 360° 任意角度旋轉（無垂直限制）
- 點擊門板、床板掀板、抽屜、鍵盤托板可開啟
- 測距：第一點吸附線的端點或中點；第二點可吸附任何可見面（含地板、牆壁），量測線自動對齊 X／Y／Z 單一軸
- 圖層：家具／牆壁／地板／其他
- 附靜態預覽：在不執行 JavaScript 的檢視器（例如 WhatsApp 開啟 .html 附件）仍看得到 3D 圖

## 授權

僅供個人／居家規劃參考使用。
