# ApexNexus Terminal v2.0.1

ApexNexus Terminal 是可直接部署到 GitHub Pages 的純前端交易研究與紀律管理工具。

## 功能

1. 交易點子生成器
2. 自動技術分析師
3. 新聞轉交易策略
4. 策略回測分析師
5. 投資組合風險管理
6. 交易日誌分析師
7. 全自動每日交易計畫
8. 總覽儀表板、資料備份與設定

## 技術功能

- MA5 / MA20 / MA60
- RSI(14)
- MACD
- ATR
- 20 日支撐與壓力
- 均線交叉回測
- RSI 超賣反彈回測
- 20 日突破回測
- 勝率、獲利因子、最大回撤
- 投資組合 Beta / 集中度 / 壓力測試
- 交易日誌與行為檢討
- LocalStorage 本機保存
- JSON 匯入 / 匯出備份
- CSV 匯入歷史行情
- PWA 可安裝網頁 App
- 響應式手機 / 平板 / 電腦介面

## CSV 格式

```csv
date,open,high,low,close,volume
2026-09-01,100,103,99,102,12345
2026-09-02,102,105,101,104,15200
```

## GitHub Pages 部署

1. 建立 Repository：`ApexNexus-Terminal`
2. 上傳本資料夾中的全部檔案到 Repository 根目錄
3. Repository → Settings → Pages
4. Source 選 `Deploy from a branch`
5. Branch 選 `main`
6. Folder 選 `/ (root)`
7. Save

## 即時資料架構

目前 v2.0.1 是 GitHub Pages 純前端版本，因此不把券商 API Key 或付費資料金鑰直接寫在瀏覽器。

如需即時行情，建議下一階段採：

GitHub Pages 前端 → Cloudflare Worker / Vercel Function → TWSE / TPEx / 美股 API / 新聞 API

這樣可以避免 API Key 暴露、CORS 與流量限制問題。

## 免責聲明

本工具僅供研究、策略測試與交易紀律管理，不構成投資建議。回測績效不代表未來績效。


## v2.0.1 更新
- 觀察清單防重複：同一市場＋同一代號只保留一筆。
- 股票代號標準化：英文自動轉大寫，台股可將 `.TW` / `.TWO` 正規化。
- 既有重複資料啟動時自動去重。
- JSON 備份匯入時自動去重。
- 儀表板與交易點子清單新增單筆刪除。
- 清空觀察清單新增確認提示。
- 更新 Service Worker 快取策略，減少 GitHub Pages 顯示舊版本的情況。
