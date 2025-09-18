---
title: Create an advance letter from an order  
description: This article describes how to create an advance letter from a sales or purchase order in the Czech version.  
author: v-pejano  
ms.reviewer: v-pejano  
ms.author: v-pejano  
ms.service: dynamics-365-business-central  
ms.topic: article  
ms.search.keywords: Czech, Advance Payments, Localization  
ms.date: 09/17/2025  
ms.custom: bap-template
---

# Create an advance letter from an order

You can also create an advance letter directly from a sales or purchase order. To do so, follow these steps:

1. Choose the ![Lightbulb icon](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders** or **Purchase Orders**, and then select the related link.  
2. Create a new order.
3. After you fill in the required fields and lines, choose the **Create Advance Letter** action.
4. In the dialog that opens, select the **Advance Letter Code** (linked to the Advance Letter Templates table) and the method of calculating the advance.  

   > [!NOTE]
   > You can either enter a percentage or a specific amount for the advance.  
   >
   > If you select **Suggest by Line**, the advance letter mirrors the order lines 1:1. For example, the number of lines in the advance matches the number of lines in the order.  
   >
   > If **Suggest by Line** isn't selected, the advance amounts aggregate based on the VAT rates and VAT posting groups in the order lines.

5. After you confirm, the advance invoice page opens. You can review, modify, print, and release the advance invoice to prepare it for payment.

## Related information

[Advance Payments for Czech Republic (Extension)](ui-extensions-advance-payments-localization-cz.md)  
[Czech Local Functionality](czech-local-functionality.md)  
[Finance](../../finance.md)
