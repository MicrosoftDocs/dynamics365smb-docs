---
title: Creating an Advance Letter from an Order  
description: This section describes how to create an advance letter from a sales or purchase order using the Czech Advance Payments Localization extension in Business Central.  
author: v-pejano  

ms.service: dynamics365-business-central  
ms.topic: article  
ms.search.keywords: Czech, Advance Payments, Localization  
ms.date: 10/01/2021  
ms.reviewer: v-pejano  
ms.author: v-pejano  
---

# Creating an Advance Letter from an Order

You can also create an advance letter directly from a sales or purchase order. To do so, follow these steps:

1. Choose the ![Lightbulb icon](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, and then select the related link.  
   For purchases, search for **Purchase Orders** instead.
2. Create a new sales order.
3. After entering the order (including lines), run the **Create Advance Letter** action from the **Advance Letter** section.
4. In the dialog that appears, select the **Advance Letter Code** (linked to the Advance Letter Templates table) and the method of calculating the advance.  
   You can either enter a percentage or a specific amount for the advance.  

   If you select **Suggest by Line**, the advance letter will mirror the order lines 1:1 — i.e., the number of lines in the advance matches the number of lines in the order.  
   If **Suggest by Line** is not selected, the advance amounts will be aggregated based on VAT rates and VAT posting groups used in the order lines.
5. After confirming, the advance invoice page will open. You can review, modify, print, and release the advance invoice to prepare it for payment.

## See Also

[Advance Payments for Czech Republic (Extension)](ui-extensions-advance-payments-localization-cz.md)  
[Czech Local Functionality](czech-local-functionality.md)  
[Finance](../../finance.md)
