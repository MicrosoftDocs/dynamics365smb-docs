---
    title: Set Up Work Centers and Machine Centers
    description: A Work Center card organizes the fixed values and requirements of the production resource, and thus governs the output of production performed in that work center.
    author: brentholtorf
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.form: 99000754, 99000755, 99000756, 99000758, 99000760, 99000761, 99000762
    ms.date: 04/01/2021
    ms.author: bholtorf

---
# Set Up Work Centers and Machine Centers

The application distinguishes between three types of capacities. These are arranged hierarchically. Each level contains the subordinate levels.  

The top level is the work center group. Work centers are assigned to the work center groups. Every work center can only belong to one work center group.

You can assign various machine centers to every work center. A machine center may only belong to one work center.  

The planned capacity of a work center consists of the availability of the corresponding machine centers and the additional planned availability of the work center. The planned availability of the work center group is, therefore, the sum of all corresponding availabilities of the machine centers and work centers.  

The availability is stored in calendar entries.  

> [!IMPORTANT]
> Before you set up work or machine centers, you must set up shop calendars. For more information, see [Create Shop Calendars](production-how-to-create-work-center-calendars.md).

## To set up a work center

The following primarily describes how to set up a work center. The steps to set up a machine center calendar are similar except for the **Routing Setup** FastTab.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Work Centers**, and then choose the related link.  
2. Choose the **New** action.  
3. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. In the **Work Center Group** field, select the higher-level resource grouping that the work center is organized under, if relevant. Choose the **New** action in the drop-down list.  
5. In the **Alternate Work Center** field, select the work center to use if this work center isn't available or when demand exceeds its capacity. The alternate work center is for information only, and isn't automatically included in planning processes.
6. Select the **Blocked** field if you want to prevent the work center from being used in any processing. This means that output cannot be posted for an item that is produced at the work center. For more information, see [Post Production Output](production-how-to-post-output-quantity.md).
7. In the **Direct Unit Cost** field, enter the cost of producing one unit of measure at this work center, excluding any other cost elements. This cost is often referred to as the *direct labor rate*.  
8. In the **Indirect Cost %** field, enter the general operation costs of using the work center as a percentage of the direct unit cost. This percentage amount is added to the direct cost in the calculation of the unit cost.  
9. In the **Overhead Rate** field, enter any non-operational costs, for example maintenance expenses, of the work center as an absolute amount.  

    The **Unit Cost** field contains the calculated unit cost of producing one unit of measure at this work center, including all cost elements, as follows:  

    Unit Cost = Direct Unit Cost + (Direct Unit Cost x Indirect Cost %) + Overhead Rate.  

10. In the **Unit Cost Calculation** field, define whether the above calculation should be based on the amount of time used:  **Time**, or on the number of produced units:  **Units**.  
11. Select the **Specific Unit Cost** field if you want to define the work center's unit cost on the routing line where it is being used. This may be relevant for operations with dramatically different capacity costs than what would normally be processed at that work center.  
12. In the **Flushing Method** field, select whether output posting at this work center should be calculated and posted manually or automatically, using either of the following methods.

    |Option|Description|
    |------|-----------|
    |**Manual**| Used time, output and scrap are posted manually in the output journal or production journal.|
    |**Forward**|Output is posted automatically when the production order is released.|
    |**Backward**|Output is posted automatically when the production order is finished.|

    > [!NOTE]
    > If necessary, the flushing method selected here, can be overridden for individual operations by changing the setting on routing lines

13. In the **Unit of Measure Code** field, enter the time unit in which this work center's cost calculation and capacity planning are made.
    In order to be able to constantly monitor consumption, you must first set up a method of measure. The units you enter are basic units. For example, the processing time is measured in hours and minutes.

    > [!NOTE]  
    > If you select to use Days then remember that 1 day = 24 hours - and not 8 (working hours).

