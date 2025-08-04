---
title: Electronic Payments to Vendors in Norway
description: Learn about the Norwegian enhancements that simplify vendor payments, enabling invoice searches, bank transactions, status updates, and electronic payments in various formats.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: vendor payments, invoice searches, electronic payments, telepay, remittance payment, Norwegian version
ms.date: 05/12/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Electronic payments to vendors in Norway

[!INCLUDE[prod_short](../../includes/prod_short.md)] includes Norwegian enhancements for automatically making payments to vendors. This reduces errors that occur from manual data entry. You can use this functionality to perform the following operations:  

- Search invoices that are due based on different conditions.  
- Send payments to the bank.  
- Receive messages from the bank on the status of payments.  
- Receive paid transaction information to be posted.  

You can make electronic payments using the following formats:  

- TelePay  
- Remittance payment  

## Electronic payment process

The following steps show how electronic payments are processed:  

1. The payment proposal is run in the electronic payments feature and transferred to the bank by using the bank’s software.  
1. The bank's software receives the payments and transfers payments to the bank.  
1. The bank receives the payments and sends the first-time return receipt to [!INCLUDE[prod_short](../../includes/prod_short.md)] using the bank's software.  
1. The bank executes the payments and sends the settlement return (second-time return receipt) to [!INCLUDE[prod_short](../../includes/prod_short.md)] using the bank's software where the payments are posted.  

## Vendor payment requirements

If the payment transactions don't fulfill the requirements, an error message appears and you can't create a payment file for transfers to the bank. The following criteria must be met when you process payments to vendors:  

- The payment transaction must be positive or zero. A payment transaction must transfer a positive amount (or zero) to the payment receiver. This means that deducting a credit memo requires an invoice with the same or higher amount in the same payment transaction. Money can't be deducted from the vendor's account.  

- A credit memo must be applied with the invoice. Generally a credit memo doesn't contain a Kunde ID (KID). You can't pay a credit memo in a payment transaction with invoices that contain a KID. This is because payments are usually split into transactions with or without a KID. This means that if a credit memo without a KID is paid with an invoice in the same payment transaction, the invoice must be paid without a KID, and the recipient reference number must be used instead.  

- If the invoice and credit memo are paid in the same payment transaction, the payment must occur on the same date using the same currency and exchange rate.  

## Related information

- [Norway Local Functionality](norway-local-functionality.md)   
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
- [Cancel Payments](how-to-cancel-payments.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
