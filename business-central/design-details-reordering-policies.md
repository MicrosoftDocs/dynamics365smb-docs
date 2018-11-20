---
    title: Design Details - Reordering Policies | Microsoft Docs
    description: This topic gives an overview of policies for item replenishment.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 10/01/2018
    ms.author: sgroespe
    redirect_url: design-details-handling-reordering-policies

---
# Design Details: Reordering Policies
Reordering policies define how much to order when the item needs to be replenished. Four different reordering policies exist.  

## Fixed Reorder Qty.
The Fixed Reorder Qty. policy is related to inventory planning of typical C-items (low inventory cost, low risk of obsolescence, and/or many items). This policy is usually used in connection with a reorder point reflecting the anticipated demand during the lead time of the item.  

### Calculated per Time Bucket  
 If the planning system detects that the reorder point has been reached or crossed in a given time bucket (reorder cycle) – above or on the reorder point at the start of the period and below or on the reorder point at the end of the period – it will suggest to create a new supply order of the specified reorder quantity and forward schedule it from the first date after the end of the time bucket.  

 The bucketed reorder point concept reduces the number of supply suggestions. This reflects a manual process of frequently walking through the warehouse to check the actual contents in the various bins.  

### Creates only Necessary Supply  
 Before suggesting a new supply order to meet a reorder point, the planning system checks if supply has already been ordered to be received within the item’s lead time. If an existing supply order will solve the problem by bringing the projected inventory to or above the reorder point within the lead time, the system will not suggest a new supply order.  

 Supply orders that are created specifically to meet a reorder point is excluded from ordinary supply balancing, and will not in any way be changed afterwards. Consequently, if an item using reorder point is to be phased out (not replenished), it is advisable to review outstanding supply orders manually or change the reordering policy to Lot-for-Lot, whereby the system will reduce or cancel superfluous supply.  

### Combines with Order Modifiers  
 The order modifiers, Minimum Order Quantity, Maximum Order Quantity, and Order Multiple, should not play a big role when the fixed reorder quantity policy is used. However, the planning system still takes these modifiers into account and will decrease the quantity to the specified maximum order quantity (and create two or more supplies in order to reach the total order quantity), increase the order to the specified minimum order quantity, or round the order quantity up to meet a specified order multiple.  

### Combines with Calendars  
 Before suggesting a new supply order to meet a reorder point, the planning system checks if the order is scheduled for a non-working day, according to any calendars that are defined in the **Base Calendar Code** field in the **Company Information** and **Location Card** windows.  

 If the scheduled date is a non-working day, the planning system moves the order forward to the nearest working date. This may result in an order that meets a reorder point but does not meet some specific demand. For such unbalanced demand, the planning system creates an extra supply.  

### Should Not be Used with Forecast  
 Because the anticipated demand is already expressed in the reorder point level it is not necessary to include a forecast in the planning of an item using a reorder point. If it is relevant to base the plan on a forecast, use the lot-for-lot policy.  

### Must Not be Used with Reservations  
 If the user has reserved a quantity, for instance a quantity in inventory, for some distant demand, the planning foundation will be disturbed. Even if the projected inventory level is acceptable in relation to the reorder point, the quantities might not be available. The system may try to compensate for that by creating exception orders; however, it is recommended that the Reserve field is set to Never on items that are planned using a reorder point.

## Maximum Qty.
The Maximum Quantity policy is a way to maintain inventory using a reorder point.  

Everything regarding the Fixed Reorder Qty. policy also applies to this policy. The only difference is the quantity of the suggested supply. When using the maximum quantity policy, the reorder quantity will be defined dynamically based on the projected inventory level and will therefore usually differ from order to order.  

### Calculated per Time Bucket  
The reorder quantity is determined at the point of time (the end of a time bucket) when the planning system detects that the reorder point has been crossed. At this time, the system measures the gap from the current projected inventory level up to the specified maximum inventory. This constitutes the quantity that should be reordered. The system then checks if supply has already been ordered elsewhere to be received within the lead time and, if so, reduces the quantity of the new supply order by already ordered quantities.  

