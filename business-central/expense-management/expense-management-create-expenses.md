---
title: Create and Manage Expenses in Business Central
description: Learn how to record individual expenses, attach receipts, add itemizations and participants, and track per diem and mileage in Business Central.
author: brentholtorf
ms.topic: how-to
ms.date: 04/22/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: solsen
ms.search.form: 6974, 6975, 6988, 6989, 6992
---

# Create and manage expenses

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

When you incur a business expense, you record it in [!INCLUDE[prod_short](../includes/prod_short.md)] as an individual expense. Each expense captures the amount, date, category, and supporting details like receipts or merchant information. After you record expenses, you can add them to an expense report for submission.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

If you use Expense Agent, however, the agent does almost all of that for you. The expense user uploads a receipt file in the web app, and viola, the agent handles the rest. Learn more at [Upload receipts and create expenses in Expense Agent](expense-agent-upload-receipts.md).

This article describes how to enter an expense using [!INCLUDE [prod_short](../includes/prod_short.md)] only.

## Create an expense

1. [!INCLUDE[open-search](../includes/open-search.md)], enter **Expenses**, and then choose the related link.
2. Choose **New** to open a blank **Expense** card.
3. In the **Expense User No.** field, select the expense user who incurred the expense.
4. In the **Expense Category** field, choose the category that matches the type of expense.
5. In the **Expense Date** field, enter the date the expense occurred.
6. In the **Description** field, enter a brief description.
7. In the **Amount** field, enter the total amount in the expense currency.
8. In the **Merchant Name** field, enter the name of the vendor or merchant.
9. Optionally, fill in the **Receipt No.** field with the receipt or external document reference number.
10. In the **Currency Code** field, choose the currency if it differs from the local currency.

> [!TIP]
> If your organization uses expense rules, any violations appear in the **Rule Violations** FactBox on the right side of the page. Review and address violations before submitting the expense in a report.

## Attach a receipt

You can attach receipt images or PDF files to an expense for documentation purposes.

1. On the **Expense** card, the **Attachments** pane in the FactBox shows attached files.
2. Choose **Attachments** pane, choose **Documents**, and then choose **Upload Files**.

If you attach a PDF, a **Preview** FactBox displays the document directly on the expense card.

<!--## Add itemizations

For expenses that require itemization (based on the category), you can break down the total amount into line items.

1. On the **Expense** card, choose the **Itemizations** action.
2. Add line items with the relevant details and amounts.

## Add participants

For expense categories that require participants, such as business meals, you can list the attendees.

1. On the **Expense** card, choose the **Participants** action.
2. Add each participant with their name and type. -->

## To record a mileage expense

When the expense category requires mileage details, more fields appear in the **Travel** section.

1. Create an expense and select a mileage category.
2. In the **Starting Point** field, enter where the trip began.
3. In the **Ending Point** field, enter the destination.
4. In the **Mileage** field, enter the one-way distance.
5. If the trip was a round trip, turn on **Round Trip**. The **Total Mileage** field doubles the distance automatically.

The amount is calculated based on the mileage rate configured on the **Expense Agent Setup** page.

## To record a per diem expense

When the expense category requires per diem details, the **Travel** section shows date and time fields.

1. Create an expense and select a per diem category.
2. In the **Expense Location** field, choose the travel destination.
3. In the **Starting Date and Time** field, enter when the travel period began.
4. In the **Ending Date and Time** field, enter when it ended.
5. Choose the **Per Diem** action to view or edit the calculated per diem entries.

[!INCLUDE [prod_short](../includes/prod_short.md)] calculates the per diem amount based on the rates and rules configured on the **Expense Agent Setup** page.

## To release an expense

Before an expense can be added to an expense report, it must be released.

1. On the **Expense** card, choose the **Release** action, or press <kbd>Ctrl</kbd>+<kbd>F9</kbd>.

To make changes to a released expense, choose **Reopen** first.

## To create an expense report from an expense

You can quickly create a new expense report directly from an expense.

1. On the **Expense** card, choose **Create Expense Report**.

## Billing and reimbursement fields

The **Billing** FastTab on the **Expense Card** page lets you specify more details.

| Fields | Description |
| -- | -- |
| **Refundable** | Indicates whether the expense complies with company policy and is eligible for processing. Nonrefundable expenses aren't posted to the general ledger. The expense category sets the default. |
| **Reimbursement Type** | Specifies how to process the reimbursement based on the payment method. Expenses paid by the employee (cash) are reimbursable. Expenses paid by company card or bank account are expensed but not reimbursed. |
| **Reimbursable Amount** | The amount eligible for reimbursement. This amount is zero for expenses paid by company credit card, because the company already covered the cost. |
| **Payment Method Code** | The payment method used for this expense, such as **Cash**, **Credit Card**, or **Company Paid**. Changing the method recalculates the reimbursable amount. |
| **Billable** | Turn on this toggle to bill a customer for the expense. When you post the expense report, [!INCLUDE [prod_short](../includes/prod_short.md)] creates a sales invoice for the customer. |
| **Billable to Customer** | Specify which customer to bill. |

## To connect an expense to a project

You can link an expense to a project for tracking and billing purposes.

1. On the **Expense** card, in the **Dimensions** section, fill in the **Project No.** field.
2. In the **Project Task No.** field, select the relevant project task.

When you post the expense report, [!INCLUDE [prod_short](../includes/prod_short.md)] creates a project ledger entry and the standard expense and employee ledger entries.

## Understand refundable versus reimbursable

The terms *refundable* and *reimbursable* describe different aspects of an expense:

- **Refundable** means the expense complies with company policy and is accepted as a valid business expense. The default value comes from the expense category, but you can change it on individual expenses if you have permission. Nonrefundable expenses aren't posted to the general ledger, but they must still be tracked in the system. For example, if an employee uses a company card for a nonbusiness purchase, the amount needs to be recorded and potentially recovered from the employee.
- **Reimbursable** means the employee paid out of pocket and is eligible to receive money back. An expense paid with a company credit card or bank account is refundable but not reimbursable, because the company already covered the cost.

When itemization is required, individual subcategory lines can have different refundable settings. For example, a hotel receipt might have the room charge as refundable while a minibar charge is marked as nonrefundable. The employee is reimbursed only for the refundable portion.

## Related information

[Create and submit expense reports](expense-management-submit-report.md)  
[Set up expense categories and rules](expense-management-categories-rules.md)  
[Manage employee expenses](expense-management-overview.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