14. In the **Capacity** field, define whether the work center has more than one machine or person working at the same time. If your [!INCLUDE[prod_short](includes/prod_short.md)] installation does not include the Machine Center functionality, then the value in this field must be **1**.  
15. In the **Efficiency** field, enter the percentage of the expected standard output that this work center actually outputs. If you enter **100**, it means that the work center has an actual output that is the same as the standard output.  
16. Select the **Consolidated Calendar** check box if you are also using machine centers. This ensures that calendar entries are rolled up from machine center calendars.  
17. In the **Shop Calendar Code** field, select a shop calendar. For more information, see [Create Shop Calendars](production-how-to-create-work-center-calendars.md).  
18. In the **Queue Time** field, specify a fixed time span that must pass before assigned work can begin at this work center. 

> [!NOTE]
> Use queue times to provide a buffer between the time that a component arrives at a machine or work center and when the operation actually starts. For example, a part is delivered to a machine center at 10:00 but it takes an hour to mount it on the machine so the operation does not start until 11.00. To account for that hour, the queue time would be one hour. The value of the **Queue Time** field on a machine or work center card plus the sum of the values in the **Setup Time**, **Run Time**, **Wait Time**, and **Move Time** fields on the item routing line combine to give the production lead time of the item. This helps provide accurate overall production times.  

## Considerations about capacity

The capacity and efficiency that is specified for a work and machine center not only affect the available capacity. They also impact the overall production time that consists of the setup time and run time, which are both defined on the routing line.  

When a specific routing line is allocated to a work or machine center, the system calculates how much capacity is needed and how long will it take to complete the operation.  

### Run time

To calculate the run time, the system allocates the exact time that is defined in the **Run Time** field of the routing line. Neither efficiency nor capacity impact the allocated time. For example, if the run time is defined as 2 hours, then the allocated time will be 2 hours, regardless of values in the efficiency and capacity fields in the work center.  

> [!NOTE]
> The capacity that is used in the calculations is defined as the minimal value between the capacity that is defined in the work or machine center and the concurrent capacity that is defined for the routing line. If a work center has a capacity of 100, but the concurrent capacity for the routing line is 2, then *2* will be used in the calculations.

The *duration* of an operation, on the contrary, considers both efficiency and capacity. Duration is calculated as *Run Time / Efficiency / Capacity*. The following list shows a few examples of the calculation of duration for the same run time, which is defined as 2 hours for the routing line:

- Efficiency 80% means you will need 2.5 hours instead of two hours  
- Efficiency 200% means you can complete the work in one hour - you can dig the hole twice faster if you have an excavator that is twice the size of the smaller one  

    You can achieve the same result if you use two smaller excavators instead of a large one – use *2* as the capacity and *100%* as the efficiency  

The fractional capacity is tricky, and we will discuss it later. 

### Setup time

Time allocation for the setup time depends on the capacity and is calculated as *Setup Time * Capacity*. For example, if the capacity is set to *2*, your allocated setup time will be doubled, because you must set up two machines for the operation.  

*Duration* of setup time depends on efficiency and is calculated as *Setup Time / Efficiency*. 

- Efficiency 80% means you will need 2.5h instead of two hours to set up  
- Efficiency 200% means you can complete setup in 1h instead of 2 hours defined in the Routing Line  

The fractal capacity is not something easy to embrace, and it is used in very specific cases.

### Work center processing multiple orders simultaneously

Let's use a paint-spraying booth as an example. It has the same setup and run time for each processed lot. But each lot can contain multiple individual orders that are painted simultaneously.  

In this case, the time and cost that is allocated to orders is managed by the setup time and the concurrent capacity. We recommend that you not use run time in the routing lines.  

The allocated setup time for each individual order will be in reverse order of the number of orders (quantities) that are executed simultaneously. Here are some more examples of the calculation of setup time when that is defined as two hours for the routing line:

- If there are two orders, then the concurrent capacity in the routing line should be set to 0.5.

    As a result, the allocated capacity for each will be one hour, but the duration for each order will remain two hours.
