---
title: How to set up payment line information [NO]
description: Learn how to set up payment journal line information for remittance payments on the Payment Info page in the Norwegian version of Business Central.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: payment journal line, remittance payment, payment info, Norwegian version
ms.date: 05/14/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up payment line information in the Norwegian version

Payment journal line information for the remittance payment is set up on the **Payment Info** page.  

## Set up payment line information  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Journals**, and then choose the related link.  
1. Choose the **Payment Info** action.  
1. On the **Payment Info** page, on the **General** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Remittance Account Code**|Select the remittance account code.|  
    |**Remittance Agreement Code**|Specify the agreement code assigned to the account code.|  
    |**Remittance Type**|Specify the remittance type assigned to the account code. Remittance types include **Domestic** and **Foreign**.|  

1. On the **Domestic** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Recipient Ref. 1 – 3**|Specify the payment text, which is sent to the vendor.|  
    |**KID (Cust. id number)**|Specify the number sent to the vendor during payment.|  
    |**Our Account. No.**|Specify the account number for your company.|  
    |**External Document No.**|Specify the number of the external document.|  
    |**Payment Type Code Domestic**|Specify the payment type code that is assigned to the payment.|  

    > [!NOTE]  
    > The recipient reference and the KID number can't be entered for the same payment. If the KID is used, this is the only information that the vendor receives.  

1. On the **Foreign** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Recipient Ref. Abroad**|Specify the payment text that is sent to the vendor.|  
    |**Payment Type Code Abroad**|Specify the payment type code that is assigned to the payment.|  
    |**Check**|Specify whether a check must be issued.<br>* **No** - No check is issued.<br>* **Send to employer**- Check is issued and sent to the employer.<br>* **Send to beneficiary** - Check is issued and sent to the beneficiary.|  
    |**Urgent**|Select if the payment is urgent and should be treated as an urgent transfer.|  
    |**Agreed Exch. Rate**|Specify the exchange rate, which the bank agrees upon.|  
    |**Agreed With**|Specify who the agreement is entered with, if an exchange rate is agreed upon.|  
    |**Futures Contract No.**|Specify the future contract number that is used for this payment.|  
    |**Futures Contract Exch. Rate**|Specify the future contract exchange rate that is used for this payment.|  

1. Choose the **OK** button.  

## Related information

- [Electronic Payments to Vendors in Norway](electronic-payments-to-vendors-in-norway.md)
- [Set Up Remittance Agreements](how-to-set-up-remittance-agreements.md)
- [Create Remittance Accounts](how-to-create-remittance-accounts.md)
- [Set Up Vendors for Remittance](how-to-set-up-vendors-for-remittance.md)
- [Recipient Reference Codes](recipient-reference-codes.md)
- [Create Remittance Suggestions](how-to-create-remittance-suggestions.md)
- [Create Manual Remittance Payments](how-to-create-manual-remittance-payments.md)
- [Test Remittance Payments](how-to-test-remittance-payments.md)
- [Export Remittance Payments](how-to-export-remittance-payments.md)
- [Types of Payment Returns Files](types-of-payment-returns-files.md)
- [Import Payment Return Data](how-to-import-payment-return-data.md)
- [Delete Remittance Payment Orders](how-to-delete-remittance-payment-orders.md)
- [Remittance Errors](remittance-errors.md)
- [View Remittance Error Codes](how-to-view-remittance-error-codes.md)
- [Cancel Payments](how-to-cancel-payments.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
