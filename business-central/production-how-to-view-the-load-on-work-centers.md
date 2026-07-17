---
title: View Load on Work and Machine Centers
description: Learn how to compare resource load and capacity, identify bottlenecks, use finite scheduling, and review the Work Center Task List.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.form: 99000887, 99000888, 99000889, 99000890, 99000891, 99000892, 99000915, 99000916
ms.date: 07/15/2026
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# View the load on work and machine centers

Capacity shows how much work a production resource can perform, while load shows the work assigned by planned and released production orders. Comparing them helps you identify overloaded resources, unused capacity, and operations that might delay production. This article explains how to review load and use finite capacity scheduling for constrained resources.

## Understanding load and capacity

**Capacity** is the amount of work a resource can perform in a given period, based on the shop calendar, number of shifts, and efficiency settings. For example, a work center running one eight-hour shift at 100% efficiency has a daily capacity of 480 minutes.

**Load** is the total work allocated to a resource from all production orders (planned, firm planned, and released). The load includes setup time and run time from routing operations assigned to that resource.

When load exceeds capacity, the resource is overloaded, which can cause scheduling delays. When load is well under capacity, the resource is underutilized.

## To view the load on work centers

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Work Centers**, and then choose the related link.  
2. Open the relevant **Work Center** card from the list, and then choose the **Load** action.  

Use the **View by** and **View as** fields on the **Options** FastTab to select the required period.

- **View by**: Select the period length: Day, Week, Month, Quarter, Year, or Accounting Period.
- **View as**: Select **Net Change** to see the load for each period, or **Balance at Date** to see the cumulative load up to each date.

The matrix shows capacity, load, and available capacity for each period. Use this view to identify bottlenecks where load consistently exceeds capacity.

## Infinite and finite capacity scheduling

By default, [!INCLUDE [prod_short](includes/prod_short.md)] uses *infinite capacity scheduling*. The system schedules operations based on lead times and routing sequences, but assumes that each resource has unlimited capacity. This approach is fast and simple, but can result in schedules where multiple operations overlap on the same resource, leading to overloaded work centers.

For bottleneck resources, you can switch to *finite capacity scheduling*. Finite scheduling ensures that operations are scheduled only when capacity is available, preventing overloads on critical resources.

To set up finite capacity scheduling, register the resource as a capacity-constrained resource. To learn more, go to [Set Up a Capacity Constrained Machine or Work Center](production-how-to-set-up-work-and-machine-centers.md#to-set-up-a-capacity-constrained-machine-or-work-center).

## View the Work Center Task List

The **Work Center Task List** page shows all production order routing lines that are currently assigned to a work center. Use this page to review planned work or in progress at a specific work center. You can also monitor the timing and capacity allocation for each operation.

To open the Work Center Task List:

1. Open the **Work Center Card** or **Work Center List** page.
2. Choose the **Work Center Task List** action (under **Planning**).

The page shows one line per production order routing operation assigned to the work center, with the following key fields:

| Field | Description |
| -- | -- |
| **Status** | The production order status (Simulated, Planned, Firm Planned, Released, or Finished). |
| **Prod. Order No.** | The production order number. |
| **Operation No.** | The operation number from the routing. |
| **Description** | The description of the operation or the production order. |
| **Setup Time** / **Run Time** | The expected setup and run times for the operation. |
| **Wait Time** / **Move Time** | The expected wait and move times after the operation. |
| **Starting Date/Time** | The scheduled start of the operation. |
| **Ending Date/Time** | The scheduled end of the operation. |
| **Send-Ahead Quantity** | The quantity to send to the next operation before this operation completes the full lot. |
| **Concurrent Capacities** | The number of machines or people allocated to this operation. |

Use the Work Center Task List to quickly identify scheduling conflicts, overloaded time periods, or gaps between operations at a work center.

> [!TIP]
> You can also access the task list from the **Work Center Calendar Matrix** page, which provides a graphical overview of capacity allocation across multiple work centers and time periods.

## Related information  

[Manufacturing](production-manage-manufacturing.md)  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Planning](production-planning.md)  
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
