---
    title: Design Details - Balancing Supply with Demand | Microsoft Docs
    description: The core of the planning system involves balancing demand and supply by means of suggesting user actions to revise the supply orders in case of imbalance. This takes place per combination of variant and location.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# Design Details: Balancing Supply with Demand
The core of the planning system involves balancing demand and supply by means of suggesting user actions to revise the supply orders in case of imbalance. This takes place per combination of variant and location.  
  
Imagine that each inventory profile contains a string of demand events (sorted by date and priority) and a corresponding string of supply events. Each event refers back to its source type and identification. The rules for counterbalancing the item are straightforward. Four instances of matching demand and supply can occur at any point of time in the process:  
  
1. No demand or supply exists for the item => the planning has finished (or should not start).  
2. Demand exists but there is no supply => supply should be suggested.  
3. Supply exists but there is no demand for it => supply should be canceled.  
4. Both demand and supply exist => questions should be asked and answered before the system can ensure that demand will be met and supply is sufficient.  
  
     If the timing of the supply is not suitable, perhaps the supply can be rescheduled as follows:  
  
    1.  If the supply is placed earlier than the demand, perhaps the supply can be rescheduled out so that inventory is as low as possible.  
    2.  If the supply is placed later than the demand, perhaps the supply can be rescheduled in. Otherwise, the system will suggest new supply.  
    3.  If the supply meets the demand on the date, the planning system can proceed to investigate whether the quantity of the supply can cover the demand.  
  
     Once the timing is in place, the adequate quantity to be supplied can be calculated as follows:  
  
    1.  If the supply quantity is less than the demand, it is possible that the supply quantity could be increased (or not, if limited by a maximum quantity policy).  
    2.  If the supply quantity is greater than the demand, it is possible that the supply quantity can be decreased (or not, if limited by a minimum quantity policy).  
  
     At this point, either of these two situations exists:  
  
    1.  The current demand can be covered, in which case it can be closed and planning for the next demand can start.  
    2.  The supply has reached its maximum, leaving some of the demand quantity uncovered. In this case, the planning system can close the current supply and proceed to the next one.  
  
 The procedure starts all over with the next demand and the current supply or vice versa. The current supply might be able to cover this next demand as well, or the current demand has not yet been fully covered.  
  
## Rules Concerning Actions for Supply Events  
When the planning system performs a top-down calculation in which supply must fulfill demand, the demand is taken as a given, that is, it lies outside the control of the planning system. However, the supply side can be managed. Therefore, the planning system will suggest creating new supply orders, rescheduling existing ones, and/or changing the order quantity. If an existing supply order becoming superfluous, the planning system will suggest that the user cancels it.  
  
If the user wants to exclude an existing supply order from the planning suggestions, he can state that it has no planning flexibility (Planning Flexibility = None). Then, excess supply from that order will be used to cover demand, but no action will be suggested.  
  
In general, all supply has a planning flexibility that is limited by the conditions of each of the suggested actions.  
  
-   **Reschedule Out**: The date of an existing supply order can be scheduled out to meet the demand due date unless:  
  
    -   It represents inventory (always on day zero).  
    -   It has an order-to-order linked to another demand.  
    -   It lies outside the reschedule window defined by the time bucket.  
    -   There is a closer supply that could be used.  
    -   On the other hand, the user may decide not to reschedule because:  
    -   The supply order has already been tied to another demand on a previous date.  
    -   The needed rescheduling is so minimal that the user finds it negligible.  
  
-   **Reschedule In**: The date of an existing supply order can be scheduled in, except in the following conditions:  
  
    -   It is linked directly to some other demand.  
    -   It lies outside the reschedule window defined by the time bucket.  
  
> [!NOTE]  
>  When planning an item using a reorder point, the supply order can always be scheduled in if necessary. This is common in forward-scheduled supply orders triggered by a reorder point.  
  
-   **Increase Quantity**: The quantity of an existing supply order can be increased to meet the demand unless the supply order is linked directly to a demand by an order-to-order link.  
  
> [!NOTE]  
>  Even though it is possible to increase the supply order, it may be limited due to a defined maximum order quantity.  
  
-   **Decrease Quantity**: An existing supply order with a surplus compared to an existing demand can be decreased to meet the demand.  
  
> [!NOTE]  
>  Even though the quantity could be decreased, there may still be some surplus compared to the demand due to a defined minimum order quantity or order multiple.  
  
-   **Cancel**: As a special incident of the decrease quantity action, the supply order could be canceled if it has been decreased to zero.  
-   **New**: If no supply order already exists, or an existing one cannot be changed to meet the necessary quantity on the demanded due date, a new supply order is suggested.  
  
## Determining the Supply Quantity  
Planning parameters defined by the user control the suggested quantity of each supply order.  
  
When the planning system calculates the quantity of a new supply order or the quantity change on an existing one, the suggested quantity may be different from what is actually demanded.  
  
If a maximum inventory or fixed order quantity are selected, the suggested quantity may be increased to meet that fixed quantity or the maximum inventory. If a reordering policy uses a reorder point, the quantity may be increased at least to meet the reorder point.  
  
 The suggested quantity may be modified in this sequence:  
  
1. Down to the maximum order quantity (if any).  
2. Up to the minimum order quantity.  
3. Up to meet the nearest order multiple. (In case of erroneous settings, this may violate the maximum order quantity.)  
  
## Order Tracking Links during Planning  
Concerning order tracking during planning, it is important to mention that the planning system rearranges the dynamically created order tracking links for the item/variant/location combinations.  
  
There are two reasons for this:  
  
-   The planning system must be able to justify its suggestions; that all demand has been covered, and that no supply orders are superfluous.  
-   Dynamically created order tracking links need to be rebalanced regularly.  
  
Over time, dynamic order tracking links become out of balance since the entire order tracking network is not rearranged until a demand or supply event is actually closed.  
  
Before balancing supply by demand, the program deletes all existing order tracking links. Then during the balancing procedure, when a demand or supply event is closed, it establishes new order tracking links between the demand and supply.  
  
> [!NOTE]  
>  Even if the item is not set up for dynamic order tracking, the planned system will create balanced order tracking links as explained above.  
  
## See Also  
[Design Details: Balancing Demand and Supply](design-details-balancing-demand-and-supply.md)   
[Design Details: Central Concepts of the Planning System](design-details-central-concepts-of-the-planning-system.md)   
[Design Details: Supply Planning](design-details-supply-planning.md)