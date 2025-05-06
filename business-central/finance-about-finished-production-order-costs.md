---
title: About Finished Production Order Costs
description: Finishing the production order is key to completing the costing lifecycle of a production item. Final costs are calculated in Adjust Cost Item Entries batch job.
author: brentholtorf
ms.topic: concept-article
ms.search.form: 99000867
ms.date: 06/16/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# About Finished Production Order Costs

Finishing the production order is an important task in completing the costing lifecycle of the item that is being produced. Final costs, including variances in a standard cost environment, actuals in a FIFO, Average, or LIFO cost environment, are calculated using the **Adjust Cost - Item Entries** batch job, which allows for financial reconciliation of the costs of item production. For a production order to be considered for cost adjustment, the status must be **Finished**. It is therefore critical that upon completion, the status of a production order is changed to **Finished**.  

## Example

In a standard cost environment, when you consume material to produce an item, stated simply, the cost of the item plus labor and overhead go into WIP. When the item is produced, WIP is reduced by the amount of the standard cost of the item. Typically, these costs do not net to zero. So that these costs can net to zero, you must run the **Adjust Cost - Item Entries** batch job, noting that only production orders with the status of **Finished** will be considered for adjustment.  

## Related information

[Managing Inventory Costs](finance-manage-inventory-costs.md)  
[Manufacturing](production-manage-manufacturing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
