---
title: About finished production order costs
description: Finishing the production order is key to completing the costing lifecycle of a production item.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.form: 99000867,
ms.date: 07/01/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template

---
# About finished production order costs

Finishing a production order is an important task in completing the costing lifecycle of the item that you're producing. Final costs, including variances in a standard cost environment, actuals in a FIFO, Average, or LIFO cost environment, are calculated using the **Adjust Cost - Item Entries** batch job. The batch job allows for financial reconciliation of the costs of item production. For a production order to be considered for cost adjustment, its status must be **Finished**, so it's important to update the status when the order is complete.

## Example

In a standard cost environment, when you consume material to produce an item, stated simply, the cost of the item plus labor and overhead go into WIP. When the item is produced, WIP is reduced by the amount of the standard cost of the item. Typically, these costs don't net to zero. So that these costs can net to zero, you must run the **Adjust Cost - Item Entries** batch job, noting that only production orders with the status of **Finished** are considered for adjustment.  

## Related information

[Managing Inventory Costs](finance-manage-inventory-costs.md)  
[Manufacturing](production-manage-manufacturing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
