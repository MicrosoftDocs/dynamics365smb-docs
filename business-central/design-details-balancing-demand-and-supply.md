---
title: Design Details - Balancing supply and demand
description: This article describes how to prioritized goals by balancing supply with demand.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.date: 12/15/2022
ms.custom: bap-template
---
# Design Details: Balancing supply and demand

To understand how the planning system works, it's important to understand its prioritized goals:  

* Any demand will be met by sufficient supply.  
* Any supply serves a purpose.  

Generally, these goals are achieved by balancing supply with demand.  

## Supply and demand

The term *supply* refers to any kind of positive or inbound quantity, such as:

* Inventory
* Purchases
* Assembly
* Production
* Inbound transfers
* Sales returns  

The term *demand* refers to any kind of gross demand, such as:

* An item for a sales order
* A component for a production order

[!INCLUDE [prod_short](includes/prod_short.md)] also lets you use more technical types of demand, such as negative inventory and purchase returns.

To sort the sources of supply and demand, the planning system organizes them on two timelines called inventory profiles. One profile is for demand events, and the other is for the corresponding supply events. Each supply event represents one entity on an order, such as:

* A sales order line
* An item ledger entry
* A production order line

When inventory profiles are loaded, the demand-supply sets are balanced to output a supply plan that fulfills the listed goals.

Inventory levels and planning parameters are other types of supply and demand. These types undergo integrated balancing to replenish stock items. Learn more at [Design Details: Handling Reordering Policies](design-details-handling-reordering-policies.md).

## The concept of balancing, in brief

Demand comes from your customers. Supply is what you create and remove to establish balance. The planning system starts with the demand and then tracks backwards to the supply.  

Inventory profiles contain information about the demands and supplies, quantities, and timing. These profiles make up the two sides of the balancing scale.  

The objective of planning is to balance the supply and demand of an item to ensure that supply will match demand as defined by the planning parameters and rules.  

:::image type="content" source="media/nav_app_supply_planning_2_balancing.png" alt-text="Overview of balancing supply and demand.":::

## Process orders before the planning start date

To avoid that a supply plan shows unreasonable suggestions, the planning system won't plan anything in the period before the planning starting date. The following rule applies to that period:

* All supply and demand before the starting date of the planning period are considered part of inventory or shipped.  

With a few exceptions, the planning system won't suggest any changes to supply orders in the period or create order tracking links for that period. The following are exceptions to this rule:  

* The inventory that's projected to be available, including the sum of supply and demand in the period, is below zero.  
* Backdated orders require serial or lot numbers.  
* The supply-demand set is linked by an order-to-order policy. 

If the initial available inventory is below zero, the planning system suggests an emergency supply order on the day before the planning period to cover the missing quantity. So, the projected and available inventory will always be at least zero when planning for the future period begins. The planning line for this supply order will display an Emergency warning icon and provide additional information.

### Serial and lot numbers and order-to-order links are exempt from the previous period  

If serial or lot numbers are required or an order-to-order link exists, the planning system disregards the rule about the previous period. It will include back-dated quantities from the starting date and might suggest corrective actions if supply and demand aren't synchronized. These demand-supply sets must match to ensure that a specific demand is fulfilled.

## Load inventory profiles

To sort the sources of supply and demand, the planning system organizes them on two timelines called inventory profiles.  

Supply and demand with due dates on or after the planning starting date are loaded into each inventory profile. When loaded, the supply and demand types are sorted according to overall priorities, such as:

* Due date
* Low-level codes
* Location
* Variant

