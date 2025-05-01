---
title: Activate SEPA payments in the Dutch version
description: To submit vendor payments electronically in Single Euro Payments Area (SEPA) ISO 20022 payment format, you must set up prerequisites for enabling SEPA payments.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: submit vendor payments, SEPA, enable SEPA payments, electronic vendor payments, Dutch version, Netherlands
ms.date: 03/17/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Activate SEPA payments in the Dutch version

[!INCLUDE [activate-sepa-payments](../includes/BENL/activate-sepa-payments.md)]

## Enable transaction modes for SEPA  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Transaction Modes**, and then choose the related link.  
1. Select the transaction mode that you want to enable for SEPA, and then choose the **Edit** action.  
1. On the **Transaction Mode Card** page, on the **Paym. Proposal** FastTab, in the **Export Protocol** field, select the SEPA export protocol that you created, such as **SEPA ISO20022**.  
1. Choose the **OK** button.  

> [!NOTE]
> If you want to use *SEPA DD 008.001.08* and *SEPA CT Pain 001.001.09*, you must set up new reports *11000015* for Pain 008.001.08" and *11000014* for Pain 001.001.09" that can be selected in the **Export Protocol** field to export files in the corresponding formats.  

## Verify vendor payment transaction modes for SEPA  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then choose the related link.  
1. Select the vendor that you want to verify the transaction mode for, and then choose the **View** action.  
1. On the **Payments** FastTab, in the **Transaction Mode Code** field, verify that the vendor payment transaction mode is one that is enabled for SEPA.  
1. Choose the **OK** button.  

## Related information

- [Single EURO Payments Area (SEPA)](single-euro-payments-area-sepa-.md)  
- [Submit Vendor Payments Electronically in SEPA ISO 20022 Payment Format](how-to-submit-vendor-payments-electronically-in-sepa-iso-20022-payment-format.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
