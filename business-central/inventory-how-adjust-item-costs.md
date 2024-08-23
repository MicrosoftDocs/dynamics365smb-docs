---
title: Manually adjust the costs of items
description: You can adjust the inventory valuation of an item using the FIFO or Average costing methods when the costs of products change.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: cost adjustment, cost forwarding, costing method, inventory valuation, costing
ms.date: 07/29/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Adjust item costs

The cost of an item (inventory value) that you purchase and later sell might change during its lifetime, for example because a freight cost is added to its purchase cost after you sell the item. Cost adjustment is especially relevant in situations where you sell goods before you invoice the purchase of those goods. To always know the correct inventory value, you should regularly adjust item costs. Correct costs help ensure that sales and profit statistics are up to date and that financial KPIs are correct. For more information, see [Design Details: Cost Adjustment](design-details-cost-adjustment.md).

The value in the **Unit Cost** field on the item card is based on the standard cost for items with the Standard costing method. For items with any other costing method, the value is based on the calculation of available inventory (invoiced costs and expected costs) divided by the quantity on hand. For more information, see [Understanding Unit Cost Calculation](inventory-how-adjust-item-costs.md#understanding-unit-cost-calculation).

In [!INCLUDE[prod_short](includes/prod_short.md)], item costs are automatically adjusted every time that an inventory transaction occurs, such as when posting a purchase invoice for an item.

You can also manually adjust the costs of one or more items. For example, manual adjustments are useful when you know that item costs are changed for reasons other than item transactions.

Item costs are adjusted by the FIFO or the Average costing method, depending on your selection in the **Set Up My Company** assisted setup guide or in the **Costing Method** field on the item card. For more information, see [Register New Items](inventory-how-register-new-items.md).  

For the FIFO costing method, an item’s unit cost is the actual value of any receipt of the item. Inventory is valued with the assumption that the first items placed in inventory are sold first.

If you use the Average costing method, then an item’s unit cost is calculated as the average unit cost at each point in time after a purchase. Inventory is valuated with the assumption that all inventories are sold simultaneously. For items that use this costing method, you can choose the **Unit Cost** field on the item card to view the history of transactions that the average cost is calculated from

Cost adjustment processes only value entries that aren't adjusted. In a situation where changed inbound costs need to be forwarded to related outbound entries, it creates new adjustment value entries. The adjustment value entries are based on the information in the original value entries but contain the adjustment amount. The cost adjustment function uses the posting date of the original value entry in the adjustment entry, unless that date is in a closed inventory period. In that case, application uses the starting date of the next open inventory period. If inventory periods aren't used, then the date in the **Allow Posting From** field on the **General Ledger Setup** page defines when the adjustment entry is posted.

## To adjust item costs manually

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Adjust Cost - Item Entries**, and then choose the related link.
2. On the **Adjust Cost - Item Entries** page, specify which items to adjust costs for.
3. Choose the **OK** button.

## To make general changes in the direct unit cost

If you need to change the direct unit cost for several items, you can use the **Adjust Item Costs/Prices** batch job.  

The batch job changes the contents in the **Unit Price** field on the item card. The batch job changes the content of the field in the same way for all items or selected items. The batch job multiplies the value in the field by an adjustment factor that you specify.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Adjust Item Costs/Prices**, and then choose the related link.  
2. In the **Adjust Field** field, specify which item or SKU card field you want to adjust.  
3. In the **Adjustment Factor** field, specify the factor by which to adjust the value. For example, enter **1.5** to increase the value by 50%.  
4. On the **Item** FastTab, set filters to specify, for example, which items to process with the batch job.  
5. Choose the **OK** button.  

## Understanding unit cost calculation

The value in the **Unit Cost** field on the item card is based on the standard cost for items with the Standard costing method. For items with any other costing methods, the value is based on the calculation of available inventory (invoiced costs and expected costs) divided by the quantity on hand.  

How the contents of the **Costing Method** field influence the unit cost calculation for purchases and sales is described in more detail in the following sections.  

## Unit cost calculation for purchases  

When you purchase items, the value in the **Last Direct Cost** field on the item card copies to the **Direct Unit Cost** field on a purchase line or to the **Unit Amount** line on an item journal line.  

What you select in the **Costing Method** field influences how [!INCLUDE[prod_short](includes/prod_short.md)] calculates the contents of the **Unit Cost** field on the lines.  

### FIFO, LIFO, Specific, or Average costing methods  

[!INCLUDE[prod_short](includes/prod_short.md)] uses the following formula to calculate the contents of the **Unit Cost (LCY)** field on the purchase line or the contents of the **Unit Cost** field on the item journal line:  

Unit Cost (LCY) = (Direct Unit Cost – (Discount Amount / Quantity)) x (1 + Indirect Cost % / 100) + Overhead Rate  

### Standard costing method  

The **Unit Cost (LCY)** field on the purchase line or the **Unit Cost** field is filled on the item journal line by copying the value in the **Unit Cost** field on the item card. If you use the Standard costing method, the value is always based on the standard cost.  

When you post a purchase, the unit cost from the purchase line or item journal line copies to the purchase item invoice entry. It shows on the entry list for the item.  

### All costing methods  

The unit cost from the source document line is used to calculate the value in the **Cost Amount (Actual)** field or, if applicable, the **Cost Amount (Expected)** field that relates to this item entry. The cost is included in the calculation regardless of the item's costing method.  

## Unit cost calculation for sales  

When you sell items, the unit cost copies from the **Unit Cost** field on the item card to the sales line or the item journal line.  

When you post, the unit cost copies to the sales invoice item entry, and it shows on the entry list for the item. [!INCLUDE[prod_short](includes/prod_short.md)] uses the unit cost from the source document line to calculate the contents of the **Cost Amount (Actual)** field or, if applicable, the **Cost Amount (Expected)** field in the value entry related to this item entry.  

## Track item cost adjustments

Item costs can change for many reasons, so it's important that you can keep track of cost adjustments. Use the **Inventory Cost Adjustment** page to manage and monitor the cost adjustment process. This page displays items along with their costing parameters and cost adjustment status. You can filter the list to focus on items that require adjustment or that are excluded from the cost adjustment process. To learn more about tracking cost adjustments, go to [Track item cost adjustments](finance-track-inventory-costs.md).

## See also

[Managing Inventory Costs](finance-manage-inventory-costs.md)  
[Inventory](inventory-manage-inventory.md)  
[Sales](sales-manage-sales.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]