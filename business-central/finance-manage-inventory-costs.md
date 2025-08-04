---
title: Managing inventory costs
description: Cost management is concerned with recording and reporting business operating costs and includes the reporting of manufacturing costs and inventory costs.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords:
ms.date: 07/01/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Managing inventory costs

Cost management, also referred to as 'costing,' concerns recording and reporting business operating costs. Costing includes the reporting of manufacturing costs and inventory costs, that is, the value of items.

To make sure that inventory costs are recorded correctly, you must set up various fields and pages before you begin to make item transactions. Typically, businesses choose a specific costing method and apply that to inventory items, for example, to help them track the value of items on stock.

The following tables describe a sequence of tasks, with links to the articles that describe them.

|**To...**|**Go to...**|  
|------------|-------------|
|Specify a default costing method for the company to govern how incoming cost is used to assess inventory value and the cost of goods sold.|[Set Up General Inventory Information](inventory-how-setup-general.md)|  
|Specify a costing method on individual items if they require a different costing method.|[Register New Items](inventory-how-register-new-items.md)|  
|Define inventory periods to control inventory value over time by disallowing transaction posting in closed inventory periods.|[Work with Inventory Periods](finance-how-to-work-with-inventory-periods.md)|  
|Ensure that sales returns are applied to the original outbound transaction to preserve inventory value.|**Exact Cost Reversing Mandatory** field on the **Sales & Receivables** page|  
|Ensure that purchase returns are applied to the original inbound transaction to preserve inventory value.|**Exact Cost Reversing Mandatory** field on the **Purchases & Payables** page|
|Set up the rounding rules to apply when adjusting or suggesting item prices and when adjusting or suggesting standard costs.|**Rounding Method** page|  

Central principles to understand are that costing methods define how items are valued when they leave inventory, that cost adjustment updates the cost of goods sold with related purchase costs posted after the sale, and that inventory values must be posted to dedicated G/L accounts at regular intervals.

|**To...**|**Go to...**|  
|------------|-------------|  
|Ensure that you know the cost of shipped items by assigning added item costs, such as freight, physical handling, insurance, and transportation that you incur after selling.|[Use Item Charges to Account for Additional Trade Costs](payables-how-assign-item-charges.md)|
|Appreciate or depreciate the value of one or more items in inventory by posting their current, calculated value.|[Revalue Inventory](inventory-how-revalue-inventory.md)|
|View and manually change certain item application entries that are created automatically during inventory transactions.|[Remove and Reapply Item Ledger Entries](finance-how-to-remove-and-reapply-item-entries.md)|
|Ensure that the cost automatically posts to the general ledger when you post an inventory transaction.|**Automatic Cost Posting** field on the **Inventory Setup** page.|
|Ensure that expected costs post to the general ledger so the interim G/L accounts show an estimate of the amounts due and the cost of the traded items before you invoice them.|**Expected Cost Posting to G/L** field on the **Inventory Setup** page.|
|Define whether to calculate the average cost for an item only, or per item for each stockkeeping unit and for each variant of the item.|**Average Cost Calc. Type** field on the **Inventory Setup** page.|
|Select the period of time you want to use for calculating the weighted average cost of items that use the average costing method.|**Average Cost Period** field on the **Inventory Setup** page.|
|Adjust item costs, either automatically or manually, to forward cost changes from inbound entries to their related outbound entries.|[Adjust Item Costs](inventory-how-adjust-item-costs.md)|
|Perform period-end control and reporting tasks, such as calculate the value of inventory and post costs to the general ledger.|[Reporting Costs and Reconciling with the General Ledger](finance-how-to-post-inventory-costs-to-the-general-ledger.md)|
|Learn how you can use the job queue to move the tasks for adjusting inventory cost or reconciling it with the general ledger to the background.|[Adjust and Reconcile Inventory Cost with General Ledger with Job Queue](finance-adjust-reconcile-inventory-cost-job-queue.md)|
|Use the **Applies-from Entry** field in the item journal to manually create a fixed application between an inbound transaction and the original outbound transaction.|[Close Open Item Ledger Entries Resulting from Fixed Application in the Item Journal](finance-how-to-close-open-item-ledger-entries-resulting-from-fixed-application-in-the-item-journal.md)|
|Ensure that sales returns apply to the original outbound transaction to preserve inventory value.|**Exact Cost Reversing Mandatory** field on the **Sales & Receivables Setup** page.|
|Ensure that purchase returns apply to the original inbound transaction to preserve inventory value.|**Exact Cost Reversing Mandatory** field on the **Purchases & Payables Setup** page.|
|Set up the rounding rules to apply when adjusting or suggesting item prices, and when adjusting or suggesting standard costs.|**Rounding Method** page.|  

Use special costing functions for every-day item transactions in the item operations.

|**To...**|**Go to...**|  
|------------|-------------|  
|Read why standard costs are often used by manufacturing companies as a valuation base for components and end items and how to periodically update the standard costs of components, in assembly or production BOMs, and roll the new costs up to the parent item.|[About Calculating Standard Cost](finance-about-calculating-standard-cost.md)|
|Calculate the unit cost of a BOM item based on the unit costs of its underlying components.|[Work with Bills of Material](inventory-how-work-BOMs.md) |  
|Complete the costing life cycle of a produced item by adjusting the costs and reconciling the value entries with the general ledger.|[About Finished Production Order Costs](finance-about-finished-production-order-costs.md)|  

The following table provides conceptual information to help you understand the principles and definitions that govern the inventory cost accounting features in [!INCLUDE[prod_short](includes/prod_short.md)].

|**To...**|**Go to...**|  
|------------|-------------|  
|Understand all mechanisms in the costing engine, including what happens when you post assembly and production transactions.|[Design Details: Inventory Costing](design-details-inventory-costing.md)|  
|Distinguish the five different costing methods and their effect on cost flows.|[Design Details: Costing Methods](design-details-costing-methods.md)|  
|Learn how item application entries dynamically link inventory decreases with increases to keep control of cost flows.|[Design Details: Item Application](design-details-item-application.md)|  
|Understand the cost adjustment mechanism, which ensures that costs are brought forward even if inventory transactions happen in a random manner.|[Design Details: Cost Adjustment](design-details-cost-adjustment.md)|  
|Distinguish expected cost (not yet invoiced) from actual cost and learn how it is managed in the general ledger.|[Design Details: Expected Cost Posting](design-details-expected-cost-posting.md)|  
|Learn how an item's average cost is dynamically calculated according to the selected average cost period.|[Design Details: Average Cost](design-details-average-cost.md)|  

## Related information

[Managing Inventory Costs](finance-manage-inventory-costs.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Finance](finance.md)  
[Inventory](inventory-manage-inventory.md)  
[Sales](sales-manage-sales.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
