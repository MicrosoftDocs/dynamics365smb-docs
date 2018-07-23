---
    title: How to Block Items from Sales or Purchasing
    description: In Business Central, an item can be marked as blocked for sales, blocked for purchase, or blocked for all purposes.

    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/23/2018
    ms.author: sgroespe

---
# Block Items from Sales or Purchasing
You can block an item from being entered on sales or purchase lines, and you can block it from being posted in any transaction.  

The following table illustrates what occurs when items are blocked.  

|Option|Description|  
|--------------------|------------|  
|**Sale Blocked**|You cannot enter the item in a sales document or in a sales item journal.|  
|**Purchase Blocked**|You cannot enter the item in a purchase document, in a purchase item journal, or in purchase planning processes.|  
|**Blocked**|You cannot use the item for any item transaction. For more information about blocking an item for all purposes, see Item Card.|  

## To block an item from being entered on sales lines  

1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Items**, and then choose the related link.  
2.  Select the item that you want to block, and then select the **Sale Blocked** check box.  

If you try to enter the item on a sales document or journal line, you will now get an error message that the item is blocked.

## To block an item from being entered on purchase lines  

1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Items**, and then choose the related link.  
2.  Select the item that you want to block, and then select the **Purchase Blocked** check box.  

If you try to enter the item on a purchase document or journal line, you will now get an error message that the item is blocked.

## To block an item from being posted
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Items**, and then choose the related link.
2. Select the item that you want to block, and then select the **Blocked** check box.

If you try to post any type of transaction for the item, you will now get an error message that the item is blocked.

## See Also  
[Register New Items](inventory-how-register-new-items.md)  
[Inventory](inventory-manage-inventory.md)  
