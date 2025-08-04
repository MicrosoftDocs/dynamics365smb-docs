---
title: Automatic Payments and Automatic Bills [IT]
description: Learn how to set up automatic payments and bills in the Italian version of Business Central.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: automatic payments, automatic bills, set up automatic payments, set up automatic bills, Italian version
ms.search.form: 12203, 12204
ms.date: 05/21/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up automatic payments and automatic bills in the Italian version

In [!INCLUDE[prod_short](../../includes/prod_short.md)], you can manage automatic payments and bills.  

To use automatic payments and automatic bills, you must set up the relevant information.  

## Add bank information for your company  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Company Information**, and then choose the related link.  
1. On the **Payments** FastTab, fill in the key fields as described in the following table.  

    |Field|Description|  
    |------------------------------------|---------------------------------------|  
    |**Payment Method**|Select the payment method for the type of payments made to or from this bank account. For example, for the bank account that is used for automatic payments made by customers, select a payment method for bank transfers.|  
    |**Bills For Collection Acc. No.**|Specify the general ledger account where bills for collection are credited.|  
    |**Bills For Discount Acc. No.**|Specify the general ledger account where bill discounts are debited.|  
    |**Bills Subj. to Coll. Acc. No.**|Specify the general ledger account where bills subject to collection are credited.|  
    |**Expense Bill Account No.**|Specify the general ledger account where expenses for bank receipts are posted.|  

1. Choose the **OK** button.  

> [!IMPORTANT]  
> Before you can export a vendor bill, you must select a payment format in the **Payment Export Format** field on the **Bank Account Card** page.  
>
> Before you can export a customer bill, you must select a payment format in the **SEPA Direct Debit Exp. Format** field on the **Bank Account Card** page.

## Set up automatic bills for sales and receivables

The following procedure describes how to set up automatic bills for sales and receivables, but the same steps also apply to setting up purchases and payables for using automatic payments.

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales & Receivables Setup**, and then choose the related link.  
1. On the **Bills** FastTab, in the **Temporary Bill List No.** field, select the temporary bill list number. Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Temporary Bill List No.**|Select the number series that are used for temporary bill lists.|  
    |**Recall Bill Description**|Specify the descriptive text that are used for recalled bills.|  
    |**Bank Receipts Risk Period**|Specify a date formula to calculate the risk period in days, such as **20D**.<br><br/> This is a reference for bank receipt closing. Customer bills are closed only at the end of the risk period that you specify here.|  

1. Choose the **OK** button.  

 Next, you must specify bill codes for those payment methods that you use for automatic payments and automatic bills.  

## Specify bill codes for a payment method  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Methods**, and then choose the related link.  
1. Select the payment method that you use for bank transfers to vendors, and then, in the **Bill Code** field, select a bill code.  
1. To create a bill code, in the **Bill Code** field, choose the field, and then choose the **New** action.  
1. On the **Bill** page, fill in the fields.

Now, you can process customer bills and vendor bills so that they're handled automatically.  

## Related information

- [Defining Payment Methods](../../finance-payment-methods.md)
- [Italy Local Functionality](italy-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
