---
title: How to Block Items from Sales or Purchasing
description: You can block items from being entered on lines in sales or purchase documents, as well as from being posted in a transaction. 
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.date: 11/03/2022
ms.author: bholtorf

---
# Block Items from Sales or Purchasing

You can block an item from being entered on lines in sales or purchase documents, and you can block it from being posted in transactions. For example, this is useful when an item has a known defect. If someone chooses a blocked item on a sales or purchase document a message will inform them that the item is blocked.

The following table describes what occurs when items are blocked.  

|Option|Description|  
|--------------------|------------|  
|**Sales Blocked**|You can't enter the item in a sales document or in a sales item journal.|  
|**Purchasing Blocked**|You can't enter the item in a purchase document, in a purchase item journal, or in purchase planning processes.|  
|**Blocked**|You can't include the item in transactions.|  

> [!NOTE]
> Blocked items can be returned. This means that none of the above settings apply to return orders and credit memos.

When you use the **Copy from Document** action to create new documents based on existing documents, you're notified if items on the source document lines are blocked. The blocked document lines are excluded from the new document, and a notification shows an overview of all document lines that are blocked in the source document.

## To block an item from being entered on sales lines  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.  
2. Select the item that you want to block, and then select the **Sales Blocked** checkbox.  

## To block an item from being entered on purchase lines  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.  
2. Select the item that you want to block, and then select the **Purchasing Blocked** checkbox.  

## To block an item from being posted

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.
2. Select the item that you want to block, and then select the **Blocked** checkbox.

## See Also  

[Register New Items](inventory-how-register-new-items.md)  
[Inventory](inventory-manage-inventory.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]