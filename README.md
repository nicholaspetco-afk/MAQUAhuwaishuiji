# GitHub Pages 部署（戶外水機 Demo，離線模擬數據）

這個資料夾已包含可直接部署到 GitHub Pages 的靜態檔案（使用相對路徑）。

- 自動離線 Demo：在網址加上 `?demo=1`，頁面會自動進入離線模式（免登入）。
- 也可手動離線登入：管理員帳號 `MAUQA` 密碼 `maqua28453792`。

## 發布方式 A：整個資料夾作為獨立 repo
1. 建新 repo，例如 `water-machine-demo`。
2. 將本資料夾內容提交為 repo root。
3. 在 GitHub 設定中啟用 Pages，Branch 選擇 `main`/`master`，資料夾選 `/`（root）。

## 發布方式 B：做為現有 repo 的 gh-pages 分支
```bash
npm i -D gh-pages
npx gh-pages -d deploy/github-pages-demo
```
發佈後網址通常為 `https://<user>.github.io/<repo>/`。

若需要預設就自動離線（免加 ?demo=1），可在打包前設定：
```bash
# 在 frontend 目錄
VITE_DEMO_AUTO_OFFLINE=1 npm run build -- --base=./
```
然後再把 `frontend/dist` 的內容放到本資料夾即可。

