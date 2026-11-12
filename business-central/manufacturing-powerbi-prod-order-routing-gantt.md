---
title: Production Order Routing Gantt Power BI Report
description: Review scheduled production operations, routing timelines, work and machine centers, and posted output with the Prod. Order Routing Gantt Power BI report.
author: kennienp
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: 37099_Primary
ms.date: 11/12/2026
ai-usage: ai-assisted
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Prod. order routing Gantt (Power BI report)

[!INCLUDE[applies-to-2025w1](includes/applies-to-2025w1.md)]

The **Prod. Order Routings Gantt** report provides an overview of production processes, combining visual and tabular formats to enhance understanding. The report helps you monitor and analyze production tasks, offering insights into scheduling, durations, and task locations.

:::image type="content" source="media/manufacturing/prod-order-routing-gantt-v26.png" alt-text="Screenshot of the Prod Order Routing Gantt Power BI Report" lightbox="media/manufacturing/prod-order-routing-gantt-v26.png":::

The **Production Time Line (Gantt Chart Visual)** visualization provides a Gantt chart representation of production processes, enabling you to effectively monitor and analyze tasks within production orders. Key features of this visualization include:

1. **Hierarchy:**  
   - *Parent:* Production orders serve as the primary grouping level.  
   - *Nested Tasks:* Routing line descriptions represent individual tasks in the process.  

1. **Timeline Configuration:**  
   - By default, the timeline displays at a daily level.  
   - Nonworking days are shaded for improved clarity.

1. **Task Duration:**  
   - Task durations calculate based on the routing line's starting and ending date-time values.  

1. **Task Bar Representation:**  
   - The color of the task bars differentiates between routing through machine centers and work centers.  
   - Within each bar, the name of the machine center or work center displays, providing added context about where the task is done.  

The **Routing Line Details** table shows production orders, routing and operation numbers, and work center or machine center names. **Starting Date Time** and **Ending Date Time** show the scheduled start and completion times. **Duration Total Hours** and **Duration Total Days** express the elapsed scheduled duration, not posted actual time. The table also shows posted output quantity and routing status.

## Use the report

Manufacturing Managers use the report to gain an overview of production scheduling and routing processes. The **Production Time Line** Gantt chart helps you monitor task durations and sequencing. The bar colors and contextual information on machine centers or work centers allow you to quickly identify resource usage and task assignments. Paired with the **Routing Line Details** table, you can analyze scheduled production timelines and durations. These durations come from routing line start and end times, not posted actual time. These details help you detect scheduling conflicts, optimize schedules, and ensure you allocate resources effectively across work centers and machine centers.

Production supervisors rely on the report to manage day-to-day production tasks and maintain operational efficiency. The Gantt chart shows production order tasks so that you can easily track which operations are occurring at what locations and for how long. The shaded nonworking days help you identify gaps or conflicts in scheduling and address potential bottlenecks. Meanwhile, the **Routing Line Details** table provides starting and ending date times with total task durations by day and by hours. Together, the Gantt visual and tabular components of the report support effective coordination for smooth production workflows.

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
- Capacity Ledger Entry
- Work Center
- Machine Center
  
## Try the report

Try the report here: [Prod. Order Routing Gantt](https://businesscentral.dynamics.com?page=37099)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Track your business KPIs with Power BI goals](track-kpis-with-power-bi-metrics.md)  
[Power BI Manufacturing app](manufacturing-powerbi-app.md)  
[Built-in production reports](production-reports.md)  
[Manufacturing overview](production-manage-manufacturing.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
