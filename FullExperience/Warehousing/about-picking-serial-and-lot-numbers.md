---
title: "About Picking Serial and Lot Numbers"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: 766e2066-2f54-4212-a308-eb97fb06df72
caps.latest.revision: 3
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
# About Picking Serial and Lot Numbers
Outbound handling of serial or lot numbers is a frequent task in different warehouse processes.  
  
 In simple processes, the inventory items already carry item tracking numbers, and these numbers are automatically transferred through all outbound warehouse activities without an interaction by warehouse workers.  
  
 In other processes, the inventory items do not carry item tracking numbers, and the warehouse worker must assign new during the outbound handling, typically from a predefined number series. For more information, see [How to: Assign Serial Numbers and Lot Numbers During Outbound Transactions](../WarehouseActivities/how-to-assign-serial-numbers-and-lot-numbers-during-outbound-transactions.md).  
  
 In special processes, the inventory items already carry item tracking numbers, but the warehouse worker must select them specifically during the outbound handling. For more information, see [How to: Select from Existing Serial Numbers and Lot Numbers](../DesignAndEngineering/how-to-select-from-existing-serial-numbers-and-lot-numbers.md). This process is typically used when the item is set up for specific tracking. For more information, see [\($ T\_6502\_41 Lot Specific Tracking $\)](../Topic/\($%20T_6502_41%20Lot%20Specific%20Tracking%20$\).md).  
  
 In some situations, the serial or lot numbers are already defined on the source document, which the warehouse worker must respect during the outbound warehouse handling. This may be because the customer requested a specific lot during the order process. In that case, warehouse workers must pick the specific serial or lot numbers, similarly to the special process above, but they have little means of editing the **Item Tracking Lines** window.  
  
> [!NOTE]  
>  To enable, for example, lot number handling in warehouse activities, the **Lot Warehouse Tracking** field must be selected in the item’s item tracking code setup.  
  
## Picking Serial or Lot Numbers Specified on Source Documents  
 When the inventory pick or warehouse pick document is created from an outbound source document where item tracking numbers are already defined, then all fields in the **\($ N\_6510 Item Tracking Lines $\)** window under the inventory pick are locked for writing, except the **Qty. to Handle** field.  
  
 The inventory pick lines specify the item tracking numbers on individual take and place lines. The quantity is already split into unique serial or lot number combinations because the sales order specifies the item tracking numbers to ship.  
  
### Deleting Pick Lines  
 If items on a pick line are not available, then you can typically delete those pick lines and delete the pick document. The source document, such as sales order, production order, or warehouse shipment will then have remaining items to be picked, which can be obtained through a new pick later when the items become available.  
  
> [!CAUTION]  
>  We do not recommend this method if serial or lot numbers are specified on the source document.  
  
 Instead, change the **Qty. to Handle** field to zero, post the other pick lines, and then delete the pick document. This makes sure that the pick lines for those serial or lot numbers can be recreated from the source document later.  
  
## See Also  
 [Pick Items](../WarehouseActivities/pick-items.md)   
 [\($ N\_6510 Item Tracking Lines $\)](../Topic/\($%20N_6510%20Item%20Tracking%20Lines%20$\).md)   
 [How to: Assign Serial Numbers and Lot Numbers During Outbound Transactions](../WarehouseActivities/how-to-assign-serial-numbers-and-lot-numbers-during-outbound-transactions.md)   
 [How to: Set Up Warehouse Management](../WarehouseActivities/how-to-set-up-warehouse-management.md)   
 [Design Details: Warehouse Management](../ApplicationDesign/design-details-warehouse-management.md)   
 [\($ T\_6502\_41 Lot Specific Tracking $\)](../Topic/\($%20T_6502_41%20Lot%20Specific%20Tracking%20$\).md)   
 [\($ T\_6502\_45 Lot Warehouse Tracking $\)](../Topic/\($%20T_6502_45%20Lot%20Warehouse%20Tracking%20$\).md)