---
title: "How to: Sell Items Assembled to Order"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "assembly, sell to order"
  - "assemble to order, selling items"
  - "sales, assemble to order"
ms.assetid: 6bd294a1-11d3-4ecc-ab0f-ad10c1a8f4e2
caps.latest.revision: 19
ms.author: "sgroespe"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-nz"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# How to: Sell Items Assembled to Order
If the **Assembly Policy** field on the item card of an assembly item is **Assemble\-to\-Order**, then the item is not expected to be in inventory, and it must be assembled specifically to a sales order. When you enter the item on a sales order line, then an assembly order is automatically created and linked to the sales order.  
  
> [!NOTE]  
>  If some assemble\-to\-order items are already in inventory, then you can deduct that quantity from the assembly order and reserve it from inventory. For more information, see [How to: Sell Inventory Items in Assemble\-to\-Order Flows](../Sales/how-to-sell-inventory-items-in-assemble-to-order-flows.md). Similarly, when you are selling assembly items from inventory and all items are not available, you can initiate an assembly order to automatically supply a part or all of the sales order quantity. For more information, see [How to: Sell Assemble\-to\-Order Items and Inventory Items Together](../Sales/how-to-sell-assemble-to-order-items-and-inventory-items-together.md).  
  
 In this procedure, you process the sale of an item that will be assembled according to specifications that are requested by the customer. The steps include initiating the sales order line, customizing the assembly item by editing its components and resources, checking availability to establish a delivery date, and releasing the sales order to be assembled and immediately shipped.  
  
> [!NOTE]  
>  The following procedure does not include the standard sales order steps before the step where you enter the assemble\-to\-order item on a sales order line.  
  
### To sell an item that is assembled to order  
  
1.  In the **Search** box, enter **Sales Orders**, and then choose the related link.  
  
2.  Create a sales order. For more information, see [How to: Create Sales Orders Manually](../Sales/how-to-create-sales-orders-manually.md).  
  
3.  In the **No.** field, enter an item that is set up to be assembled to order. For more information, see [Assembly Policy](../Topic/\($%20T_27_910%20Assembly%20Policy%20$\).md).  
  
4.  In the **Location Code** field, define which location the item will be sold from. The assembly process will occur at that location.  
  
5.  In the **Quantity** field, enter how many units to sell.  
  
    > [!NOTE]  
    >  If one or more components of the requested assembly item quantity are not available, then a detailed availability warning window opens. For more information, see [Assembly Availability](../Topic/\($%20N_908%20Assembly%20Availability%20$\).md).  
  
     An assembly order is now automatically created and linked to the sales order line. The due date of this assembly order is synchronized with the shipment date of the sales order line.  
  
     The quantity to sell is copied to the **Qty. to Assemble to Order** field, which indicates that the item setup expects the full quantity on the sales line to be assembled to the order. You can decrease the quantity to assemble to order, such as if you know that some items are already available. For more information, see [How to: Sell Inventory Items in Assemble\-to\-Order Flows](../Sales/how-to-sell-inventory-items-in-assemble-to-order-flows.md).  
  
6.  To reflect that the customer wants an additional item in a kit, on the **Lines** FastTab, choose **Line**, choose **Assemble to Order**, and then choose **Assemble\-to\-Order Lines** to view and change the standard assembly components. Alternatively, choose the **Qty. to Assemble to Order** field.  
  
7.  In the **Assemble\-to\-Order Lines** window, create a new line of type **Item** for the requested additional kit content. The line represents an additional assembly component.  
  
     You could also customize the order by increasing the quantity of one standard item in the kit. You can do this by increasing the value in the **Quantity Per** field on the specific assembly order line.  
  
    > [!NOTE]  
    >  The **Assemble\-to\-Order Lines** window only contains the basic fields that a salesperson is expected to use to customize the component list, add item tracking numbers, or to solve component availability issues. To see more assembly order information, such as the assembly order starting date, on the **Home** tab, in the **Process** group, choose **Show Documents**. This opens a full view of the assembly order that is linked to the sales order line. You cannot change the contents of most fields on the assembly order header, and you cannot post assembly output from it because you must use shipment posting of the sales order line.  
    >   
    >  On the header of linked assembly orders, only the **Starting Date** field can be changed to enable assembly workers to specify a date that is earlier than the due date when they will start the process. All fields on the lines of the linked assembly order can be changed so that warehouse workers can enter consumption figures during the process.  
  
8.  Review or react to component availability issues. For example, select an available substitute item or establish a later due date.  
  
9. Close the **Assemble\-to\-Order Lines** window. The linked assembly order is now ready to start to assemble the customized items by the due date.  
  
10. On the sales order, on the **Actions** tab, in the **Release** group, choose **Release** to notify the assembly department that the assembly process can start.  
  
11. In the assembly department, perform the steps of assembling the items that are sold in this procedure. For more information, see [How to: Assemble Items](../WarehouseActivities/how-to-assemble-items.md).  
  
## See Also  
 [Assembly Order](../WarehouseActivities/-$-n_900-assembly-order-$-.md)   
 [Assembly Policy](../Topic/\($%20T_27_910%20Assembly%20Policy%20$\).md)   
 [From\-Assembly Bin Code](../Topic/\($%20T_14_7331%20From-Assembly%20Bin%20Code%20$\).md)   
 [Qty. to Assemble to Order](../Topic/\($%20T_37_900%20Qty.%20to%20Assemble%20to%20Order%20$\).md)   
 [Assemble\-to\-Order Lines](../Topic/\($%20N_914%20Assemble-to-Order%20Lines%20$\).md)   
 [Starting Date](../Topic/\($%20T_900_25%20Starting%20Date%20$\).md)   
 [Substitution Available](../Topic/\($%20T_901_51%20Substitution%20Available%20$\).md)   
 [Quantity per](../Topic/\($%20T_901_60%20Quantity%20per%20$\).md)   
 [How to: Sell Inventory Items in Assemble\-to\-Order Flows](../Sales/how-to-sell-inventory-items-in-assemble-to-order-flows.md)   
 [How to: Sell Assemble\-to\-Order Items and Inventory Items Together](../Sales/how-to-sell-assemble-to-order-items-and-inventory-items-together.md)   
 [How to: Assemble Items](../WarehouseActivities/how-to-assemble-items.md)   
 [Assemble to Order or Assemble to Stock](../DesignAndEngineering/assemble-to-order-or-assemble-to-stock.md)   
 [Assemble\-to\-Order Link](../Topic/\($%20T_904%20Assemble-to-Order%20Link%20$\).md)