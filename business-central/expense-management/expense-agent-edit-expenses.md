---
title: Review and Edit Expenses in Expense Agent
description: Review and edit expense details in Expense Agent after AI receipt scanning or manual entry. Update the vendor, amount, category, and other fields.
author: brentholtorf
ms.topic: how-to
ms.date: 04/22/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: solsen
ai-usage: ai-generated
---

# Review and edit your expenses

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

After Expense Agent scans a receipt or you create an expense manually in [!INCLUDE[prod_short](../includes/prod_short.md)], take a moment to review the details and make any corrections. Accurate expenses make the approval process faster and help you stay compliant with company policy.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## Edit an expense

1. Open Expense Agent and go to the **Drafts** tab.
1. Select the expense you want to edit.
1. Update any of the following fields on the **Details** tab, as described in the following table.  

   | Fields | Description |
   | --- | --- |
   | **Merchant** | The merchant or business name. |
   | **Amount** | The expense total. |
   | **Date** | The transaction date. |
   | **Description** | An optional note about the expense. |
   | **Payment Means** | How the expense was paid, such as credit card or cash. |

1. On the **Categorization** tab, you can update how the expense is categorized for reporting and policy compliance purposes. In the **Category** field, specify the type of expense, such as meals, travel, or office supplies.
1. Select **Save Changes**.

> [!NOTE]
> You can edit an expense as long as it isn't submitted as part of an expense report. After you submit a report, you must wait for it to be sent back before you can make changes.

## Delete an expense

1. On the **Drafts** tab, select the expense you want to remove.
1. Select ![Shows the icon to show more option on a field](../media/show-more-options-icon.png) **Show more options**, and then choose **Delete**.
1. Confirm the deletion when prompted.

Deleting an expense also removes it from any draft expense report it was added to.

## View expense details

Select any expense on the **Drafts** tab and choose **Review** to open details. On the **Submitted** tab, you can also view by choosing **Details**. The detail view shows a summary that includes the following fields.

| Fields | Description |
| --- | --- |
| **Amount and currency** | The expense total. |
| **Policy status** | Whether the expense meets company policy, including any warnings or issues. |
| **Attachments** | The uploaded receipt image or file. |

Use the detail view to quickly check an expense in draft mode before you add it to a report.

## Resolve issues flagged by AI

Sometimes the AI can't fully process a receipt. For example, if it can't identify a location or required details are missing. When it can't fully process a receipt, the expense shows a summary of what needs attention.

1. Open the expense on the **Drafts** tab.
1. To understand what's missing, review the issue summary at the top of the expense details.
1. Expand the expense details to see the affected fields.
1. Fill in or correct the flagged information.
1. Select **Save Changes**.

After you save your corrections, AI runs the processing flow again. If everything is resolved, the expense is added to an expense report.

## Next steps

- [Create and submit expense reports](expense-agent-expense-reports.md)  

## Related information

[Manage expenses with Expense Agent](expense-agent-overview.md)  
[Upload and process receipts with Expense Agent](expense-agent-upload-receipts.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
