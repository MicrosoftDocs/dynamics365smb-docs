---
title: Upload Receipts and Create Mileage Expenses
description: Upload receipts to Expense Agent for AI extraction or create mileage expenses with route-based distance calculation in the web app.
author: brentholtorf
ms.topic: how-to
ms.date: 04/23/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: solsen
ai-usage: ai-generated
---

# Upload receipts and create expenses in Expense Agent

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

When you upload a receipt to Expense Agent in [!INCLUDE[prod_short](../includes/prod_short.md)], AI scans the image and suggests key details like the merchant name, total amount, transaction date, and expense category. You always review and confirm the extracted details before the expense is saved. You can also create mileage expenses directly from the dashboard by entering your trip details.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## Upload a receipt in the web app

1. Open Expense Agent and go to **Expense reports**.
1. Drag and drop your receipt file onto the **Upload receipt (or drop here)** area, or select it to browse for a file on your device. You can also drop an entire folder of receipts to upload multiple files at once.
1. Wait for the upload to complete.

Expense Agent supports JPEG, PNG, and PDF files up to 10 MB, including printed invoices, digital PDFs, and handwritten receipts such as taxi slips.

> [!NOTE]
> As the web app reminds you: "Files are processed using AI. Review for accuracy." Always check the extracted details before submitting an expense.

> [!TIP]
> Expense Agent uses AI to process receipts, so it works well with handwritten receipts like taxi receipts, not just printed or digital ones. If a field isn't detected correctly, you can always edit it manually.

## Automatic currency conversion

When you upload a receipt in a foreign currency, Expense Agent automatically converts the amount to your company's local currency. When you look into created expense, you will see both original amounts and the local amount.

All totals in the expense report displayed in the web app use the local currency, so you can easily track spending across different countries.

> [!IMPORTANT]
> If the currency extracted from an uploaded receipt does not exist in Business Central, a validation error is shown during processing with the message: _The expense data could not be validated_.
>  
> When opening the expense, the **Amount** field is highlighted, displaying the error: _The currency value is not recognized_.  
>  
> To continue, contact your administrator to add the missing currency to the system, and then retry the process.

## Create a mileage expense


If you use your private vehicle for business purposes, you can create a mileage expense directly from the Expense Agent without uploading a receipt.

The travel distance is calculated based on the selected route, and the reimbursement amount is determined using your company’s configured mileage rate.

1. On the dashboard, choose **Create mileage expense** in the **Quick actions** panel.  
1. In the **Starting point** field, enter or search for the departure location.  
1. In the **Ending point** field, enter or search for the destination.  
1. Review the route displayed on the map. If multiple route options are available, select the one that reflects your actual journey.  

> [!NOTE]  
> Multiple route options are shown below the map in the left pane. You can select a route either from the list or directly on the map.

1. If the trip includes a same-day return, enable **Same-day round trip** to include the return distance.  
1. Review the **Mileage** and **Amount** fields.  
1. Select **Create**.  

The mileage expense is created and processed like any other expense and is automatically added to an expense report.

> [!NOTE]
> The **Create mileage expense** action is only available if your administrator configured at least one expense category with mileage enabled in [!INCLUDE[prod_short](../includes/prod_short.md)]. If the action appears dimmed, ask your administrator to enable mileage on an expense category.

> [!NOTE]  
> The expense category cannot be changed, as only mileage-type categories are supported in this flow.

> [!NOTE]  
> After the expense is created, the system captures a screenshot of the selected route and attaches it to the expense record.

## Send a receipt by email

You can also send receipts to Expense Agent by email. This is a convenient way to submit receipts from your phone or forward digital invoices directly.

1. Open your email application, such as Outlook.
1. Create a new email and address it to your organization's expense mailbox. Ask your administrator for the email address if you don't have it.
1. Attach one or more receipt files to the email. You can attach photos of paper receipts taken with your phone, PDF invoices, or scanned receipts.
1. Send the email.

Expense Agent processes each attachment and creates a separate expense for each receipt. You can review and edit the created expenses in **Expense reports**.

After the upload, the expense status shows **Processing** while AI analyzes your receipt. When scanning finishes, the status changes to **Open** and the extracted details appear for your review. If the receipt passes validation, it's automatically added to a default expense report, so you don't need to create one manually.

## Review scanned receipt details

AI suggests values for the following fields based on what it detects in your receipt:

- **Merchant** — The business or merchant name.
- **Amount** — The total amount on the receipt.
- **Date** — The transaction date.
- **Category** — The expense category, such as meals, travel, or office supplies.

To review and adjust the details:

1. Open the expense.
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

You can continue working while receipts process — there's no need to wait. Come back to **Expense reports** to check on your uploads at any time.

## Next steps

- [Review and edit your expenses](expense-agent-edit-expenses.md)  
- [Create and submit expense reports](expense-agent-expense-reports.md)  

## Related information

[Manage expenses with Expense Agent](expense-agent-overview.md)  
[Review and edit expenses in Expense Agent](expense-agent-edit-expenses.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
