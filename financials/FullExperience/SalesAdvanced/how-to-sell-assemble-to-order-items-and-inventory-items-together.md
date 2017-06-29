---
title: "How to: Sell Assemble-to-Order Items and Inventory Items Together"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "assemble, to order"
ms.assetid: 5597829a-4ad1-489e-aeba-dded812bc1ec
caps.latest.revision: 14
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
# How to: Sell Assemble-to-Order Items and Inventory Items Together
If the **Assembly Policy** field on the item card of an assembly item contains **Assemble\-to\-Stock**, then the default sales order process assumes that the item is already assembled and can be picked from inventory, if it is available. Therefore, no assembly order is automatically created and linked to the sales order line. However, if a part \(or all\) of the quantity is not available, then you have the flexibility to create an assembly order for the remaining quantity by filling in the **Qty. to Assemble to Order** field on the sales order line. In this manner, you can assemble the item to order although it is set up to be assembled to stock by default.  
  
 Similar flexibility exists when you are selling items to be assembled to the order and a part of the quantity is in inventory, which you want to deduct from the assembly order. For more information, see [How to: Sell Inventory Items in Assemble\-to\-Order Flows](../Sales/how-to-sell-inventory-items-in-assemble-to-order-flows.md).  
  
> [!NOTE]  
>  Certain rules apply to the **Qty. to Ship** field on sales order lines that contain a combination of assemble\-to\-order quantities and inventory quantities. For more information, see the Combination Scenarios section in [Assemble to Order or Assemble to Stock](../DesignAndEngineering/assemble-to-order-or-assemble-to-stock.md).  
  
> [!NOTE]  
>  The following procedure does not include the standard sales order steps that you need to follow before you create an assembly order for unavailable quantities.  
  
### To sell assemble\-to\-order items and inventory items together  
  
1.  On a sales order line for an item that is set up to be assembled to stock, enter a quantity in the **Quantity** field that exceeds inventory. The **Check Availability** window appears.  
  
2.  Note the **Total Quantity** field \(a negative value\), which you will enter in the next step.  
  
3.  In the **Qty. to Assemble to Order** field, enter the value from the previous step.  
  
4.  Perform any changes to the assembly components. For more information, see [How to: Sell Items Assembled to Order](../Sales/how-to-sell-items-assembled-to-order.md).  
  
5.  Proceed to release the sales order, to prepare it for picking of the inventory items and for assembly of the unavailable items. For more information about these standard assembly steps, see [How to: Assemble Items](../WarehouseActivities/how-to-assemble-items.md).  
  
> [!CAUTION]  
>  The **Bin Code** field on the sales order may be prefilled according to the **Assemble\-to\-Order Shpt. Bin Code** field or the **From\-Assembly Bin Code** field on the location card. In that case, the **Bin Code** field on the sales order line may be incorrect in this combination of assemble\-to\-order and assemble\-to\-stock quantities. It is a good idea to examine the **Bin Code** field and make sure that the placement works for all quantities. Alternatively, enter the two different quantities on separate sales order lines.  
  
## See Also  
 Assembly Order   
 Assembly Policy   
 Qty. to Assemble to Order   
 [How to: Sell Items Assembled to Order](../Sales/how-to-sell-items-assembled-to-order.md)   
 [How to: Sell Inventory Items in Assemble\-to\-Order Flows](../Sales/how-to-sell-inventory-items-in-assemble-to-order-flows.md)   
 [How to: Assemble Items](../WarehouseActivities/how-to-assemble-items.md)   
 Assemble\-to\-Order Link   
 [Design Details: Assembly Order Posting](../ApplicationDesign/design-details-assembly-order-posting.md)