---
title: Prod.Order Routing Gantt
description: The Prod. Order Routing Gantt
author: kennienp
ms.author: kepontop
ms.reviewer:
ms.topic: conceptual
ms.search.keywords: reporting
# TODO correct page id must be added
# ms.search.form: 37042_Primary 
ms.date: 04/25/2024
ms.service: dynamics-365-business-central
---

# Prod. Order Routing Gantt (Power BI Report)

[!INCLUDE[applies-to-2025w1](includes/applies-to-2025w1.md)]

The Prod. Order Routings Gantt report provides an overview of production processes, combining visual and tabular formats to enhance user understanding. The report helps users monitor and analyze production tasks, offering insights into scheduling, durations, and task locations. 

:::image type="content" source="media/manufacturing/prod-order-routing-gantt.png" alt-text="Screenshot of the Prod Order Routing Gantt Power BI Report" lightbox="media/manufacturing/prod-order-routing-gantt.png":::

The **Production Time Line (Gantt Chart Visual)** visualization provides a Gantt chart representation of production processes, enabling users to effectively monitor and analyze tasks within production orders. Key features of this visualization include:

1. **Hierarchy:**  
   - *Parent:* Production Orders serve as the primary grouping level.  
   - *Nested Tasks:* Routing Line Descriptions represent individual tasks within the process.  

2. **Timeline Configuration:**  
   - By default, the timeline is displayed at a daily granularity.  
   - Non-working days are highlighted in red for improved clarity.  

3. **Task Duration:**  
   - Task durations are calculated based on the routing line's starting and ending date-time values.  

4. **Task Bar Representation:**  
   - The color of the task bars differentiates between routing through machine centers and work centers.  
   - Within each bar, the name of the machine center or work center is displayed, providing added context about where the task is executed.  

The **Routing Line Details** table serves as a tabular representation of production and routing data. It includes essential information such as the **Production Order No.** and the **Operations No.** which specifies individual operations within the process. The table also highlights the **Work Center/Machine Center No.**, identifying the location associated with each routing line task. Additionally, the table displays the **Starting Date Time** and **Ending Date Time**, outlining the scheduled start and completion times for tasks. The date times are used to calculate the **Total Duration Hours**, showing the time taken to execute tasks in hours, and the **Duration Total Days**, which represents the task duration in days for an alternative perspective. Together, these details ensure users have a clear and structured view of production processes.

## Use the report

## Key Performance Indicators (KPIs)

The *Prod. Order List* report includes the following KPIs and measures:

- [Actual Total Cost]()
- [Expected Total Cost]()
- [Standard Total Cost]()
- [Total Expected Cost Dev %]()
- [Total Standard Cost Dev %]()
- [No. of Production Orders]()
- [Planned Quantity]()
- [Finished Quantity]()
- [Variance Quantity]()

[!INCLUDE[click-on-a-kpi-link](includes/click-on-a-kpi-link.md)]

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]

## Data used in the report

The report uses data from the following tables in [!INCLUDE[prod_short](includes/prod_short.md)]:

- Item Ledger Entry
- Capacity Ledger Entry
- Value Entries
- Production Order
- Production Order Line
- Inventory Adjustment Entry Order Line
  
## Try the report

Try the report here: [Prod. Order List](https://businesscentral.dynamics.com?page=)<!-- TODO Set page ID for link -->

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](includes/ctrl-right-click-to-open-in-new-tab.md)]

## See also

[Track your business KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md)  
[Power BI Manufacturing app](manufacturing-powerbi-app.md)  
[Built-in production reports](production-reports.md)  
[Manufacturing overview](production-manage-manufacturing.md)
