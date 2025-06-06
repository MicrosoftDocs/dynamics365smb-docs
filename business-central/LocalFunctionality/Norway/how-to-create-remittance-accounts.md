---
title: Create remittance accounts [NO]
description: Learn how to create a remittance account for each bank account used for payments in the Norwegian version of Business Central.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: create remittance account, remittance account, remittance payment, Norwegian version
ms.search.form: 15000000, 15000002, 15000004, 15000006, 15000007, 15000010
ms.date: 05/12/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Create remittance accounts in the Norwegian version

You must create one remittance account for each bank account where payment is made. If an account is used to make payments to both domestic and foreign vendors, this account must be created two times—one time for domestic payments and one time for foreign payments.  

> [!NOTE]  
> The currency used for the bank account should be the same as the currency that the bank is using for this account. Exchange rates are based on the currency of the account and calculations are based on this currency.  

## Create a remittance account  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Remittance Account Overview**, and then choose the related link.  
1. Choose the **New** action.  
1. On the **Remittance Account Card** page, on the **General** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Code**|Specify the identification code for the account.|  
    |**Remittance Agreement Code**|Select the agreement to which the account is connected.|  
    |**Type**|Select the payment type. Payment types include **Domestic**, **Foreign**, and **Payment Instr**.<br><br/> If remitting to Bankernes Betalingssentral (BBS), you can only choose **Domestic**.|  
    |**Description**|Specify the description of the account.|  
    |**Bank Account No.**|Specify the account number of the bank.|  
    |**BBS Agreement ID**|Specify the agreement identification for each account in BBS.|  

1. On the **Finance** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Account Type**|Select the account type. Account types include **Finance account** and **Bank account**.|  
    |**Account No.**|Specify the account number depending on your selection in the **Account Type** field.|  
    |**Charge Account No.**|Specify the account number for the charge account.|  
    |**Round off/Divergence Acc. No.**|Specify the finance account to post the difference as a result of rounding.|  
    |**Max. Round off/Diverg. (LCY)**|Specify the maximum rounding or difference, that settlement return accept.|  
    |**Document No. Series**|Specify the number series to be used when you post payments by using the remittance system.|  
    |**New Document Per.**|Select how documents are numbered when you post a payment:<br><br/>- **Date**: A new document is numbered according to the date the payment is made.<br/>- **Vendor**: A new document is numbered according to the vendor.|  
    |**Return Journal Template Name**|Specify the general journal template to which settled payments are transferred.|  
    |**Return Journal Name**|Specify the general journal batch to which settled payments are transferred.|  

1. On the **Domestic** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Recipient ref. 1- Invoice**|Specify the text that prints on the payment invoice.|  
    |**Recipient ref. 1- Cr. Memo**|Specify the text that prints on the payment invoice when deducting a credit memo.|  

1. On the **Foreign** FastTab, fill in the fields as described in the following table.  

   This information is only used if the account is used for foreign payments. For remittance to BBS, don't use this tab.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Currency Code**|Specify the currency that is used for the bank account.<br><br/> If the account is a currency account, the currency code must be given.|  
    |**Recipient Ref. Aboard**|Specify the template text that displays on the vendor card. This field is for foreign payments only.|  
    |**Futures Contract No.**|Specify the number of the futures contract, if the transaction is linked to a futures contract.|  
    |**Futures Contract Exch. Rate**|Specify the exchange rate for the futures contract.|  

1. Choose the **OK** button.  

## Related information

- [Electronic Payments to Vendors in Norway](electronic-payments-to-vendors-in-norway.md)
- [Set Up Remittance Agreements](how-to-set-up-remittance-agreements.md)
- [Set Up Vendors for Remittance](how-to-set-up-vendors-for-remittance.md)
- [Recipient Reference Codes](recipient-reference-codes.md)
- [Create Remittance Suggestions](how-to-create-remittance-suggestions.md)
- [Create Manual Remittance Payments](how-to-create-manual-remittance-payments.md)
- [Set Up Payment Line Information](how-to-set-up-payment-line-information.md)
- [Test Remittance Payments](how-to-test-remittance-payments.md)
- [Export Remittance Payments](how-to-export-remittance-payments.md)
- [Types of Payment Returns Files](types-of-payment-returns-files.md)
- [Import Payment Return Data](how-to-import-payment-return-data.md)
- [Delete Remittance Payment Orders](how-to-delete-remittance-payment-orders.md)
- [Remittance Errors](remittance-errors.md)
- [View Remittance Error Codes](how-to-view-remittance-error-codes.md)
- [Cancel Payments](how-to-cancel-payments.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
