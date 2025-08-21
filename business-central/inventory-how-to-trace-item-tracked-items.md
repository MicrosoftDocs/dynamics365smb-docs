---
title: Trace item-tracked items
description: You can see where an item-tracked item was used, including how and when it was received, produced, or returned with Item Tracing and Find Entries features.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords:
ms.search.forms: 6520,
ms.date: 05/16/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Trace item-tracked items

You can see where an item-tracked item was used, including how and when it was received or produced, transferred, sold, consumed, or returned. You can also find all current instances of a specific serial or lot number in the database. You do this by using the Item Tracing and the [Find Entries](ui-find-entries.md) features.  

These features can be useful in quality control when you need to find out which customers received products with a particular lot number or when you need to find out which lot a defective component came from.  

 On the **Item Tracing** page, you can trace forwards and backwards in a sequence of posted inventory transactions for the serial or lot number.  

 On the **Find Entries** page, you can't see the sequence of transactions, but you can see all records of the serial or lot number, both posted entries and open records.  

 The two features can be used in combination by transferring a traced serial or lot number to the **Find Entries** page to finish a complete trace scenario. <!-- For more information, see [Walkthrough: Tracing Serial-Lot Numbers](walkthrough-tracing-serial-lot-numbers.md).   -->

## To trace item-tracked items  

1.  [!INCLUDE[open-search](includes/open-search.md)], enter **Item Tracing**, and then choose the related link.  
2.  In the filter fields at the top of the page, enter the specific item numbers or a filter on the item numbers that you would like to trace.  
3.  In the **Show Components** field, select whether to also see where the components for the items came from. The following table describes the options.  

    |Field|Description|  
    |----------------------------------|---------------------------------------|  
    |**No**|Don't show components.|  
    |**Item-tracked Only**|Show only components that have lot or serial numbers.|  
    |**All**|Show all components.|  

4.  In the **Trace Method** field, select the method to use for tracing the item. The following table describes the options.  

    |Field|Description|  
    |----------------------------------|---------------------------------------|  
    |**Usage->Origin**|Trace the item from where it was used to where it came from. For instance, if a manufactured item was sold to a customer, the **Item Tracing** page shows this with the sales shipment line first, which you can then expand to see from which production order it came.|  
    |**Origin->Usage**|Trace the item from where it came into inventory to where it was used. For instance, if a manufactured item was sold to a customer, the **Item Tracing** page shows this with the finished production order first, which you can then expand to see the sale shipment lines where the item was used.|  

5.  Choose the **Trace** action to run the trace.  

> [!NOTE]  
>  Only applied transactions are shown. If you have received the same lot on multiple transactions, the **Item Tracing** page may not show all transactions.   

> [!NOTE]  
>  If additional transaction history under an item tracing line has already been traced by another line above it, then the **Already Traced** check box is selected. To provide a simpler view, such underlying lines are not shown.  
>   
>  To find the item tracing lines where the transaction history has already been traced, choose the **Go to Already Traced** button. The item tracing line in question is selected, and all underlying lines are expanded.  

## To find item-tracked items with Find Entries  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Find Entries**, and then select the related link.  
2. Choose **Search for item references**.
3. In the **Serial No.** and **Lot No.** fields, enter the item tracking numbers that you want to trace.  
4. Choose the **Find** action to find all instances of the serial or lot number in the database.  

## Related information

[Inventory](inventory-manage-inventory.md)  
[Work with Serial, Lot, and Package Numbers](inventory-how-work-item-tracking.md)  
[Design Details: Item Tracking](design-details-item-tracking.md)  
[Design Details - Item Tracking and Reservations](design-details-item-tracking-and-reservations.md)  
[Reserve Items](inventory-how-to-reserve-items.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
<!-- [Walkthrough: Tracing Serial-Lot Numbers](walkthrough-tracing-serial-lot-numbers.md)   -->
[Find Entries](ui-find-entries.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
