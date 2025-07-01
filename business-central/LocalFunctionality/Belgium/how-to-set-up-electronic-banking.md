---
title: Set up electronic banking [BE]
description: Learn how to set up electronic banking to process domestic, international, SEPA, and non-Euro SEPA payments for vendors and customers in the Belgian version of Business Central.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: electronic banking setup, electronic banking, electronic payments, Belgian version
ms.search.form: 11308
ms.date: 04/03/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up electronic banking in the Belgian version

With electronic banking, you can make electronic payments to domestic, international, SEPA, and non-Euro SEPA vendors and customers. Before you can use electronic banking, you must set up the following information:  

- Electronic banking setup.  
- IBLC/BLWI codes - Learn more in [Set Up IBLC-BLWI Transaction Codes](how-to-set-up-iblc-blwi-transaction-codes.md).  

## Setup process

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Electronic Banking Setup**, and then choose the related link.  
1. On the **Electronic Banking Setup** page, fill in the fields as described in the following table.

   |Field|Description|  
   |---------------------------------|---------------------------------------|  
   |**Summarize Gen. Jnl. Lines**|Select to indicate if you want to group the payment journal lines for each vendor.|  
   |**Cut off Payment Message Texts**|Select to indicate if you want to truncate long payment messages. Messages are truncated if greater than 106 characters for domestic payments and fewer than 140 characters for international payments.|  

1. Choose the **OK** button.  

## Related information

- [Isabel website](https://go.microsoft.com/fwlink/?LinkId=210323)
- [Belgian Electronic Banking](belgian-electronic-banking.md)
- [Belgian Electronic Payments](belgian-electronic-payments.md)
- [Set Up IBLC-BLWI Transaction Codes](how-to-set-up-iblc-blwi-transaction-codes.md)
- [Set Up Vendors for Automatic Payment Suggestions](how-to-set-up-vendors-for-automatic-payment-suggestions.md)
- [Generate Payment Suggestions](how-to-generate-payment-suggestions.md)
- [Create Payment Journal Templates and Batches](how-to-create-payment-journal-templates-and-batches.md)
- [Test Electronic Payments](how-to-test-electronic-payments.md)
- [Print Payment Files](how-to-print-payment-files.md)
- [Summarizing Payment Lines and General Journal Lines](summarizing-payment-lines-and-general-journal-lines.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