Order priorities are applied to the different types to fulfill the most important demand first. Learn more at [Prioritizing Orders](design-details-balancing-demand-and-supply.md#prioritize-orders).  

Demand can also be negative. Treat negative demand as supply. However, unlike typical supply, negative demand is considered fixed supply. The planning system can take it into account, but will not suggest changes to it.  

In general, the planning system considers all supply orders after the planning starting date as subject to change in order to fulfill demand. However, after a quantity is posted from a supply order the planning system can't change it. The following orders can't be replanned:  

* Released production orders where consumption or output has been posted.  
* Assembly orders where consumption or output has been posted.  
* Transfer orders where shipment has been posted.  
* Purchase orders where receipt has been posted.  

Apart from loading the supply and demand types, certain types are loaded with attention to special rules and dependencies. The following sections in this article describe these rules and dependencies.  

### Item dimensions are separated  

The supply plan must be calculated for each combination of the item dimensions, such as variant and location. Only the combinations that carry a demand and/or supply need to be calculated.  

The planning system looks for combinations in the inventory profile. When it finds a new combination, it creates an internal control record that holds the information about the combination. The planning system then inserts the SKU as the control record, or outer loop. As a result, the planning parameters are set according to a combination of variant and location, and the system can proceed to the inner loop. 

> [!NOTE]  
> You don't have to enter a SKU record when you enter demand and/or supply for a particular combination of variant and location. Therefore, if a SKU doesn't exist for a given combination, [!INCLUDE [prod_short](includes/prod_short.md)] creates a temporary SKU record based on data from the item. If the **Location Mandatory** is toggle is turned on on the **Inventory Setup page**, you must either create a SKU or turn on the **Components at Location** toggle. Learn more at [Planning With or Without Locations](production-planning-with-without-locations.md).  

### Serial and lot numbers are loaded by specification level  

Serial and lot numbers are loaded into the inventory profiles along with the supply and demand they're assigned to.  

Supply and demand attributes are arranged by order priority and by their level of specification. Because serial and lot number matches reflect the level of specification, a more specific demand will match before a less specific demand. For example, a specific demand might be a lot number specified for a sale line. A less specific demand might be a sale from any lot number.

> [!NOTE]  
> The only dedicated prioritization rules for serial and lot-numbered supply and demand are the level of specification defined by their combinations and how item tracking is set up for the items.  

During balancing, the planning system regards supply that has serial and lot numbers as inflexible. The system won't increase or reschedule such supply orders. The one exception to this is if they're used in an order-to-order relation. Learn more at [Order-to-order links are never broken](#order-to-order-links-are-never-broken). This exception protects the supply from receiving several, possibly conflicting, action messages when it has varying attributes. For example, varying attributes might be when the supply has a collection of different serial numbers.  

Another reason why serial and lot-numbered supply are inflexible is because serial and lot numbers are often assigned late in the process. It could be confusing if changes are suggested at that point.  

Serial and lot number balancing doesn't respect the rule about not planning anything before the planning starting date. If supply and demand aren't synchronized, the planning system will suggest changes or new orders, regardless of the planning starting date.  

### Order-to-order links are never broken

When planning an order-to-order item, the linked supply must only be used for what it was originally intended. The linked demand shouldn't be covered by any other supply, even if the supply is available in time and quantity. For example, you can't use an assembly order that's linked to a sales order in an assemble-to-order scenario to cover another demand.  

Order-to-order supply and demand must balance precisely. The planning system will ensure the supply without regarding order sizing parameters, modifiers, and quantities in inventory (other than quantities relating to the linked orders). For the same reason, the system will suggest decreasing excess supplies if the linked demand is decreased.  

This balancing also affects the timing. The limited horizon that is given by the time bucket is not regarded; the supply will be rescheduled if the timing of the demand has changed. However, dampener time will be respected and will prevent order-to-order supplies from being scheduled out, except for the internal supplies of a multi-level production order (project order).  

> [!NOTE]  
> Serial and lot numbers can also be specified on order-to-order demand. In that case, the supply is not inflexible, which is normally is for serial and lot numbers. In this case, the system will increase or decrease according to changes in demand. If one demand has varying serial and lot numbers, such as more than one lot number, one supply order will be suggested for each lot.  

> [!NOTE]  
> Forecasts should not lead to creating supply orders that are bound by an order-to-order link. If the forecast is used, it should only be used as a generator of dependent demand in a manufacturing environment.

### Component need is loaded according to production order changes

When handling production orders, the planning system must monitor the needed components before loading them into the demand profile. Component lines that result from a changed production order will replace the lines of the original order. The change ensures that the planning system doesn't duplicate planning lines for a component need.  

### Consume safety stock

Safety stock quantity is a demand that's loaded into the inventory profile on the planning starting date.  

Safety stock is a quantity of inventory that's set aside to meet uncertainties in demand during replenishment. However, it can be consumed to fulfill a demand. In that case, the planning system will ensure that the safety stock is quickly replaced. The system suggests a supply order to replenish the safety stock quantity on the date it's consumed. The planning line will display an Exception warning icon explaining that the safety stock has been partly or fully consumed by an exception order for the missing quantity.  

### Forecast demand is reduced by sales orders

Demand forecasts express anticipated future demand. While actual demand is entered, typically as sales orders for produced items, it consumes the forecast.

The forecast itself is not reduced by sales orders. However, the forecast quantities that are used in the planning calculation are reduced by the sales order quantities before the remaining quantity enters the demand profile. For sales during a period, planning includes both open sales orders and item ledger entries from shipped sales. The exception to this rule is when they come from a blanket order.  

You must define a valid forecast period. The date on the forecasted quantity defines the start of the period, and the date on the next forecast defines the end of the period.  

The forecast for periods prior to the planning period isn't used, regardless of whether it was consumed. The first forecast figure of interest is either the planning starting date, or the closest date to it.  

The forecast can be for different types of demand:

* Independent demand, such as sales orders
* Dependent demand, such as production order components.

An item can have both types of forecast. During planning, consumption happens separately, first for independent demand and then for dependent demand.  

### Blanket order demand is reduced by sales orders

Forecasting is supplemented by blanket sales orders as a way to specify future demand from a specific customer. As with the (unspecified) forecast, actual sales should consume the anticipated demand, and the remaining quantity should enter the demand inventory profile. Consumption doesn't reduce the blanket order quantity.

The planning calculation includes open sales orders linked to the specific blanket order line, but it doesn't include any valid time period. Also, it doesn't include posted orders because the posting procedure has already reduced the outstanding blanket order quantity.

## Prioritize orders

Within a given SKU, the requested or available date represents the highest priority. Today's demand should be dealt with before the next week's demand. But, in addition to this overall priority, the planning system will make the following suggestions according to order priorities:

* Which type of demand you should fulfill first.
* What source of supply should be applied before applying other sources of supply.  

Loaded supply and demand contribute to a profile for projected inventory according to priorities.  

### Priorities on the demand side  

1. Already shipped: Item Ledger Entry  
2. Purchase return order  
3. Sales order  
4. Service order  
5. Production component needs  
6. Assembly order line  
7. Outbound transfer order  
8. Blanket order (that has not already been consumed by related sales orders)  
9. Forecast (that has not already been consumed by other sales orders)  

> [!NOTE]  
> Purchase returns aren't usually involved in supply planning; they should always be reserved from the lot that's going to be returned. If not reserved, purchase returns play a role in availability and are highly prioritized to avoid that the planning system suggests a supply order just to serve a purchase return.  

### Priorities on the supply side  

1. Already in inventory: Item Ledger Entry (Planning Flexibility = None)  
2. Sales return order (Planning Flexibility = None)  
3. Inbound transfer order  
4. Production order  
5. Assembly order  
6. Purchase order  

### Priority related to the state of supply and demand  

In addition to the priorities from the type of supply and demand, there are other things that affect planning flexibility. For example, warehouse activities, and the status of the following orders:

* Sales
* Purchase
* Transfer
* Assembly
* Production

The status of these orders has the following effects: 

1. Partly handled (Planning Flexibility = None)  
2. Already in process in the warehouse (Planning Flexibility = None)  
3. Released – all order types (Planning Flexibility = Unlimited)  
4. Firm Planned Production Order (Planning Flexibility = Unlimited)  
5. Planned/Open – all order types (Planning Flexibility = Unlimited)

## Balancing supply with demand

The planning system balances supply and demand by suggesting actions to revise supply orders that aren't balanced. This balance happens for each combination of variant and location.  

Imagine that each inventory profile contains two strings:

* A string of demand events, sorted by date and priority
* A corresponding string of supply events

Each event refers to its source type and identification. The rules for balancing the item are straightforward. Matching supply and demand can occur at any point in the process, as follows:  

1. No demand or supply exists for the item => the planning has finished (or should not start).  
2. Demand exists but there's no supply => supply should be suggested.  
3. Supply exists but there's no demand for it => supply should be canceled.  
4. Both supply and demand exist => questions should be asked and answered before [!INCLUDE [prod_short](includes/prod_short.md)] can ensure that the supply can meet the demand.

    If the timing of the supply isn't suitable, perhaps the supply can be rescheduled, as follows:  

    1. If the supply is placed earlier than the demand, perhaps the supply can be scheduled out so that inventory is as low as possible.  
    2. If the supply is placed later than the demand, perhaps the supply can be scheduled forward. Otherwise, the system will suggest new supply.  
    3. If the supply meets the demand on the date, the planning system can investigate whether the quantity of the supply can cover the demand.  

    When the timing is in place, the quantity to supply can be calculated as follows:  

    1. If the supply quantity is less than the demand, the supply quantity could be increased (or not, if you have a maximum quantity policy).  
    2. If the supply quantity is greater than the demand, the supply quantity can be decreased (or not, if you have a minimum quantity policy).  

    At this point, one of these two situations exist:  

    1. The current demand can be covered, in which case it can be closed and planning for the next demand can start.  
    2. The supply has reached its maximum, leaving some of the demand quantity uncovered. In this case, the planning system can close the current supply and proceed to the next one.  

 The procedure starts all over with the next demand and the current supply, or vice versa. The current supply might be able to cover this next demand as well, or the current demand has not yet been fully covered.  

### Rules for actions for supply events

For top-down calculations in which supply must fulfill demand, the demand is taken as a given. It's outside the control of the planning system. However, the planning system can manage the supply side and will make the following suggestions:

* Create new supply orders
* Reschedule existing orders or change their quantities
* Cancel supply orders that are no longer needed  

To exclude a supply order from the planning suggestions, you can state that it has no planning flexibility (Planning Flexibility = None). Then, excess supply from that order will be used to cover demand, but no action will be suggested. 

In general, all supply has a planning flexibility that's limited by the conditions of each of the suggested actions.  

* **Reschedule Out**: The date of an existing supply order can be scheduled out to meet the demand due date unless:

  * It represents inventory (always on day zero).  
  * It has an order-to-order linked to another demand.  
  * It's outside the window for rescheduling in the time bucket.
  * There's a closer supply that could be used.  
  * On the other hand, the user may decide not to reschedule because:
  * The supply order is tied to another demand on a previous date.  
  * The needed rescheduling is so minimal it's negligible.  

* **Reschedule In**: The date of an existing supply order can be scheduled in, except under the following conditions:

  * It's linked directly to some other demand.  
  * It's outside the window for rescheduling defined by the time bucket.

> [!NOTE]  
> When planning an item using a reorder point, you can reschedule the supply order. This often happens in forward-scheduled supply orders triggered by a reorder point.

* **Increase Quantity**: The quantity of an existing supply order can be increased to meet the demand unless the supply order is linked directly to a demand by an order-to-order link.  

> [!NOTE]  
> Although you can increase the supply order, the increase might be limited due to a defined maximum order quantity.  

* **Decrease Quantity**: An existing supply order with a surplus compared to an existing demand can be decreased to meet the demand.  

> [!NOTE]  
> Although the quantity can be decreased, there might be surplus compared to the demand due to a defined minimum order quantity or order multiple. 

* **Cancel**: As a special incident of the decrease quantity action, the supply order can be canceled if it's been decreased to zero. 
* **New**: If there aren't any supply orders, or an existing order can't be changed to meet the quantity needed on the due date for the demand, a new supply order is suggested.  

### Determine the supply quantity  

You define the planning parameters that control the suggested quantity of each supply order.  

When the planning system calculates the quantity of a new supply order or the quantity to change on an existing order, the suggested quantity might differ from the actual demand.  

If a maximum inventory or fixed order quantities are selected, the suggested quantity might be increased to meet the fixed quantity or the maximum inventory. If a reordering policy uses a reorder point, the quantity may be increased at least to meet the reorder point. 

The suggested quantity might be modified in this sequence:  

1. Down to the maximum order quantity.  
2. Up to the minimum order quantity.  
3. Up to meet the nearest order multiple.

### Order tracking links during planning  

For order tracking during planning, the planning system rearranges the order tracking links for the combinations of items, variants, and locations. The system rearranges the tracking links for the following reasons:

* To verify its suggestions for covering all demand, and ensure that all supply orders are needed.  
* The order tracking links must be rebalanced regularly.  

Over time, order tracking links become out of balance. The links become out of balance because the order tracking network isn't rearranged until a demand or supply event is closed.

Before balancing supply by demand, the planning system deletes all order tracking links. During the balancing process, when a demand or supply event is closed, it creates new order tracking links between the supply and demand.  

> [!NOTE]  
> Even if the item isn't set up for dynamic order tracking, the planning system will create balanced order tracking links.

## Close balanced supply and demand

Balancing supply has three possible outcomes:

* The required quantity and date of the demand events are met and planning for them can be closed. The supply event stays open and might be able to cover the next demand. Keeping the supply event open lets the balancing procedure start over with the current supply event and the next demand.  
* The supply order can't be modified to cover all of the demand. The demand event is still open with an uncovered quantity that might be covered by the next supply event. Therefore the current supply event is closed, and balancing can start over with the current demand and the next supply event.  
* All of the demand is covered and there isn't a next demand (or there wasn't any demand at all). Surplus supply might be decreased (or canceled) and then closed. Any other supply events should also be canceled.  

Finally, the planning system will create an order tracking link between the supply and the demand.  

### Create the planning line (Suggested Action)  

If a **New**, **Change Quantity**, **Reschedule**, **Reschedule and Change Quantity**, or **Cancel** action is suggested to revise the supply order, the planning system creates a planning line in the planning worksheet. For order tracking, the planning line is created not only when the supply event is closed, but also if the demand event is closed. This is true even though the supply event is still open and might be changed when the next demand event is processed. The planning line may be changed again when it's created.

To reduce the load on the database when handling production orders, the planning line can be maintained in three levels:

* Create only the planning line with the current due date and quantity but without the routing and components.  
* Include routing: the planned routing includes calculation of starting and ending dates and times. Include routing is demanding in terms of database accesses. To determine the ending and due dates, it might be necessary to calculate the routing even if the supply event hasn't been closed. For example, if you're doing forward scheduling.  
* Include BOM explosion: can happen just before the supply event is closed.

## Related information  

[Design Details: Central Concepts of the Planning System](design-details-central-concepts-of-the-planning-system.md)  
[Design Details: Handling Reordering Policies](design-details-handling-reordering-policies.md)  
[Design Details: Supply Planning](design-details-supply-planning.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