- If there are two orders with a quantity of one and four, respectively, then the concurrent capacity for the routing line of the first order is 0.2, and 0.8 for the second.  

    As a result, the allocated capacity for the first order will be 24 min and for the second one 96. The duration for both orders remain two hours.  

In both cases, the total allocated time for all orders is two hours.


### Efficient resource can dedicate only part of their work date to productive work

> [!NOTE]
> This scenario is not recommended. We recommend that you use efficiency instead. 

One of your work centers represents an experienced worker who works with 100% efficiency on tasks. But they can only spend 50% of their working time on tasks because the rest of the time they solve administrative tasks. While this worker is capable to complete a two hour task in exactly two hours, in average you must wait another two hours while the person is dealing with other assignments.  

The allocated run time is two hours, and the duration is four hours.  

Do not use setup time for such scenarios, as the system will allocate only 50% of the time. If the setup time is set to *2*, then the allocated setup time is one hour, and the duration is two hours.

### Consolidated calendar

When **Consolidated calendar** field is selected, then the work center has no capacity of its own. Instead, its capacity is equal to the sum of the capacities of all the machine centers that are assigned to the work center.  

> [!NOTE]
>  The efficiency of the machine center is converted to the capacity of the work center.

For example, if you have two machine centers with an efficiency of 80 and 70, respectively, the consolidated calendar entry will have an efficiency of 100, a capacity of 1.5, and a total capacity as 12 hours (eoithgt hour shift * 1.5 capacity). 

> [!NOTE]
>  Use the **Consolidated Calendar** field when you structure your routings to schedule production operations at the machine center level, not the work center level. When you consolidate the calendar, the **Work Center Load** page and reports become an overview of the aggregate load in all machine centers that are assigned to the work center.

### Example - Different Machine Centers Assigned to a Work Center

It is important to plan which capacities are to make up the total capacity when setting up the machine centers and work centers.

If different machine centers (such as 210 Packing table 1, 310 Painting Cabin ...) are assigned to a work center, the consideration of the single capacities of the machine centers is significant because failure of one machine center can interrupt the entire process. The machine groups can be entered according to their capacity but may not be included in the planning. By deactivating the **Consolidated Calendar** field only the capacity of the work center but not the machine center is assigned in the planning.

If, however, identical machine centers (such as 210 Packing table 1 and 220 Packing table 2) are combined in a work center, the consideration of the work center as a sum of the assigned machine centers is of interest. Therefore, the work center would be listed with zero capacity. By activating the **Consolidated Calendar** field, the common capacity is assigned to the work center.

If capacities of work centers are to make no contribution to the total capacity, you can achieve this with efficiency = 0.

## To set up a capacity constrained machine or work center

You must set up production resources that you regard as critical and mark them to accept a finite load instead of the default infinite load that other production resources accept. A capacity-constrained resource can be a work center or machine center that you have identified as a bottleneck and would like to establish a limited, finite load for.

[!INCLUDE[prod_short](includes/prod_short.md)] does not support detailed shop floor control. It plans for a feasible utilization of resources by providing a rough-cut schedule, but it does not automatically create and maintain detailed schedules based on priorities or optimization rules.

On the **Capacity-Constrained Resources** page, you can make setup that avoids overload of specific resources and ensure that no capacity is left unallocated if it could increase the turn-around time of a production order. In the **Dampener (% of Total Capacity)** field, you can add dampener time to resources to minimize operation splitting. This enables the system to schedule load on the last possible day by exceeding the critical load percent slightly if this can reduce the number of operations that are split.

When planning with capacity-constrained resources, the system ensures that no resource is loaded above its defined capacity (critical load). This is done by assigning each operation to the nearest available time slot. If the time slot is not big enough to complete the entire operation, then the operation will be split into two or more parts placed in the nearest available time slots.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Capacity Constrained Resources**, and then choose the related link.
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
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
