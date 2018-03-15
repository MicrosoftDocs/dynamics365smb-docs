---
    title: Design Details - Monitoring the Projected Inventory Level and the Reorder Point | Microsoft Docs
    description: Learn how inventory planning distinguishes between projected inventory and projected available inventory levels.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords: design, supply, inventory, planning
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# Design Details: Monitoring the Projected Inventory Level and the Reorder Point
Inventory is a type of supply, but for inventory planning, the planning system distinguishes between two inventory levels:  

* Projected inventory  
* Projected available inventory  

## Projected Inventory  
Initially, projected inventory is the quantity of gross inventory, including supply and demand in the past even if not posted, when starting the planning process. In the future, this becomes a moving projected inventory level that is maintained by gross quantities from future supply and demand because those are introduced along the time line (whether reserved or in other ways allocated).  

The projected inventory is used by the planning system to monitor the reorder point and to determine the reorder quantity when using the Maximum Qty. reordering policy.  

## Projected Available Inventory  
The projected available inventory is the part of the projected inventory that at a given point in time is available to fulfill demand. The projected available inventory is used by the planning engine when monitoring the safety stock level.  

The projected available inventory is used by the planning system to monitor the safety stock level, since the safety stock must always be available to serve unexpected demand.  

## Time Buckets  
Having a tight control of the projected inventory is crucial to detect when the reorder point is reached or crossed and to calculate the right order quantity when using the Maximum Qty. reordering policy.  

As stated earlier, the projected inventory level is calculated at the start of the planning period. It is a gross level that does not consider reservations and similar allocations. To monitor this inventory level during the planning sequence, the system monitors the aggregated changes over a period of time, a time bucket. The system ensures that the time bucket is at least one day since it is the most precise unit of time for a demand or supply event.  

## Determining the Projected Inventory Level  
The following sequence describes how the projected inventory level is determined:  

* When a supply event, such as a purchase order has been totally planned, it will increase the projected inventory on its due date.  
* When a demand event has been fully satisfied, it will not decrease the projected inventory right away. Instead, it posts a decrease reminder, which is an internal record that holds the date and quantity of the contribution to the projected inventory.  
* When a subsequent supply event is planned and placed on the time line, the posted decrease reminders are investigated one by one up until the planned date of the supply while updating the projected inventory. During this process, the reorder point level of the internal increase reminder may be reached or crossed.  
* If a new supply order is introduced, the system checks if it is entered before the current supply. If it is, the new supply becomes current supply and the balancing procedure starts over.  

The following shows a graphical illustration of this principle:  

![](media/nav_app_supply_planning_2_projected_inventory.png "NAV_APP_supply_planning_2_projected_inventory")  

1. Supply **Sa** of 4 (fixed) closes Demand **Da** of -3.  
2. CloseDemand: Create a decrease reminder of -3 (not shown).  
3. Supply **Sa** is closed with a surplus of 1 (no more demand exists).  

     This increases the projected inventory level to +4, while the projected **available** inventory becomes -1.  

4. The next supply **Sb** of 2 (another order) has already been placed on the timeline.  
5. System checks if there is any decrease reminder preceding **Sb** (there is not, so no action is taken).  
6. System closes supply **Sb** (no more demand exists)—either A: by reducing it to 0 (cancel) or B: by leaving as is.  

     This increases the projected inventory level (A: +0 => +4 or B: +2 = +6).  

7. System makes a final check: Is there any decrease reminder? Yes, there is one on the date of **Da**.  
8. System adds the decrease reminder of -3 reminder to the projected inventory level, either A: +4 -3 = 1 or B: +6 -3 = +3.  
9. In case of A, the system creates a forward-scheduled order starting on date **Da**.  

     In case of B, the reorder point is reached and a new order is created.  

## See Also  
[Design Details: Reordering Policies](design-details-reordering-policies.md)   
[Design Details: Planning Parameters](design-details-planning-parameters.md)   
[Design Details: Handling Reordering Policies](design-details-handling-reordering-policies.md)   
[Design Details: Supply Planning](design-details-supply-planning.md)
