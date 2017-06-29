---
    title: Insert topic title| Microsoft Docs
    description: Insert description
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

    ---
# How to: Reserve Item-Tracked Items
From outbound documents for item-tracked items, such as sales orders or production component lists, you can reserve specific serial or lot numbers. This may be relevant, for example, if you need production components from a specific lot to ensure consistency with earlier production batches, or because a customer has requested a specific serial number.  
  
 This is referred to as a specific reservation, because you reserve from the quantity of  Item X that belongs to Lot X. If you simply reserve from quantities of Item X, then it is a normal, non-specific, reservation. For more information, see [How to: Reserve Items for Sales Lines](../how-to-reserve-items-for-sales-lines.md).  
  
 The following procedure is based on a sales order.  
  
### To reserve a specific serial or lot number  
  
1.  In the **Search** box, enter **Sales Orders**, and then select the related link.  
  
2.  Create a sales order line for an item-tracked item.  
  
     Proceed to assign serial and lot numbers to the sales order line.  
  
3.  On the **Lines** FastTab, choose **Line**, and then choose **Item Tracking Lines**.  
  
4.  In the **Serial No.** field, enter **SN1**, in the **Lot No.** field, enter **LOT1**, and then enter **1** in the **Quantity \(Base\)** field.  
  
5.  Close the **Item Tracking List** window.  
  
6.  On the sales order, on the **Lines** FastTab, choose **Functions**, and then choose **Reserve**.  
  
7.  Choose the **Yes** button to reserve specific serial or lot numbers.  
  
8.  In the   **Item Tracking List** window, select the serial and lot number combination that you have just assigned.  
  
9. Choose the **OK** button to open the **Reservation** window showing only supply with the specified item tracking number. If there are any non-specific reservations on any of the item tracking numbers that you have specified for this line, you are informed of the quantity that has already been reserved.  
  
10. On the **Actions** tab, in the **Functions** group, choose either **Auto Reserve** or **Reserve from Current Line** to create the reservation on the specific item tracking numbers.  
  
## See Also  
 [How to: Reserve Items for Sales Lines](../how-to-reserve-items-for-sales-lines.md)   
 [How to: Reserve Items for Production Components](../how-to-reserve-items-for-production-components.md)   
 [How to: Reserve Items for Production Order Lines](../how-to-reserve-items-for-production-order-lines.md)   
 [How to: Cancel Reservations](../how-to-cancel-reservations.md)   
 [How to: Change Reservations](../how-to-change-reservations.md)