---
    title: Design Details - Loading the Inventory Profiles | Microsoft Docs
    description: To sort out the many sources of demand and supply, the planning system organizes them on two timelines called inventory profiles.
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
# Design Details: Loading the Inventory Profiles
To sort out the many sources of demand and supply, the planning system organizes them on two timelines called inventory profiles.  

 The normal types of demand and supply with due dates on or after the planning starting date are loaded into each inventory profile. When loaded, the different demand and supply types are sorted according to overall priorities, such as due date, low-level codes, location, and variant. In addition, order priorities are applied to the different types to ensure that the most important demand is fulfilled first. For more information, see [Design Details: Prioritizing Orders](design-details-prioritizing-orders.md).  

 As previously mentioned, demand could also be negative. This means that it should be treated as supply; however, unlike the normal types of supply, negative demand is considered fixed supply. The planning system can take it into account, but will not suggest any changes to it.  

 In general, the planning system considers all supply orders after the planning starting date as subject to change in order to fulfill demand. However, as soon as a quantity is posted from a supply order, it can no longer be changed by the planning system. Accordingly, the following different orders cannot be replanned:  

-   Released production orders where consumption or output has been posted.  

-   Assembly orders where consumption or output has been posted.  

-   Transfer orders where shipment has been posted.  

-   Purchase orders where receipt has been posted.  

 Apart from loading demand and supply types, certain types are loaded with attention to special rules and dependencies that are described in the following.  

## Item Dimensions are Separated  
 The supply plan must be calculated per combination of the item dimensions, such as variant and location. However, there is no reason to calculate any theoretical combination. Only those combinations that carry a demand and/or supply need to be calculated.  

 The planning system controls this by running through the inventory profile. When a new combination is found, the program creates an internal control record that holds the actual combination information. The program inserts the SKU as the control record, or outer loop. As a result, the proper planning parameters according to a combination of variant and location are set, and the program can proceed to the inner loop.  

> [!NOTE]  
>  The program does not require the user to enter a SKU record when entering demand and/or supply for a particular combination of variant and location. Therefore, if a SKU does not exist for a given combination, the program creates its own temporary SKU record based on the item card data. If Location Mandatory is set to Yes in the Inventory Setup window, then either a SKU must be created or Components at Location must be set to Yes. For more information, see [Design Details: Demand at Blank Location](design-details-demand-at-blank-location.md).  

## Serial/Lot Numbers are Loaded by Specification Level  
 Attributes in the form of serial/lot numbers are loaded into the inventory profiles along with the demand and supply that they are assigned to.  

 Demand and supply attributes are arranged by order priority as well as by their level of specification. Because serial/lot number matches reflect the level of specification, the more specific demand, such as a lot number selected specifically for a sale line, will seek a match before less specific demand, such as a sale from any lot number selected.  

> [!NOTE]  
>  There are no dedicated prioritization rules for serial/lot-numbered demand and supply, other than the level of specification defined by their combinations of serial and lot numbers and the item tracking setup of the involved items.  

 During balancing, the planning system regards supply that carries serial/lot numbers as inflexible and will not try to increase or reschedule such supply orders (unless they are used in an order-to-order relation). See Order-to-Order Links are Never Broken). This protects the supply from receiving several, possibly conflicting, action messages when a supply carries varying attributes—such as a collection of different serial numbers.  

 Another reason that serial/lot numbered supply is inflexible is that serial/lot numbers are generally assigned so late in the process that it would be confusing if changes are suggested.  

 The balancing of serial/lot numbers does not respect the [Frozen Zone](design-details-dealing-with-orders-before-the-planning-starting-date.md). If demand and supply is not synchronized, the planning system will suggest changes or suggest new orders, regardless of the planning starting date.  

