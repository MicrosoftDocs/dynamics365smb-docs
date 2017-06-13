---
title: "How to: Sell Inventory Items in Assemble-to-Order Flows"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "assemble, to order"
ms.assetid: 9044cc6f-0f56-4d5e-81f2-ff478678d1d3
caps.latest.revision: 21
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
# How to: Sell Inventory Items in Assemble-to-Order Flows
If the **Assembly Policy** field on the item card of an assembly item contains **Assemble\-to\-Order**, then the default sales order process assumes that the item is not in inventory and must be assembled for that specific sales order. Therefore, a linked assembly order is automatically created when you add the item to a sales order line. For more information, see [How to: Sell Items Assembled to Order](../Sales/how-to-sell-items-assembled-to-order.md). However, if a part of the sales order quantity is already available in inventory, then you can decrease the assembly order quantity by changing the **Qty. to Assemble to Order** field on the sales order line.  
  
 This scenario is rare because assemble\-to\-order items are expected to always be customized, and the chance that they are in inventory in the configuration that is requested by another customer is low. However, if a company does have assemble\-to\-order quantities in inventory because of returns or order cancellations, then these quantities should be picked and sold before new ones are assembled.  
  
> [!NOTE]  
>  No functionality exists on sales orders that automatically alerts or helps you deduct assembly order quantities that are already available. Instead, you must monitor availability information, such as in the **Sales Line Details** FactBox.  
  
 Similar functionality is available when you are selling assembly items from inventory and a part or all of the quantity is unavailable and can be supplied by an assembly order. For more information, see [How to: Sell Assemble\-to\-Order Items and Inventory Items Together](../Sales/how-to-sell-assemble-to-order-items-and-inventory-items-together.md).  
  
> [!NOTE]  
>  Certain rules apply to the **Qty. to Ship** field on sales order lines that contain a combination of assemble\-to\-order quantities and inventory quantities. For more information, see the Combination Scenarios section in [Assemble to Order or Assemble to Stock](../DesignAndEngineering/assemble-to-order-or-assemble-to-stock.md).  
  
 In this procedure, you replace assemble\-to\-order quantities with inventory quantities on a sales order line. The steps include detecting that availability exists, deducting that quantity from the linked assembly order, and then reserving the inventory quantity to make sure that it is picked and shipped for the order.  
  
### To sell inventory items in assemble\-to\-order flows  
  
1.  In the **Search** box, enter **Sales Orders**, and then choose the related link.  
  
2.  Create a sales order. For more information, see [How to: Create Sales Orders Manually](../Sales/how-to-create-sales-orders-manually.md).  
  
3.  On a sales order line for an assemble\-to\-order item, in the **Quantity** field, enter the demanded quantity.  
  
4.  In the **Sales Line Details** FactBox, determine if all or some of the demanded quantity is available.  
  
5.  In the **Qty. to Assemble to Order** field, deduct the available quantity so that only the unavailable quantity is assembled to the order. The **Reserved Quantity** field is decreased accordingly to reflect that the order\-to\-order link, or reservation, only applies to the quantity to be assembled.  
  
6.  On the **Lines** FastTab, choose **Functions**, and then choose **Reserve**.  
  
7.  In the **Reservation** window, select the item ledger entry line or lines that contain the available quantities, on the **Actions** tab, in the **Functions** group, choose **Reserve from Current Line**, and then choose the **OK** button.  
  
     In the **Sales Order** window, the **Reserved Quantity** field now shows that the whole order line quantity is reserved. The **Qty. to Assemble to Order** field still reflects the subquantity that has to be assembled.  
  
8.  Release the sales order for picking of the inventory items and for assembly of the unavailable items. For more information, see [How to: Assemble Items](../WarehouseActivities/how-to-assemble-items.md).  
  
> [!CAUTION]  
>  The **Bin Code** field on the sales order may be prefilled according to the **Assemble\-to\-Order Shpt. Bin Code** or the **From\-Assembly Bin Code** field on the location card. In that case, the **Bin Code** field on the sales order line may be incorrect in this combination of assemble\-to\-order and assemble\-to\-stock quantities. It is a good idea to look in the **Bin Code** field and ensure that the placement works for all quantities. Alternatively, enter the two different quantities on separate sales order lines.  
  
## See Also  
 [Assembly Order](../WarehouseActivities/-$-n_900-assembly-order-$-.md)   
 [Assembly Policy](../Topic/\($%20T_27_910%20Assembly%20Policy%20$\).md)   
 [Reserve](../Topic/\($%20T_37_96%20Reserve%20$\).md)   
 [Reservation](../Topic/\($%20N_498%20Reservation%20$\).md)   
 [Assemble\-to\-Order Link](../Topic/\($%20T_904%20Assemble-to-Order%20Link%20$\).md)   
 [Qty. to Assemble to Order](../Topic/\($%20T_37_900%20Qty.%20to%20Assemble%20to%20Order%20$\).md)   
 [Asm.\-to\-Order Shpt. Bin Code](../Topic/\($%20T_14_7332%20Asm.-to-Order%20Shpt.%20Bin%20Code%20$\).md)   
 [From\-Assembly Bin Code](../Topic/\($%20T_14_7331%20From-Assembly%20Bin%20Code%20$\).md)   
 [How to: Sell Assemble\-to\-Order Items and Inventory Items Together](../Sales/how-to-sell-assemble-to-order-items-and-inventory-items-together.md)   
 [How to: Assemble Items](../WarehouseActivities/how-to-assemble-items.md)   
 [Design Details: Assembly Order Posting](../ApplicationDesign/design-details-assembly-order-posting.md)