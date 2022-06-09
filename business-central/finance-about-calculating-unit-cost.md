---
title: About Unit Cost Calculation
description: Learn how the costing method and other factors impact the Unit Cost field on the Item card.
author: rubenseishima

ms.service: dynamics365-business-central
ms.topic: article
ms.date: 03/06/2022
ms.author: a-reishima
---
# About Unit Cost Calculation

The unit cost for items can be calculated in different ways according to how the **Costing Method** was defined in the [Company Setup](setup-best-practices-costing-method.md) or in the item card. The costing method determines whether an actual or a budgeted value is used in the cost calculation.

As a rule, with costing method set as Standard, the **Unit Cost** field value is based on the standard cost for the item. The option also sets the field in the item card non-editable.

For items with all other costing methods (FIFO, LIFO, Specific, or Average), the value is based on the calculation of the inventory available (expected costs and invoiced costs) divided by the quantity on hand.

> [!NOTE]
> You cannot change a costing method for an item after you have included the item in a transaction. For solutions on how to fix an incorrect costing method assigned to an item, see [Design Details: Changing the Costing Method for Items](design-details-changing-costing-methods.md).

## Available costing methods

|Costing method |Description |
|---------------|------------|
|Standard |The item's unit cost is preset. |
|FIFO |An item's unit cost is the actual value of any receipt of the item, selected by the FIFO rule. |
|LIFO |An item's unit cost is the actual value of any receipt of the item, selected by the LIFO rule. |
|Average |An item's unit cost is calculated as the average unit cost at each point in time after a purchase. |
|Specific |An item's unit cost is the exact cost at which the particular unit was received. |

For more information, see [About Inventory Costing](finance-learn-about-costing.md).

## Unit Cost Calculation for Purchases  

When you purchase items, the value in the **Last Direct Cost** field on the item card is copied to the **Direct Unit Cost** field on a purchase line or to the Unit Amount line on an item journal line.

What you select in the **Costing Method** field influences how [!INCLUDE[prod_short](includes/prod_short.md)] calculates the contents of the **Unit Cost** field on the lines.

### Costing Method FIFO, LIFO, Specific, or Average  

[!INCLUDE[prod_short](includes/prod_short.md)] calculates the contents of the **Unit Cost (LCY)** field on the purchase line or the contents of the **Unit Cost** field on the item journal line according to the following formula:

*Unit Cost (LCY) = (Direct Unit Cost – (Discount Amount / Quantity)) x (1 + Indirect Cost % / 100) + Overhead Rate*

### Costing Method Standard  

The **Unit Cost (LCY)** field on the purchase line or the **Unit Cost** field is filled on the item journal line by copying the value in the **Unit Cost** field on the item card. By using costing method set as Standard, this is always based on the standard cost.

When you post the purchase, the unit cost from the purchase line or item journal line is copied to the purchase item invoice entry, and it can be seen on the entry list for the item.

### All Costing Methods  

The unit cost from the source document line is used to calculate the contents of the **Cost Amount (Actual)** field, or if applicable, the **Cost Amount (Expected)** field that relates to this item entry, regardless of the costing method of the item.

## Unit Cost Calculation for Sales  

When you sell items, the unit cost is copied from the Unit Cost field on the item card to the sales line or the item journal line.

When you post, the unit cost is copied to the sales invoice item entry, and it can be seen on the entry list for the item. [!INCLUDE[prod_short](includes/prod_short.md)] uses the unit cost from the source document line to calculate the contents of the **Cost Amount (Actual)** field, or if applicable, the **Cost Amount (Expected)** field in the value entry related to this item entry.

## When is the unit cost field updated

The selected costing method also influences when the item cost is updated.

When the costing method is set as Standard, the **Unit Cost** field is updated whenever the standard cost is changed. For more information, see [Updating Standard Costs](finance-how-to-update-standard-costs.md).

If the costing method is FIFO, LIFO, Specific, or Average, then the **Unit Cost** is updated in the following cases:

* When the item is cost-adjusted, automatically or by an [Adjust Cost](inventory-how-adjust-item-costs.md#to-adjust-item-costs-manually) task.
* During the posting of purchase invoices, output, or positive adjustment if one of the following conditions is true:
  * The net invoiced quantity of the item changes from negative or zero to positive.
  * The current unit cost is zero.

If one of these conditions is true, then the **Unit Cost** field is updated with the value in the **Last Direct Cost** field on the item card.

> [!NOTE]
> The **Unit Cost** field is not updated if the current unit cost is higher than zero and the new unit cost is zero. A unit cost of zero is considered an exception from regular business. Therefore, the current unit cost is retained to provide the last known, relevant value. This exception applies even if the existing inventory has been revalued to zero.

If you use the Average costing method, then an item’s unit cost is calculated as the average unit cost at each point in time after a purchase. Inventory is valuated with the assumption that all inventories are sold simultaneously. For items that use this costing method, you can choose the **Unit Cost** field on the item card to view the history of transactions that the average cost is calculated from in the **Average Cost Calc. Overview** window.

## See also

[Managing Inventory Costs](finance-manage-inventory-costs.md)  
[Registering New Items](inventory-how-register-new-items.md)  
[Inventory](inventory-manage-inventory.md)  
[Sales](sales-manage-sales.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Design Details: Costing Methods](design-details-costing-methods.md)  
[Design Details: Cost Adjustment](design-details-cost-adjustment.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
