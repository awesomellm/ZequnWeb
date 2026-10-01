# 询盘收到，需要明确确认

[English](INQUIRY-RECEIPTS.md) | [简体中文](INQUIRY-RECEIPTS.zh-CN.md) | [日本語](INQUIRY-RECEIPTS.ja.md) | [繁體中文](INQUIRY-RECEIPTS.zh-HK.md)

产品演示可以选中型号，将其带入表单，再生成可阅读的报价请求草稿。这证明草稿流程可用，不证明消息已经到达企业。ZequnWeb 的 2026 年 9 月 30 日本地记录明确说明，当时没有配置表单接收端，也没有发送真实或测试询盘。

## 区分状态

分别表示编辑、校验、生成草稿、传输、服务器收件和业务资格确认。打开邮件应用或复制草稿仍是草稿操作，普通 HTTP 200 也不等于收件。

接收服务可以返回以下虚构接口示例：

```json
{"submissionId":"demo-submission-01","received":true,"receiptId":"demo-receipt-01"}
```

只有 `submissionId` 与当前提交匹配、`received` 严格为真且 `receiptId` 有效，才接受收件确认。同一提交只记录一次；重复点击或网络重试不能增加询盘数量。是否属于有效业务机会还须另行判断，不能由收件直接推断。

## 让失败可以处理

发送前检查必填项及长度。超时或拒绝后保留输入，明确显示失败，提供受控重试及草稿或企业联系入口。收到确认前不显示成功。型号、数量、目的地与选中产品保持一致，相应语言资料也必须属于同一型号。

## 验收证据

检查空输入、错误邮箱、型号连续性、超时、拒绝、提交编号不匹配、缺少回执、重复响应和成功。随后在获得许可且清楚标注测试消息的条件下，验证接收服务和业务邮箱或处理流程。使用[询盘验收表](https://github.com/awesomellm/website-migration-kit/blob/main/inquiry-acceptance.zh-CN.csv) 记录结果。

[四语言网站示例](https://github.com/awesomellm/multilingual-website-starter/blob/main/README.zh-CN.md) 生成本地草稿，并明确说明没有发送。接入服务器需要真实收件实现、交付监控及指定负责人。确认收件须与表单点击、打开邮件应用及复制操作分开统计。
