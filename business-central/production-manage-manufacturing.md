---
title: Execute Production
description: When demand is planned for and the materials are issued according to production BOMs, the production operations can start.
author: brentholtorf
ms.topic: concept-article
ms.devlang: al
ms.search.form: 5406, 5407, 5728, 8903, 9011, 9012, 9013, 9041, 9044, 9047, 9323, 9324, 9325, 9326, 9327, 37040, 37041, 37042, 37043, 37044, 37045, 37046, 37047, 37048, 37049, 37055, 99000784, 99000785
ms.date: 09/10/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ms.custom: bap-template
---
# Manufacturing

> [!NOTE]
> The features this article describes are available only if you have the **Premium** experience. To learn more, go to [Change Which Features are Displayed](ui-experiences.md).

When demand is planned for and the materials are issued according to production BOMs, production operations can start in the sequence defined by the production order routing.  

An important part of production, from a system point of view, is to post production output to report progress and to update inventory with the finished items. You can post output manually, by filling in and posting journal lines after production operations. Or, it can post automatically with the use of backward flushing. In that case, material consumption is automatically posted along with output when the production order changes to finished.  

As an alternative to the batch journal for output posting for multiple production orders, you can use the **Production Journal** page to post consumption and/or output for one production order line.

There are a few things to set up before you can start production. For example, work centers, routings, and production BOMs. To learn more, go to [Setting Up Manufacturing](production-configure-production-processes.md).

The following table describes a sequence of tasks, with links to the articles that describe them.  

|**To**|**See**|  
|------------|-------------|  
|Understand how production orders work.|[About Production Orders](production-about-production-orders.md)|
|Create production orders manually.|[Create Production Orders](production-how-to-create-production-orders.md)|
| Analyze and monitor your manufacturing KPIs with the Power BI Projects apps. | [Power BI Manufacturing app](manufacturing-powerbi-app.md) |
|Outsource all or selected operations in a production order to a subcontractor.|[Subcontract Manufacturing](production-how-to-subcontract-manufacturing.md)|
|Record and post production output along with material and time consumption for a single released production order line.|[Post Consumption and Output for One Released Production Order Line](production-how-to-register-consumption-and-output.md)|  
|Batch-post the quantity of components used per operation in a journal that processes multiple planned production orders.|[Batch Post Consumption](production-how-to-post-consumption.md)|
|Post the quantity of finished items and the time spent per operation in a journal that processes multiple released production orders.|[Batch Post Output and Run Times](production-how-to-post-output-quantity.md)|
|Undo output, for example, because a data entry error occurred and the amount is incorrect.  |[Reverse Output Posting](production-how-to-reverse-output-posting.md)|  
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
