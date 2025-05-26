---
title: Cancel payments [NO]
description: Learn how the Norwegian enhancements of Business Central allow you to cancel payments and remittances received.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: payment cancellation, cancel payment, cancel remittance, remittance cancellation, Norwegian version
ms.search.form: 15000000, 15000002, 15000004, 15000006, 15000007, 15000010
ms.date: 05/12/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Cancel payments in the Norwegian version

[!INCLUDE[prod_short](../../includes/prod_short.md)] includes Norwegian enhancements that allow you to cancel payments. If the payment is sent to the bank, it's necessary to contact the bank to cancel the remittance that was received.  

- A payment order can be canceled if the payments aren't received by the bank and a new remittance must be made. You can also cancel a payment order if you don't want to transfer the payments to the bank, for example if the payments are incorrect. Only open payment orders can be canceled.  

- An individual payment can be canceled if the payment can't be processed by the bank and a new remittance has to be made. You can also cancel a payment if you don't want to process the payment. Settled payments can't be canceled.  

## Cancel a payment order  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Remittance Payment Order**, and then choose the related link.  
1. Select the payment order, choose the **Export** action, and then choose the **Cancel Payment Order** action.  
1. Choose the **Yes** button.  

## Cancel a payment  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Waiting Journal**, and then choose the related link.  
1. Select the payment, and then choose the **Cancel Payment** action.  
1. Choose the **Yes** button.  

## Related information

- [Electronic Payments to Vendors in Norway](electronic-payments-to-vendors-in-norway.md)
- [Set Up Remittance Agreements](how-to-set-up-remittance-agreements.md)
- [Create Remittance Accounts](how-to-create-remittance-accounts.md)
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

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
