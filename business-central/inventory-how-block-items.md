---
title: How to Block Items or Item Variants from Sales or Purchasing
description: You can block items and item variants from being entered on lines in sales or purchase documents, as well as from being posted in a transaction. 
author: brentholtorf
ms.author: bholtorf
ms.reviewer: andreipa
ms.topic: conceptual
ms.search.keywords: item, variant, product
ms.date: 08/22/2023
---
# Block Items or Item Variants from Sales or Purchasing

You can block items and item variants from being entered on lines in sales or purchase documents, and you can block them from being posted in transactions. For example, this is useful when an item has a known defect. If someone chooses a blocked item or variant on a sales or purchase document a message will inform them that the item is blocked.

The following table describes what occurs when items or variants are blocked.  

|Option|Description|  
|--------------------|------------|  
|**Sales Blocked**|You can't choose the item or variant on a sales document or a sales item journal.|  
|**Purchasing Blocked**|You can't choose the item or variant on a purchase document, a purchase item journal, or in purchase planning processes.|  
|**Blocked**|You can't include the item or variant when you post transactions.|  

> [!NOTE]
> Blocked items can be returned. This means that none of the above settings apply to return orders and credit memos.

When you use the **Copy from Document** action to create new documents based on existing documents, you're notified if items or variants on the source document lines are blocked. The blocked document lines are excluded from the new document, and a notification shows an overview of all document lines that are blocked in the source document.

## To block an item  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.  
2. Depending on what you want to do, select the item, and then choose one or more of the following checkboxes:
    * **Blocked**
    * **Sales Blocked**
    * **Purchasing Blocked**  

## To block an item variant  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.  
2. Select the item that that has a variant you want to block, choose **Variants**, and then choose one or more of the following checkboxes:  
    * **Blocked**
    * **Sales Blocked**
    * **Purchasing Blocked**

## See Also  

[Register New Items](inventory-how-register-new-items.md)  
[Inventory](inventory-manage-inventory.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]