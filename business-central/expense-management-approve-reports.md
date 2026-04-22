---
title: Approve Expense Reports in Business Central
description: Learn how to review, approve, reject, and reopen submitted expense reports as a manager using Business Central expense management.
author: brentholtorf
ms.topic: how-to
ms.date: 04/21/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: solsen
ms.search.form: 6939, 6980, 6981
---

# Approve expense reports

When the approval workflow is enabled, submitted expense reports require manager review before they can be posted. This article explains how managers review, approve, or reject expense reports in [!INCLUDE[prod_short](includes/prod_short.md)].

## To view reports awaiting approval

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Manager Expense Reports**, and then choose the related link.

The list shows expense reports that are pending your review. If the approval workflow limits visibility, you see only reports assigned to you for approval.

## To review an expense report

1. On the **Manager Expense Reports** page, select a report and open it.
2. Review the expense lines in the report subpage. Each line shows the expense category, date, amount, and description.
3. Check the **Rule Violations** factbox on the right side for any policy violations.
4. Check the **Expense Report Statistics** factbox for totals and reimbursable amounts.
5. Use the **Documents** factbox to view attached receipts.

## To approve an expense report

1. On the **Manager Expense Report** card, choose the **Approve** action.

The report status changes to **Approved**. The report is now ready to be posted.

## To reject an expense report

If the report doesn't meet requirements, you can reject it and send it back to the submitter with a comment.

1. On the **Manager Expense Report** card, choose the **Reject** action.
2. Enter a comment explaining why the report is being rejected.

The report status changes to **Rejected**. The submitter can view your comment in the **Approver Comment** section on their expense report, make corrections, and resubmit.

## To reopen an approved or rejected report

If you need to reconsider a decision, you can reopen a report.

1. On the **Manager Expense Report** card, choose **Reopen Approved**.

The report returns to a status where it can be processed again.

## To set up approval workflows

Administrators configure approval workflows on the **Expense Agent Setup** page.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Expense Agent Setup**, and then choose the related link.
2. Turn on **Enable Approval Workflow**.
3. To configure approver assignments, open the **Expense Approvals Setup** page from the role center.

> [!NOTE]
> When the approval workflow is enabled, managers can only view reports where they're assigned as the approver, unless they have **Unlimited Expense Approval** permission.

## Related information

[Create and submit expense reports](expense-management-submit-report.md)  
[Post expense reports](expense-management-post-reports.md)  
[Set up expense management](expense-management-setup.md)  
[Manage employee expenses](expense-management-overview.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
