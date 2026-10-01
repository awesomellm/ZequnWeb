# An inquiry is received only after confirmation

[English](INQUIRY-RECEIPTS.md) | [简体中文](INQUIRY-RECEIPTS.zh-CN.md) | [日本語](INQUIRY-RECEIPTS.ja.md) | [繁體中文](INQUIRY-RECEIPTS.zh-HK.md)

A product demo can select a model, carry it into a form and produce a readable request-for-quotation draft. That proves the draft workflow. It does not prove that a message reached the business. ZequnWeb's 30 September 2026 local record explicitly says the form endpoint was not configured and no real or test inquiry was sent.

## Define separate states

Use distinct states for editing, validation, draft creation, transport, server receipt and business qualification. Opening a mail app or copying a draft remains a draft action. An ordinary HTTP 200 alone is not a receipt.

A receiving service can return a response like this fictional contract example:

```json
{"submissionId":"demo-submission-01","received":true,"receiptId":"demo-receipt-01"}
```

Accept the receipt only if `submissionId` matches the submitted request, `received` is exactly true, and `receiptId` is valid. Record receipt once for a submission; repeated button clicks or network retries must not multiply leads. Qualification is another business decision and should not be inferred from receipt.

## Make failures usable

Validate required fields and lengths before sending. Preserve entered data on timeout or rejection. Show an explicit failure, allow a controlled retry, and offer a draft or business contact fallback. Never display a success state before confirmation. Keep model, quantity and destination consistent with the chosen product; translated downloads must refer to that same model.

## Acceptance evidence

Test blank input, malformed email, selected-model continuity, timeout, rejected response, wrong submission id, absent receipt id, duplicate response and success. Then verify the receiving service and the business mailbox or workflow with permission and a clearly labelled test message. Use the [inquiry acceptance worksheet](https://github.com/awesomellm/website-migration-kit/blob/main/inquiry-acceptance.csv).

The [four-language starter](https://github.com/awesomellm/multilingual-website-starter/blob/main/README.md) intentionally generates a local draft and clearly says it was not sent. Extending it with a server requires a real receiving implementation, delivery monitoring and a defined owner. Track confirmed receipt separately from form clicks, mail app opens and copies.
