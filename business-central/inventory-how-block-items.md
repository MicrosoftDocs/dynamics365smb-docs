---
    title: How to Block Items from Sales or Purchasing
    description: In Business Central, an item can be marked as blocked for sales, blocked for purchase, or blocked for all purposes.

    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Block Items from Sales or Purchasing
You can block an item from being entered on sales or purchase lines, and you can block it from being posted in any transaction.  

The following table illustrates what occurs when items are blocked.  

|Option|Description|  
|--------------------|------------|  
|**Sales Blocked**|You cannot enter the item in a sales document or in a sales item journal.|  
|**Purchasing Blocked**|You cannot enter the item in a purchase document, in a purchase item journal, or in purchase planning processes.|  
|**Blocked**|You cannot use the item for any item transaction.|  

> [!NOTE]
> Blocked items can be returned. This means that none of the above settings apply when the item is used on return orders and credit memos.

When you use the **Copy from Document** function to create new documents based on existing documents, you are notified if any items on the source document lines are blocked. The blocked document lines are excluded from the new document, and a notification shows an overview of all document lines that are blocked in the source document.

## To block an item from being entered on sales lines  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.  
2.  Select the item that you want to block, and then select the **Sales Blocked** check box.  

If you try to enter the item on a sales document or journal line, you will now get an error message that the item is blocked.

## To block an item from being entered on purchase lines  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.  
2.  Select the item that you want to block, and then select the **Purchasing Blocked** check box.  

If you try to enter the item on a purchase document or journal line, you will now get an error message that the item is blocked.

## To block an item from being posted
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.
2. Select the item that you want to block, and then select the **Blocked** check box.

If you try to post any type of transaction for the item, you will now get an error message that the item is blocked.

## See Also  
[Register New Items](inventory-how-register-new-items.md)  
[Inventory](inventory-manage-inventory.md)  
