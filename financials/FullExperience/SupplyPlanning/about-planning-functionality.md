---
title: "About Planning Functionality"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "planning, about"
  - "demand, about"
ms.assetid: f822be64-0c04-4383-b618-0a58e3e39115
caps.latest.revision: 10
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
# About Planning Functionality
The planning system takes all demand and supply data into account, nets the results, and creates suggestions for balancing the supply to meet the demand.  
  
 For detailed information, see [Design Details: Supply Planning](../ApplicationDesign/design-details-supply-planning.md).  
  
## Demand and Supply  
 Planning has two elements: demand and supply. These must be held in balance to ensure that the demand is met in a timely and cost\-efficient manner.  
  
-   Demand is the common term used for any kind of gross requirement such as a sales order, service order, component need from assembly or production orders, outbound transfer, blanket order or forecast. In addition to these, the program allows some other technical types of demand \- such as a negative production or purchase order, negative inventory, and purchase return.  
  
-   Supply is the common word used for any kind of replenishment such as inventory, a purchase order, assembly order, production order, or inbound transfer. Correspondingly, there can be a negative sales or service order, negative component need or sales return – all of which in some way also represent supply.  
  
 Another goal of the planning system is to ensure that the inventory does not grow unnecessarily. In the case of decreasing demand, the planning system will suggest that you postpone, decrease in quantity, or cancel existing replenishment orders.  
  
## Planning Calculation  
 The planning system is driven by anticipated and actual customer demand, as well as inventory reordering parameters. Running the planning calculation will result in the program suggesting specific actions \(Action Messages\) to take concerning possible replenishment from vendors, transfers between warehouses, or production. If replenishment orders already exist, the suggested actions could be to increase or expedite the orders to meet the changes in demand.  
  
 The basis of the planning routine is in the gross\-to\-net calculation. Net requirements drive planned order releases, which are scheduled based on the routing information \(manufactured items\) or the item card lead time \(purchased items\). Planned order release quantities are based on the planning calculation, and are affected by the parameters set on the individual item cards.  
  
## Planning Parameters  
 The planning parameters control when, how much, and how to replenish based on the various settings on the item card \(or stockkeeping unit \- SKU\), and the manufacturing setup.  
  
 The following planning parameters exist on the item or SKU card:  
  
-   Dampener Period  
  
-   Dampener Quantity  
  
-   Reordering Policy  
  
-   [Reorder Point](../Topic/\($%20T_27_34%20Reorder%20Point%20$\).md)  
  
-   Maximum Inventory  
  
-   Overflow Level  
  
-   Time Bucket  
  
-   Lot Accumulation Period  
  
-   Rescheduling Period  
  
-   Reorder Quantity  
  
-   [Safety Lead Time](../Topic/\($%20T_27_5415%20Safety%20Lead%20Time%20$\).md)  
  
-   Safety Stock Quantity  
  
-   Assembly Policy  
  
-   [Manufacturing Policy](../DesignAndEngineering/-$-t_27_5442-manufacturing-policy-$-.md)  
  
 The following order modifiers exist on the item or SKU card:  
  
-   Minimum Order Quantity  
  
-   Maximum Order Quantity  
  
-   Order Multiple  
  
 Global planning setup fields on the **Manufacturing Setup** window include:  
  
-   [Dynamic Low\-Level Code](../Topic/\($%20T_99000765_12%20Dynamic%20Low-Level%20Code%20$\).md)  
  
-   [Current Production Forecast](../Topic/\($%20T_99000765_35%20Current%20Production%20Forecast%20$\).md)  
  
-   [Use Forecast on Locations](../Topic/\($%20T_99000765_37%20Use%20Forecast%20on%20Locations%20$\).md)  
  
-   [Default Safety Lead Time](../Topic/\($%20T_99000765_42%20Default%20Safety%20Lead%20Time%20$\).md)  
  
-   Blank Overflow Level  
  
-   [Combined MPS\/MRP Calculation](../Topic/\($%20T_99000765_38%20Combined%20MPS-MRP%20Calculation%20$\).md)  
  
-   [Components at Location](../Topic/\($%20T_99000765_39%20Components%20at%20Location%20$\).md)  
  
-   Default Dampener Period  
  
-   Default Dampener Quantity  
  
 For more information, see [Design Details: Planning Parameters](../ApplicationDesign/design-details-planning-parameters.md)  
  
 Planning is affected by many additional factors, such as the planning horizon defined by the order and ending dates specified when you run MPS\/MRP from the **Planning Worksheet** or **Order Planning** windows.  
  
## See Also  
 Item Card   
 Stockkeeping Unit   
 Planning Worksheet   
 Order Planning   
 [How to: Run MPS and MRP](../OperationsPlanning/how-to-run-mps-and-mrp.md)   
 [Design Details: Supply Planning](../ApplicationDesign/design-details-supply-planning.md)   
 [About Forecasting Functionality](../Sales/about-forecasting-functionality.md)   
 [How to: Plan Project Orders](../OperationsPlanning/how-to-plan-project-orders.md)   
 [How to: Plan for New Demand](../OperationsPlanning/how-to-plan-for-new-demand.md)