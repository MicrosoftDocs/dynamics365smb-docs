---
title: Set up and post employee withholding tax
description: Learn how to configure employee withholding tax, post supported employee journal transactions, and review the tax entries that posting creates.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: employee, withholding tax, payment journal, general journal, expense
ms.search.form: Primary_39, 256, 5200, 6786, 6788, 6789, 6790, 6945
ms.date: 09/01/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Set up withholding tax for employee transactions

You can calculate withholding tax when you post employee transactions through general journals and payment journals. Withholding tax is calculated when all of the following conditions are met:

- Withholding tax is enabled on the **General Ledger Setup** page.
- The account or balancing account on the journal line is an employee.
- The employee exists and **Withholding Tax Exempt** is turned off.
- The journal line contains a **Withholding Tax Bus. Post. Group** and a **Withholding Tax Prod. Post. Group**.
- A matching withholding tax posting setup exists.
- The journal amount isn't zero.

The posting setup must contain a **Payable Withholding Tax Account Code** when the calculation produces a tax amount.

## Set up an employee for withholding tax

1. Open the **Employee Card** page.
1. In **Withholding Tax Bus. Post. Group**, select the business posting group for the employee.
1. Leave **Withholding Tax Exempt** turned off.
1. If needed, enter the **Withholding Tax Certificate No.** and **Withholding Tax Certificate Type**.

The certificate fields store information about the employee. They don't affect the calculation.

To learn more about posting groups, rates, thresholds, and accounts, go to [Set up withholding tax](finance-set-up-withholding-tax.md).

## Add posting groups to the journal line

When you select an employee in **Account No.**, [!INCLUDE [prod_short](includes/prod_short.md)] copies the employee's **Withholding Tax Bus. Post. Group** to the journal line. The product posting group must come from the transaction or an integration.

The calculation also recognizes an employee in **Bal. Account No.**. In that case, the journal line must already contain both withholding tax posting groups.

If you install the cloud-based **Expense Withholding Tax** app, selecting an **Expense Category** on a general journal line copies the category's **Withholding Tax Prod. Post. Group** to the line. The app requires **Expense Agent (Preview)** and the **Withholding Tax** app.

## Set up expense categories for withholding tax

On the **Expense Category Card** page, use the fields in the **Withholding Tax** group.

| Field | Description |
|-------|-------------|
| **Withholding Selection Mode** | Indicates whether the category is configured for a **Single Tax** or a **Tax Group**. |
| **Withholding Tax Prod. Post. Group** | Specifies the product posting group that is copied to the journal line. This field and its matching posting setup are required for both selection modes. |
| **Withholding Group Code** | Specifies the group of tax components to use when the selection mode is **Tax Group**. |

For a single tax, the business and product posting groups must identify a withholding tax posting setup. For a tax group, the category must also specify an existing group. Each group component must have a posting setup for the employee's business posting group.

Learn more in [Set up expense categories, rules, and policies](expense-management/expense-management-categories-rules.md#create-expense-categories).

## Choose calculation and threshold options

On the **Withholding Tax Posting Setup** page, use the following fields for employee transactions.

| Field | Behavior |
|-------|----------|
| **Calculation Base** | **Gross** calculates tax from the journal amount. **Net (Gross-up)** treats the entered amount as the net amount and calculates the related gross amount. |
| **Calculation Method** | **Simple** calculates a component from the current base. **Compound** adds the component tax to the base for the next component. |
| **Withholding Threshold Amount** | Specifies the minimum evaluated amount. A value of 0 turns off threshold checking. |
| **Withholding Threshold Base** | **Record/Line** evaluates the journal line. **Document** currently evaluates the journal line in the same way. **Category in Period** accumulates amounts for the same employee and posting groups. **Total in Period** accumulates amounts for the employee across posting groups. |
| **Withholding Threshold Period** | Specifies a month, quarter, calendar year, or fiscal period. If the field is blank, only the posting date is used. |
| **Threshold Category Code** | Identifies the expense category on threshold accumulator entries. This field is available with the **Expense Withholding Tax** app. |

For employee transactions, tax is calculated when the evaluated amount is equal to or greater than **Withholding Threshold Amount**. The **Withholding Threshold Type** field continues to support vendor scenarios, but it doesn't change the comparison for employee transactions.

## Post the employee transaction

1. Open a **General Journal** or **Payment Journal**.
1. Select **Employee** in the **Account Type** or **Bal. Account Type** fields, and then select the employee in the **Account No.** field.
1. Enter the transaction details. If you use **Expense Withholding Tax**, select an **Expense Category** to add the product posting group.
1. Post the journal.

Posting can create the following entries:

- An employee ledger entry that contains the withholding tax base and amount.
- A G/L entry for the **Payable Withholding Tax Account Code**.
- A withholding tax entry with **Party Type** set to **Employee** and the employee number.
- One G/L entry and withholding tax entry for each nonzero component in a withholding tax group.
- A threshold accumulator entry for period-based thresholds. The base is accumulated even when the threshold isn't reached.

Learn more in [View withholding tax entries](finance-withholding-tax-entries.md).

## Related information

[Set up withholding tax](finance-set-up-withholding-tax.md)  
[Record and reimburse employees' expenses](finance-how-record-reimburse-employee-expenses.md)  
[Work with general journals](ui-work-general-journals.md)  
[View withholding tax entries](finance-withholding-tax-entries.md)  
[Financial management](finance.md)  

[!INCLUDE [footer-banner](includes/footer-banner.md)]
