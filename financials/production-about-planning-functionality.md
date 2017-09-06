---
    title: About Planning Functionality | Microsoft Docs
    description: The planning system takes all demand and supply data into account, nets the results, and creates suggestions for balancing the supply to meet the demand.
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
# About Planning Functionality
The planning system takes all demand and supply data into account, nets the results, and creates suggestions for balancing the supply to meet the demand.  

For detailed information, see [Design Details: Supply Planning](design-details-supply-planning.md).  

> (!NOTE)
> For all the fields that are mentioned in this topic, read the tooltip to understand their function. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## Demand and Supply  
Planning has two elements: demand and supply. These must be held in balance to ensure that the demand is met in a timely and cost-efficient manner.  

- Demand is the common term used for any kind of gross requirement such as a sales order, service order, component need from assembly or production orders, outbound transfer, blanket order or forecast. In addition to these, the program allows some other technical types of demand - such as a negative production or purchase order, negative inventory, and purchase return.  
- Supply is the common word used for any kind of replenishment such as inventory, a purchase order, assembly order, production order, or inbound transfer. Correspondingly, there can be a negative sales or service order, negative component need or sales return – all of which in some way also represent supply.  

Another goal of the planning system is to ensure that the inventory does not grow unnecessarily. In the case of decreasing demand, the planning system will suggest that you postpone, decrease in quantity, or cancel existing replenishment orders.  

## Planning Calculation  
The planning system is driven by anticipated and actual customer demand, as well as inventory reordering parameters. Running the planning calculation will result in the program suggesting specific actions (Action Messages) to take concerning possible replenishment from vendors, transfers between warehouses, or production. If replenishment orders already exist, the suggested actions could be to increase or expedite the orders to meet the changes in demand.  

The basis of the planning routine is in the gross-to-net calculation. Net requirements drive planned order releases, which are scheduled based on the routing information (manufactured items) or the item card lead time (purchased items). Planned order release quantities are based on the planning calculation, and are affected by the parameters set on the individual item cards.  

# Planning with Manual Transfer Orders
As you can see from the **Replenishment System** field on a SKU card, the planning system can be set up to create transfer orders to balance supply and demand across locations.  

In addition to such automatic transfer orders, you may sometimes need to perform a general move of inventory quantities to another location, irrespective of existing demand. For this purpose you would manually create a transfer order for the quantity to move. To ensure that the planning system does not try to manipulate this manual transfer order, you must set the **Planning Flexibility** on the transfer line(s) to None.  

Contrarily, if you do want the planning system to adjust the transfer order quantities and [dates](../($%20T_5741_39%20Receipt%20Date%20$).md) to existing demand, you must set the Planning Flexibility field to the default value, Unlimited.

## Planning Parameters  
The planning parameters control when, how much, and how to replenish based on the various settings on the item card (or stockkeeping unit - SKU), and the manufacturing setup.  

The following planning parameters exist on the item or SKU card:  

-   Dampener Period  
-   Dampener Quantity  
-   Reordering Policy  
-   Reorder Point
-   Maximum Inventory  
-   Overflow Level  
-   Time Bucket  
-   Lot Accumulation Period  
-   Rescheduling Period  
-   Reorder Quantity  
-   Safety Lead Time  
-   Safety Stock Quantity  
-   Assembly Policy  
-   Manufacturing Policy  

The following order modifiers exist on the item or SKU card:  

-   Minimum Order Quantity  
-   Maximum Order Quantity  
-   Order Multiple  

Global planning setup fields on the **Manufacturing Setup** window include:  

-   Dynamic Low-Level Code]  
-   Current Production Forecast  
-   Use Forecast on Locations  
-   Default Safety Lead Time  
-   Blank Overflow Level  
-   Combined MPS/MRP Calculation   
-   Components at Location  
-   Default Dampener Period  
-   Default Dampener Quantity  

For more information, see [Design Details: Planning Parameters](design-details-planning-parameters.md)  

Planning is affected by many additional factors, such as the planning horizon defined by the order and ending dates specified when you run MPS/MRP from the **Planning Worksheet** or **Order Planning** windows.  

## See Also  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Manufacturing](production-manage-manufacturing.md)    
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Design Details: Supply Planning](design-details-supply-planning.md)   
[Setup Best Practices: Supply Planning](setup-best-practices-supply-planning.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
