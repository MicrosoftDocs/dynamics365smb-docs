---
title: Review and Edit Expenses in Expense Agent
description: Review and edit expense details in Expense Agent after AI receipt scanning or manual entry. Update the vendor, amount, category, and other fields.
author: brentholtorf
ms.topic: how-to
ms.date: 04/22/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: solsen
---

# Review and edit your expenses

After Expense Agent scans a receipt or you create an expense manually in [!INCLUDE[prod_short](includes/prod_short.md)], take a moment to review the details and make any corrections. Accurate expenses make the approval process faster and help you stay compliant with company policy.

## To edit an expense

1. Open Expense Agent and go to the **Expenses** page.
1. Select the expense you want to edit.
1. Update any of the following fields as needed:
   - **Vendor** — The merchant or business name.
   - **Amount** — The expense total.
   - **Date** — The transaction date.
   - **Category** — The type of expense, such as meals, travel, or office supplies.
   - **Description** — An optional note about the expense.
   - **Mileage** or **Per Diem** — If applicable to the expense type.
1. Select **Save**.

> [!NOTE]
> You can edit an expense as long as it hasn't been submitted as part of an expense report. Once a report is submitted, you must wait for it to be sent back before you can make changes.

## To resolve issues flagged by AI

Sometimes the AI flags an issue during processing — for example, a missing location or an unrecognized currency. When this happens, the expense shows an issue indicator.

1. Open the expense with the issue.
2. Review the summary at the top of the expense, which describes what needs attention.
3. Correct the flagged field (for example, select the correct location).
4. Select **Save**.

After you save your corrections, the AI processes the expense again. Once reprocessing completes, the expense is automatically added to an expense report.

## To delete an expense

1. Open the **Expenses** page and select the expense you want to remove.
1. Select **Delete**.
1. Confirm the deletion when prompted.

Deleting an expense also removes it from any draft expense report it was added to.

## To view expense details

Select any expense on the **Expenses** page to open its detail panel. The panel shows a summary that includes:

- **Amount and currency** — The expense total.
- **Policy status** — Whether the expense meets company policy, including any warnings or issues.
- **Attachments** — The uploaded receipt image or file.
- **Expense status** — The current status, such as **Open**, **Pending Report**, or **Added to Report**.

Use the detail panel to quickly check an expense before you add it to a report.

## To resolve issues flagged by AI

Sometimes the AI can't fully process a receipt — for example, if a location can't be identified or required details are missing. When this happens, the expense shows a summary of what needs attention.

1. Open the expense from the **Expenses** page.
1. Review the issue summary at the top of the expense detail panel to understand what's missing.
1. Expand the expense details to see the affected fields.
1. Fill in or correct the flagged information.
1. Select **Save**.

After you save your corrections, the AI re-runs the processing flow. If everything is resolved, the expense is automatically added to an expense report.

## Related information

[Manage expenses with Expense Agent](expense-agent-overview.md)  
[Upload and process receipts with Expense Agent](expense-agent-upload-receipts.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
