---
    title: Insert topic title| Microsoft Docs
    description: Insert description
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

    ---
# Perform Master Planning
Before a detailed executable plan \( [see MRP](../OperationsPlanning/perform-material-requirements-planning.md)\) is in place, a number of initial, high-level information must be established through master planning. Master planning considers all independent demand, including forecasts. Master planning also considers [resource availability](../OperationsPlanning/plan-for-resource-availability.md) and the final-assembly production schedule, that is expected production orders for demanded end items.  
  
 In FIX INCLUDE HERE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] -->, the Calculate MPS option \(Master Production Schedule\) is the system expression of the above master planning activities.  
  
 The following table describes a sequence of tasks, with links to the topics that describe them. These tasks are listed in the order in which they are generally performed.  
  
|**To**|**See**|  
|------------|-------------|  
|Learn how the planning system can be used to detect and prioritize demand and suggest a consolidated balanced supply plan for MPS or MRP.|[About Planning Functionality](../OperationsPlanning/about-planning-functionality.md)|  
|Create and manage expected demand presented by sales forecasts.|[How to: Create a Forecast](../OperationsPlanning/how-to-create-a-forecast.md)|  
|Run the planning worksheet with the MPS option to automatically create a high-level supply plan based on actual demand and the production forecast.|[How to: Run MPS and MRP](../OperationsPlanning/how-to-run-mps-and-mrp.md)|  
|Use the **Order Planning** window to manually plan for sales or production demand one production BOM level at a time.|[How to: Plan for New Demand](../OperationsPlanning/how-to-plan-for-new-demand.md)|  
|Create one-to-one production orders automatically from a sales order to cover the exact demand of that sales order line.|[How to: Create Production Orders from Sales Orders](../OperationsPlanning/how-to-create-production-orders-from-sales-orders.md)|  
|Create a project production order directly from a multiline sales order representing a production project.|[How to: Plan Project Orders](../OperationsPlanning/how-to-plan-project-orders.md)|  
|Create production orders manually either to build to stock or in response to known sales demand for produced items.|[How to: Create Production Order Headers](../OperationsPlanning/how-to-create-production-order-headers.md)|  
|Initiate or update a production order as rough-scheduled operations in the master production schedule.|[How to: Refresh Production Orders](../OperationsPlanning/how-to-refresh-production-orders.md)|  
  
## See Also  
 [Schedule Production Activities](../Production/schedule-production-activities.md)   
 [Execute Production](../Production/execute-production.md)   
 [Working with Product Name](../WorkingWithDynamics/working-with-$-p_1-product-name-$-.md)