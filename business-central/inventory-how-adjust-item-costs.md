---
title: Manually adjust the costs of items
description: You can adjust the inventory valuation of an item using the FIFO or Average costing methods when the costs of products change.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: cost adjustment, cost forwarding, costing method, inventory valuation, costing
ms.date: 04/28/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Adjust item costs

The cost of an item (inventory value) that you purchase and later sell might change during its lifetime, for example because a freight cost is added to its purchase cost after you sell the item. Cost adjustment is especially relevant in situations where you sell goods before you invoice the purchase of those goods. To always know the correct inventory value, you should regularly adjust item costs. Correct costs help ensure that sales and profit statistics are up to date and that financial KPIs are correct. To learn more, go to [Design Details: Cost Adjustment](design-details-cost-adjustment.md).

The value in the **Unit Cost** field on the item card is based on the standard cost for items with the Standard costing method. For items with any other costing method, the value is based on the calculation of available inventory (invoiced costs and expected costs) divided by the quantity on hand.

In [!INCLUDE[prod_short](includes/prod_short.md)], item costs are automatically adjusted every time that an inventory transaction occurs, such as when posting a purchase invoice for an item. However, you can also manually adjust the costs of one or more items if needed. For example, manual adjustments are useful when you know that item costs are changed for reasons other than item transactions.

For both automatic and manual adjustments, item costs are adjusted by the FIFO or the Average costing method, depending on your selection in the **Set Up My Company** assisted setup guide or in the **Costing Method** field on the item card. To learn more, go to [Register New Items](inventory-how-register-new-items.md).  

For the FIFO costing method, an item’s unit cost is the actual value of any receipt of the item. Inventory is valued with the assumption that the first items placed in inventory are sold first.

If you use the Average costing method, then an item’s unit cost is calculated as the average unit cost at each point in time after a purchase. Inventory is valuated with the assumption that all inventories are sold simultaneously. For items that use this costing method, you can choose the **Unit Cost** field on the item card to view the history of transactions that the average cost is calculated from

Cost adjustment processes only value entries that aren't adjusted. In a situation where changed inbound costs need to be forwarded to related outbound entries, it creates new adjustment value entries. The adjustment value entries are based on the information in the original value entries but contain the adjustment amount. The cost adjustment function uses the posting date of the original value entry in the adjustment entry, unless that date is in a closed inventory period. In that case, application uses the starting date of the next open inventory period. If inventory periods aren't used, then the date in the **Allow Posting From** field on the **General Ledger Setup** page defines when the adjustment entry is posted.

## To adjust item costs manually

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Adjust Cost - Item Entries**, and then choose the related link.
2. On the **Adjust Cost - Item Entries** page, specify which items to adjust costs for.
3. Choose the **OK** button.

## Track item cost adjustments

Item costs can change for many reasons, so it's important that you can keep track of cost adjustments. Use the **Inventory Cost Adjustment** page to manage and monitor the cost adjustment process. This page displays items along with their costing parameters and cost adjustment status. You can filter the list to focus on items that require adjustment or that are excluded from the cost adjustment process. To learn more about tracking cost adjustments, go to [Track item cost adjustments](finance-track-inventory-costs.md).

## Related information

[Managing Inventory Costs](finance-manage-inventory-costs.md)  
[Inventory](inventory-manage-inventory.md)  
[Sales](sales-manage-sales.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
