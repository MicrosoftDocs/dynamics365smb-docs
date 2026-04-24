---
title: Create and Submit Expense Reports
description: Learn how to create expense reports, add expenses, review rule violations, and submit reports for approval in Business Central.
author: brentholtorf
ms.topic: how-to
ms.date: 04/22/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: solsen
ms.search.form: 6910, 6911, 6960, 6979, 6997
---

# Create and submit expense reports

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

An expense report groups related expenses into a single document that you submit for approval. After approval, the report is posted to the general ledger and reimbursement is processed. This article explains how to create, fill, and submit expense reports in [!INCLUDE[prod_short](../includes/prod_short.md)].

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## To create an expense report

1. [!INCLUDE[open-search](../includes/open-search.md)], enter **Expense Reports**, and then choose the related link.
2. Choose **New** to open a blank **Expense Report** card.
3. In the **Expense User No.** field, select the expense user.
4. In the **Description** field, enter a description of the report, such as "March travel expenses."
5. In the **Expense Report Date** field, enter the report date.
6. Optionally, set the **Posting Date** if it differs from the report date.

## To add expenses to a report

You can add existing released expenses to the report.

1. On the **Expense Report** card, choose **Get Expense Line** in the action bar.
2. Select the expenses you want to include, and then confirm.

The selected expenses appear as lines in the expense report subpage.

> [!TIP]
> You can also create an expense report directly from an individual expense by using the **Create Expense Report** action on the expense card.

## To add expense lines directly

If you don't use the expense agent, you can add expense lines directly to the expense report without creating individual expenses first. This is also useful when you want to add a line manually.

1. On the **Expense Report** card, in the report lines subpage, enter the expense details directly: category, amount, description, and other relevant fields.
2. If the category requires itemization, choose the **Itemizations** action to break down the line.
3. If the category requires participants, choose the **Participants** action to add attendees.

## To review rule violations

If expense rules are enabled, the system checks each expense line against the applicable rules. Violations appear in the **Rule Violations** factbox on the right side of the expense report.

Review all violations before submitting. While violations don't block submission, they're visible to the approver and may cause the report to be rejected.

## To release an expense report

Releasing the report locks it for editing and prepares it for submission.

1. On the **Expense Report** card, choose the **Release** action, or press <kbd>Ctrl</kbd>+<kbd>F9</kbd>.

To make changes after releasing, choose **Reopen** first.

## To submit an expense report for approval

If the approval workflow is enabled in the expense agent setup, you must submit the report for manager review.

1. On the **Expense Report** card, choose **Submit** in the **Request Approval** group.

The report status changes to **Pending Approval**. You can track the status in the **Status** field on the report.

If the report is rejected, you receive an approver comment explaining the reason. To make changes and resubmit:

1. Choose **Reopen Submitted** to change the status back to **Open**.
2. Make the needed changes.
3. Release and submit again.

## To add an attestation

If your organization requires an anti-corruption attestation, the **Attestation** section appears on the expense report.

1. Turn on **Anti-Corruption Attestation** to confirm the attestation.
2. Optionally, enter details in the **Anti-Corruption Description** field.

## To print expense reports

You can print reports for documentation or filing purposes.

1. On the **Expense Report** card, choose an action under **Report**:
   - **Expense Report Details** — A detailed breakdown of all expenses.
   - **Expense Report Summary Page** — A summary of totals.
   - **Expense Report Cover Page** — A cover page for the report.

## Related information

[Create and manage expenses](expense-management-create-expenses.md)  
[Approve expense reports](expense-management-approve-reports.md)  
[Post expense reports](expense-management-post-reports.md)  
[Manage employee expenses](expense-management-overview.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
