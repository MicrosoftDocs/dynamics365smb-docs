---
    title: Design Details - Planning Assignment Table | Microsoft Docs
    description: This topic provides insight into what happens when you change how you plan for an item.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Design Details: Planning Assignment Table
All items should be planned for, however, there is no reason to calculate a plan for an item unless there has been a change in the demand or supply pattern since the last time a plan was calculated.  

If the user has entered a new sales order or changed an existing one, there is reason to recalculate the plan. Other reasons include a change in forecast or the desired safety stock quantity. Changing a bill of material by adding or removing a component would most likely indicate a change, but for the component item only.  

For multiple locations, the assignment takes place at the level of item per location combination. If, for example, a sales order has been created at only one location, application will assign the item at that specific location for planning.  

The reason for selecting items for planning is a matter of system performance. If no change in an item’s demand-supply pattern has occurred, the planning system will not suggest any actions to be taken. Without the planning assignment, the system would have to perform the calculations for all items in order to find out what to plan for, and that would drain system resources.  

The **Planning Assignment** table monitors demand and supply events and assigns the appropriate items for planning. The following events are monitored:  

* A new sales order, forecast, component, purchase order, production order, assembly order, or transfer order.  
* Change of item, quantity, location, variant, or date on a sales order, forecast, component, purchase order, production order, assembly order, or transfer order.  
* Cancellation of a sales order, forecast, component, purchase order, production order, assembly order, or transfer order.  
* Consumption of items other than planned.  
* Output of items other than planned.  
* Unplanned changes in inventory.  

For these direct supply-demand displacements, the order tracking and action messaging system maintains the Planning Assignment table and states a planning reason as an action message.  

The following changes in master data can also cause a planning imbalance:  

* Change of status to Certified in the production BOM header (for all items using that header).  
* Deleted line (child item).  
* Change of status to Certified in the routing header (for all items using that routing).  
* Changes in the following item card fields.  
* Safety Stock Quantity or Safety Lead Time.  
* Lead Time Calculation.  
* Reorder Point.  
* Production BOM No. (and all children of old BOM reference).  
* Routing No.  
* Reordering Policy.  

In these cases, a new function, Planning Assignment Management, maintains the table and states the planning reason as Net Change.  

The following changes do not cause a planning assignment:  

* Calendars  
* Other planning parameters on the item card  

When calculating an MPS or an MRP, the following restrictions apply:  

* MPS: The planning system checks that the item carries a demand forecast or a sales order. If not, the item is not included in the plan.  
* MRP: If the planning system detects that the item is being replenished by an MPS planning line or MPS supply order, the item will be left out of the planning. However, any demand from relevant components is included.  

## See Also  
[Design Details: Balancing Demand and Supply](design-details-balancing-demand-and-supply.md)   
[Design Details: Handling Reordering Policies](design-details-handling-reordering-policies.md)   
[Design Details: Transfers in Planning](design-details-transfers-in-planning.md)   
[Design Details: Planning Parameters](design-details-planning-parameters.md)  
