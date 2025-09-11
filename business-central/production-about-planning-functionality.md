---
title: About planning functionality
description: Learn how planning uses demand and supply data to suggest how to balance supply to meet demand.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.form: 5430,
ms.date: 09/11/2025
ms.custom: bap-template
ms.service: dynamics-365-business-central
---
# About planning functionality

The planning system takes all demand and supply data into account, nets the results, and creates suggestions for balancing supply to meet demand. To learn more, go to [Design Details: Supply Planning](design-details-supply-planning.md).  

> [!TIP]  
> To understand the fields that this article mentions, read their tooltip in [!INCLUDE [prod_short](includes/prod_short.md)]. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## Supply and demand

Planning has two elements, supply and demand, that must balance to ensure that the demand is met.  

- Demand is any kind of gross requirement. For example, a sales or service order, or a component need for assembly or production orders, outbound transfer, blanket order, or forecast. There are also other technical types of demand, such as a negative production or purchase order, negative inventory, and purchase return.  
- Supply refers to any kind of replenishment. For example, inventory, purchase, assembly, and production order, or inbound transfer. There can also be a negative sales or service order, negative component need, or sales return that also represent supply.  

Another goal of the planning system is to ensure that the inventory doesn't grow unnecessarily. For decreasing demand, the planning system suggests that you postpone, decrease in quantity, or cancel existing replenishment orders.  

## Planning calculation

