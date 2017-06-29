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
# About Picking Serial and Lot Numbers
Outbound handling of serial or lot numbers is a frequent task in different warehouse processes.  
  
 In simple processes, the inventory items already carry item tracking numbers, and these numbers are automatically transferred through all outbound warehouse activities without an interaction by warehouse workers.  
  
 In other processes, the inventory items do not carry item tracking numbers, and the warehouse worker must assign new during the outbound handling, typically from a predefined number series. For more information, see [How to: Assign Serial Numbers and Lot Numbers During Outbound Transactions](../FullExperience/how-to-assign-serial-numbers-and-lot-numbers-during-outbound-transactions.md).  
  
 In special processes, the inventory items already carry item tracking numbers, but the warehouse worker must select them specifically during the outbound handling. For more information, see [How to: Select from Existing Serial Numbers and Lot Numbers](../FullExperience/how-to-select-from-existing-serial-numbers-and-lot-numbers.md). This process is typically used when the item is set up for specific tracking. For more information, see Lot Specific Tracking.  
  
 In some situations, the serial or lot numbers are already defined on the source document, which the warehouse worker must respect during the outbound warehouse handling. This may be because the customer requested a specific lot during the order process. In that case, warehouse workers must pick the specific serial or lot numbers, similarly to the special process above, but they have little means of editing the **Item Tracking Lines** window.  
  
> [!NOTE]  
>  To enable, for example, lot number handling in warehouse activities, the **Lot Warehouse Tracking** field must be selected in the item’s item tracking code setup.  
  
## Picking Serial or Lot Numbers Specified on Source Documents  
 When the inventory pick or warehouse pick document is created from an outbound source document where item tracking numbers are already defined, then all fields in the **Item Tracking Lines** window under the inventory pick are locked for writing, except the **Qty. to Handle** field.  
  
 The inventory pick lines specify the item tracking numbers on individual take and place lines. The quantity is already split into unique serial or lot number combinations because the sales order specifies the item tracking numbers to ship.  
  
### Deleting Pick Lines  
 If items on a pick line are not available, then you can typically delete those pick lines and delete the pick document. The source document, such as sales order, production order, or warehouse shipment will then have remaining items to be picked, which can be obtained through a new pick later when the items become available.  
  
> [!CAUTION]  
>  We do not recommend this method if serial or lot numbers are specified on the source document.  
  
 Instead, change the **Qty. to Handle** field to zero, post the other pick lines, and then delete the pick document. This makes sure that the pick lines for those serial or lot numbers can be recreated from the source document later.  
  
## See Also  
 [Pick Items](../FullExperience/pick-items.md)   
 Item Tracking Lines   
 [How to: Assign Serial Numbers and Lot Numbers During Outbound Transactions](../FullExperience/how-to-assign-serial-numbers-and-lot-numbers-during-outbound-transactions.md)   
 [How to: Set Up Warehouse Management](../FullExperience/how-to-set-up-warehouse-management.md)   
 [Design Details: Warehouse Management](../FullExperience/design-details-warehouse-management.md)   
 Lot Specific Tracking   
 Lot Warehouse Tracking