---
    title: Perform Supply and Capacity Planning | Microsoft Docs
    description: Prepare a detailed executable plan and the final-assembly production schedule for sales and production demand.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 09/05/2017
    ms.author: sgroespe

---
# Planning
The production operations required to transform inputs into finished goods must be planned daily or weekly depending on the volume and nature of the products.

M[!INCLUDE[d365fin](includes/d365fin_md.md)] offers features to supply for anticipated and actual demand from sale and production as well as features for distribution planning using stockkeeping units and location transfers.

Although a production order can be used to execute a project sale of produced items, the planning of operations involved in a project may be better supported with the Project Management functionality.

Operations planning typically starts with resource planning, such as setting production capacities in the shop calendars and planning for potential subcontracting of production operations. Then you can perform master planning to manage sales demand and production demand for components.

Before you can plan and execute production orders, you must configure production capacities, such as creating shop calendars, routings, production BOMs, and machine centers. For more information, see [Setting Up Manufacturing](production-configure-production-processes.md).

The following table describes a sequence of tasks, with links to the topics that describe them.   

|**To**|**See**|  
|------------|-------------|  
|Learn how the planning system can be used to detect and prioritize demand and suggest a consolidated balanced supply plan for MPS or MRP.|[About Planning Functionality](production-about-planning-functionality.md)|  
|Create and manage expected demand presented by sales forecasts.|[How to: Create a Forecast](production-how-to-create-a-forecast.md)|  
|Run the planning worksheet with the MPS option to automatically create a high-level supply plan based on actual demand and the production forecast.|[How to: Run MPS and MRP](production-how-to-run-mps-and-mrp.md)|  
|Use the **Order Planning** window to manually plan for sales or production demand one production BOM level at a time.|[How to: Plan for New Demand](production-how-to-plan-for-new-demand.md)|  
|Create one-to-one production orders automatically from a sales order to cover the exact demand of that sales order line.|[How to: Create Production Orders from Sales Orders](production-how-to-create-production-orders-from-sales-orders.md)|  
|Create a project production order directly from a multiline sales order representing a production project.|[How to: Plan Project Orders](production-how-to-plan-project-orders.md)|  
|Initiate or update a production order as rough-scheduled operations in the master production schedule.|[How to: Refresh Production Orders](production-how-to-refresh-production-orders.md)|
|Recalculate work or machine center calendars due to planning changes.|[How to: Set Up Work Centers and Machine Centers](production-how-to-set-up-work-and-machine-centers.md)|  

## See Also  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Manufacturing](production-production.md)    
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
