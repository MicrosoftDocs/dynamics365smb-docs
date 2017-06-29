---
title: "Perform Material Requirements Planning"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "requirements planning, about"
  - "planning, material requirements"
  - "materials, planning"
  - "production, planning"
  - "materials, requirements planning"
ms.assetid: 62e3c68a-ad38-4142-8308-1ac050fa3df7
caps.latest.revision: 9
ms.author: "sgroespe"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-nz"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# Perform Material Requirements Planning
To establish executable supply orders to meet all dependent and independent demand, you must plan for material requirements on all product levels. The material requirements plan, created with the Calculate MRP option, considers production BOM data, inventory levels, and the [master production schedule](../OperationsPlanning/perform-master-planning.md).  
  
 The MRP calculation makes recommendations to release supply orders for items, either by purchase, transfer, or production. Further, because it is time\-phased, it makes recommendations to reschedule open orders when due dates and need dates are out of phase.  
  
 Material requirements planning can be performed in two different tools depending on the complexity of the production BOM and the volume of orders. The **Order Planning** window is used to plan for one BOM level at a time with manual decision\-making, whereas the planning worksheet is used for automatic supply order calculations based on planning parameters. For purchase planning of purchase and transfer orders only, the requisition worksheets can be used as a light\-weight MRP worksheet.  
  
 The planning worksheets offers supporting planning information, such as [tracking to non\-order entities](../Topic/\($%20T_99000855%20Untracked%20Planning%20Element%20$\).md) and [warnings](../Topic/\($%20N_99000852_118%20Warning%20$\).md) to help the planner obtain an optimal supply plan.  
  
 The following table describes a sequence of tasks, with links to the topics that describe them. These tasks are listed in the order in which they are generally performed.  
  
|**To**|**See**|  
|------------|-------------|  
|Run the planning worksheet with the MRP option to automatically create a detailed supply plan \(purchase, production, or transfer\) based on the master production schedule and material requirements on all BOM levels.|[How to: Run MPS and MRP](../OperationsPlanning/how-to-run-mps-and-mrp.md)|  
|Use the **Order Planning** window to manually plan for sales or production demand one production BOM level at a time.|[How to: Plan for New Demand](../OperationsPlanning/how-to-plan-for-new-demand.md)|  
|Run the requisition worksheet to automatically create a detailed supply plan to cover demand for items that are replenished by purchase or transfer only.|Req. Worksheet|  
|Refresh the master data requirements of a production order shown in a planning tool: Order Planning or Planning Worksheet.|Refresh Planning Demand|  
|Learn how the planning logic differentiates between demand at locations according to the SKU setup and demand without location codes.|[Planning with\-without Locations](../OperationsPlanning/planning-with-without-locations.md)|  
|Enable a non\-demanded move between locations without involving the planning system.|[Planning with Manual Transfer Orders](../OperationsPlanning/planning-with-manual-transfer-orders.md)|  
|Exclude an existing supply order from the automatic planning run.|Planning Flexibility|  
|View clear status icons and read warnings about planning lines created for exceptional events, such as violation of safety stock or crossing of a reorder point.|Warning|  
|Find out which non\-order demand types, such as planning parameters or blanket orders, gave rise to the planning line.|Untracked Planning Element|  
|View an item's projected available inventory by different views and see which gross requirements, planned order receipts, and other events influence it over time.|[How to: View Item Availability](../OperationsPlanning/how-to-view-item-availability.md)|  
|Reserve items from inventory or inbound orders to use for sales order lines when they are due for shipping.|[How to: Reserve Items for Production Components](../OperationsPlanning/how-to-reserve-items-for-production-components.md)|  
|Reserve items with serial\/lot numbers by making a specific or non\-specific reservation.|[How to: Reserve Item\-Tracked Items](../DesignAndEngineering/how-to-reserve-item-tracked-items.md)|  
|Track the order demand \(tracked quantity\), forecast, blanket sales order, or planning parameter \(untracked quantity\) that has given rise to the planning line in question.|Order Tracking|  
  
## See Also  
 [Schedule Production Activities](../Production/schedule-production-activities.md)   
 [Execute Production](../Production/execute-production.md)   
 [Design and Engineering](../DesignAndEngineering/design-and-engineering.md)   
 [Working with Product Name](../WorkingWithDynamics/working-with-$-p_1-product-name-$-.md)