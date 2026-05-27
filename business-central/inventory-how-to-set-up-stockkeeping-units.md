---
title: How to set up stockkeeping units
description: Use stockkeeping units to record information about your items for a specific location or a specific variant.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 07/01/2025
ms.custom: bap-template
ms.search.forms: 5704, 5700, 5702, 5701
ms.service: dynamics-365-business-central
---

# Set up stock keeping units

Use stock keeping units (SKUs) to record information about items for a specific location or a variant. They let you add different information about an item for a specific location, for example:

* A warehouse or distribution center
* Variants, such as different shelf numbers and different replenishment information, for the same item  

## To set up a SKU  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Stock keeping Units**, and then choose the related link.  
2. Choose the **New** action.  
3. Fill in the fields as necessary. The following fields are required: **Item No.**, **Location Code**, and/or **Variant Code**. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

After you set up the first SKU for an item, the **Stockkeeping Unit Exists** checkbox on the **Item** card is selected.  

To create several SKUs for an item, use the **Create Stockkeeping Unit** batch job. To learn more about batch jobs, go to [Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md).  

> [!NOTE]  
> The information on the **Stockkeeping Unit** card has priority over the **Item** card.

> [!Warning]
> If the SKU is supplied through production, go to the **Manufacturing Setup** page and turn on the **Load SKU Cost on Manufacturing** toggle. Otherwise, the **Standard Cost** field isn't used when invoicing and adjusting the actual cost of the produced item. Instead, [!INCLUDE [prod_short](includes/prod_short.md)] uses the value in the **Standard Cost** field on the item, and calculates variances against the cost shares of that item.<br><br>
> After you assign production BOMs and routings to SKUs, run the **Calc. Production Std. Cost** action on the **Stockkeeping Unit Card** page to roll up the component and capacity costs. Subassemblies use information from items. To learn more about standard costs, go to [About Calculating Standard Cost](finance-about-calculating-standard-cost.md).

## Manufacturing fields on stock keeping units

When you set the **Replenishment System** on a SKU card to **Prod. Order**, additional manufacturing fields become available. These fields let you override the item card's manufacturing configuration for a specific location or variant combination.

| Field | Description |
|--|--|
| **Production BOM No.** | Specifies a production BOM that differs from the one on the item card. Use this field when a location requires different components, such as locally sourced materials. |
| **Routing No.** | Specifies a routing that differs from the one on the item card. Use this field when a location uses different production equipment or processes. |
| **Manufacturing Policy** | Overrides the item's manufacturing policy. Choose **Make-to-Stock** for items you produce to replenish inventory, or **Make-to-Order** for items you produce only when a specific demand exists. |
| **Components at Location** | Determines which location to use when calculating component availability. When blank, [!INCLUDE [prod_short](includes/prod_short.md)] uses the production order's location. |
| **Lot Size** | Specifies the lot size for standard cost calculation on the routing's setup time proration. This field overrides the item card's lot size for the SKU location. |

The SKU-level BOM and routing are used when [!INCLUDE [prod_short](includes/prod_short.md)] creates or refreshes production orders for the item at that location. They're also used by the planning system when it generates planned production orders.

> [!TIP]
> Use SKU-level manufacturing data when the same item is produced at multiple locations with different equipment, different component sources, or different cost structures. This approach keeps the item card clean while capturing location-specific variations.

## Related information

[Register New Items](inventory-how-register-new-items.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)  
[Warehouse Management Overview](design-details-warehouse-management.md)
[Inventory](inventory-manage-inventory.md)  
[Assembly Management](assembly-assemble-items.md)    
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
