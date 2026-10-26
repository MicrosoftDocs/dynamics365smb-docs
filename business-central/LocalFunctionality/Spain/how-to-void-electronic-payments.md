---
title: Void Electronic Payment Exports in Spain
description: Learn how to void an electronic payment export in Business Central for Spain, reset export details, and export the payments again before posting.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: void electronic payments, void payment file, cartera module, delete payment journal, Spanish version
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Void electronic payments

In the Spanish version of [!INCLUDE[prod_short](../../includes/prod_short.md)], you can void an electronic payment export. Voiding clears the export status, export file name, and document number on the affected payment journal lines. It doesn't delete the journal or its lines. You must export the payments again before posting.

Voiding an export in Business Central doesn't cancel a payment already submitted to your bank. Contact your bank if the file has already been submitted.

## Steps to void electronic payments  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Void Electronic Payments**, and then choose the related link.  
1. On the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |-----|-----------|  
    |**Bank Account No.**|Specify the bank account number from which the payments are voided.|  

1. Choose **OK**, and confirm that you want to void the electronic payments.

## Void electronic payments in the Cartera module  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Void PO - Export**, and then choose the related link.  
1. On the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |-----|-----------|  
    |**Payment Order No.**|Specify the payment order number from which the payments are voided.|  

1. Choose **OK**, and confirm the operation.

The payment order and its Cartera documents remain. Their electronic payment export status is cleared, and you must export the payment order again before posting.

## Related information

- [Set Up Bank Accounts for Electronic Payments](how-to-set-up-bank-accounts-for-electronic-payments.md)  
- [Pay Vendors by Using Electronic Payments](how-to-pay-vendors-by-using-electronic-payments.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
