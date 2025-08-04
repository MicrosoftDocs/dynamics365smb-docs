---
title: Undo Assembly Posting
description: Learn how correct mistakes in a posted assembly order.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 02/21/2023
ms.custom: bap-template
ms.search.keywords: kit, kitting
ms.search.form: 900, 901, 902, 903, 904, 907, 910, 916, 920, 921, 922, 923, 940, 941, 942, 930, 931, 932, 914, 915, 905
ms.service: dynamics-365-business-central
---
# Undo Assembly Posting

Undo the posting of an assembly order to correct a mistake or remove an unwanted posting.

When you undo a posted assembly order, corrective item ledger entries are created to reverse the original entries. Each positive output entry for the assembly item is reversed by a negative output entry. Each negative consumption entry for an assembly component is reversed by a positive consumption entry. Fixed cost application is automatically created between the corrective and original entries to ensure exact cost reversal.  

When you undo a fully posted assembly order, you can recreate the original order. For example, to make corrections before you post it again.  

When you undo a partially posted assembly order, all affected quantity fields, such as the **Assembled Quantity**, **Consumed Quantity**, and **Remaining Quantity** fields, are restored to the values they had before the posting.  

To recreate or restore assembly orders, the item in the original posting must meet the following conditions:  

* It's still in inventory. That is, it hasn't been sold or otherwise consumed by outbound transactions.  
* It isn't reserved.  
* It's in the bin that it was output to.  

Assembly orders can only be restored if the number and sequence of lines on the original assembly order aren't changed.  

> [!TIP]  
> To resolve conflicts caused by changes in the lines, manually revert the changes on the lines in question before undoing the posted assembly order. You can post the assembly order and then recreate it when you undo the posting.  

The following procedure describes how to undo posted assembly orders that contain items that were assembled-to-stock. To undo posted assembly orders with items that were assembled-to-order, use the **Undo Shipment** action on the related posted shipment. To learn more about undoing shipments, go to [Reverse Journal Postings and Undo Receipts/Shipments](finance-how-reverse-journal-posting.md). Undoing the posted assembly order happens in the same way as described in that article.  

## To undo posting of an assembly order

You can undo fully or partially posted assembly orders.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Posted Assembly Orders**, and choose the related link.  

   Each partial posting creates a separate posted assembly order.  
2. Open the posted assembly order that you want to undo, and then choose the **Undo Assembly** action.  

    If the posted assembly order is related to a fully posted assembly order that's been deleted, you can recreate then deleted order. For example, you might recreate the order because you want to reprocess it.  
3. To recreate the assembly order, choose **Yes**. To undo the posting without recreating the assembly order, choose **No**.  

The **Reversed** field on the assembly order changes to **Yes**. The assembly order posting is now reversed. You can process the entire assembly order if you chose to recreate it, or the open assembly order that you have restored to its original state.  

> [!NOTE]  
> To restore quantities from multiple partial postings in an assembly order, you must undo all the posted assembly orders by following steps 1 through 3.  

## Related information

[Assembly Management](assembly-assemble-items.md)  
[Reverse Journal Postings and Undo Receipts/Shipments](finance-how-reverse-journal-posting.md)  
[Process Sales Returns or Cancellations](sales-how-process-sales-returns-cancellations.md)  
[Work with Assembly BOMs](assembly-how-work-assembly-boms.md)  
[Inventory](inventory-manage-inventory.md)  
[Warehouse Management Overview](design-details-warehouse-management.md)
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]