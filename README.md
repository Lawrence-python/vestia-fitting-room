# VESTIA｜RWD 虛擬試穿間

可直接部署至 GitHub Pages 的靜態網站。HTML、CSS、JavaScript 與示範配樂均已整合於 `index.html`，圖片使用相對路徑，不需要 Node.js、建置指令或 API 金鑰。

## 上傳 GitHub

1. 在 GitHub 建立儲存庫，建議名稱 `vestia-fitting-room`。若使用 GitHub Free 的免費 Pages 託管，需使用公開儲存庫；選擇 Public 代表程式碼與素材也會公開。
2. 先解壓縮部署 ZIP。將解壓縮後的**檔案與 img 資料夾**上傳至儲存庫最外層。`index.html` 必須直接位於根目錄；不要只上傳 ZIP，也不要再包一層資料夾。
3. 在儲存庫進入 **Settings → Pages**。
4. 在 **Build and deployment → Source** 選擇 **Deploy from a branch**。
5. 選擇存放檔案的分支，通常為 **main**，資料夾選擇 **/(root)**，按 **Save**。
6. 等待 GitHub 完成部署，再從 Pages 設定頁開啟實際產生的網站網址。

完成後修改網頁時，更新 `index.html`；新增或替換圖片時，一併更新 `img` 內對應檔案，GitHub Pages 會依發布來源更新網站。

## 檔案

| 路徑 | 用途 |
| --- | --- |
| `index.html` | 完整 RWD 網頁，含互動與配樂 |
| `img/` | 28 張圖片：模特兒、商品及穿搭 |
| `README.md` | 部署與操作說明 |

請保留部署包內所有檔案。此版本已將入口放在根目錄，可用於 GitHub 的專案網站子路徑。

## 操作

- 桌機採三欄、平板採雙欄，手機提供固定試穿鏡與底部快速導覽。
- 上衣和裙子共有 9 種無包搭配；3 套主打穿搭各支援 3 款包包，共 18 張穿搭圖。
- 沒有包包圖片的搭配，會顯示可用套裝供你確認選擇。
- 點 **Play demo** 播放 16 秒配樂示範。播放中選擇商品會結束示範並回應操作。
- **Shop the look** 為示範購物袋，不會建立真實訂單或付款。

品牌、模特兒、商品與價格均為虛構展示素材。此 GitHub 專用包包含執行網站所需檔案；原始生圖提示詞與影片重製工具另存於完整專案下載包。

## GitHub 官方說明

- [設定 GitHub Pages 發布來源](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)
- [建立 GitHub Pages 網站](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site)

## 上傳人臉，套用至穿搭模特兒

1. 按試穿鏡下方「上傳人臉照片」，選擇 JPG、PNG 或 WebP 正面單人照（12 MB 以下）。
2. 自動辨識成功時會套用至全部 18 張穿搭圖。若裝置無法啟動辨識元件，依序點選照片中的畫面左眼、右眼、嘴巴中央，再按「套用人臉」。
3. 可切換「我的臉／預設臉」、調整對位或移除人臉；未上傳、移除或重新整理時使用預設臉。衣服與包包仍可正常切換。

此版本是瀏覽器內的二維臉部對位與柔邊合成，不是生成式照片重繪。髮型、身材、姿勢與服裝沿用原模特兒；照片角度、光線與標記位置會影響效果。

照片使用本機 canvas 與 object URL 處理，不會傳送到 GitHub 或辨識服務。首次選檔會從 Google 模型儲存空間與 jsDelivr 載入釘選版本的 MediaPipe 執行元件與模型；此步驟需網路與裝置支援，失敗時仍可手動三點對位。

技術參考：[Google MediaPipe Face Landmarker 官方文件](https://developers.google.com/edge/mediapipe/solutions/vision/face_landmarker?tab=Web)。
