---
title: Design Details - Revaluation
description: You can revalue the inventory based on the valuation base that most accurately reflects the inventory value.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 07/07/2023
ms.custom: bap-template
ms.service: dynamics-365-business-central
---

# Design Details: Revaluation

You can revalue the inventory based on the valuation base that most accurately reflects the inventory value. You can also backdate a revaluation to correctly update the cost of goods sold (COGS) for items you've already sold. Items that use the Standard costing method and aren't completely invoiced can also be revalued.  

In [!INCLUDE[prod_short](includes/prod_short.md)], the following flexibility is supported regarding revaluation:  

- The revaluable quantity can be calculated for any date, also back in time.  
- For items using Standard costing method, expected cost entries are included in revaluation.  
- Inventory decreases affected by revaluation are detected.  

## Calculate the revaluable quantity

The quantity you can revalue is the remaining inventory that's available on a given date. The quantity is the total of completely invoiced item ledger entries that you post on or before the revaluation date.  

> [!NOTE]  
>  Items using the Standard costing method are treated differently when calculating the revaluable quantity per item, location, and variant. The quantities and values of item ledger entries that are not completely invoiced are included in the revaluable quantity.  

After a revaluation has been posted, you can post an inventory increase or decrease with a posting date that comes before the revaluation posting date. However, this quantity will not be affected by the revaluation. To balance the inventory, only the original revaluable quantity is considered.  

Because you can revaluate on any date, you must have conventions for when you consider an item as part of inventory. For example, when the item is on inventory and when the item is work in process (WIP).  

### Example  

The following example illustrates when a WIP item transitions to become part of inventory. The example is based on the production of a chain with 150 links.  

![WIP inventory and revaluation.](media/design_details_inventory_costing_10_revaluation_wip.png "WIP inventory and revaluation")  

**1Q**: The user posts the purchased links as received. The following table shows the resulting item ledger entry.  

|Posting Date|Item|Entry Type|Quantity|Entry No.|  
|------------------|----------|----------------|--------------|---------------|  
|01-01-20|LINK|Purchase|150|1|  

> [!NOTE]  
>  Now an item using the Standard costing method is available for revaluation.  

**1V**: The user posts the purchased links as invoiced and the links become part of inventory, from a financial point of view. The following table shows the resulting value entries.  

|Posting Date|Entry Type|Valuation Date|Cost Amount (Actual)|Item Ledger Entry No.|Entry No.|  
|------------------|----------------|--------------------|----------------------------|---------------------------|---------------|  
|01-15-20|Direct Cost|01-01-20|150.00|1|1|  

 **2Q + 2V**: The user posts the purchased links as consumed for the production of the iron chain. From a financial point of view, the links become part of WIP inventory.  The following table shows the resulting item ledger entry.  

|Posting Date|Item|Entry Type|Quantity|Entry No.|  
|------------------|----------|----------------|--------------|---------------|  
|02-01-20|LINK|Consumption|-150|1|  

The following table shows the resulting value entry.  

|Posting Date|Entry Type|Valuation Date|Cost Amount (Actual)|Item Ledger Entry No.|Entry No.|  
|------------------|----------------|--------------------|----------------------------|---------------------------|---------------|  
|02-01-20|Direct Cost|02-01-20|-150.00|2|2|  

The valuation date is set to the date of the consumption posting (02-01-20), as a regular inventory decrease.  

**3Q**: The user posts the chain as output and finishes the production order. The following table shows the resulting item ledger entry.  

|Posting Date|Item|Entry Type|Quantity|Entry No.|  
|------------------|----------|----------------|--------------|---------------|  
|02-15-20|CHAIN|Output|1|3|  

**3V**: The user runs the **Adjust Cost - Item Entries** batch job, which posts the chain as invoiced to indicate that all material consumption has been completely invoiced. From a financial point of view, the links are no longer part of WIP inventory when the output is completely invoiced and adjusted. The following table shows the resulting value entries.  

|Posting Date|Entry Type|Valuation Date|Cost Amount (Actual)|Item Ledger Entry No.|Entry No.|  
|------------------|----------------|--------------------|----------------------------|---------------------------|---------------|  
|01-15-20|Direct Cost|01-01-20|150.00|2|2|  
|02-01-20|Direct Cost|02-01-20|-150.00|2|2|  
|02-15-20|Direct Cost|02-15-20|150.00|3|3|  

