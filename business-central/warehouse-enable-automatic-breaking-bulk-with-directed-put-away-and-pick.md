---
title: Breaking Bulk with Directed Put-away and Pick
description: Learn how to enable automatic breaking bulk with directed put-away and pick, as well as breakbulking in picks, put-aways, movements, and more.
author: brentholtorf
ms.topic: concept-article
ms.devlang: al
ms.search.keywords:
ms.search.form: 5703, 7352
ms.date: 11/04/2022
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Enable Automatic Breaking Bulk with Directed Put-away and Pick

For locations that use directed put-away and pick, [!INCLUDE[prod_short](includes/prod_short.md)] can break larger units of measure into smaller units of measure when it creates warehouse instructions for source documents, production orders, or internal picks and put-aways. To breakbulk can also mean gathering items in smaller units of measure to equal the quantity of a larger unit of measure on a source document or production order.

## Breakbulk in picks  

If you want to store items in several different units of measure in a location and allow them to be automatically combined in the picking process, turn on the **Allow Breakbulk** toggle on the Location Card page. Afterward, to fulfill a task [!INCLUDE [prod_short](includes/prod_short.md)] will look for an item in the same unit of measure. If it doesn't find one, [!INCLUDE [prod_short](includes/prod_short.md)] will suggest that you break a larger unit of measure into the unit of measure that is needed.  

If only smaller units of measure are available, [!INCLUDE [prod_short](includes/prod_short.md)] will suggest that you gather items to fulfill the quantity on the shipment or production order. In effect, it breaks the larger unit of measure on the source document into smaller units for picking.  

## Breakbulk in put-aways  

In warehouse put-aways, [!INCLUDE [prod_short](includes/prod_short.md)] suggests Place action lines in the put-away unit of measure. For example, it might suggest pieces even though the items arrive in a different unit of measure.  

## Breakbulk in movements  

[!INCLUDE [prod_short](includes/prod_short.md)] can also breakbulk in replenishment movements if the **Allow Breakbulk** toggle on the **Calculate Bin Replenishment** page is turned on.  

You can view the results of the conversion process from one unit of measure to another as intermediate breakbulk lines in the put-away, pick, or movement instructions.  

> [!NOTE]  
> If you select the **Set Breakbulk Filter** field on the warehouse instruction header, application will hide the breakbulk lines whenever the larger unit of measure is going to be completely used. For example, if a pallet is 12 pieces and you'll use all 12 pieces, the pick will then direct you to take 1 pallet and place 12 pieces. However, if you must pick only 9 pieces the breakbulk lines aren't hidden, even if you've selected the **Breakbulk Filter** field. The lines aren't hidden because you must put the remaining three pieces somewhere in the warehouse.  

> [!NOTE]  
> If you want your units of measure to perform optimally in the warehouse, also in connection with breakbulk, you should try to:  
>
> - Set up the base unit of measure for an item as the smallest unit of measure that you expect to handle in your warehouse processes.  
> - Set up your alternative units of measure for the item as multiples of the base unit of measure.  

## Related information  

[Warehouse Management Overview](design-details-warehouse-management.md)
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md) 
[Assembly Management](assembly-assemble-items.md)
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
