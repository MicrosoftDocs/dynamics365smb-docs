---
    
title: How to Split Warehouse Activity Lines
description: Learn how to split warehouse activity lines if the available capacity in a suggested bin is not sufficient.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.date: 01/25/2023
ms.custom: bap-template
ms.search.forms: 931, 9314, 9313, 9315, 9330
---
# Split Warehouse Activity Lines

In warehouse put-aways, movements, or picks, and in inventory put-aways and inventory picks, bins are suggested for picking or putting away items. The quantity that's actually in the suggested bin may not be sufficient, or there isn't enough room in the bin to put away the required quantity. In these cases, you can split the line so that the items for one line are either taken from or placed in more than one bin.  

The following procedure applies to the following warehouse documents:

* Warehouse put-aways
* Warehouse movements
* Warehouse picks
* Inventory put-aways
* Inventory movements
* Inventory picks  

## To split warehouse activity lines  

1. Open a warehouse activity line where you are trying to handle an insufficient quantity.  
2. In the **Qty. to Handle** field, enter the reduced quantity that you're able to handle.  
3. On the **Lines** FastTab, choose the **Actions** action, choose the **Functions** action, and then choose the **Split Line** action. A new line appears. The line is a copy of the original line except that the **Qty. to Handle** field contains the quantity that you removed from the original line.  
4. Assign a bin and, if you're using directed put-away and pick, a zone, or continue splitting the line as necessary until you find appropriate bins for all of the quantity.  

> [!NOTE]  
> If the location uses directed put-away and pick and you split the lines, you must be familiar with the warehouse and be able to choose a bin that matches the storage requirements of the item and that fulfills the general requirements of the warehouse document. For example, you would not split a line on a pick document and place some items in bulk storage.  

## Related information  

[Warehouse Management Overview](design-details-warehouse-management.md)
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]