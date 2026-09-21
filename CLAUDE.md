# 元素週期寶 宣傳網站（periodicbaby-site）

純靜態單頁，部署到 Vercel（Root Directory 用預設 `/`，不需 build）。
App 本體在另一個 repo：`/Users/ivyhsu/development/元素週期表`。宣傳素材（118 隻寶寶透明 PNG、LINE 邀請圖）在那邊的 `marketing/`。

## 檔案
- `index.html`：宣傳單頁（`:root` 變數是色票與字級的唯一來源）
- `go/index.html`：智慧下載頁，QR code 指向這裡；Android→Google Play、iPhone→App Store
- `assets/`：圖片（全站 WebP；`og.jpg` 為 1200×630 JPG，社群分享用）

## 設計定案
沒有設計稿，token 取自 App 的 `values-night/colors.xml`（只做夜間深色，與 App 一致）。CSS 只能引用 `:root` 變數。

- 色票：`--bg #14161F`、`--surface #1D2030`、`--surface-tint #25293D`、`--stroke #3A405A`、`--text #F5F5F7`、`--muted #A6ABBD`（App 無此值，暫定，待補）、`--primary #5C6BC0`、`--accent #FFCA28`；家族色 10 色取自 `cat_*`
- 字型：`Noto Sans TC` → PingFang TC／Microsoft JhengHei
- 字級：固定值三檔（桌機 ≥900／平板 600–899／手機 ≤599），不隨視窗連續縮放
- 驗收寬度：1440、1280、768、390

## 上線前清單
- [ ] 換掉 `SITE_URL`（`index.html` 的 canonical、og:url、og:image、twitter:image）
- [ ] App Store 網址：`index.html` 兩個按鈕、`go/index.html` 的 `APPLE`
- [ ] 確認 Google Play 連結真的可開（目前由套件名 `com.ayumi.periodictable` 推得）
- [ ] 確認 `--muted` 灰色
- [ ] 回饋表單區塊（待選 Tally 或 Google 表單）
- [ ] 補 `sitemap.xml`、`robots.txt`
