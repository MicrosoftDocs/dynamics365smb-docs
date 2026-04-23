---
title: Upload and Process Receipts with Expense Agent
description: Upload receipts to Expense Agent and let AI automatically detect the vendor, amount, date, and category so you can quickly create accurate expenses.
author: brentholtorf
ms.topic: how-to
ms.date: 04/22/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: solsen
---

# Upload receipts and let AI extract expense details

When you upload a receipt to Expense Agent in [!INCLUDE[prod_short](../includes/prod_short.md)], AI scans the image and suggests key details like the vendor name, total amount, transaction date, and expense category. You always review and confirm the extracted details before the expense is saved.

## To upload a receipt in the web app

1. Open [Expense Agent](https://app.expenses.dynamics.com/) and go to the **Expenses** page.
1. Select **Upload Receipt**.
1. Drag and drop your receipt file onto the upload area, or select **Browse** to choose a file from your device. You can also drop an entire folder of receipts to upload multiple files at once.
1. Wait for the upload to complete.

Expense Agent supports JPEG, PNG, and PDF files up to 10 MB, including printed invoices, digital PDFs, and handwritten receipts such as taxi slips.

> [!TIP]
> Expense Agent uses AI to process receipts, so it works well with handwritten receipts like taxi receipts, not just printed or digital ones. If a field isn't detected correctly, you can always edit it manually.

## Automatic currency conversion

When you upload a receipt in a foreign currency, Expense Agent automatically converts the amount to your company's local currency. All totals displayed in the web app use the local currency, so you can easily track spending across different countries.

## To send a receipt by email

You can also send receipts to Expense Agent by email. This is a convenient way to submit receipts from your phone or forward digital invoices directly.

1. Open your email application, such as Outlook.
1. Create a new email and address it to your organization's expense mailbox. Ask your administrator for the email address if you don't have it.
1. Attach one or more receipt files to the email. You can attach photos of paper receipts taken with your phone, PDF invoices, or scanned receipts.
1. Send the email.

Expense Agent processes each attachment and creates a separate expense for each receipt. You can review and edit the created expenses on the **Expenses** page.

After the upload, the expense status shows **Processing** while AI analyzes your receipt. When scanning finishes, the status changes to **Open** and the extracted details appear for your review. If the receipt passes validation, it's automatically added to a default expense report, so you don't need to create one manually.

## To review scanned receipt details

AI suggests values for the following fields based on what it detects in your receipt:

- **Vendor** — The business or merchant name.
- **Amount** — The total amount on the receipt.
- **Date** — The transaction date.
- **Category** — The expense category, such as meals, travel, or office supplies.

To review and adjust the details:

1. Open the expense from the **Expenses** page.
1. Check each suggested field and correct any values that don't look right.
1. Add a description or any extra details if needed.
1. Select **Save**.

> [!TIP]
> AI does a great job with clear, well-lit receipt photos. If a field isn't detected correctly, you can edit it manually. Blurry or folded receipts may need more manual corrections.

## Real-time processing status

Expense Agent keeps you updated as your receipt moves through processing:

| Status | What it means |
|---|---|
| **Processing** | AI is scanning your receipt and extracting details. |
| **Open** | Scanning is complete. The expense is ready for your review. |

You can continue working while receipts process — there's no need to wait on the page. Come back to the **Expenses** page to check on your uploads at any time.

## Related information

[Manage expenses with Expense Agent](expense-agent-overview.md)  
[Review and edit expenses in Expense Agent](expense-agent-edit-expenses.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
