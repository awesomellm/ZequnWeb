# 詢盤收到，需要明確確認

[English](INQUIRY-RECEIPTS.md) | [简体中文](INQUIRY-RECEIPTS.zh-CN.md) | [日本語](INQUIRY-RECEIPTS.ja.md) | [繁體中文](INQUIRY-RECEIPTS.zh-HK.md)

產品示範可以選中型號，將其帶入表單，再生成可閱讀的報價請求草稿。這證明草稿流程可用，不證明訊息已到達企業。ZequnWeb 的 2026 年 9 月 30 日本機記錄明確說明，當時沒有設定表單接收端，亦沒有發送真實或測試詢盤。

## 區分狀態

分別表示編輯、驗證、生成草稿、傳輸、伺服器收件及業務資格確認。開啟郵件應用程式或複製草稿仍是草稿操作，普通 HTTP 200 亦不等於收件。

接收服務可以傳回以下虛構介面範例：

```json
{"submissionId":"demo-submission-01","received":true,"receiptId":"demo-receipt-01"}
```

只有 `submissionId` 與當前提交匹配、`received` 嚴格為真且 `receiptId` 有效，才接受收件確認。同一提交只記錄一次；重複點擊或網絡重試不能增加詢盤數量。是否屬於有效業務機會還須另行判斷，不能由收件直接推斷。

## 讓失敗可以處理

發送前檢查必填項及長度。逾時或拒絕後保留輸入，明確顯示失敗，提供受控重試及草稿或企業聯絡入口。收到確認前不顯示成功。型號、數量、目的地與選中產品保持一致，相應語言資料亦須屬於同一型號。

## 驗收證據

檢查空輸入、錯誤電郵、型號連續性、逾時、拒絕、提交編號不匹配、缺少回執、重複回應及成功。隨後在獲得許可且清楚標示測試訊息的條件下，驗證接收服務及業務電郵或處理流程。使用[詢盤驗收表](https://github.com/awesomellm/website-migration-kit/blob/main/inquiry-acceptance.zh-HK.csv) 記錄結果。

[四語言網站範例](https://github.com/awesomellm/multilingual-website-starter/blob/main/README.zh-HK.md) 生成本機草稿，並明確說明沒有發送。接入伺服器需要真實收件實作、交付監控及指定負責人。確認收件須與表單點擊、開啟郵件應用程式及複製操作分開統計。
