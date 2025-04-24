---
title: Archive Payment Slips [FR]
description: Learn how to separate a payment slip from the active payment slips by archiving it in the French version of Business Central.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: archive payment slip, French version
ms.search.form: 10868, 10870, 10860, 10861, 10864, 10865, 10866, 10871, 10872, 10873, 10874, 10877, 10878, 10879, 10869, 10867, 10882, 10880
ms.date: 04/14/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Archive payment slips in the French version

After a payment slip is processed, you can separate it from the active payment slips by archiving it.  

You can archive the payment slip by using the following methods:  

- Manually – for individual payment slips.  
- Automatically – for a batch of payment slips.  

## Archive a payment slip  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Slips**, and then choose the relevant link.  
1. Select the relevant payment slip, and then choose the **Edit** action.  
1. On the **Payment Slip** page, choose the **Archive** action.  
1. Choose the **Yes** button to archive the payment slip.  

   > [!NOTE]  
   > If the current status of the payment slip doesn't allow archiving, a message displays.  

## Archive a batch of payment slips  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Archive Payment Slips**, and then choose the relevant link.  
1. On the **Archive Payment Slips** page, on the **Payment Header** FastTab, select the appropriate filters.  
1. Choose the **OK** button.  

The payment slips are archived.  

> [!NOTE]  
> This batch job only archives payment slips that have the **Archiving Authorized** checkbox selected on the **Payment Status** page. Learn more in [Set Up Payment Statuses](/dynamics365/business-central/LocalFunctionality/France/how-to-set-up-payment-classes).  

## Related information

- [Payment Management](payment-management.md)
- [Set Up Payment Classes](how-to-set-up-payment-classes.md)
- [Set Up Payment Statuses](/dynamics365/business-central/LocalFunctionality/France/how-to-set-up-payment-classes)
- [Set Up Payment Steps](/dynamics365/business-central/LocalFunctionality/France/how-to-set-up-payment-classes)
- [Set Up Payment Addresses](how-to-set-up-payment-addresses.md)
- [Create Payment Slips](how-to-create-payment-slips.md)
- [Post Payment Slips](how-to-post-payment-slips.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
