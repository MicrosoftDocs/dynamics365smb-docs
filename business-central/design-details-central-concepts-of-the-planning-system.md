---
    title: Design Details - Central Concepts of the Planning System| Microsoft Docs
    description: The planning functions are contained in a batch job that first selects the relevant items and period to plan for and then suggests possible actions for the user to take based on the demand/supply situation and the items' planning parameters.
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
# Design Details: Central Concepts of the Planning System
The planning functions are contained in a batch job that first selects the relevant items and period to plan for. Then, according to each item’s low-level code (BOM position), the batch job calls a code unit, which calculates a supply plan by balancing supply-demand sets and suggesting possible actions for the user to take. The suggested actions appear as lines in the planning worksheet or the requisition worksheet.  

![Contents of the Planning Worksheet page](media/NAV_APP_supply_planning_1_planning_worksheet.png "Contents of the Planning Worksheet page")  

The planner of a company, such as a purchaser or a production planner is presumed to be the user of the planning system. The planning system assists the user by performing the extensive but rather straightforward calculations of a plan. The user can then concentrate on solving the more difficult problems, such as when things differ from normal.  

The planning system is driven by anticipated and actual customer demand, such as forecast and sales orders. Running the planning calculation will result in application suggesting specific actions for the user to take concerning possible supply from vendors, assembly or production departments, or transfers from other warehouses. These suggested actions could be to create new supply orders, such as purchase or production orders. If supply orders already exist, the suggested actions could be to increase or expedite the orders to meet the changes in demand.  

Another goal of the planning system is to ensure that the inventory does not grow unnecessarily. If demand decreases, the planning system will suggest that the user postpone, decrease in quantity, or cancel existing supply orders.  

MRP and MPS, Calculate Net Change Plan, and Calculate Regenerative Plan are all functions within one code unit that contains the planning logic. However, the supply plan calculation involves different sub systems.  

Note that the planning system includes no dedicated logic for capacity leveling or fine scheduling. Therefore, such scheduling work is performed as a separate discipline. The lack of direct integration between the two areas also means that substantial capacity or schedule changes will require that the planning is rerun.  

## Planning Parameters  
Planning parameters that the user sets for an item or a group of items control which actions the planning system will suggest in the various situations. The planning parameters are defined on each item card to control when, how much, and how to replenish.  

Planning parameters can also be defined for any combination of item, variant, and location by setting up a stockkeeping unit (SKU) for each needed combination, and then specifying individual parameters.  

For more information, see [Design Details: Handling Reordering Policies](design-details-handling-reordering-policies.md) and [Design Details: Planning Parameters](design-details-planning-parameters.md).  

## Planning Starting Date  
To avoid a supply plan that incorporates open orders in the past and suggests potentially impossible actions, the planning system treats all dates before the planning starting date as a frozen zone where the following special rule applies:  

All supply and demand before the starting date of the planning period will be considered a part of inventory or shipped.  

In other words, it assumes that the plan for the past is executed according to the given plan.  

