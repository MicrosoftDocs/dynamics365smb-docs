---
title: Manually Adjust the Costs of Items| Microsoft Docs
description: You can adjust the inventory valuation of an item using the FIFO or Average costing methods, for example, when item costs change for reasons other than transactions.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: cost adjustment, cost forwarding, costing method, inventory valuation, costing
ms.date: 04/01/2020
ms.author: sgroespe

---
# Adjust Item Costs
The cost of an item (inventory value) that you purchase and later sell may change during its lifetime, for example because a freight cost is added to its purchase cost after you have sold the item. Cost adjustment is especially relevant in situations where you sell goods before you invoice the purchase of those goods. To always know the correct inventory value, item costs must therefore regularly be adjusted. This ensures that sales and profit statistics are up to date and that financial KPIs are correct. For more information, see [Design Details: Cost Adjustment](design-details-cost-adjustment.md).

As a rule, the value in the **Unit Cost** field on the item card is based on the standard cost for items with costing method standard. For items with all other costing methods, it is based on the calculation of the inventory available (invoiced costs and expected costs) divided by the quantity on hand. For more information, see [Understanding Unit Cost Calculation](inventory-how-adjust-item-costs.md#understanding-unit-cost-calculation).

In [!INCLUDE[d365fin](includes/d365fin_md.md)], item costs are automatically adjusted every time that an inventory transaction occurs, such as when posting a purchase invoice for an item.

You can also use a function to manually adjust the costs of one or more items. This is useful, for example, when you know that item costs have changed for other reasons than item transactions.

Item costs are adjusted by the FIFO or the Average costing method, depending on your selection in the **Set Up My Company** assisted setup guide or in the **Costing Method** field on the item card. For more information, see [Register New Items](inventory-how-register-new-items.md).  

If you use the FIFO costing method, then an item’s unit cost is the actual value of any receipt of the item. Inventory is valuated with the assumption that the first items placed in inventory are sold first.

If you use the Average costing method, then an item’s unit cost is calculated as the average unit cost at each point in time after a purchase. Inventory is valuated with the assumption that all inventories are sold simultaneously. For items that use this costing method, you can choose the **Unit Cost** field on the item card to view the history of transactions that the average cost is calculated from

The cost adjustment function processes only value entries that have not yet been adjusted. If the function encounters a situation where changed inbound costs need to be forwarded to associated outbound entries, then new adjustment value entries are created, which are based on the information in the original value entries but contain the adjustment amount. The cost adjustment function uses the posting date of the original value entry in the adjustment entry, unless that date is in a closed inventory period. In that case, application uses the starting date of the next open inventory period. If inventory periods are not used, then the date in the **Allow Posting From** field on the **General Ledger Setup** page will define when the adjustment entry is posted.

## To adjust item costs manually
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Adjust Cost - Item Entries**, and then choose the related link.
2. On the **Adjust Cost - Item Entries** page, specify which items to adjust costs for.
3. Choose the **OK** button.

## To make general changes in the direct unit cost
If you need to change the direct unit cost for several items, you can use the **Adjust Item Costs/Prices** batch job.  

 The batch job changes the contents in the **Unit Price** field on the item card. The batch job changes the content of the field in the same way for all items or selected items. The batch job multiplies the value in the field by an adjustment factor that you specify.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Adjust Item Costs/Prices**, and then choose the related link.  
2. In the **Adjust Field** field, specify which item or SKU card field you want to adjust.  
3. In the **Adjustment Factor** field, specify the factor by which the value will be adjusted. For example, enter **1.5** to increase the value by 50%.  
4. On the **Item** FastTab, set filters to specify, for example, which items to process with the batch job.  
5. Choose the **OK** button.  

## Understanding Unit Cost Calculation
As a rule, the value in the **Unit Cost** field on the item card is based on the standard cost for items with costing method standard. For items with all other costing methods, it is based on the calculation of the inventory available (invoiced costs and expected costs) divided by the quantity on hand.  

 How the contents of the **Costing Method** field influence the unit cost calculation for purchases and sales is described in more detail in the following sections.  

## Unit Cost Calculation for Purchases  
 When you purchase items, the value in the **Last Direct Cost** field on the item card is copied to the **Direct Unit Cost** field on a purchase line or to the Unit Amount line on an item journal line.  

 What you select in the **Costing Method** field influences how [!INCLUDE[d365fin](includes/d365fin_md.md)] calculates the contents of the **Unit Cost** field on the lines.  

### Costing Method FIFO, LIFO, Specific, or Average  
 [!INCLUDE[d365fin](includes/d365fin_md.md)] calculates the contents of the **Unit Cost (LCY)** field on the purchase line or the contents of the **Unit Cost** field on the item journal line according to the following formula:  

 Unit Cost (LCY) = (Direct Unit Cost – (Discount Amount / Quantity)) x (1 + Indirect Cost % / 100) + Overhead Rate  

### Costing Method Standard  
 The **Unit Cost (LCY)** field on the purchase line or the **Unit Cost** field is filled on the item journal line by copying the value in the **Unit Cost** field on the item card. By using costing method set as Standard, this is always based on the standard cost.  

 When you post the purchase, the unit cost from the purchase line or item journal line is copied to the purchase item invoice entry, and it can be seen on the entry list for the item.  

### All Costing Methods  
 The unit cost from the source document line is used to calculate the contents of the **Cost Amount (Actual)** field, or if applicable, the **Cost Amount (Expected)** field that relates to this item entry, regardless of the costing method of the item.  

## Unit Cost Calculation for Sales  
 When you sell items, the unit cost is copied from the Unit Cost field on the item card to the sales line or the item journal line.  

 When you post, the unit cost is copied to the sales invoice item entry, and it can be seen on the entry list for the item. [!INCLUDE[d365fin](includes/d365fin_md.md)] uses the unit cost from the source document line to calculate the contents of the **Cost Amount (Actual)** field, or if applicable, the **Cost Amount (Expected)** field in the value entry related to this item entry.  

## See Also
[Managing Inventory Costs](finance-manage-inventory-costs.md)  
[Inventory](inventory-manage-inventory.md)  
[Sales](sales-manage-sales.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
