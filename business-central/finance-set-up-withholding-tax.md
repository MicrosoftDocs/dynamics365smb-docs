---
title: Set up withholding tax
description: Learn how to configure Business Central so that you can record withholding taxes.
author: brentholtorf
ms.reviewer: bholtorf
ms.author: bholtorf
ms.topic: how-to
ms.search.keyword: prepayment
ms.search.form: 
ms.date: 03/16/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Set up withholding tax

Companies in some countries/regions must pay withholding tax to the government for certain services or vendor purchases. This article describes the steps to set up your [!INCLUDE [prod_short](includes/prod_short.md)] to do that.

[!INCLUDE [prod_short](includes/prod_short.md)] calculates withholding tax when you pay a vendor invoice, or when you post it, based on your setup. The tax amount is withheld from the payment and reduces the total amount owed to the vendor.

## Get started

To enable withholding tax calculation, open the **General Ledger Setup** page and turn on the **Enable Withholding Tax** toggle. 

Next, configure following setups:

- [Set up revenue types for withholding tax](#set-up-revenue-types-for-withholding-tax), including their sequences and posting groups.
- [Set up withholding tax posting groups](#set-up-withholding-tax-posting-groups) and apply them to items, general ledger accounts, and vendors that are subject to withholding tax.
- [Create a posting setup for withholding tax](#create-a-posting-setup-for-withholding-tax) using the product and business posting groups.
- [Calculate withholding tax for vendors](finance-withholding-tax.md), so that you include the appropriate vendors in tax calculations.
- [Set up general ledger accounts for withholding tax](#set-up-general-ledger-accounts-for-withholding-tax), so that tax amounts go to the correct accounts.

If needed, you can override the product posting group on purchase document lines using the **Withholding Tax Prod. Post. Group** field.

### Set up revenue types for withholding tax 

Revenue types categorize withholding tax entries and are used for Revenue types are used to categorize withholding tax (WHT) entries and are used for withholding tax certificates.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Withholding Tax Revenue Types**, and then choose the related link.
1. Fill in the fields as described in the following table.

   | Field | Description |
   |-------|-------------|
   | Code | Specifies the unique code for the revenue type. You can enter a maximum of 10 alphanumeric characters. |
   | Description | Specifies the description for the WHT revenue type. |
   | Sequence | Specifies the sequence in which you want to group revenue types. For example, a revenue type with sequence 0 is displayed before sequence 1. |

1. Choose the OK button.

### Set up withholding tax posting groups

To use withholding tax, you must set up the business posting groups and product posting groups for withholding tax so that the correct withholding tax calculations are made for each vendor. To learn more about posting groups, go to [Set up posting groups](finance-posting-groups.md). After you set up your posting groups, then next step is to combine them in a posting setup that helps ensure that the tax amounts go to the correct general ledger accounts.

> [!NOTE]
> As a prerequisite, you must set up source codes for withholding tax settlement on the Source Code Setup page. Learn more in [Setting Up Source Codes and Reason Codes for Audit Trails](finance-setup-trail-codes.md).

The following procedure describes how to set up product posting groups for withholding tax. The steps are the same for business posting groups.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Withholding Tax Prod. Post. Group**, and then choose the related link.
1. Fill in the fields as described in the following table.

   | Field | Description |
   |-------|-------------|
   | Code | Specify the code for the product posting group. You can enter a maximum of 10 alphanumeric characters. |
   | Description | Specify the description for the product posting group. You can enter a maximum of 50 alphanumeric characters. |
   
1. Choose the OK button.

### Create a posting setup for withholding tax

Finally, you must set up how these posting groups must be used when documents are posted.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Withholding Tax Posting Setup**, and then choose the related link.
1. Fill in the fields as described in the following table.

   | Field | Description |
   |-------|-------------|
   | Withholding Tax Bus. Post. Group | Specifies the business posting group code for withholding tax. |
   | Withholding Tax Prod. Post. Group | Specifies the product posting group code for withholding tax. |
   | Withholding Tax Calculation Rule | Specifies the calculation rule for withholding tax, which is used with the amount specified in the **Withholding Tax Minimum Invoice Amount** field. This rule helps identify the transactions for which you don't deduct withholding tax.<br><br> For example, if you select the **Less than** option here and enter **100** in the withholding tax **Withholding Tax Minimum Invoice Amount** field, withholding tax isn't deducted for transactions amounts that are less than **100**. |
   | Withholding Tax Minimum Invoice Amount | Specifies the minimum amount that you deduct withholding tax for. Withholding tax isn't deducted for amounts that are less than this value. |
   | Withholding Tax % | Specifies the withholding tax rate. Enter the rate without the percent sign. |
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

### Set up general ledger accounts for withholding tax

You must assign the product and business posting groups to the general ledger accounts that you want to use to register withholding tax. On the **G/L Account Card** page, fill in the **Withholding Tax Bus. Post. Group** and **Withholding Tax Prod. Post. Group** fields.

### Specify default posting groups for items and general ledger accounts

To ensure that documents include the correct posting groups for items and general ledger accounts, you can specify the groups to use by default. On the **Item Card** and **G/L Account Card** pages, fill in the **Withholding Tax Bus. Post. Group** and **Withholding Tax Prod. Post. Group** fields.

## Related information

[Calculate withholding tax for vendors](finance-withholding-tax.md)  
[Setting up finance](finance-setup-finance.md)  

[!INCLUDE [footer-banner](includes/footer-banner.md)]