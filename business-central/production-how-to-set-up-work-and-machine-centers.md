---
    title: How to Set Up Work Centers and Machine Centers | Microsoft Docs
    description: A **Work Center** card organizes the fixed values and requirements of the production resource, and thus governs the output of production performed in that work center.
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
# Set Up Work Centers and Machine Centers
The application distinguishes between three types of capacities. These are arranged hierarchically. Each level contains the subordinate levels.  

The top level is the work center group. Work centers are assigned to the work center groups. Every work center can only belong to one work center group.

You can assign various machine centers to every work center. A machine center may only belong to one work center.  

The planned capacity of a work center consists of the availability of the corresponding machine centers and the additional planned availability of the work center. The planned availability of the work center group is, therefore, the sum of all corresponding availabilities of the machine centers and work centers.  

The availability is stored in calendar entries. Before you set up work or machine centers, you must set up shop calendars. For more information, see [Create Shop Calendars](production-how-to-create-work-center-calendars.md).  

## To set up a work center
The following primarily describes how to set up a work center. The steps to set up a machine center calendar are similar except for the **Routing Setup** FastTab.  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Work Centers**, and then choose the related link.  
2.  Choose the **New** action.  
3. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4.  In the **Work Center Group** field, select the higher-level resource grouping that the work center is organized under, if relevant. Choose the **New** action in the drop-down list.  
5.  Select the **Blocked** field if you want to prevent the work center from being used in any processing. This means that output cannot be posted for an item that is produced at the work center. For more information, see [Post Production Output](production-how-to-post-output-quantity.md).
6.  In the **Direct Unit Cost** field, enter the cost of producing one unit of measure at this work center, excluding any other cost elements. This cost is often referred to as the *direct labor rate*.  
7.  In the **Indirect Cost %** field, enter the general operation costs of using the work center as a percentage of the direct unit cost. This percentage amount is added to the direct cost in the calculation of the unit cost.  
8.  In the **Overhead Rate** field, enter any non-operational costs, for example maintenance expenses, of the work center as an absolute amount.  

    The **Unit Cost** field contains the calculated unit cost of producing one unit of measure at this work center, including all cost elements, as follows:  

    Unit Cost = Direct Unit Cost + (Direct Unit Cost x Indirect Cost %) + Overhead Rate.  

9.  In the **Unit Cost Calculation** field, define whether the above calculation should be based on the amount of time used:  **Time**, or on the number of produced units:  **Units**.  
10.  Select the **Specific Unit Cost** field if you want to define the work center’s unit cost on the routing line where it is being used. This may be relevant for operations with dramatically different capacity costs than what would normally be processed at that work center.  
11.  In the **Flushing Method** field, select whether output posting at this work center should be calculated and posted manually or automatically, using either of the following methods.

|Option|Description|
|------|-----------|
|**Manual**|Concumption is posted manually in the output journal or production journal.|
|**Forward**|Consumption is calculated and posted automatically when the production order is released.|
|**Backward**|Consumption is calculated and posted automatically when the production order is finished.|

> [!NOTE]
> If necessary, the flushing method selected here and on the **Item** card, can be overridden for individual operations by changing the setting on routing lines

12.  In the **Unit of Measure Code** field, enter the time unit in which this work center’s cost calculation and capacity planning are made.
    In order to be able to constantly monitor consumption, you must first set up a method of measure. The units you enter are basic units. For example, the processing time is measured in hours and minutes.

> [!NOTE]  
> If you select to use Days then remember that 1 day = 24 hours - and not 8 (working hours).

13.  In the **Capacity** field, define whether the work center has more than one machine or person working at the same time. If your [!INCLUDE[d365fin](includes/d365fin_md.md)] installation does not include the Machine Center functionality, then the value in this field must be **1**.  
14.  In the **Efficiency** field, enter the percentage of the expected standard output that this work center actually outputs. If you enter **100**, it means that the work center has an actual output that is the same as the standard output.  
15. Select the **Consolidated Calendar** check box if you are also using machine centers. This ensures that calendar entries are rolled up from machine center calendars.  
16.  In the **Shop Calendar Code** field, select a shop calendar. For more information, see [Create Shop Calendars](production-how-to-create-work-center-calendars.md).  
17.  In the **Queue Time** field, specify a fixed time span that must pass before assigned work can begin at this work center. Note that queue time is added to other non-productive time elements such as wait time and move time that you may define on routing lines using this work center.  

## Example - Different Machine Centers Assigned to a Work Center
It is important to plan which capacities are to make up the total capacity when setting up the machine centers and work centers.

If different machine centers (such as 210 Packing table 1, 310 Painting Cabin ...) are assigned to a work center, the consideration of the single capacities of the machine centers is significant because failure of one machine center can interrupt the entire process. The machine groups can be entered according to their capacity but may not be included in the planning. By deactivating the **Consolidated Calendar** field only the capacity of the work center but not the machine center is assigned in the planning.

If, however, identical machine centers (such as 210 Packing table 1 and 220 Packing table 2) are combined in a work center, the consideration of the work center as a sum of the assigned machine centers is of interest. Therefore, the work center would be listed with zero capacity. By activating the **Consolidated Calendar** field, the common capacity is assigned to the work center.

If capacities of work centers are to make no contribution to the total capacity, you can achieve this with efficiency = 0.

## To set up a capacity constrained machine or work center
You must set up production resources that you regard as critical and mark them to accept a finite load instead of the default infinite load that other production resources accept. A capacity-constrained resource can be a work center or machine center that you have identified as a bottleneck and would like to establish a limited, finite load for.

[!INCLUDE[d365fin](includes/d365fin_md.md)] does not support detailed shop floor control. It plans for a feasible utilization of resources by providing a rough-cut schedule, but it does not automatically create and maintain detailed schedules based on priorities or optimization rules.

On the **Capacity-Constrained Resources** page, you can make setup that avoids overload of specific resources and ensure that no capacity is left unallocated if it could increase the turn-around time of a production order. In the **Dampener (% of Total Capacity)** field, you can add dampener time to resources to minimize operation splitting. This enables the system to schedule load on the last possible day by exceeding the critical load percent slightly if this can reduce the number of operations that are split.

When planning with capacity-constrained resources, the system ensures that no resource is loaded above its defined capacity (critical load). This is done by assigning each operation to the nearest available time slot. If the time slot is not big enough to complete the entire operation, then the operation will be split into two or more parts placed in the nearest available time slots.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Capacity Constrined Resources**, and then choose the related link.
2. Choose the **New** action.
3. Fill in the fields as necessary.

> [!NOTE]
> Operations on work centers or machine centers that are set up as constrained resources will always be planned serially. This means that if a constrained resource has multiple capacities, then those capacities can only be planned in sequence, not in parallel as they would be if the work or machine center was not set up as a constrained resource. In a constrained resource, the Capacity field on the work center or machine center is greater than 1.

> In case of operation splitting, the setup time is only assigned once because it is assumed that some manual adjustment is done to optimize the schedule.

## See Also  
[Create Shop Calendars](production-how-to-create-work-center-calendars.md)  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Manufacturing](production-manage-manufacturing.md)    
[Planning](production-planning.md)   
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
