---
title: Review and Approve Expense Reports
description: Learn how managers and accountants review expense reports, decide VAT reclaim, approve or reject reports, and prepare them for posting.
author: brentholtorf
ms.topic: how-to
ms.date: 11/04/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: solsen
ms.search.form: 6939, 6980, 6981
ai-usage: ai-assisted
---

# Review and approve expense reports

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

When Expense Agent or the approval workflow is enabled, submitted expense reports require approval before posting. This article explains how managers review, approve, reject, or assign an interim approver to expense reports in [!INCLUDE[prod_short](../includes/prod_short.md)]. When VAT reclaim is enabled, accountants also review the VAT calculation and make the final reclaim decision.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## View reports awaiting approval

The page you use depends on whether Expense Agent is enabled. Set up approvers as expense users and link them to their [!INCLUDE[prod_short](../includes/prod_short.md)] user accounts. Learn more in [Set up expense approvers](expense-management-users-teams.md#set-up-expense-approvers).

### With Expense Agent enabled

Use the **Expense Reports** list and **Expense Report** card for agent-enabled approvals.

1. [!INCLUDE[open-search](../includes/open-search.md)], enter **Expense Reports**, and then choose the related link.
1. Find a report assigned to you with the **Pending Approval** or **Interim Approved** status.
1. Open the report.

The **Approve** and **Reject** actions appear only when you're signed in as the report's current approver. For a report with an interim approver, the interim approver acts first. The final approver can act after the status changes to **Interim Approved**.

### With the approval workflow and no Expense Agent

Use the manager pages for the approval workflow without Expense Agent.

1. [!INCLUDE[open-search](../includes/open-search.md)], enter **Manager Expense Reports**, and then choose the related link.

The list shows expense reports that are pending your review. If the approval workflow limits visibility, you see only reports assigned to you for approval.

## Review an expense report

1. Open the report from **Expense Reports** if Expense Agent is enabled, or from **Manager Expense Reports** if you use the approval workflow without Expense Agent.
1. Review the expense lines in the report subpage. Each line shows the expense category, date, amount, and description.
1. Review the **Rule Violations** FactBox on the right side for any policy violations.
1. Review the expense report totals and reimbursable amounts in the FactBoxes.
1. Use the **Expense** FactBox to access attached receipts.

## Assign an interim approver

If Expense Agent is enabled, you can assign one optional interim approver to a submitted expense report with the **Pending Approval** status. Assign the approver in [!INCLUDE[prod_short](../includes/prod_short.md)] on the **Expense Report** card, not the **Manager Expense Report** card. The interim approver reviews the report before the final approver.

The interim approver must differ from the report's expense user and the final approver. The interim approver must have **Can Approve** turned on and a linked [!INCLUDE[prod_short](../includes/prod_short.md)] user account for approvals. Their expense user email must match the **Authentication Email** on their **User Card**. Learn more in [Set up expense approvers](expense-management-users-teams.md#set-up-expense-approvers).

1. [!INCLUDE[open-search](../includes/open-search.md)], enter **Expense Reports**, and then choose the related link.
1. Open the submitted report with the **Pending Approval** status.
1. Select **Assign Interim Approver**.
1. Select the interim approver.
1. Confirm the assignment.

The read-only **Interim Approver No.** and **Final Approver No.** fields show the assigned approvers. Select **Show more** on the **General** FastTab if the fields aren't visible.

> [!IMPORTANT]
> The web and mobile apps don't currently support the complete interim approval flow. Assign interim approvers and complete both approval stages in [!INCLUDE[prod_short](../includes/prod_short.md)].

## Review VAT reclaim

When VAT reclaim is enabled, an accountant must approve or reject every VAT reclaim suggestion before posting. Report approval doesn't replace this tax review.

1. [!INCLUDE[open-search](../includes/open-search.md)], enter **Accountant Expense Reports**, and then choose the related link.
1. Find a report where **Has VAT Specification** is turned on.
1. Select the report, and then choose **VAT Specification**.
1. Compare the VAT specification lines with the receipt. Review the expense category and subcategory, VAT posting groups, VAT percentage, VAT base, VAT amount, reclaim percentage, reclaim reason, source, and confidence.
1. Correct the VAT details or reclaim percentage when needed.
1. For each VAT specification line, choose **Approve Reclaim** or **Reject Reclaim**. To approve all pending VAT rows for the selected expense report line, choose **Approve All Reclaims**.

An approved reclaim keeps the current reclaim percentage. A rejected reclaim sets the reclaim percentage and reclaim amount to zero. If the reclaim percentage changes, its status returns to **Pending** and requires another decision.

> [!IMPORTANT]
> [!INCLUDE [prod_short](../includes/prod_short.md)] blocks posting while any VAT specification line has the **Pending** reclaim status.

## Approve an expense report

Use **Expense Report** when Expense Agent is enabled, or **Manager Expense Report** for the approval workflow without Expense Agent.

1. Open the report assigned to you.
1. Choose **Approve**, and then confirm.

If you're the interim approver, the report status changes to **Interim Approved**, and the report moves to the final approver. It can't be posted yet. If you're the final approver, or if no interim approver is assigned, the report status changes to **Approved**. Only after final approval can the report be posted, subject to any remaining posting requirements, such as VAT reclaim review.

## Reject an expense report

If the report doesn't meet requirements, you can reject it. Use **Expense Report** when Expense Agent is enabled, or **Manager Expense Report** for the approval workflow without Expense Agent.

1. Open the report assigned to you.
1. Choose **Reject**, and then confirm.

The report status changes to **Rejected**. The **Reject** action doesn't open a comment dialog. For reports without an interim approver, you can use **Send back** in the web app to return a report with comments. Learn more in [Send back an expense report](expense-agent-approve-reports.md#send-back-an-expense-report).

If an interim approver is assigned, only the active approver can reject the report. For example, the final approver rejects the report after it reaches **Interim Approved**.

After corrections and resubmission, an assigned interim approver who is still eligible reviews the report again before the final approver.

## Reopen an approved or rejected report

If you use the approval workflow and need to reconsider a decision, you can reopen a report on the **Manager Expense Report** card. The **Reopen Approved** action isn't available on the agent-enabled **Expense Report** card.

1. On the **Manager Expense Report** card, choose **Reopen Approved**.

The report returns to **Pending Approval**. If an assigned interim approver is still eligible, reopening restarts the interim stage before final approval.

## Next steps

[Post expense reports](expense-management-post-reports.md)

## Related information

[Create and submit expense reports](expense-management-submit-report.md)  
[Set up expense management](expense-management-setup.md)  
[Manage employee expenses](expense-management-overview.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
