---
title: Create and Submit Expense Reports in Expense Agent
description: Learn how to create expense reports, add expenses, move expenses between reports, and submit reports for approval in Expense Agent.
author: brentholtorf
ms.topic: how-to
ms.date: 04/15/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: solsen
ai-usage: ai-generated
---

# Create and submit expense reports Expense Agent

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

Expense Agent allows grouping related expenses together so you can submit them for review and approval as a batch. For example, you might create a report for a specific business trip or a monthly set of expenses. You can add expenses when you create a report or add them later.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## Create an expense report

Expense reports are created automatically by the agent when you submit a new expense that falls outside the period covered by existing reports. No manual action is required to create a new expense report.

All expenses within the same period are automatically grouped into a single expense report. Once created, the report is available in the **Drafts** tab.

### Edit expense report name   

To rename an expense report: 

1. Select **More actions** :::image type="icon" source="../media/assist-edit-icon.png"::: on the report.
2. Choose **Edit report name**.  
3. Enter the new name and select **Save**.

## Add expenses to a report

You can add new receipts to an existing draft report:

1. On the **Drafts** tab, select the report.
1. Select **More actions** :::image type="icon" source="../media/assist-edit-icon.png":::, and then choose **Add receipt**.
1. Select the receipt you want to include.
1. Select **Open**.

After processing, the selected receipt is added as a new expense line in the report.  

## Move an expense to a different report

To move an expense to another report:

1. Open the expense report containing the expense by selecting **Review**.
1. Select the expense line, then choose **More actions** :::image type="icon" source="../media/assist-edit-icon.png":::.
1. Select **Move**.
1. In the **Move to open or new report** dialog:
   - Select an existing report and choose **Move here**, or  
   - Select **+ Create new report**, enter a name, select **Create**, and confirm **Move here**

The expense is removed from the current report and added to the selected report.   

## Submit an expense report

When the report is ready for approval:

1. Open the report by selecting **Review**.  
1. Review all expense lines to ensure accuracy.  
1. Select **Submit**.  
1. Confirm the submission when prompted.  

The report status changes to **Submitted**, and the approver is notified. The report becomes read-only during the review process and is moved from the **Drafts** tab to the **Submitted** tab.

> [!TIP]
> Before you submit, check for any policy warnings on your expenses. Resolving issues upfront helps speed up the approval process.

## Next steps

- [Approve or send back expense reports](expense-agent-approve-reports.md)  

## Related information

[Expense Agent overview](expense-agent-overview.md)  
[Approve or send back expense reports](expense-agent-approve-reports.md)  
[Edit and manage expenses](expense-agent-edit-expenses.md)  
[Expense and report statuses](expense-agent-statuses.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