## Expected cost in revaluation

The quantity you can revalue is the sum of the quantity for completely invoiced item ledger entries that you posted on or before the revaluation date. When some items are received or shipped but not invoiced, you can't calculate their inventory value. Items that use the Standard costing method are not limited in this way.  

> [!NOTE]  
>  Another type of expected cost that can be revalued is WIP inventory, within certain rules. For more information, see [WIP Inventory Revaluation](design-details-revaluation.md#wip-inventory-revaluation).  

When you calculate the revaluable quantity for items that use the Standard costing method, the calculation includes item ledger entries that aren't completely invoiced. These entries are revalued when you post the revaluation. When you invoice the revalued entry, you create the following value entries:  

- The usual invoiced value entry with an entry type of **Direct Cost**. The cost amount on this entry is the direct cost from the source line.  
- A value entry with an entry type of **Variance**. This entry records the difference between the invoiced cost and the revalued standard cost.  
- A value entry with an entry type of **Revaluation**. This entry records the reversal of the revaluation of the expected cost.

### Example  

The following example is based on the production of the chain in the previous example. This example illustrates how the three types of entries are created, based on the following scenario:  

1.  You post the purchased links as received with a unit cost of LCY 2.00.  
2.  You post a revaluation of the links with a new unit cost of LCY 3.00, updating the standard cost to LCY 3.00.  
3.  You post the original purchase of the chain links as invoiced, which creates the following value entries:  

    1.  An invoiced value entry with an entry type of **Direct Cost**.  
    2.  A value entry with an entry type of **Revaluation** to record the reversal of the revaluation of the expected cost.  
    3.  A value entry with an entry type of Variance, recording the difference between the invoiced cost and the revalued standard cost.  

The following table shows the results.  

|Step|Posting Date|Entry Type|Valuation Date|Cost Amount (Expected)|Cost Amount (Actual)|Item Ledger Entry No.|Entry No.|  
|----------|------------------|----------------|--------------------|------------------------------|----------------------------|---------------------------|---------------|  
|1.|01-15-20|Direct Cost|01-15-20|300.00|0.00|1|1|  
|2.|01-20-20|Revaluation|01-20-20|150.00|0.00|1|2|  
|3.a.|01-15-20|Direct Cost|01-15-20|-300.00|0.00|1|3|  
|3.b.|01-15-20|Revaluation|01-20-20|-150.00|0.00|1|4|  
|3.c.|01-15-20|Variance|01-15-20|0.00|450.00|1|5|  

## Determine whether revaluation affects an inventory decrease  

Use the date of the posting or the revaluation to determine whether an inventory decrease is affected by a revaluation.  

The following table shows the criteria that's used for an item that doesn't use the Average costing method.  

|Scenario|Entry No.|Timing|Affected by revaluation|  
|--------------|---------------|------------|-----------------------------|  
|A|Earlier than revaluation entry number|Earlier than revaluation posting date|No|  
|B|Earlier than revaluation entry no.|Equal to revaluation posting date|No|  
|C|Earlier than revaluation entry no.|Later than revaluation posting date|Yes|  
|D|Later than revaluation entry no.|Earlier than revaluation posting date|Yes|  
|E|Later than revaluation entry no.|Equal to revaluation posting date|Yes|  
|F|Later than revaluation entry no.|Later than revaluation posting date|Yes|  

### Example  

The following example illustrates revaluation of an item that uses the FIFO costing method. The example is based on the following scenario:  

1.  On 01-01-20, you post a purchase of 6 units.  
2.  On 02-01-20, you post a sale of 1 unit.  
3.  On 03-01-20, you post a sale of 1 unit.  
4.  On 04-01-20, you post a sale of 1 unit.  
5.  On 03-01-20, you calculate the inventory value for the item, and post a revaluation of the item’s unit cost from LCY 10.00 to LCY 8.00.  
6.  On 02-01-20, you post a sale of 1 unit.  
7.  On 03-01-20, you post a sale of 1 unit.  
8.  On 04-01-20, you post a sale of 1 unit.  
9. You run the **Adjust Cost - Item Entries** batch job.  

The following table shows the resulting value entries.  

|Scenario|Posting Date|Entry Type|Valuation Date|Valued Quantity|Cost Amount (Actual)|Item Ledger Entry No.|Entry No.|  
|--------------|------------------|----------------|--------------------|---------------------|----------------------------|---------------------------|---------------|  
||01-01-20|Purchase|01-01-20|6|60.00|1|1|  
||03-01-20|Revaluation|03-01-20|4|-8.00|1|5|  
|A|02-01-20|Sale|02-01-20|-1|-10.00|2|2|  
|B|03-01-20|Sale|03-01-20|-1|-10.00|3|3|  
|C|04-01-20|Sale|04-01-20|-1|-10.00|4|4|  
||04-01-20|Sale|04-01-20|-1|2.00|4|9|  
|D|02-01-20|Sale|03-01-20|-1|-10.00|5|6|  
||02-01-20|Sale|03-01-20|-1|2.00|5|10|  
|E|03-01-20|Sale|03-01-20|-1|-10.00|6|7|  
||03-01-20|Sale|03-01-20|-1|2.00|6|11|  
|F|04-01-20|Sale|04-01-20|-1|-10.00|7|8|  
||04-01-20|Sale|04-01-20|-1|2.00|7|12|  

## WIP inventory revaluation  

Revaluating WIP inventory implies that you revalue components that are registered as WIP inventory.  

It's important to have conventions that control when an item is WIP inventory from a financial point of view. In [!INCLUDE[prod_short](includes/prod_short.md)], the following conventions exist:  

- A purchased component becomes part of the raw material inventory when you post a purchase as invoiced.  
- A purchased/sub-assembled component becomes part of the WIP inventory when you post its consumption with a production order.  
- A purchased/sub-assembled component remains part of the WIP inventory until you invoice a production order (manufactured item).  

The way the valuation date for the value entry of consumption is set follows the same rules as for non-WIP inventory. To learn more, go to [Determine whether revaluation affects an inventory decrease](#determine-whether-revaluation-affects-an-inventory-decrease).  

You can revalue WIP inventory under the following conditions:

- The revaluation date is before the posting dates of the corresponding item ledger entries of type Consumption.
- You haven't invoiced the production order.  

> [!CAUTION]  
> The **Inventory Valuation - WIP** report shows the value of posted production order entries, and might be a little confusing for revalued WIP items.  

## Revaluate items with the Average costing method

You can only revaluate items that use the Average costing method if **Calculate Per** is *Item*.

You can only do revaluation at the end of the period selected in the **Average Cost Period** field on the **Inventory Setup** page.

Revaluation won't affect negative transactions in the current month, which is why fully applied inbound entries aren't included either.

### Example

This example shows what happens when you calculate the inventory value on the **Item Revaluation Journal** page. On the **Inventory Setup** page, **Item** is chosen in the **Average Cost Calc. Type** field, and **Month** is chosen in the **Average Cost Period** field.

The following table shows item ledger entries for the sample average-cost item, ITEM1.

|Posting Date|Item Ledger Entry Type|Quantity|Cost Amount (Actual)|Entry No.|
|----|----|----|----|----|
25-04-23|Purchase|5|5.00|1
26-04-23|Purchase|3|3.00|2
27-04-23|Sale|-5|-5.00|3
28-04-23|Sale|-1|-1.00|4
13-05-23|Purchase|2|20.00|5
17-06-23|Sale|-6|-22.00|6

The following table shows the result of running the **Calculate Inventory Value** report with different posing dates.

|Posting Date|Quantity|Comment|
|---|---|-------------|
30-04-23|2|Includes only the remaining quantity from entry 2. Entry 1 is completely applied before the posting date, and entry 5 is after posting date.
31-05-23|4|Includes the remaining quantities from entries 2 and 13.
30-06-23|0|No remaining quantity at posting date.

The result of the following entries will be 0, regardless of the posting date.

|Posting Date|Item Ledger Entry Type|Quantity|Cost Amount (Actual)|Entry No.|
|----|----|----|----|----|
13-05-23|Purchase|5|5.00|1
26-04-23|Sale|-5|5.00|2

## Related information  

[Design Details: Inventory Costing](design-details-inventory-costing.md)   
[Design Details: Costing Methods](design-details-costing-methods.md)   
[Design Details: Inventory Valuation](design-details-inventory-valuation.md)
[Managing Inventory Costs](finance-manage-inventory-costs.md)  
[Finance](finance.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
