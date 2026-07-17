---
title: Manufacturing overview
description: Explore manufacturing capabilities for planning, capacity, production, costing, quality management, subcontracting, and analytics.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.form: 5406, 5407, 5728, 8903, 9011, 9012, 9013, 9041, 9044, 9047, 9323, 9324, 9325, 9326, 9327, 37040, 37041, 37042, 37043, 37044, 37045, 37046, 37047, 37048, 37049, 37055, 99000784, 99000785
ms.date: 07/15/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Manufacturing

> [!NOTE]
> The features described in this article are available only if you have the **Premium** experience. Learn how to [select the Premium experience](ui-experiences.md#to-select-the-premium-experience).

Manufacturing in [!INCLUDE [prod_short](includes/prod_short.md)] helps you plan, schedule, execute, and analyze production. Use production BOMs to define components, routings to define operations, and work and machine centers to model capacity and costs. Production orders coordinate material consumption, operation time, output, and finished goods from planned demand through completion.

Manufacturing connects with supply planning, inventory, warehouse management, costing, subcontracting, quality management, and analytics. Together, these features help you prepare the materials and capacity you need, follow progress on the shop floor, update inventory as items are produced, and understand production performance and costs.

You can record consumption, output, scrap, and operation time manually in production journals or automate some posting by using flushing methods and warehouse activities. The **Production Journal** page combines consumption and output for one released production order, while batch journals can process multiple orders.

There are a few things to set up before you can start production. For example, work centers, routings, and production BOMs. To learn more, go to [Setting Up Manufacturing](production-configure-production-processes.md).

The following table contains a sequence of tasks, with links to the articles that describe them.  

|**To**|**See**|  
|------------|-------------|  
|Understand how production orders work.|[About Production Orders](production-about-production-orders.md)|
|Create production orders manually.|[Create Production Orders](production-how-to-create-production-orders.md)|
| Analyze and monitor your manufacturing KPIs with the Power BI Projects apps. | [Power BI Manufacturing app](manufacturing-powerbi-app.md) |
|Outsource all or selected operations in a production order to a subcontractor.|[Subcontract Manufacturing](production-how-to-subcontract-manufacturing.md)|
|Record and post production output along with material and time consumption for a single released production order line.|[Post Consumption and Output for One Released Production Order Line](production-how-to-register-consumption-and-output.md)|  
|Batch-post the quantity of components used per operation in a journal that processes multiple planned production orders.|[Batch Post Consumption](production-how-to-post-consumption.md)|
|Post the quantity of finished items and the time spent per operation in a journal that processes multiple released production orders.|[Batch Post Output and Run Times](production-how-to-post-output-quantity.md)|
|Reverse incorrect consumption, output, capacity, or subcontracting transactions, and correct finished production orders.|[Reverse and correct production order transactions](production-cancel-production-orders-that-have-consumption.md)|  
|Post the number of items produced in each finished operation that qualify as scrap material and not finished output.|[Post Scrap](production-how-to-post-scrap.md)|
|View the shop floor load as a result of planned and released production orders.|[View the Load in Work and Machine Centers](production-how-to-view-the-load-on-work-centers.md)|  
|Use the **Capacity Journal** page to post consumed capacities that aren't assigned to a production order, such as maintenance work.|[Post Capacities](production-how-to-post-capacities.md)|  
|Calculate and adjust the cost of finished production items and consumed components for financial reconciliation.|[About Finished Production Order Costs](finance-about-finished-production-order-costs.md)|  

## Related information

[Setting Up Manufacturing](production-configure-production-processes.md)  
[Power BI Manufacturing app](manufacturing-powerbi-app.md)  
[Planning](production-planning.md)  
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  


[!INCLUDE[footer-include](includes/footer-banner.md)]