For more information, see [Dealing with Orders Before the Planning Starting Date](design-details-balancing-demand-and-supply.md#dealing-with-orders-before-the-planning-starting-date).  

## Dynamic Order Tracking (Pegging)  
Dynamic Order Tracking, with its simultaneous creation of action messages in the planning worksheet, is not a part of the supply planning system in [!INCLUDE[d365fin](includes/d365fin_md.md)]. This feature links, in real-time, the demand and the quantities that could cover them, whenever a new demand or supply is created or changed.  

For example, if the user enters or changes a sales order, the dynamic order tracking system will instantly and search for an appropriate supply to cover the demand. This could be from inventory or from an expected supply order (such as a purchase order or a production order). When a supply source is found, the system creates a link between the demand and the supply, and displays it in view-only pages that are accessed from the involved document lines. When appropriate supply cannot be found, the dynamic order tracking system creates action messages in the planning worksheet with supply plan suggestions reflecting the dynamic balancing. Accordingly, the dynamic order tracking system offers a very basic planning system that can be of help both to the planner and other roles in the internal supply chain.  

Accordingly, Dynamic Order Tracking can be considered a tool that assists the user in assessing whether to accept supply order suggestions. From the supply side, a user can see which demand has created the supply, and from the demand side, which supply should cover the demand.  

![Example of dynamic order tracking](media/NAV_APP_supply_planning_1_dynamic_order_tracking.png "Example of dynamic order tracking")  

For more information, see [Design Details: Reservation, Order Tracking, and Action Messaging](design-details-reservation-order-tracking-and-action-messaging.md).  

In companies with a low item flow and less advanced product structures, it may be adequate to use the Dynamic Order Tracking as the main means of supply planning. However, in busier environments, the planning system should be used to ensure a properly balanced supply plan at all times.  

### Dynamic Order Tracking versus the Planning System  
At a quick glance, it may be difficult to differentiate between the planning system and Dynamic Order Tracking. Both features display output in the planning worksheet by suggesting actions that the planner should take. However, the way this output is produced differs.  

The planning system deals with the entire supply-demand pattern of an item through all levels of the BOM hierarchy along the time line, whereas Dynamic Order Tracking only addresses the situation of the order that activated it. When balancing demand and supply, the planning system creates links in a user-activated batch mode, whereas Dynamic Order Tracking creates the links automatically and on the fly, whenever the user enters a demand or a supply in application, such as a sales order or purchase order.  

Dynamic Order Tracking establishes links between demand and supply when data is entered, on a first-come/first-served basis. This may lead to some disorder in priorities. For example, a sales order entered first, with a due date next month, may be linked to the supply in inventory, while the next sales order due tomorrow may cause an action message to create a new purchase order to cover it, as illustrated below.  

![Example of order tracking in supply planning 1](media/NAV_APP_supply_planning_1_dynamic_order_tracking_graph.png "Example of order tracking in supply planning 1")  

In contrast, the planning system deals with all demand and supply for a particular item, in prioritized order according to due dates and order types, that is, on a first-needed/first-served basis. It deletes all order tracking links that were created dynamically and reestablishes them according to due date priority. When the planning system has run, it has solved all imbalances between demand and supply, as illustrated below for the same data.  

![Example of order tracking in supply planning 2](media/NAV_APP_supply_planning_1_planning_graph.png "Example of order tracking in supply planning 2")  

After the planning run, no action messages remain in the Action Message Entry table, because they have been replaced by the suggested actions in the planning worksheet  

For more information, see Order Tracking Links during Planning in [Balancing Supply with Demand](design-details-balancing-demand-and-supply.md#balancing-supply-with-demand).  

## Sequence and Priority in Planning  
When establishing a plan, the sequence of the calculations is important to get the job done within a reasonable timeframe. In addition, the prioritization of requirements and resources play an important role in obtaining the best results.  

The planning system in [!INCLUDE[d365fin](includes/d365fin_md.md)] is demand-driven. High-level items should be planned before low-level items, because the plan for high-level items might generate additional demand for the lower-level items. This means, for example, that retail locations should be planned before distribution centers are planned, because the plan for a retail location may include additional demand from the distribution center. On a detailed balancing level, this also means that a sales order should not trigger a new supply order if an already released supply order is can cover the sales order. Likewise, a supply carrying a specific lot number should not be allocated to cover a generic demand if another demand requires this specific lot.  

### Item Priority / Low-Level Code  
In a manufacturing environment, the demand for a finished, sellable item will result in derived demand for components that comprise the finished item. The bill-of-material structure controls the component structure and can cover several levels of semi-finished items. Planning an item at one level will cause derived demand for components at the next level, and so on. Eventually, this will result in derived demand for purchased items. Consequently, the planning system plans for items in order of their ranking in the total BOM hierarchy, starting with finished saleable items at the top level and continuing down through the product structure to the lower level items (according to the low-level code).  

![Planning for bills of material](media/NAV_APP_supply_planning_1_BOM_planning.png "Planning for bills of material")  

The figures illustrates in which sequence the system makes suggestions for supply orders at the top level and, assuming that the user will accept these suggestions, for any lower-level items as well.  

For more information about manufacturing considerations, see [Loading the Inventory Profiles](design-details-balancing-demand-and-supply.md#loading-the-inventory-profiles).  

### Locations / Transfer-Level Priority  
Companies that operate at more than one location may need to plan for each location individually. For example, an item’s safety stock level and its reordering policy may differ from one location to another. In this case, the planning parameters must be specified per item and also per location.  

This is supported with the use of SKUs, where individual planning parameters can be specified at the SKU level. An SKU can be regarded as an item at a specific location. If the user has not defined a SKU for that location, application will default to the parameters that have been set on the item card. The application calculates a plan for active locations only, which is where there is existing demand or supply for the given item.  

In principle, any item can be handled at any location, but application’s approach to the location concept is quite strict. For example, a sales order at one location cannot be fulfilled by some quantity on stock at another location. The quantity on stock must first be transferred to the location specified on the sales order.  

![Planning for stockkeeping units](media/NAV_APP_supply_planning_1_SKU_planning.png "Planning for stockkeeping units")  

For more information, see [Design Details: Transfers in Planning](design-details-transfers-in-planning.md).  

### Order Priority  
Within a given SKU, the requested or available date represents the highest priority; the demand of today should be dealt with before the demand of the coming days. But apart from this some kind of priority, the different demand and supply types are sorted according to business importance to decide which demand should be satisfied before satisfying another demand. On the supply side, the order priority will tell what source of supply should be applied before applying other sources of supply.  

For more information, see [Prioritizing Orders](design-details-balancing-demand-and-supply.md#prioritizing-orders).  

## Demand Forecasts and Blanket Orders  
Forecasts and blanket orders both represent anticipated demand. The blanket order, which covers a customer’s intended purchases over a specific period of time, acts to lessen the uncertainty of the overall forecast. The blanket order is a customer-specific forecast on top of the unspecified forecast as illustrated below.  

![Planning with forecasts](media/NAV_APP_supply_planning_1_forecast_and_blanket.png "Planning with forecasts")  

For more information, see the “Forecast Demand is Reduced by Sales Orders” section in [Loading the Inventory Profiles](design-details-balancing-demand-and-supply.md#loading-the-inventory-profiles).  

## Planning Assignment  
All items should be planned for, however, there is no reason to calculate a plan for an item unless there has been a change in the demand or supply pattern since the last time a plan was calculated.  

If the user has entered a new sales order or changed an existing one, there is reason to recalculate the plan. Other reasons include a change in forecast or the desired safety stock quantity. Changing a bill-of-material by adding or removing a component would most likely indicate a change, but for the component item only.  

The planning system monitors such events and assigns the appropriate items for planning.  

For multiple locations, the assignment takes place at the level of item per location combination. If, for example, a sales order has been created at only one location, application will assign the item at that specific location for planning.  

The reason for selecting items for planning is a matter of system performance. If no change in an item’s demand-supply pattern has occurred, the planning system will not suggest any actions to be taken. Without the planning assignment, the system would have to perform the calculations for all items in order to find out what to plan for, and that would drain system resources.  

The full list of reasons for assigning an item for planning is provided in [Design Details: Planning Assignment Table](design-details-planning-assignment-table.md).  

The planning options in [!INCLUDE[d365fin](includes/d365fin_md.md)] are:  

-   Calculate Regenerative Plan – Calculates all selected items, whether it is necessary or not.  
-   Calculate Net Change Plan – Calculates only those selected items that have had some change in their demand-supply pattern and, therefore, have been assigned for planning.  

Some users believe that net change planning should be performed on the fly, for example, when sales orders are entered. However, this could be confusing because dynamic order tracking and action messaging are also calculated on the fly. Besides, [!INCLUDE[d365fin](includes/d365fin_md.md)] offers real-time available-to-promise control, which provides pop–up warnings when entering sales orders if the demand cannot be fulfilled under the present supply plan.  

In addition to these considerations, the planning system only plans for those items that the user has prepared with appropriate planning parameters. Otherwise, it is assumed that the user will plan the items manually or semi-automatically by using the Order Planning feature.  

For more information about the automatic planning procedures, see [Design Details: Balancing Demand and Supply](design-details-balancing-demand-and-supply.md).  

## Item Dimensions  
Demand and supply can carry variant codes and location codes that must be respected when the planning system balances demand and supply.  

The system treats variant and location codes as item dimensions on a sales order line, inventory ledger entry, and so on. Accordingly, it calculates a plan for each combination of variant and location as if the combination were a separate item number.  

Instead of calculating any theoretical combination of variant and location, application calculates only those combinations that actually exist in the database.  

For more information on how the planning system deals with location codes on demand, see [Design Details: Demand at Blank Location](design-details-balancing-demand-and-supply.md).  

## Item Attributes  
Apart from general item dimensions, such as item number, variant code, location code, and type of order, each demand and supply event can carry additional specifications in the form of serial/lot numbers. The planning system plans these attributes in certain ways depending on their level of specification.  

An order-to-order link between demand and supply is another type of attribute that affects the planning system.  

### Specific Attributes  
Certain attributes on demand are specific and must be matched exactly by a corresponding supply. The following two specific attributes exist:  

-   Demanded serial/lot numbers that require specific application (The **SN Specific Tracking** or **Lot Specific Tracking** check box is selected on the **Item Tracking Code Card** page for the item tracking code that is used by the item.)  
-   Links to supply orders created manually or automatically for a specific demand (order-to-order links).  

For these attributes, the planning system applies the following rules:  

-   Demand with specific attributes can only be fulfilled by supply with matching attributes.  
-   Supply with specific attributes can also satisfy demand that does not ask specifically for those attributes.  

Accordingly, if a demand for specific attributes cannot be met by inventory or projected supplies, the planning system will suggest a new supply order to cover this specific demand with no regard of planning parameters.  

### Non-Specific Attributes  
Serial/lot-numbered items without specific item tracking setup may carry serial/lot numbers that do not need to be applied to the exact same serial/lot number, but can be applied to any serial/lot number. This gives the planning system more freedom to match, for example, a serialized demand with a serialized supply, typically in inventory.  

Demand-supply with serial/lot numbers, specific or non-specific, are considered high priority and are therefore exempt from the frozen zone, meaning that they will be part of planning even if they are due before the planning starting date.  

For more information, see the “Serial/Lot Numbers are Loaded by Specification Level” section in [Loading the Inventory Profiles](design-details-balancing-demand-and-supply.md#loading-the-inventory-profiles).  

For more information about how the planning system balances attributes, see [Serial/Lot Numbers and Order-to-Order Links are Exempt from the Frozen Zone](design-details-balancing-demand-and-supply.md#seriallot-numbers-and-order-to-order-links-are-exempt-from-the-frozen-zone).  

## Order-to-Order Links  
Order-to-order procurement means that an item is purchased, assembled, or produced to exclusively cover a specific demand. Typically it relates to A-items and the motivation for choosing this policy can be that the demand is infrequent, the lead-time is insignificant, or the required attributes vary.  

Another special case that uses order-to-order links is when an assembly order is linked to a sales order in an assemble-to-order scenario.  

Order-to-order links are applied between demand and supply in four ways:  

-   When the planned item uses the reordering policy Order.  
-   When using the manufacturing policy Make-to-Order to create multi-level or project-type production orders (producing needed components on the same production order).  
-   When creating production orders for sales orders with the Sales Order Planning feature.  
-   When assembling an item to a sales order. (Assembly Policy is set to Assemble-to-Order.  

In these instances, the planning system will only suggest to order the required quantity. Once created, the purchase, production, or assembly order will continue to match the corresponding demand. For example, if a sales order is changed in time or quantity, the planning system will suggest that the corresponding supply order is changed accordingly.  

When order-to-order links exist, the planning system does not involve linked supply or inventory in the balancing procedure. It is up to the user to evaluate if the linked supply should be used to cover other or new demand and, in that case, delete the supply order or reserve the linked supply manually.  

Reservations and order tracking links will break if a situation becomes impossible, such as moving the demand to a date earlier than the supply. However, the order-to-order link adapts to any changes in the respective demand or supply and thereby the link is never broken.  

## Reservations  
The planning system does not include any reserved quantities in the calculation. For example, if a sales order has been totally or partially reserved against the quantity in inventory, the reserved quantity in inventory cannot be used to cover other demand. The planning system does not include this demand-supply set in its calculation.  

However, the planning system will still include reserved quantities in the projected inventory profile because all quantities must be considered when determining both when the reorder point has been passed and how many to reorder to reach and not exceed the maximum inventory level. Consequently, unnecessary reservations will lead to increased risks that inventory levels run low because the planning logic does not detect reserved quantities.  

The following illustration shows how reservations can hinder the most feasible plan.  

![Planning with reservations](media/NAV_APP_supply_planning_1_reservations.png "Planning with reservations")  

For more information, see [Design Details: Reservation, Order Tracking, and Action Messaging](design-details-reservation-order-tracking-and-action-messaging.md).  

## Warnings  
The first column in the planning worksheet is for the warning fields. Any planning line created for an unusual situation will display a warning icon in this field, which the user can click for additional information.  

Supply on planning lines with warnings will normally not be modified according to planning parameters. Instead, the planning system only suggests a supply to cover the exact demand quantity. However, the system can be set up to respect certain planning parameters for planning lines with certain warnings. For more information, see the description of these options for the **Calculate Plan - Plan. Wksh.** batch job and the **Calculate Plan - Req. Wksh.** batch job respectively.  

The warning information is shown on the **Untracked Planning Elements** page, which is also used to show order tracking links to non-order network entities. The following warning types exist:  

-   Emergency  
-   Exception  
-   Attention  

![Warnings in the planning worksheet](media/NAV_APP_supply_planning_1_warnings.png "Warnings in the planning worksheet")  

### Emergency  
The emergency warning is displayed in two situations:  

-   When the inventory is negative on the planning starting date.  
-   When back-dated supply or demand events exist.  

If an item’s inventory is negative on the planning starting date, the planning system suggests an emergency supply for the negative quantity to arrive on the planning starting date. The warning text states the starting date and the quantity of the emergency order. For more information, see [Handling Projected Negative Inventory](design-details-handling-reordering-policies.md#handling-projected-negative-inventory).  

Any document lines with due dates before the planning starting date are consolidated into one emergency supply order for the item to arrive on the planning starting date.  

### Exception  
The exception warning is displayed if the projected available inventory drops below the safety stock quantity. The planning system will suggest a supply order to meet the demand on its due date. The warning text states the item’s safety stock quantity and the date on which it is violated.  

Violating the safety stock level is considered an exception because it should not occur if the reorder point has been set correctly. For more information, see [The Role of the Reorder Point](design-details-handling-reordering-policies.md#the-role-of-the-reorder-point).  

In general, exceptional order proposals ensure that the projected available inventory is never lower than the safety stock level. This means that the proposed quantity is just enough to cover the safety stock, without considering planning parameters. However, in some scenarios, order modifiers will be considered.  

> [!NOTE]  
>  The planning system may have consumed the safety stock intentionally and will then replenish it straight away. For more information, see [Safety Stock May Be Consumed](design-details-balancing-demand-and-supply.md#loading-the-inventory-profiles).

### Attention  
The attention warning is displayed in three situations:  

-   The planning starting date is earlier than the work date.  
-   The planning line suggests changing a released purchase or production order.  
-   The projected inventory exceeds the overflow level on the due date. For more information, see [Staying under the Overflow Level](design-details-handling-reordering-policies.md#staying-under-the-overflow-level).  

> [!NOTE]  
>  In planning lines with warnings, the **Accept Action Message** field is not selected, because the planner is expected to further investigate these lines before carrying out the plan.  

## Error Logs  
In the Calculate Plan request page, the user can select the **Stop and Show First Error** field to have the planning run stop when it encounters the first error. At the same time, a message is displayed with information about the error. If an error exists, only the successful planning lines that were made before the error was encountered will be presented in the planning worksheet.  

If the field is not selected, the Calculate Plan batch job will continue until it has completed. Errors will not interrupt the batch job. If one or more errors exist, application will display a message after completion saying how many items are affected by errors. The **Planning Error Log** page then opens to provide more details about the error and to provide links to the affected documents or setup cards.  

![Error messages in the planning worksheet](media/NAV_APP_supply_planning_1_error_log.png "Error messages in the planning worksheet")  

## Planning Flexibility  
It is not always practical to plan an existing supply order, such as when production has started or extra people are hired on a specific day to do the job. To indicate whether an existing order can be changed by the planning system, all supply order lines have a Planning Flexibility field with two options: Unlimited or None. If the field is set to None, the planning system will not try to change the supply order line.  

The field can be manually set by the user, however, in some cases it will be set automatically by the system. The fact that planning flexibility can be manually set by the user is important, because it makes it easy to adapt the usage of the feature to different workflows and business cases.  

For more information about how this field is used, see [Design Details: Transfers in Planning](design-details-transfers-in-planning.md).  

## Order Planning  
The basic supply planning tool represented by the **Order Planning** page is designed for manual decision making. It does not consider any planning parameters and is therefore not discussed further in this document. For more information on the Order Planning feature, refer to Help in [!INCLUDE[d365fin](includes/d365fin_md.md)].  

> [!NOTE]  
>  It is not advisable to use Order Planning if the company already uses the planning or requisition worksheets. Supply orders created through the **Order Planning** page may be changed or deleted during the automated planning runs. This is because the automated planning run uses planning parameters and these may not be considered by the user who made the manual plan in the Order Planning page.  

##  Finite Loading  
[!INCLUDE[d365fin](includes/d365fin_md.md)] is a standard ERP system, not a dispatching or shop floor control system. It plans for a feasible utilization of resources by providing a rough-cut schedule, but it does not automatically create and maintain detailed schedules based on priorities or optimization rules.  

The intended use of the Capacity-Constrained Resource feature is 1): to avoid overload of specific resources and 2): to ensure that no capacity is left unallocated if it could increase the turn-around time of a production order. The feature includes no facilities or options to prioritize or optimize operations as one would expect to find in a dispatching system. However, it can provide rough-cut capacity information useful to identify bottlenecks and to avoid overloading resources.  

When planning with capacity-constrained resources, the system ensures that no resource is loaded above its defined capacity (critical load). This is done by assigning each operation to the nearest available time slot. If the time slot is not big enough to complete the entire operation, then the operation will be split into two or more parts placed in the nearest available time slots.  

> [!NOTE]  
>  In case of operation splitting, the setup time is only assigned once because it is assumed that some manual adjustment is done to optimize the schedule.  

Dampener time can be added to resources to minimize operation splitting. This enables the system to schedule load on the last possible day by exceeding the critical load percent slightly if this can reduce the number of operations that are split.  

This completes the outline of central concepts relating to supply planning in [!INCLUDE[d365fin](includes/d365fin_md.md)]. The following sections investigate these concepts deeper and place them in the context of the core planning procedures, balancing demand and supply as well as the use of reordering policies.  

## See Also  
[Design Details: Transfers in Planning](design-details-transfers-in-planning.md)   
[Design Details: Planning Parameters](design-details-planning-parameters.md)   
[Design Details: Planning Assignment Table](design-details-planning-assignment-table.md)   
[Design Details: Handling Reordering Policies](design-details-handling-reordering-policies.md)   
[Design Details: Balancing Demand and Supply](design-details-balancing-demand-and-supply.md)
