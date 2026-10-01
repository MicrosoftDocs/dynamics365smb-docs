---
title: Set up withholding tax
description: Learn how to configure Business Central so that you can record withholding taxes.
author: brentholtorf
ms.reviewer: bholtorf
ms.author: bholtorf
ms.topic: how-to
ms.search.keyword: prepayment
ms.search.form: Primary_6786, 6784, 6789, 6790, 5200, 118
ms.date: 09/01/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Set up withholding tax

Companies in some countries/regions must withhold tax from amounts that they pay to vendors or employees. This article describes how to set up withholding tax in [!INCLUDE [prod_short](includes/prod_short.md)].

[!INCLUDE [prod_short](includes/prod_short.md)] calculates vendor withholding tax when you post or pay a vendor invoice, based on your setup. For employees, withholding tax is calculated when you post a general journal line that contains the required withholding tax posting groups.

## Get started

To enable withholding tax calculation, open the **General Ledger Setup** page and turn on the **Enable Withholding Tax** toggle. 

Next, configure the following setups:

- [Set up revenue types for withholding tax](#set-up-revenue-types-for-withholding-tax), including their sequences and posting groups.
- [Set up withholding tax posting groups](#set-up-withholding-tax-posting-groups) and apply them to items, general ledger accounts, vendors, and employees that are subject to withholding tax.
- [Create a posting setup for withholding tax](#create-a-posting-setup-for-withholding-tax) using the product and business posting groups.
- [Calculate withholding tax for vendors](finance-withholding-tax.md), so that you include the appropriate vendors in tax calculations.
- [Set up employees for withholding tax](#set-up-employees-for-withholding-tax).
- [Set up general ledger accounts for withholding tax](#set-up-general-ledger-accounts-for-withholding-tax), so that tax amounts go to the correct accounts.

If needed, you can override the product posting group on purchase document lines using the **Withholding Tax Prod. Post. Group** field.

### Set up revenue types for withholding tax 

Revenue types categorize withholding tax entries and are used for withholding tax certificates.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Withholding Tax Revenue Types**, and then choose the related link.
1. Fill in the fields as described in the following table.

   | Field | Description |
   |-------|-------------|
   | Code | Specifies the unique code for the revenue type. You can enter a maximum of 10 alphanumeric characters. |
   | Description | Specifies the description for the withholding tax revenue type. |
   | Sequence | Specifies the sequence in which you want to group revenue types. For example, a revenue type with sequence 0 is displayed before sequence 1. |

1. Choose the OK button.

### Set up withholding tax posting groups

To use withholding tax, you must set up the business posting groups and product posting groups for withholding tax so that the correct withholding tax calculations are made for each vendor. To learn more about posting groups, go to [Set up posting groups](finance-posting-groups.md). After you set up your posting groups, then next step is to combine them in a posting setup that helps ensure that the tax amounts go to the correct general ledger accounts.

> [!NOTE]
> As a prerequisite, set up source codes for withholding tax settlement on the **Source Code Setup** page. Learn more in [Setting Up Source Codes and Reason Codes for Audit Trails](finance-setup-trail-codes.md).

The following procedure describes how to set up product posting groups for withholding tax. The steps are the same for business posting groups.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Withholding Tax Prod. Post. Group**, and then choose the related link.
1. Fill in the fields as described in the following table.

   | Field | Description |
   |-------|-------------|
   | Code | Specify the code for the product posting group. You can enter a maximum of 10 alphanumeric characters. |
   | Description | Specify the description for the product posting group. You can enter a maximum of 50 alphanumeric characters. |

1. Choose the OK button.

For business posting groups, you can also fill in the following fields.

| Field | Description |
|-------|-------------|
| **Party Applicability** | Specifies whether the group is intended for vendors, customers, or employees. |
| **Jurisdiction Code** | Specifies the tax jurisdiction for the group. |
| **Default Certificate Type** | Specifies the default certificate type for the group. |

### Create a posting setup for withholding tax

Finally, set up how to use these posting groups when you post documents.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Withholding Tax Posting Setup**, and then choose the related link.
1. Fill in the fields as described in the following table.

   | Field | Description |
   |-------|-------------|
   | Withholding Tax Bus. Post. Group | Specifies the business posting group code for withholding tax. |
   | Withholding Tax Prod. Post. Group | Specifies the product posting group code for withholding tax. |
   | Withholding Threshold Type | Specifies the comparison to use with the **Withholding Threshold Amount**. Employee journal transactions calculate withholding tax when the evaluated amount is equal to or greater than the threshold, regardless of the option in this field. |
   | Withholding Threshold Amount | Specifies the amount that must be reached before withholding tax is calculated. Enter 0 if you don't want to use a threshold. |
   | Withholding Tax % | Specifies the withholding tax rate. Enter the rate without the percent sign. |
   | Calculation Base | Specifies whether an employee journal amount is the **Gross** amount or a **Net (Gross-up)** amount. |
   | Calculation Method | Specifies whether each tax component uses the original base or compounds the tax into the base for the next component. The options are **Simple** and **Compound**. |
   | Withholding Threshold Base | Specifies how to evaluate the threshold for an employee transaction. The options are **Record/Line**, **Document**, **Category in Period**, and **Total in Period**. |
   | Withholding Threshold Period | Specifies the accumulation period for **Category in Period** and **Total in Period**. The options are **Month**, **Quarter**, **Year**, and **Fiscal Period**. |
   | Threshold Category Code | Specifies the expense category recorded on threshold accumulator entries. This field is available with the cloud-based **Expense Withholding Tax** app. |
   | Realized Withholding Type | Specifies when to realize the withholding tax for the transaction. You can realize the withholding when you post the invoice, post the payment, or at the earliest of the two. |
   | Prepaid Withholding Tax Account Code | Specifies the G/L account number used to post prepaid (advance) withholding tax for the selected combination of withholding tax business posting group and product posting group. |
   | Payable Withholding Tax Account Code | Specifies the G/L account number used to post payable withholding tax for the selected combination of withholding tax business posting group and product posting group. This account is used when withholding tax becomes due and payable to the tax authority, such as upon payment posting or when the withholding obligation is finalized. |
   | Bal. Prepaid Account Type | Specifies the type of balancing account for withholding tax transactions. |
   | Bal. Prepaid Account No. | Specifies the account number or bank name for withholding tax transactions, based on the type selected in the **Bal. Prepaid Account Type** field. |
   | Bal. Payable Account Type | Specifies the type of balancing account for purchase withholding tax transactions. |
   | Bal. Payable Account No. | Specifies the account number or bank name for purchase withholding tax transactions. This option is based on the type selected in the **Bal. Payable Account Type** field. |
   | Withholding Tax Report Line No. Series | Specifies the number series for the withholding tax report line. |
   | Revenue Type | Specifies the type of revenue. |
   | Purch. Withholding Tax Adj. Account No. | Specifies the account number on which to post purchase credit memo adjustments. |
   | Sequence | Specifies the sequence in which the withholding tax posting setup information displays in reports. |

1. Choose the **OK** button.

### Set up employees for withholding tax

1. Open the **Employee Card** page.
1. In **Withholding Tax Bus. Post. Group**, select the business posting group for the employee.
1. If the employee isn't subject to withholding tax, turn on **Withholding Tax Exempt**.
1. If needed, fill in the **Withholding Tax Certificate No.** and **Withholding Tax Certificate Type** fields.

The certificate fields store information about the employee. They don't change the withholding tax calculation.

### Set up a withholding tax group

A withholding tax group combines multiple product posting groups. Use a group when an employee expense requires more than one tax component.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Withholding Tax Groups**, and then choose the related link.
1. Choose **New**.
1. Enter a code and a description.
1. In the **Party Applicability** field, choose **Employee**.
1. Add a line for each withholding tax product posting group.
1. Enter a **Component Order**. Lower numbers are calculated first.
1. Verify that a withholding tax posting setup exists for each component.

For a compound calculation, tax from an earlier component is added to the base for the next component.

You select a withholding tax group for an employee transaction by assigning the group to an expense category. This option requires the cloud-based **Expense Withholding Tax** app and its **Expense Agent (Preview)** dependency. Learn more in [Set up expense categories, payment methods, and rules](expense-management/expense-management-categories-rules.md#create-expense-categories).

### Set up general ledger accounts for withholding tax

You must assign the product and business posting groups to the general ledger accounts that you want to use to register withholding tax. On the **G/L Account Card** page, fill in the **Withholding Tax Bus. Post. Group** and **Withholding Tax Prod. Post. Group** fields.

### Specify default posting groups for items and general ledger accounts

To ensure that documents include the correct posting groups for items and general ledger accounts, you can specify the groups to use by default. On the **Item Card** and **G/L Account Card** pages, fill in the **Withholding Tax Bus. Post. Group** and **Withholding Tax Prod. Post. Group** fields.

## Related information

[Calculate withholding tax for vendors](finance-withholding-tax.md)  
[Set up and post employee withholding tax](finance-withholding-tax-employees.md)  
[View withholding tax entries](finance-withholding-tax-entries.md)  
[Setting up finance](finance-setup-finance.md)  

[!INCLUDE [footer-banner](includes/footer-banner.md)]