---
title: About finished production order costs
description: Learn how finished production orders reconcile material, capacity, subcontracting, overhead, work-in-process, inventory, and variances.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.form: 99000867,
ms.date: 07/15/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template

---
# About finished production order costs

A finished production order brings together the actual cost of consumed materials, capacity, subcontracting, and overhead for the items produced. Cost adjustment reconciles those costs with work in process and inventory and calculates variances when you use standard costing. This article explains why production orders must be finished before their final costs can be adjusted.

Final costs, including variances in a standard cost environment and actual costs in a FIFO, Average, or LIFO cost environment, are calculated by using the **Adjust Cost - Item Entries** batch job. For a production order to be considered for cost adjustment, its status must be **Finished**, so it's important to update the status when the order is complete.

## Example

In a standard cost environment, when you consume material to produce an item, stated simply, the cost of the item plus labor and overhead go into WIP. When the item is produced, WIP is reduced by the amount of the standard cost of the item. Typically, these costs don't net to zero. So that these costs can net to zero, you must run the **Adjust Cost - Item Entries** batch job, noting that only production orders with the status of **Finished** are considered for adjustment.  

## Related information

[Managing Inventory Costs](finance-manage-inventory-costs.md)  
[Manufacturing](production-manage-manufacturing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
