---
title: Create and Manage Expenses in Business Central
description: Learn how to record individual expenses, attach receipts, add itemizations and participants, and track per diem and mileage in Business Central.
author: brentholtorf
ms.topic: how-to
ms.date: 04/21/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: solsen
ms.search.form: 6974, 6975, 6988, 6989, 6992
---

# Create and manage expenses

When you incur a business expense, you record it in [!INCLUDE[prod_short](includes/prod_short.md)] as an individual expense. Each expense captures the amount, date, category, and supporting details like receipts or merchant information. After you record expenses, you can add them to an expense report for submission.

## To create an expense

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Expenses**, and then choose the related link.
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
> If your organization uses expense rules, any violations appear in the **Rule Violations** factbox on the right side of the page. Review and address violations before submitting the expense in a report.

## To attach a receipt

You can attach receipt images or PDF files to an expense for documentation purposes.

1. On the **Expense** card, the **Documents** factbox on the right side shows attached files.
2. Choose the factbox to open the document attachment list and add files.

If you attach a PDF, a **Preview** factbox displays the document directly on the expense card.

## To add itemizations

For expenses that require itemization (based on the category), you can break down the total amount into line items.

1. On the **Expense** card, choose the **Itemizations** action.
2. Add line items with the relevant details and amounts.

## To add participants

For expense categories that require participants (such as business meals), you can list the attendees.

1. On the **Expense** card, choose the **Participants** action.
2. Add each participant with their name and type.

## To record a mileage expense

When the expense category requires mileage details, additional fields appear in the **Travel** section.

1. Create an expense and select a mileage category.
2. In the **Starting Point** field, enter where the trip began.
3. In the **Ending Point** field, enter the destination.
4. In the **Mileage** field, enter the one-way distance.
5. If the trip was a round trip, turn on **Round Trip**. The **Total Mileage** field doubles the distance automatically.

The amount is calculated based on the mileage rate configured in the expense agent setup.

## To record a per diem expense

When the expense category requires per diem details, the **Travel** section shows date and time fields.

1. Create an expense and select a per diem category.
2. In the **Expense Location** field, choose the travel destination.
3. In the **Starting Date and Time** field, enter when the travel period began.
4. In the **Ending Date and Time** field, enter when it ended.
5. Choose the **Per Diem** action to view or edit the calculated per diem entries.

The system calculates the per diem amount based on the rates and rules configured in the setup.

## To release an expense

Before an expense can be added to an expense report, it must be released.

1. On the **Expense** card, choose the **Release** action, or press <kbd>Ctrl</kbd>+<kbd>F9</kbd>.

To make changes to a released expense, choose **Reopen** first.

## To create an expense report from an expense

You can quickly create a new expense report directly from an expense.

1. On the **Expense** card, choose **Create Expense Report** under **Functions**.

This creates a new expense report and adds the current expense to it. The action is available only when the expense status is **Released**.

## Billing and reimbursement fields

The **Billing** section on the expense card lets you specify additional details:

- **Billable** — Turn on if the expense should be billed to a customer.
- **Billable to Customer** — Specify which customer to bill.
- **Refundable** — Indicates whether the expense is reimbursable.
- **Reimbursement Type** — Specifies how the reimbursement is processed.
- **Reimbursable Amount** — The amount eligible for reimbursement based on policy.
- **Payment Method Code** — The payment method used for this expense.

## Related information

[Create and submit expense reports](expense-management-submit-report.md)  
[Set up expense categories and rules](expense-management-categories-rules.md)  
[Manage employee expenses](expense-management-overview.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