The system will ensure that the projected inventory at least reaches the reorder point level – in case the user has forgotten to specify a maximum inventory quantity.  

### Combines with Order Modifiers  
Depending on the setup, it may be best to combine the Maximum Quantity policy with order modifiers to ensure a minimum order quantity or round it to an integer number of purchase units of measure, or split it into more lots as defined by the maximum order quantity.  

### Combines with Calendars  
Before suggesting a new supply order to meet a reorder point, the planning system checks if the order is scheduled for a non-working day, according to any calendars that are  defined in the **Base Calendar Code** field in the **Company Information** and **Location Card** windows.  

If the scheduled date is a non-working day, the planning system moves the order forward to the nearest working date. This may result in an order that meets a reorder point but does not meet some specific demand. For such unbalanced demand, the planning system creates an extra supply.

## Order
In a make-to-order environment, an item is purchased or produced to exclusively cover a specific demand. Typically it relates to A-items, and the motivation for choosing the order reordering policy can be that the demand is infrequent, the lead-time is insignificant, or the required attributes vary.  

The program creates an order-to-order link, which acts as a preliminary connection between the supply, a supply order or inventory, and the demand that it is going to fulfill.  

Apart from using the Order policy, the order-to-order link can be applied during planning in the following ways:  

* When using the Make-to-Order manufacturing policy to create multi-level or project type production orders (producing needed components on the same production order).  
* When using the Sales Order Planning feature to create a production order from a sales order.  

Even if a manufacturing company considers itself as a make-to-order environment, it might be best to use a Lot-for-Lot reordering policy if the items are pure standard without variation in attributes. As a result, the system will use unplanned inventory and only accumulates sales orders with the same shipment date or within a defined time bucket.  

### Order-to-Order Links and Past Due Dates  
Unlike most supply-demand sets, linked orders with due dates before the planning starting date are fully planned for by the system. The business reason for this exception is that specific demand-supply sets must be synchronized through to execution. For more information about the frozen zone that applies to most demand-supply types, see [Design Details: Dealing with Orders Before the Planning Starting Date](design-details-dealing-with-orders-before-the-planning-starting-date.md).

## Lot-for-Lot
The lot-for-lot policy is the most flexible because the system only reacts on actual demand, plus it acts on anticipated demand from forecast and blanket orders and then settles the order quantity based on the demand. The lot-for-lot policy is aimed at A- and B-items where inventory can be accepted but should be avoided.  

In some ways, the lot-for-lot policy looks like the Order policy, but it has a generic approach to items; it can accept quantities in inventory, and it bundles demand and corresponding supply in time buckets defined by the user.  

The time bucket is defined in the **Time Bucket** field. The system works with a minimum time bucket of one day, since this is the smallest time unit of measure on demand and supply events in the system (although, in practice, the time unit of measure on production orders and component needs can be seconds).  

The time bucket also sets limits on when an existing supply order should be rescheduled to meet a given demand. If the supply lies within the time bucket, it will be rescheduled in or out to meet the demand. Otherwise, if it lies earlier, it will cause unnecessary build-up of inventory and should be canceled. If it lies later, a new supply order will be created instead.  

With this policy, it is also possible to define a safety stock in order to compensate for possible fluctuations in supply, or to meet sudden demand.  

Because the supply order quantity is based on the actual demand it can make sense to use the order modifiers: round the order quantity up to meet a specified order multiple (or purchase unit of measure), increase the order to a specified minimum order quantity, or decrease the quantity to the specified maximum quantity (and thus create two or more supplies to reach the total needed quantity).

## See Also  
[Design Details: Planning Parameters](design-details-planning-parameters.md)   
[Design Details: Handling Reordering Policies](design-details-handling-reordering-policies.md)   
[Design Details: Supply Planning](design-details-supply-planning.md)
