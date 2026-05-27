---
title: View Load on Work and Machine Centers
description: Learn how to view shop floor load on work and machine centers, and how finite capacity planning prevents overloading bottleneck resources.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.form: 99000887, 99000888, 99000889, 99000890, 99000891, 99000892, 99000915, 99000916
ms.date: 05/28/2026
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# View Load on Work and Machine Centers

In the **Work Center Card** and **Machine Center Card** pages, you can view the shop floor load as a result of planned and released production orders.

## Understanding load and capacity

**Capacity** is the amount of work a resource can perform in a given period, based on the shop calendar, number of shifts, and efficiency settings. For example, a work center running one eight-hour shift at 100% efficiency has a daily capacity of 480 minutes.

**Load** is the total work allocated to a resource from all production orders (planned, firm planned, and released). The load includes setup time and run time from routing operations assigned to that resource.

When load exceeds capacity, the resource is overloaded, which can cause scheduling delays. When load is well below capacity, the resource is underutilized.

## To view the load on work centers

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Work Centers**, and then choose the related link.  
2. Open the relevant **Work Center** card from the list, and then choose the **Load** action.  

Use the **View by** and **View as** fields on the **Options** FastTab to select the required period.

- **View by** — Select the period length: Day, Week, Month, Quarter, Year, or Accounting Period.
- **View as** — Select **Net Change** to see the load for each period, or **Balance at Date** to see the cumulative load up to each date.

The matrix shows capacity, load, and available capacity for each period. Use this view to identify bottlenecks where load consistently exceeds capacity.

## Infinite and finite capacity scheduling

By default, [!INCLUDE [prod_short](includes/prod_short.md)] uses *infinite capacity scheduling*. The system schedules operations based on lead times and routing sequences, but assumes that each resource has unlimited capacity. This approach is fast and simple, but can result in schedules where multiple operations overlap on the same resource, leading to overloaded work centers.

For bottleneck resources, you can switch to *finite capacity scheduling*. Finite scheduling ensures that operations are scheduled only when capacity is available, preventing overloads on critical resources.

### Set up capacity-constrained resources

To use finite capacity scheduling, register the resource as a capacity-constrained resource.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Capacity Constrained Resources**, and then choose the related link.
2. Choose the **New** action.
3. Select the **Capacity Type** (Work Center or Machine Center) and the **Capacity No.** of the resource.
4. In the **Critical Load %** field, specify the maximum percentage of the resource's available capacity that the scheduler can allocate. For example, entering **90** means the scheduler loads the resource to at most 90% of capacity, leaving a 10% buffer.
5. In the **Dampener (% of Total Capacity)** field, specify a tolerance percentage. This value allows the scheduler to slightly exceed the critical load when it avoids splitting an operation across multiple time slots.

When the planning system calculates schedules for production orders, operations on constrained resources are scheduled serially in the nearest available time slot. If the available time slot is too small for the entire operation, the operation is split across multiple slots.

> [!NOTE]
> Operations on constrained resources are always planned serially, even if the work center has multiple capacities. For unconstrained resources, multiple capacities can be used in parallel.

To learn more about setting up constrained resources, go to [Set Up Work Centers and Machine Centers](production-how-to-set-up-work-and-machine-centers.md).

## Related information  
[Manufacturing](production-manage-manufacturing.md)
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Planning](production-planning.md)  
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
