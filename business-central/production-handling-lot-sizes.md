---
title: Handling Lot Sizes
description: This topic describes different ways to handle lot sizes. 
author: brentholtorf
ms.topic: concept-article
ms.devlang: al
ms.search.form:
ms.date: 04/01/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Handling Lot Sizes in Production
In terms of quantity, the number of items you produce in a production operation might not correlate to how sell them. For example, you might produce hundreds of items in a single lot, but sell each item individually. When you configure your production routes and bills of materials (BOMs), there are few nuances you should consider with regards to lot sizes. This topic describes how lot sizes impact cost calculations and resource planning.

## Units of Measure in Production Bill of Materials
Although you specify the base unit of measure (UOM) for an item, your BOM might use a different UOM for the finished product. For example, the base UOM for an item might be PCS, but your BOM might call for pallet or ton. This comes in handy when your machines or raw components dictate the volume. For example, you probably wouldn't want to bake a single muffin because it is difficult to use a portion of an egg. Instead, you bake a batch of muffins to reduce waste. For more information, see [Create Production BOMs](production-how-to-create-production-boms.md).

## Lot size on routing lines
From a routing perspective, you can specify a lot size on routing lines to align with the capacity of the machines that produce the items. The run time on routing lines is reduced proportionally to the lot size. 

This works well when the quantity on a production order is a factor of the lot size on the route. For example, if your baking sheet can hold 10 muffins, you should bake 10, 20, 30, and so on, and not 5 nor 15.  This is much less of an issue if you are dealing with large quantities.

Lot size is also popular in manufacturing environments where output is measured as quantity you can make during fixed amount of time. Example, if Volume per 9 hour shift is 25000 cubic feet, you can set run time as 9 hours and lot size as 25000.
The production order quantity becomes less important as on the production order the run time gets calculated as the Run time / Lot size to get the run time per piece.
 
> [!NOTE]
> The value defined in Lot size doesn't have impact on time specified in **Setup Time** field of the routing line. The setup will happen only one time, even if there are several lots. For example, so that you don’t need to warm the oven for the second lot of muffins. For more information, see [Create Routings](production-how-to-create-routings.md).

## Lot Sizes for Items and Stockkeeping Units
Lot sizes defined for routings are not the same as lot sizes for items or stockkeeping units. Those values are used for a different purpose, and do not affect production capacity. 

## Lot size on item and stockkeeping units
For items and stockkeeping units, lot sizes have the following effects on cost calculation and supply planning:

* For standard cost calculation, if you enable **Cost Incl Setup** on the **Manufacturing Setup** page, the cost for the setup is added to the standard cost. If you specify a lot size, the setup cost for routing operation will be reduced according to one lot size. For example, if your lot size defined on item card is 10, and it takes 15 minutes to heat the oven, the cost of the fuel will be allocated to the 10 muffins as roughly 1.5 minutes. 

> [!NOTE]
> Setup costs are handled differently from a standard cost and capacity allocation perspectives. If produced quantity doesn't match lot size defined in the item card that will lead to variation. For more information, see [Managing Inventory Costs](finance-manage-inventory-costs.md). <!--not sure that I got this part right seems to repeat the first example.-->

For supply planning, the lot size setting on items works with the **Default Dampener %** on the **Manufacturing Setup** page. [!INCLUDE[prod_short](includes/prod_short.md)] will ignore changes in demand that are below the dampener percentage and will not create planning suggestions. For example, 15 is specified in the Default Dampener % field, and we have a production order for 20 muffins to feed 20 guests, but one guest cannot attend. [!INCLUDE[prod_short](includes/prod_short.md)] will ignore the single missing guest because it's only 10% of the lot size 10 defined on the item. However, if two guests cannot make it, [!INCLUDE[prod_short](includes/prod_short.md)] will suggest that we reduce the order quantity because two is 20% of the lot size. For more information about planning, see [Planning](production-planning.md).

## Related information
[Create Production BOMs](production-how-to-create-production-boms.md)  
[Work with Manufacturing Batch Units of Measure](production-how-to-use-the-manufacturing-batch-unit-of-measure.md)
[Create Routings](production-how-to-create-routings.md)  
[Managing Inventory Costs](finance-manage-inventory-costs.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
