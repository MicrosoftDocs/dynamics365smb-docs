---
title: Create and Submit Expense Reports
description: Learn how to create expense reports, add expenses, move expenses between reports, and submit reports for approval in Expense Agent.
author: brentholtorf
ms.topic: how-to
ms.date: 04/15/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: solsen
---

# Create and submit expense reports in Expense Agent

[!INCLUDE[prod_short](../includes/prod_short.md)]

*Expense reports* group related expenses together so you can submit them for review and approval as a batch. For example, you might create a report for a specific business trip or a monthly set of expenses. You can add expenses when you create a report or add them later.

## To create an expense report

1. In Expense Agent, select **Expense Reports** in the navigation.
1. Select **New Report**.
1. Enter a name for the report in the **Report Name** field.
1. Optionally, add a description in the **Description** field.
1. To add expenses now, select **Add Expenses** and choose the expenses you want to include.
1. Select **Create**.

The new report appears with a **Draft** status. You can continue to add or remove expenses before you submit it.

## To add expenses to a report

You can add expenses that have a status of **Open** to any draft report.

1. Open the expense report you want to add expenses to.
1. Select **Add Expenses**.
1. Select the expenses you want to include.
1. Select **Add**.

The selected expenses are added as report lines and their status changes to **AddedToReport**.

## To move an expense to a different report

If you added an expense to the wrong report, you can move it without removing and re-adding it manually.

1. Open the expense report that contains the expense you want to move.
1. Find the expense in the report lines and select it.
1. Select **Move**.
1. In the **Move Expense** dialog, choose the destination report.
1. Select **Confirm**.

The expense is removed from the current report and added to the destination report.

## To submit an expense report

When your report is ready for review, submit it to your approver.

1. Open the expense report you want to submit.
1. Review the report lines to make sure everything looks correct.
1. Select **Submit**.
1. Confirm the submission when prompted.

The report status changes to **Submitted**, and your approver is notified. You can't edit the report while it's under review.

> [!TIP]
> Before you submit, check for any policy warnings on your expenses. Resolving issues upfront helps speed up the approval process.

## Related information

- [Expense Agent overview](expense-agent-overview.md)
- [Approve or send back expense reports](expense-agent-approve-reports.md)
- [Edit and manage expenses](expense-agent-edit-expenses.md)
- [Expense and report statuses](expense-agent-statuses.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
