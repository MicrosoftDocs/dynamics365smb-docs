---
title: Create and Submit Expense Reports
description: Learn how to create expense reports, add expenses, review rule violations, and submit reports for approval in Business Central.
author: brentholtorf
ms.topic: how-to
ms.date: 09/26/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: solsen
ms.search.form: 6910, 6911, 6960, 6979, 6997
ai-usage: ai-assisted
---

# Create and submit expense reports

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

An expense report groups related expenses into a single document that you submit for approval. After approval, the report is posted to the general ledger and reimbursement is processed. This article explains how to create, fill, and submit expense reports in [!INCLUDE[prod_short](../includes/prod_short.md)].

> [!NOTE]
> Approvals in Expense Management are optional when the agent is not enabled, and can be configured on the **Expense Agent Setup** page.  
> If the Expense Agent is enabled, approvals are handled automatically through the web app using the agent’s built-in approval process.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## Create an expense report

1. [!INCLUDE[open-search](../includes/open-search.md)], enter **Expense Reports**, and then choose the related link.
1. Choose **New** to open a blank **Expense Report** card.
1. In the **Expense User No.** field, select the expense user.
1. In the **Description** field, enter a description of the report, such as "March travel expenses."
1. In the **Expense Report Date** field, enter the report date.
1. Optionally, set the **Posting Date** if it differs from the report date.

## Add expenses to a report

You can add existing released expenses to the report.

1. On the **Expense Report** card, choose **Get Expense Line** in the action bar.
1. Select the expenses you want to include, and then confirm.

The selected expenses appear as lines on the **Lines** FastTab.

> [!NOTE]
> This functionality is available only when the agent is enabled.  
> If the agent is not enabled, expenses can be entered only directly on the expense report lines.

> [!TIP]
> You can also create an expense report directly from an individual expense by using the **Create Expense Report** action on the expense card.

## Add expense lines directly

If you don't use Expense Agent, you can add expense lines directly to the expense report without creating individual expenses first. This method is also useful when you want to add a line manually.

1. On the **Expense Report** card, in the report lines subpage, enter the expense details directly: category, amount, description, and other relevant fields.
1. If the category requires itemization, choose the **Itemizations** action to break down the line.
1. If the category requires participants, choose the **Participants** action to add attendees.
1. If the category is per diem type, enter the **Expense Location**, **Starting** and **Ending Date and Time** to the expense line, and choose the **Per diem** action to adjust per diem lines.
1. If the category is mileage type, enter the **Starting Point**, **Ending Point**, **Vehicle Type** if your organization uses vehicle-specific rates, and **Mileage**. If you entered the one-way distance for a round trip, turn on **Round Trip**.

> [!NOTE]
> All rules existing for expenses apply to the expense report lines, i.e., rule violations, justification, currencies...

Business Central selects a mileage rate for the **Expense Date**, **Vehicle Type**, and expense currency. If no mileage rate setup record matches, Business Central uses **Standard Rate of Mileage**. Learn more in [Set up mileage rates for expense management](expense-management-mileage-rate-setup.md).

## Review rule violations

If expense rules are enabled, [!INCLUDE [prod_short](../includes/prod_short.md)] checks each expense line against the applicable rules. Violations appear in the **Rule Violations** FactBox.

Review all violations before you submit the report. While violations don't block submission, they show to the approver and might cause the report to be rejected.

## Link a travel request

On the **Expense Report** card, select an approved request in **Travel Request No.** The expense user on the report must be listed as a traveler on the request. Only refundable lines are linked. Use the **Travel Request** action on the report or line to open the request.

When you assign the request, [!INCLUDE [prod_short](../includes/prod_short.md)] compares the new refundable amount plus previously posted spending with the request's total expected amount in local currency. If the total is exceeded, you receive a nonblocking notification and can continue processing.

Learn more in [Manage travel requests](expense-management-travel-requisitions.md).

## Release an expense report

Releasing the report locks it for editing and prepares it for submission.

1. On the **Expense Report** card, choose the **Release** action, or press <kbd>Ctrl</kbd>+<kbd>F9</kbd>.

To make changes after you release a report, choose **Reopen**.

## Submit or resubmit an expense report for approval

1. On the **Expense Report** card, choose **Submit**.

The report status changes to **Pending Approval**. You can track the status in the **Status** field on the report. If the report is rejected, you receive an approver comment that explains why. To make changes and resubmit:

1. Choose **Reopen** to change the status back to **Open**.
1. Make the needed changes.
1. Release and submit again.

## Add an attestation

If your organization requires an anti-corruption attestation, the **Attestation** section appears on the expense report.

1. Turn on **Anti-Corruption Attestation** to confirm the attestation.
1. Optionally, enter details in the **Anti-Corruption Description** field.

## Print expense reports

You can print reports for documentation or filing purposes.

1. On the **Expense Report** card, select an action under **Report** to generate different report views:

   - **Expense Report Details** provides a detailed breakdown of all expenses in the report, including categories, dates, merchants, payment methods, amounts, and other related information.
   - **Expense Report Summary Page** displays a summarized view with grouped totals and category-specific details, and includes designated areas for signatures.
   - **Expense Report Cover Page** generates a cover page with key information such as the employee name, submitted to and approved by fields, expense report date, and total amounts.

> [!TIP]
> In some jurisdictions, regulatory authorities require a specific expense report cover page that includes defined fields, formats, and signatures.  
>  
> The **Expense Report Summary Page** report is designed to be flexible and includes all relevant information by default. You can easily customize the report layout to match local regulatory requirements or replicate an exact required document format.

## Next steps

[Approve expense reports](expense-management-approve-reports.md)

## Related information

[Create and manage expenses](expense-management-create-expenses.md)  
[Manage travel requests](expense-management-travel-requisitions.md)
[Set up mileage rates for expense management](expense-management-mileage-rate-setup.md)
[Post expense reports](expense-management-post-reports.md)  
[Manage employee expenses](expense-management-overview.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
