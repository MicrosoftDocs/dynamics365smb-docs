---
title: Upload and Process Receipts with Expense Agent
description: Upload receipts to Expense Agent and let AI automatically detect the vendor, amount, date, and category so you can quickly create accurate expenses.
author: brentholtorf
ms.topic: how-to
ms.date: 04/15/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: solsen
---

# Upload receipts and let AI extract expense details

When you upload a receipt to Expense Agent in [!INCLUDE[prod_short](includes/prod_short.md)], AI scans the image and suggests key details like the vendor name, total amount, transaction date, and expense category. You always review and confirm the extracted details before the expense is saved.

## To upload a receipt

1. Open Expense Agent and go to the **Expenses** page.
1. Select **Upload Receipt**.
1. Drag and drop your receipt file onto the upload area, or select **Browse** to choose a file from your device.
1. Wait for the upload to complete.

Expense Agent supports JPEG, PNG, and PDF files up to 10 MB.

After the upload, the expense status shows **Processing** while AI analyzes your receipt. When scanning finishes, the status changes to **Open** and the extracted details appear for your review.

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

[!INCLUDE[footer-include](includes/footer-banner.md)]
