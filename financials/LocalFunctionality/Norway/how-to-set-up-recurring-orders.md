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
# How to: Set Up Recurring Orders
After you create a recurring group, you can set up recurring orders on the blanket sales order by adding the group to the order. For more information, see [How to: Create Blanket Sales Orders](how-to-set-up-recurring-groups.md).  
  
### To set up a recurring order  
  
1.  In the **Search** box, enter **Blanket Sales Orders**, and then choose the related link.  
  
2.  On the **Home** tab, in the **New** group, choose **New**.  
  
3.  On the **General** FastTab, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Order Date**|Enter the order date. The order date is used when you create new recurring orders. Orders with an order date on or before the processing date are processed.|  
    |**Recurring Group Code**|Enter the recurring group code for the recurring group. When a blanket order contains a recurring group code, the blanket order is available as a recurring order.|  
  
4.  On the **Lines** FastTab, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Quantity**|Enter the quantity for the blanket order.|  
    |**Qty. to Ship**|Enter the quantity to ship. This quantity is used when you create new orders as recurring orders.|  
  
5.  Choose the **OK** button.  
  
## See Also  
 [Recurring Orders](recurring-orders.md)   
 [How to: Set Up Recurring Groups](how-to-set-up-recurring-groups.md)   
 [How to: Create Recurring Orders](how-to-create-recurring-orders.md)   
 [How to: Create Blanket Sales Orders](how-to-create-blanket-sales-orders.md)