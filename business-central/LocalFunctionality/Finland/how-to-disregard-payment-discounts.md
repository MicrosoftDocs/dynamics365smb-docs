---
title: How to Disregard Payment Discounts
description: Use the disregard payment discount at full payment feature to accept payments when certain conditions are true.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: disregard payment discounts, payment discounts
ms.date: 02/12/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Disregard payment discounts

Use the disregard payment discount at full payment feature to accept payments when the following conditions are true:  

- Payment discount date < payment date <= payment tolerance date  
- Full amount >= payment amount >= full amount - payment discount  

## Disregard a payment discount  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Terms**, and then choose the related link.  
1. Select the line with the payment term for which you want to activate or deactivate payment discounts.  
1. Select the **Disreg. Pmt. Disc. at Full Pmt** checkbox to initiate activation for this feature. To deactivate, clear the checkbox.  

> [!NOTE]  
> When you apply one payment to multiple invoices, the feature to ignore payment discount at full payment isn't supported.  

## See also

- [Electronic Banking in Finland](electronic-banking-in-finland.md)
- [Generate Payment Files](how-to-generate-payment-files.md)
- [Defining Payment Methods](../../finance-payment-methods.md)  
- [Work with Payment Tolerances and Payment Discount Tolerances](../../finance-payment-tolerance-and-payment-discount-tolerance.md)
- [Set Up Bank Reference Files](how-to-set-up-bank-reference-files.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
