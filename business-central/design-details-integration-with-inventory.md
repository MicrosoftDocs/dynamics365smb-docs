---
title: Design Details - Integration with Inventory
description: The Warehouse Management and the Inventory application area interact with one another in physical inventory and in inventory or warehouse adjustment.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords:
ms.date: 06/15/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Design Details: Integration with Inventory

Warehouse management and inventory features interact with one another in physical inventory and in inventory or warehouse adjustment.  

## Physical inventory  

The **Whse. Phys. Inventory Journal** page is used with the **Phys. Inventory Journal** page for all advanced warehouse locations. The inventory on bin level is calculated, and a printed list is provided for the warehouse employee. The list shows which items in which bins must be counted.  
  
The warehouse employee enters the counted quantity on the **Whse. Phys. Inventory Journal** page and then posts the journal.  
  
If the counted quantity is greater than the quantity on the journal line, a movement is posted for this difference from the default adjustment bin to the counted bin. This increases the quantity in the counted bin and decreases the quantity in the default adjustment bin.  
  
If the quantity counted is less than the quantity on the journal line, a movement for this difference is posted from the counted bin to the default adjustment bin. This decreases the quantity in the counted bin and increases the quantity in the default adjustment bin.  
  
In advanced warehouse configurations, the value in the **Quantity (Calculated)** field is retrieved from item ledger entries and the value in the **Quantity (Phys. Inventory)** field is retrieved from warehouse entries, excluding the adjustment bin content. The **Quantity** field specifies the difference between the first two fields, which should be equal to the contents of the adjustment bin.  
  
When you post the physical inventory journal, the inventory and the default adjustment bin are updated.  

[!INCLUDE [preview-posting-inventory](includes/preview-posting-inventory.md)]
  
## Warehouse adjustments to the item ledger  

You use the **Item Journal** page and the **Calculate Whse. Adjustment** function to adjust inventory on the item ledger in accordance with an adjustment that has been made to the item quantity in a warehouse bin. To create a link between the inventory and the warehouse, you must define a default adjustment bin per location.  
  
The default adjustment bin registers items in the warehouse when you post an increase for the inventory. However, if you post a decrease, the quantity on the default bin is also decreased. In both cases, item ledger entries and warehouse entries are created.  
  
> [!NOTE]  
> Inventory calculations don't include the adjustment bin.  
  
To adjust the bin content, use a warehouse item journal, where you can enter the item number, zone code, bin code, and quantity to adjust.  
  
If you enter a positive quantity and post the line, then the inventory stored in the bin increases, and the quantity of the default adjustment bin decreases correspondingly.  
  
## Related information  

[Warehouse Management Overview](design-details-warehouse-management.md)  
[Design Details: Availability in the Warehouse](design-details-availability-in-the-warehouse.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
