---
title: How to block items or item variants from sales, purchasing, and production
description: You can block items and item variants from being entered on lines in sales or purchase documents, and from being posted in a transaction. 
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: item, variant, product
ms.date: 02/05/2025
ms.service: dynamics-365-business-central
---

# Block items or item variants from use in sales, purchasing, service, and production

You can block items and item variants from being entered on lines in sales or purchase documents, and service and production orders. You can also block them from being posted in any kind of transaction. For example, blocking for use in all transactions is useful when an item has a known defect. If you choose a blocked item or variant on a sales or purchase document, or a service or production order, a message lets you know that the item is blocked.

The following table describes what happens when items or variants are blocked.  

|Option|Description|  
|--------------------|------------|  
|**Sales Blocked**|You can't choose the item or variant on a sales document or a sales item journal.|  
|**Service Blocked**|You can't choose the item or variant on service management transactions. To learn more about blocking service items, go to [Block items, item variants, or specific service items](service-how-to-create-service-items.md#block-items-item-variants-or-specific-service-items).|
|**Purchasing Blocked**|You can't choose the item or variant on a purchase document, a purchase item journal, or in purchase planning processes.|  
|**Production Blocked**|You can't choose the item or variant on production orders. Also, you can't use the following actions:</br></br>* Post output in output journals or production journals.</br>* Refresh the production order.</br>* Replan the production order.</br>* Calculate subcontracts in the subcontracting worksheet skips the lines with blocked items or variants. |  

> [!NOTE]
> Customers can return blocked items, which means that these settings don't apply to return orders and credit memos.

When you use the **Copy from Document** action to create new documents based on existing documents, you're notified if items or variants on the source document lines are blocked. The blocked document lines are excluded from the new document, and a notification shows an overview of all document lines that are blocked in the source document.

## To block an item

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.  
2. Depending on what you want to do, select the item, and then turn on one or more of the following toggles:

    * **Sales Blocked**
    * **Service Blocked**
    * **Purchasing Blocked**  
3. To block the item from use in production output, fill in the **Production Blocked** field.

## To block an item variant  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.  
2. Select the item that has a variant you want to block, choose **Variants**, and then select one or more of the following checkboxes:  

    * **Blocked**
    * **Sales Blocked**
    * **Service Blocked**
    * **Purchasing Blocked**  

3. To block the variant from use in production output, fill in the **Production Blocked** field.

## Related information  

[Register New Items](inventory-how-register-new-items.md)  
[Inventory](inventory-manage-inventory.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
