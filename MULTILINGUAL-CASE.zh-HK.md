# 案例：讓可見內容與多語言中繼資料對應

[English](MULTILINGUAL-CASE.md) | [简体中文](MULTILINGUAL-CASE.zh-CN.md) | [日本語](MULTILINGUAL-CASE.ja.md) | [繁體中文](MULTILINGUAL-CASE.zh-HK.md)

ZequnWeb 在 2026 年 9 月 10 日的歷史檢查中發現，繁體作品頁可見八個項目，但結構化清單沒有對應同一組內容。修復改用同一資料來源生成作品卡片及結構化清單。最終記錄中，繁體清單為八項；英文及簡體清單各為十六項。

## 修改內容

內容修改日期亦改由共用解析器取得，讓結構化中繼資料及網站地圖指向實際記錄的內容修改時間，並以迴歸測試涵蓋日期擷取。語言版本按照真正存在的譯文頁面檢查：有語言標籤不代表已有相應譯文。

這是內容一致性修復，不代表搜尋引擎已收錄或業務效果提高。[歷史證據記錄](implementation-evidence.json) 記載檢查了 196 個 HTML、197 項生成工作、三項日期迴歸測試，且本機 SEO、結構及內部連結檢查通過。記錄於 2026 年 9 月 12 日公開，說明當時的靜態匯出，不代表當前線上狀態。

## 重用步驟

1. 為每個頁面分配穩定識別碼，與翻譯後的標題及網址分開管理。
2. 用同一組已確認記錄生成可見清單及相應結構化清單。
3. 輸出自身標準網址及真正對應的語言頁面，包含相互返回關係。
4. 建構靜態匯出，檢查生成的 HTML、網站地圖及每種語言的連結。
5. 記錄版本、日期、頁面數及範圍，再描述驗證結果。

[可運行網站範例](https://github.com/awesomellm/multilingual-website-starter/blob/main/README.zh-HK.md) 展示四語言、三種相同頁面識別碼；[靜態檢查器](https://github.com/awesomellm/website-seo-checker/blob/main/README.zh-HK.md) 驗證其中一部分。翻譯準確性及實際伺服器回應仍須審查。用[語言內容對應表](https://github.com/awesomellm/website-migration-kit/blob/main/multilingual-content-map.zh-HK.csv) 管理負責人及缺少的譯文。