Anticipated and actual customer demand, and inventory reordering parameters, drive the planning system. Running the planning calculation results in suggestions for specific actions ([Action Messages](production-how-to-run-mps-and-mrp.md#action-messages)) to take for possible replenishment from vendors, transfers between warehouses, or production. If replenishment orders already exist, the suggested actions could be to increase or expedite the orders to meet the changes in demand.  

The basis of the planning routine is in the gross-to-net calculation. Net requirements drive planned order releases, which are scheduled based on the routing information (manufactured items) or the item card lead time (purchased items). Planned order release quantities are based on the planning calculation, and are affected by the parameters set on the individual item cards.  

> [!TIP]
> The planning system relies on how your organization uses locations. To learn more, go to [Planning With or Without Locations](production-planning-with-without-locations.md).

## Planning with manual transfer orders

In the **Replenishment System** field on a SKU card, you can set up the planning system to create transfer orders to balance supply and demand across locations.  

In addition to such automatic transfer orders, you might need to move inventory quantities to another location, irrespective of existing demand. You can manually create a transfer order for the quantity to move. To ensure that the planning system doesn't try to manipulate this manual transfer order, you must set the **Planning Flexibility** on the transfer lines to **None**.  

Contrarily, if you do want the planning system to adjust the transfer order quantities and dates to existing demand, you must set the **Planning Flexibility** field to the default value, Unlimited.

## Planning parameters

The planning parameters control when, how much, and how to replenish based on the various settings on the item card (or stockkeeping unit - SKU), and the inventory and manufacturing setups.  

The following planning parameters exist on the item or SKU card:  

- Dampener Period  
- Dampener Quantity  
- Reordering Policy  
- Reorder Point
- Maximum Inventory  
- Overflow Level  
- Time Bucket  
- Lot Accumulation Period  
- Rescheduling Period  
- Reorder Quantity  
- Safety Lead Time  
- Safety Stock Quantity  
- Assembly Policy  
- Manufacturing Policy  

The following order modifiers exist on the item or SKU card:  

- Minimum Order Quantity  
- Maximum Order Quantity  
- Order Multiple  

Global planning setup fields on the **Inventory Setup** page include:  

- Current Demand Forecast  
- Use Forecast on Locations
- Use Forecast on Variants
- Default Safety Lead Time  
- Blank Overflow Level  
- Combined MPS/MRP Calculation
- Default Dampener Period  
- Default Dampener Quantity  

Global planning setup fields on the **Manufacturing Setup** page include:  

- Dynamic Low-Level Code  
- Components at Location  

To learn more, go to [Design Details: Planning Parameters](design-details-planning-parameters.md)  

## Other important planning fields

### Planning Flexibility

On most supply orders, such as production orders, you can select **Unlimited** or **None** in the **Planning Flexibility** field on the lines.

This setting specifies whether planning considers the supply from the production order line when it calculates action messages.

If the field contains **Unlimited**, the planning system includes the line when calculating action messages. If the field contains **None**, then the line is firm and unchangeable, and the planning system doesn't include the line when calculating action messages.

### Warnings

The **Warning** information field on the **Planning Worksheet** page informs you of any planning line created for an unusual situation with a text, which the user can choose to read additional information. The following warning types exist:

- Emergency
- Exception
- Attention

#### Emergency

The emergency warning displays in two situations:

- The inventory is negative on the planning starting date.
- Back-dated supply or demand events exist.

If an item's inventory is negative on the planning starting date, the planning system suggests an emergency supply order for the negative quantity to arrive on the planning starting date. The warning text states the starting date and the quantity of the emergency order.

Any document lines with due dates before the planning starting date are consolidated into one emergency supply order for the item to arrive on the planning starting date.

#### Exception

The exception warning displays if the projected available inventory drops below the safety stock quantity.

The planning system suggests a supply order to meet the demand on its due date. The warning text states the item's safety stock quantity and the date on which it's violated.

Violating the safety stock level is considered as an exception because it shouldn't occur if the reorder point is set correctly.

> [!NOTE]
> Supply on planning lines with Exception warnings is normally not modified according to planning parameters. Instead, the planning system only suggests a supply to cover the exact demand quantity. However, you can set the planning run up to respect certain planning parameters for planning lines with certain warnings. To learn more, go to the description for the **Respect Planning Parameters for Exception Warnings** field in the [Run Full Planning, MPS, or MRP](production-how-to-run-mps-and-mrp.md) article.

#### Attention

The attention warning displays in two situations:

- The planning starting date is earlier than the work date.
- The planning line suggests changing a released purchase or production order.

> [!NOTE]
> In planning lines with warnings, the **Accept Action Message** field isn't selected, because the planner is expected to further investigate these lines before carrying out the plan.

## Planning worksheets and requisition worksheets

As described in [Planning](production-planning.md), you can choose between two worksheets for most planning activities, the planning worksheet and the requisition worksheet. Most processes are described based on the planning worksheet, but there are a couple of scenarios where the requisition worksheet is preferred.

[!INCLUDE [edit-in-excel](includes/edit-in-excel.md)]

> [!TIP]
> When you process lines in a planning worksheet, you can print more than one firm planned orders. The **Prod. Order** option in the **Report Selection - Production Order** page determines which report to print. The default report is **99000762 Prod. Order - Job Card**. If your production orders lack routing lines or you prefer a more compact report, consider switching to the **5500 Prod. Order Comp. and Routing** report.

### Requisition worksheet

The **Requisition Worksheet** page lists items that you want to order. You can enter items in the worksheet in the following ways:

- Enter the items manually in the worksheet and fill in the relevant fields.
- Use the **Calculate Plan** batch job. The batch job calculates a replenishment plan for items and stockkeeping units that are set up with a replenishment system of **Purchase** or **Transfer**. When you use this batch job, the program automatically fills in the **Action Message** field with a suggestion for an action you can take to replenish the item. The suggestion could be increasing the item quantity on an existing order or creating a new order, for example.
- If you use the **Calculate Plan** batch job from the **Planning Worksheet** page to calculate a replenishment plan, you can use the **Carry Out Action Message** batch job to copy purchase and transfer order proposals from the planning worksheet to the requisition worksheet. This method is practical if separate users are responsible for handling production, purchase, and transfer orders.
- You can use the **Drop Shipment** action to fill in the requisition worksheet lines. This action uses the **Get Sales Orders** batch job to determine the sales order lines that you want to designate for a drop shipment.
- You can use the **Special Order** action to fill in the requisition worksheet lines. This action uses the **Get Sales Orders** batch job to determine the sales order lines that you want to designate for a special order.

Requisition worksheet lines contain detailed information about the items that need to be reordered. You can edit and delete the lines to adjust your replenishment plan, and you can further process the lines by using the **Carry Out Action Message** batch job.

To learn more about planning with locations and transfers, go to [Planning With or Without Locations](production-planning-with-without-locations.md).

> [!TIP]
> When you're working on the **Requisition Worksheet** or **Planning Worksheet** pages, you can organize the lines by sorting on a column name. This sorting is especially useful on the Planning Worksheet page because you can use it for multilevel production orders. By default, lines are sorted by the **Item No.** field. To group lines for a multilevel order, sort by the **Ref. Order No.** field. Also, the **MPS Order** and **Planning Level** fields can help show the hierarchy of the lines.

## Related information

[Design Details: Supply Planning](design-details-supply-planning.md)  
[Planning](production-planning.md)  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Manufacturing](production-manage-manufacturing.md)  
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Setup Best Practices: Supply Planning](setup-best-practices-supply-planning.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
