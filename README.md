<p align="center"><img src="logo.png" alt="凡人修仙錄" width="220"></p>

# 凡人修仙錄

把現實習慣變成修仙的打卡遊戲：每天做完現實中的事，回來打勾，累積修為、突破境界。

- 純 HTML + CSS + JavaScript，沒有後端、不需登入、不用安裝任何套件
- 資料存在瀏覽器的 LocalStorage
- 可安裝到手機主畫面，離線也能開啟（PWA）

## 檔案說明

| 檔案 | 用途 |
|---|---|
| `index.html` | App 本體（所有畫面與邏輯） |
| `manifest.webmanifest` | 讓 App 可安裝到主畫面 |
| `sw.js` | 離線快取（Service Worker） |
| `favicon.svg`、`icon-*.png`、`apple-touch-icon.png` | 網站與 App 圖示 |
| `logo.svg`、`logo.png` | Logo |
| `SPEC.md` | 產品規格與目前實作狀態 |

所有檔案放在同一層，不需要資料夾。

## 部署到 GitHub Pages

1. 在 GitHub 建立新的 repository（例如 `fanren-xiuxian`）。
2. 進入 repository，按 **Add file → Upload files**，把這個資料夾裡的**所有檔案**都上傳，按 **Commit changes**。
3. 到 **Settings → Pages**，在 **Build and deployment** 選：
   - Source：**Deploy from a branch**
   - Branch：**main**，資料夾選 **/ (root)**，按 **Save**
4. 等 1 到 2 分鐘，頁面上方會出現網址，格式是：
   `https://你的帳號.github.io/fanren-xiuxian/`

> 私人 repository 需要付費方案才能使用 Pages。免費方案請把 repository 設為 Public。

## 安裝到手機主畫面

- **iPhone（Safari）**：分享按鈕 → 加入主畫面
- **Android（Chrome）**：右上角選單 → 安裝應用程式（或加到主畫面）

## 資料與備份

- 資料只存在「這個網址、這個瀏覽器」。清除瀏覽器資料、換手機、換瀏覽器都會不見。
- 到「我」頁最下方的 **設定與備份**：
  - **匯出備份**：下載成檔案，或複製文字。
  - **匯入備份**：選擇備份檔，或貼上文字，會取代目前資料。
- 請定期匯出。
- 如果你之前在別的網址試玩過，想帶著進度過來：先在舊網址匯出（複製文字），再到新網址匯入。

## 更新網站

1. 修改檔案後，在 GitHub 上重新上傳同名檔案並 Commit。
2. 因為有離線快取，改完後如果畫面還是舊的，先重新整理一次，或完全關閉 App 再開。
3. 想確保所有人都換成新版：把 `sw.js` 最上面的 `CACHE` 版本號加 1（例如 `fanren-xiuxian-v2`），並把 `index.html` 裡的 `APP_VERSION` 一起更新。

## 測試模式

網址後面加上 `?demo=1`（例如 `https://你的帳號.github.io/fanren-xiuxian/?demo=1`），「我」頁的設定區會多出三個測試按鈕：修為 +100、補入 10 日修煉、直達突破條件，方便直接看到突破動畫等畫面。平常不會顯示。

## 技術備註

- LocalStorage key：`fanren-xiuxian-v1`（主題偏好另存為 `fanren-theme`），資料結構 `v: 1`。
- 字型使用 Google Fonts（Noto Serif TC、Noto Sans TC）。沒有網路且沒載入過時，會退回系統字型，功能不受影響。
- 同一個 GitHub 帳號下的不同 repository 共用 `你的帳號.github.io` 這個來源，但本 App 的儲存 key 是獨立的，不會互相干擾。
