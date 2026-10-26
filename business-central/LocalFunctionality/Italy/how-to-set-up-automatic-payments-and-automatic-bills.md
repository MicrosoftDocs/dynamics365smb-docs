---
title: Set Up Automatic Payments and Bills for Italy
description: Learn how to configure bank accounts, bill posting groups, number series, and payment methods for automatic bills in Business Central for Italy.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: automatic payments, automatic bills, set up automatic payments, set up automatic bills, Italian version
ms.search.form: 12203, 12204
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Set up automatic payments and automatic bills in the Italian version

In [!INCLUDE[prod_short](../../includes/prod_short.md)], you can manage automatic payments and bills.  

To use automatic payments and automatic bills, you must set up the relevant information.  

## Set up bank accounts and bill posting groups

Enter your company's bank details on **Company Information** as needed. Configure each bank account that you use for bills separately.

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Bank Accounts**, and then choose the related link.
1. Open the bank account card, and enter the bank details.
1. Choose the **Bill Posting Group** action.
1. For each payment method, fill in the fields as described in the following table.

    |Field|Description|  
    |------------------------------------|---------------------------------------|  
    |**Payment Method**|Select the payment method that applies to customer bills for this bank account.|
    |**Bills For Collection Acc. No.**|Specify the general ledger account used to post bills for collection.|
    |**Bills For Discount Acc. No.**|Specify the general ledger account used to post bills for discount.|
    |**Bills Subj. to Coll. Acc. No.**|Specify the general ledger account used to post bills subject to collection.|
    |**Expense Bill Account No.**|Specify the general ledger account where expenses for bank receipts are posted.|  

1. Choose the **OK** button.  

> [!IMPORTANT]  
> Before you can export a vendor bill, you must select a payment format in the **Payment Export Format** field on the **Bank Account Card** page.  
>
> Before you can export a customer bill, you must select a payment format in the **SEPA Direct Debit Exp. Format** field on the **Bank Account Card** page.

## Set up automatic bills for sales and receivables

The following procedure configures customer bills. For vendor bills, open **Purchases & Payables Setup** and configure **Temporary Bill List No.** on the **Bills** FastTab. The risk-period and recall-description fields in the following table apply to sales and receivables.

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Sales & Receivables Setup**, and then choose the related link.  
1. On the **Bills** FastTab, in the **Temporary Bill List No.** field, select the temporary bill list number. Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Temporary Bill List No.**|Select the number series that are used for temporary bill lists.|  
    |**Recall Bill Description**|Specify the descriptive text that are used for recalled bills.|  
    |**Bank Receipts Risk Period**|Specify a date formula to calculate the risk period in days, such as **20D**.<br><br/> This is a reference for bank receipt closing. Customer bills are closed only at the end of the risk period that you specify here.|  

1. Choose the **OK** button.  

Next, specify bill codes for the payment methods that you use for automatic payments and automatic bills.

## Specify bill codes for a payment method  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Payment Methods**, and then choose the related link.  
1. Select the payment method that you use for bank transfers to vendors, and then, in the **Bill Code** field, select a bill code.  
1. To create a bill code, in the **Bill Code** field, choose the field, and then choose the **New** action.  
1. On the **Bill** page, fill in the fields.

Now, you can process customer bills and vendor bills so that they're handled automatically.  

## Related information

- [Defining Payment Methods](../../finance-payment-methods.md)
- [Italy Local Functionality](italy-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
