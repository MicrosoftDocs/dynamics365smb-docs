---
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: include
ms.date: 03/03/2025
ms.service: dynamics-365-business-central
---

You can pick more raw materials for a production order than it initially required, which can be useful in several cases. For example, overpicking might let you pick an entire pallet, use what you need, and then return the excess to inventory. You can also post consumption of the over-picked components.

To allow over-picks for an item in production, turn on the **Allow Whse. Overpick** toggle on the **Item Card** page. You can also use the same setting on an item template to allow over-picks for all items that you create based on the template. Afterward, you can adjust the value in the **Quantity** field for the **Take** line on the warehouse pick you create for a production order.

To return excess items to the warehouse, use the **Movement worksheet** and the **Get Bin Content** action.

To post more consumption, you can either increase the value in the **Quantity Per** field on the **Production Order Components** page, or enter the required quantity on the **Consumption Journal** or **Production Journal** pages directly. If the new quantity in the journal is less than or equal to the quantity picked, you can post consumption.

> [!NOTE]
> This feature applies to warehouse picks for production orders only. Inventory picks and movements aren't supported. Also, warehouse picks for other source documents aren't supported.
