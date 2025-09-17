---
title: Prod.Order Routing Gantt
description: Learn how to benefit from using the Prod. Order Routing Gantt report.
author: kennienp
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: reporting
# TODO correct page id must be added
# ms.search.form: 37042_Primary 
ms.date: 05/26/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Prod. Order Routing Gantt (Power BI Report)

[!INCLUDE[applies-to-2025w1](includes/applies-to-2025w1.md)]

The **Prod. Order Routings Gantt** report provides an overview of production processes, combining visual and tabular formats to enhance understanding. The report helps you monitor and analyze production tasks, offering insights into scheduling, durations, and task locations.

:::image type="content" source="media/manufacturing/prod-order-routing-gantt-v26.png" alt-text="Screenshot of the Prod Order Routing Gantt Power BI Report" lightbox="media/manufacturing/prod-order-routing-gantt-v26.png":::

The **Production Time Line (Gantt Chart Visual)** visualization provides a Gantt chart representation of production processes, enabling you to effectively monitor and analyze tasks within production orders. Key features of this visualization include:

1. **Hierarchy:**  
   - *Parent:* Production orders serve as the primary grouping level.  
   - *Nested Tasks:* Routing line descriptions represent individual tasks in the process.  

2. **Timeline Configuration:**  
   - By default, the timeline displays at a daily level.  
   - Non-working days are highlighted in red for improved clarity.  

3. **Task Duration:**  
   - Task durations calculate based on the routing line's starting and ending date-time values.  

4. **Task Bar Representation:**  
   - The color of the task bars differentiates between routing through machine centers and work centers.  
   - Within each bar, the name of the machine center or work center displays, providing added context about where the task is done.  

The **Routing Line Details** table is a tabular representation of production and routing data. It includes essential information such as the **Production Order No.** and the **Operations No.** which specifies individual operations within the process. The table also highlights the **Work Center/Machine Center No.**, identifying the location associated with each routing line task. Additionally, the table displays the **Starting Date Time** and **Ending Date Time**, outlining the scheduled start and completion times for tasks. The date times are used to calculate the **Total Duration Hours**, showing the time taken to execute tasks in hours, and the **Duration Total Days**, which represents the task duration in days for an alternative perspective. Together, these details ensure you have a clear and structured view of production processes.

## Use the report

Manufacturing Managers use the report to gain an overview of production scheduling and routing processes. The **Production Time Line** Gantt chart helps you monitor task durations and sequencing. The bar colors and contextual information on machine centers or work centers allow you to quickly identify resource usage and task assignments. Paired with the **Routing Line Details** table, you can analyze production timelines, evaluate task completion dates, and compare actual durations with planned expectations. These details help you detect delays, optimize schedules, and ensure you allocate resources effectively across work centers and machine centers.  

Production supervisors rely on the report to manage day-to-day production tasks and maintain operational efficiency. The Gantt chart shows production order tasks so that you can easily track which operations are occurring at what locations and for how long. The red-marked non-working days help you identify gaps or conflicts in scheduling and address potential bottlenecks. Meanwhile, the **Routing Line Details** table provides starting and ending date times with total task durations by day and by hours. Together, the Gantt visual and tabular components of the report support effective coordination for smooth production workflows.  

## Key performance indicators (KPIs)

The Prod. Order Routing Gantt report includes the following KPIs and measures:

- [**Total Duration Hours**](manufacturing-powerbi-kpis.md#total-duration-hours)
- [**Total Duration Days**](manufacturing-powerbi-kpis.md#total-duration-days)
- [**Posted Output Quantity**](manufacturing-powerbi-kpis.md#posted-output-quantity)

[!INCLUDE[click-on-a-kpi-link](includes/click-on-a-kpi-link.md)]

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]

## Data used in the report

The report uses data from the following tables in [!INCLUDE[prod_short](includes/prod_short.md)]:

- Prod. Order Routing Line
- Production Order
  
## Try the report

Try the report here: [Prod. Order Routing Gantt](https://businesscentral.dynamics.com?page=)<!-- TODO Set page ID for link -->

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Track your business KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md)  
[Power BI Manufacturing app](manufacturing-powerbi-app.md)  
[Built-in production reports](production-reports.md)  
[Manufacturing overview](production-manage-manufacturing.md)
