---
title: How to set up stockkeeping units
description: Use stockkeeping units to record information about your items for a specific location or a specific variant.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 06/05/2026
ms.custom: bap-template
ms.search.forms: 5704, 5700, 5702, 5701
ms.service: dynamics-365-business-central
---

# Set up stock keeping units

Use stockkeeping units (SKUs) to record information about items for a specific location or a variant. They let you add different information about an item for a specific location, for example:

* A warehouse or distribution center.
* Variants, such as different shelf numbers and different replenishment information, for the same item.  

## To set up a SKU  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Stockkeeping Units**, and then choose the related link.  
2. Choose the **New** action.  
3. Fill in the fields as necessary. The following fields are required: **Item No.**, **Location Code**, and/or **Variant Code**. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

After you set up the first SKU for an item, the **Stockkeeping Unit Exists** checkbox on the **Item Card** page is selected.  

To create several SKUs for an item, use the **Create Stockkeeping Unit** batch job. To learn more about batch jobs, go to [Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md).  

> [!NOTE]  
> The information on the **Stockkeeping Unit Card** page has priority over the **Item Card** page.

## Manufacturing fields on stock keeping units

When you set the **Replenishment System** field on a SKU to **Prod. Order**, more manufacturing fields become available. These fields let you override the item's manufacturing configuration for a specific location or variant combination.

| Field | Description |
| -- | -- |
| **Production BOM No.** | Specifies a production BOM that differs from the one on the item. Use this field when a location requires different components, such as locally sourced materials. |
| **Routing No.** | Specifies a routing that differs from the one on the item. Use this field when a location uses different production equipment or processes. |
| **Manufacturing Policy** | Overrides the item's manufacturing policy. Choose **Make-to-Stock** for items you produce to replenish inventory, or **Make-to-Order** for items you produce only when a specific demand exists. |
| **Components at Location** | Determines which location to use when you calculate component availability. When blank, [!INCLUDE [prod_short](includes/prod_short.md)] uses the production order's location. |
| **Lot Size** | Specifies the lot size for standard cost calculation on the routing's setup time proration. This field overrides the item's lot size for the SKU location. |
| **Standard Cost** | Specifies the standard cost for the item at this location. When you turn on the **Load SKU Cost on Manufacturing** toggle on the **Manufacturing Setup** page, production orders use this value instead of the item's standard cost. If the toggle is off, production orders use the item's standard cost and calculate variances against the item's cost shares. Run the **Calc. Production Std. Cost** action on the SKU to roll up component and capacity costs from the SKU's BOM and routing (subassemblies use costs from their items). To learn more, go to [About Calculating Standard Cost](finance-about-calculating-standard-cost.md). |
| **Unit Cost** | Shows the unit cost for the item at this location. This field updates when you run **Calc. Production Std. Cost** or adjust costs. |

[!INCLUDE [prod_short](includes/prod_short.md)] uses the SKU-level BOM and routing when it creates or refreshes production orders for the item at that location. The planning system also uses them when it generates planned production orders.

> [!IMPORTANT]
> When a SKU exists for a production item, [!INCLUDE [prod_short](includes/prod_short.md)] loads the item's values first, then overrides them with any SKU fields that aren't blank. For example, if a SKU has a **Production BOM No.** but no **Routing No.**, the production order uses the SKU's BOM and the item's routing. You only need to fill in the SKU fields that differ from the item.

## Related information

[Register New Items](inventory-how-register-new-items.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)  
[Warehouse Management Overview](design-details-warehouse-management.md)  
[Inventory](inventory-manage-inventory.md)  
[Assembly Management](assembly-assemble-items.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
