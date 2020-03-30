---
    title: How to Trace Item-Tracked Items | Microsoft Docs
    description: You can see where an item-tracked item was used, including how and when it was received or produced, transferred, sold, consumed, or returned. You can also find all current instances of a specific serial or lot number in the database. You do this by using the Item Tracing and the Navigate features.
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
# Trace Item-Tracked Items
You can see where an item-tracked item was used, including how and when it was received or produced, transferred, sold, consumed, or returned. You can also find all current instances of a specific serial or lot number in the database. You do this by using the Item Tracing and the Navigate features.  

 These features can be particularly useful in quality control when you need to find out which customers received products with a particular lot number or when you need to find out which lot a defective component came from.  

 On the **Item Tracing** page, you can trace forwards and backwards in a sequence of posted inventory transactions for the serial or lot number.  

 On the **Navigate** page, you cannot see the sequence of transactions, but you can see all records of the serial or lot number, both posted entries and open records.  

 The two features can be used in combination by transferring a traced serial or lot number to the **Navigate** page to finish a complete trace scenario. For more information, see [Walkthrough: Tracing Serial-Lot Numbers](walkthrough-tracing-serial-lot-numbers.md).  

## To trace item-tracked items  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Item Tracing**, and then choose the related link.  
2.  In the filter fields at the top of the page, enter the specific item numbers or a filter on the item numbers that you would like to trace.  
3.  In the **Show Components** field, select whether you would like to also see where the components for the items came from. Your options in this field are as follows.  

    |Field|Description|  
    |----------------------------------|---------------------------------------|  
    |**No**|Select this option if you do not want to see any components.|  
    |**Item-tracked Only**|Select this option if you want to see only components that have lot or serial numbers.|  
    |**All**|Select this option if you want to see all components.|  

4.  In the **Trace Method** field, select the method you would like to use for tracing the item. The options are as follows  

    |Field|Description|  
    |----------------------------------|---------------------------------------|  
    |**Usage->Origin**|This method traces the item starting from where it was used to where it came from. For instance, if a manufactured item was sold to a customer, the **Item Tracing** page shows this with the sales shipment line first, which you can then expand to see from which production order it came.|  
    |**Origin->Usage**|This method traces the item starting from where it came into inventory to where it was used. For instance, if a manufactured item was sold to a customer, the **Item Tracing** page shows this with the finished production order first, which you can then expand to see sale shipment lines where the item was used.|  

5.  Choose the **Trace** action to run the trace.  

> [!NOTE]  
>  If you have received the same lot on more transactions, then the **Item Tracing** page may not show all transactions. Only applied transactions are shown.  

> [!NOTE]  
>  If additional transaction history under an item tracing line has already been traced by another line above it, then the **Already Traced** check box is selected. To provide a simpler view, such underlying lines are not shown.  
>   
>  To find the item tracing lines where the transaction history has already been traced, choose the **Go to Already Traced** button. The item tracing line in question is selected, and all underlying lines are expanded.  

## To find item-tracked items with Navigate  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Navigate**, and then select the related link.  
2.  On the **Item Tracking** FastTab, in the **Serial No.** and **Lot No.** fields, enter the item tracking numbers that you want to trace.  
3.  Choose the **Find** action to find all instances of the serial or lot number in the database.  

## See Also  
[Inventory](inventory-manage-inventory.md)  
[Design Details: Item Tracking](design-details-item-tracking.md)
[Design Details - Item Tracking and Reservations](design-details-item-tracking-and-reservations.md)  
[Reserve Items](inventory-how-to-reserve-items.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
[Walkthrough: Tracing Serial-Lot Numbers](walkthrough-tracing-serial-lot-numbers.md)
