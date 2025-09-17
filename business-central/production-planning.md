---
title: Supply Planning
description: Prepare a detailed executable plan and the final-assembly production schedule for sales and production demand.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.form: 291, 292, 293, 295, 517, 9010, 9038
ms.date: 05/19/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Planning

The production operations required to transform inputs into finished goods must be planned daily or weekly depending on the volume and nature of the products. [!INCLUDE[prod_short](includes/prod_short.md)] offers features to supply for anticipated and actual demand from sale, assembly, and production as well as features for distribution planning using stockkeeping units and location transfers.

> [!NOTE]
> This article mainly describes planning for companies involved in manufacturing or assembly management where the resulting supply orders can be either production, assembly, transfer, or purchase orders. The main interface for this planning work is the **Planning Worksheet** page.
>
> [!INCLUDE[prod_short](includes/prod_short.md)] also supports supply planning for wholesale companies where the resulting supply orders can only be transfer and purchase orders. The main interface for this planning work is the **Requisition Worksheet** page, which is described indirectly in this article as most planning functionality applies to both worksheets.

Planning can be seen as the preparation of required supply orders in the purchasing, assembly, or manufacturing departments to fulfill sales or end-item demand. To learn more, go to [Purchasing](purchasing-manage-purchasing.md), [Assembly Management](assembly-assemble-items.md), and [Manufacturing](production-manage-manufacturing.md).

The following table describes a sequence of tasks, with links to the articles that describe them.  

|To...| Go to...|  
|------------|-------------|  
|Get a brief introduction to how the planning system can be used to detect and prioritize demand and suggest a balanced supply plan.|[About Planning Functionality](production-about-planning-functionality.md)|
|Understand how all aspects of the planning system work and how to adjust the algorithms to meet planning requirements in different environments.|[Design Details: Supply Planning](design-details-supply-planning.md)|
|Learn how the planning logic differentiates between demand at locations according to the SKU setup and demand without location codes.|[Planning With or Without Locations](production-planning-with-without-locations.md)|
|Forecast demand presented by expected sales and production components.|[Create a Demand Forecast](production-how-to-create-a-forecast.md)|  
|Create one-to-one or project production orders from a sales order to cover the exact demand of that sales order.|[Create Production Orders from Sales Orders](production-how-to-create-production-orders-from-sales-orders.md)|
|Use the **Order Planning** page to manually plan for sales or production demand one production BOM level at a time.|[Plan for New Demand Order by Order](production-how-to-plan-for-new-demand.md)|
|Use the **Planning Worksheet** page to run both the MPS and MRP options to automatically create either a high-level or detailed supply plan at all item levels.|[Run Full Planning, MPS, or MRP](production-how-to-run-mps-and-mrp.md)|
|Use the **Requisition Worksheet** page to automatically create a detailed supply plan to cover demand for items that are replenished by purchase or transfer only.|[Requisition worksheet](production-about-planning-functionality.md#requisition-worksheet)|  
|Initiate or update a production order as rough-scheduled operations in the master production schedule.|[Replan or Refresh Production Orders Directly](production-how-to-replan-refresh-production-orders.md)|
|Recalculate work or machine center calendars due to planning changes.|[To calculate a work center calendar](production-how-to-create-work-center-calendars.md#to-calculate-a-work-center-calendar)|
|Track the order demand (tracked quantity), forecast, blanket sales order, or planning parameter (untracked quantity) that caused the planning line.|[Track Relations Between Demand and Supply](production-how-track-demand-supply.md)|
|View an item's projected available inventory by different views and see which gross requirements, planned order receipts, and other events influence it over time.|[View the Availability of Items](inventory-how-availability-overview.md)|  
<!--|Perform selected planning activities, such as changing or adding planning worksheet lines, in a graphical view of the supply plan.|[Modify Planning Suggestions in a Graphical View](production-how-to-modify-planning-suggestions-in-a-graphical-view.md)|-->

## Related information

[Setting Up Manufacturing](production-configure-production-processes.md)  
[Manufacturing](production-manage-manufacturing.md)  
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Design Details: Supply Planning](design-details-supply-planning.md)  
[Setup Best Practices: Supply Planning](setup-best-practices-supply-planning.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  

[!INCLUDE[footer-include](includes/footer-banner.md)]