## Order-to-Order Links are Never Broken  
 When planning an order-to-order item, the linked supply must not be used for any demand other than what it was originally intended for. The linked demand should not be covered by any other random supply, even if, in its present situation, it is available in time and quantity. For example, an assembly order that is linked to a sales order in an assemble-to-order scenario cannot be used to cover other demand.  

 Order-to-order demand and supply must balance precisely. The planning system will ensure the supply under all circumstances without regarding order sizing parameters, modifiers, and quantities in inventory (other than quantities relating to the linked orders). For the same reason, the system will suggest decreasing excess supplies if the linked demand is decreased.  

 This balancing also affects the timing. The limited horizon that is given by the time bucket is not regarded; the supply will be rescheduled if the timing of the demand has changed. However, dampener time will be respected and will prevent order-to-order supplies from being scheduled out, except for the internal supplies of a multi-level production order (project order).  

> [!NOTE]  
>  Serial/lot numbers can also be specified on order-to-order demand. In that case, the supply is not regarded inflexible by default, as is normally the case for serial/lot numbers. In this case, the system will increase/decrease according to changes in demand. Furthermore, if one demand carries varying serial/lot numbers, such as more than one lot number, one supply order will be suggested per lot.  

> [!NOTE]  
>  Forecasts should not lead to creating supply orders that are bound by an order-to-order link. If the forecast is used, it should only be used as a generator of dependent demand in a manufacturing environment.  

## Component Need is Loaded according to Production Order Changes  
 When handling production orders, the planning system must monitor the needed components before loading them into the demand profile. Component lines that result from an amended production order will replace those of the original order. This ensures that the planning system establishes that planning lines for component need are never duplicated.  

##  <a name="BKMK_SafetyStockMayBeConsumed"></a> Safety Stock May Be Consumed  
 The safety stock quantity is primarily a demand type and is therefore loaded into the inventory profile on the planning starting date.  

 Safety stock is an inventory quantity set aside to compensate for uncertainties in demand during the replenishment lead time. However, it may be consumed if it is necessary to take from it to fulfill a demand. In that case, the planning system will ensure that the safety stock is quickly replaced by suggesting a supply order to replenish the safety stock quantity on the date it is consumed. This planning line will display an Exception warning icon explaining to the planner that the safety stock has been partly or fully consumed by means of an exception order for the missing quantity.  

## Forecast Demand is Reduced by Sales Orders  
 The production forecast expresses anticipated future demand. While actual demand is entered, typically as sales orders for produced items, it consumes the forecast.  

 The forecast itself is not actually reduced by sales orders; it remains the same. However, the forecast quantities used in the planning calculation are reduced (by the sales order quantities) before the remaining quantity, if any, enters the demand inventory profile. When the planning system examines actual sales during a period, both open sales orders and item ledger entries from shipped sales are included, unless they are derived from a blanket order.  

 A user is required to define a valid forecast period. The date on the forecasted quantity defines the start of the period, and the date on the next forecast defines the end of the period.  

 The forecast for periods prior to the planning period is not used, regardless of whether it was consumed or not. The first forecast figure of interest is either the date on or the closest date prior to the planning starting date.  

 The forecast can be for independent demand, such as sales orders, or dependent demand, like production order components (module-forecast). An item can have both types of forecast. During planning, the consumption takes place separately, first for independent demand and then for dependent demand.  

## Blanket Order Demand is Reduced by Sales Orders  
 Forecasting is supplemented by the blanket sales order as a means of specifying future demand from a specific customer. As with the (unspecified) forecast, actual sales should consume the anticipated demand, and the remaining quantity should enter the demand inventory profile. Again, the consumption does not actually reduce the blanket order.  

 The planning calculation considers open sales orders linked to the specific blanket order line, but it does not consider any valid time period. Nor does it consider posted orders, since the posting procedure has already reduced the outstanding blanket order quantity.  

## See Also  
 [Design Details: Balancing Demand and Supply](design-details-balancing-demand-and-supply.md)   
 [Design Details: Central Concepts of the Planning System](design-details-central-concepts-of-the-planning-system.md)   
 [Design Details: Supply Planning](design-details-supply-planning.md)   
 [Design Details: Planning Parameters](design-details-planning-parameters.md)
