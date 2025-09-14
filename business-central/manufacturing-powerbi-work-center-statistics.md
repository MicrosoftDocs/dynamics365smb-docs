---
title: Work Center Statistics
description: The Work Center Statistics report shows key performance indicators for each work center.
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

# Work Center Statistics (Power BI Report)

[!INCLUDE[applies-to-2025w1](includes/applies-to-2025w1.md)]

The **Work Center Statistics** report offers a comprehensive view of operational performance across all work centers. Through a combination of high-level metrics and granular details, this report provides insights needed to evaluate efficiency, resource utilization, and production outcomes. The KPI cards and **Work Center Efficiency** chart provide concise summaries of key performance indicators (KPIs), enabling quick assessments of work center performance. For a deeper analysis, you can leverage the detailed insights presented in the **Statistic Details** table to support decision-making and drive operational improvements.

:::image type="content" source="media/manufacturing/work-center-statistics-v26.png" alt-text="Screenshot of the Work Center Statistics Power BI Report" lightbox="media/manufacturing/work-center-statistics-v26.png":::

The **Work Center Scrap %** KPI card highlights the work center's scrap percentage, which is an important measure of performance. The KPI compares the ratio of scrap generated to the total output processed by the work center. This data lets you quickly assess operational efficiency and pinpoint areas for improvement

The **Work Center Load** KPI card provides a holistic view of the work center's workload and capacity by showcasing three essential measures:

- Work Center Load
- Allocated Time
- Capacity (Effective)

The KPI can help you assess resource utilization, identify bottlenecks, and evaluate operational efficiency within the work center.

The **Work Center Efficiency** chart shows the actual efficiency of each work center, organized by work center number. It provides a visual comparison of efficiency levels, enabling you to identify performance variations and target areas for operational improvements.

The **Statistics Details** table provides a detailed summary of each work center, including its associated work center and a range of KPIs. The listed KPIs cover various aspects of performance, such as capacity, efficiency, cost, time allocation, output, scrap metrics, and runtime statistics. The KPIs include:

- Work Center Capacity (Total)
- Work Center Capacity (Effective)
- Work Center Expected Efficiency %
- Work Center Actual Need
- Work Center Actual Efficiency %
- Work Center Actual Total Cost
- Work Center Allocated Time

## Use the report

The Work Center Statistics report is designed to help manufacturing managers and production supervisors analyze work center performance and efficiency.

Manufacturing managers use this report to assess key statistics related to work center operations. By reviewing the performance metrics, you can identify areas for improvement, optimize resource allocation, and ensure that work centers operate at peak efficiency. This information helps with strategic planning and maintaining smooth production workflows.

Production supervisors rely on this report to monitor work center performance. By analyzing data on output levels, scrap rates, capacity needs, and potential bottlenecks, you can make informed decisions to address inefficiencies and maintain steady production.

## Key performance indicators (KPIs)

The Work Center Statistics report includes the following KPIs and measures:

- [**Work Center Capacity (Total)**](manufacturing-powerbi-kpis.md#work-center-capacity-total)
- [**Work Center Capacity (Effective)**](manufacturing-powerbi-kpis.md#work-center-capacity-effective)
- [**Work Center Expected Efficiency %**](manufacturing-powerbi-kpis.md#work-center-expected-efficiency-percent)
- [**Work Center Actual Need**](manufacturing-powerbi-kpis.md#work-center-actual-need)
- [**Work Center Actual Efficiency %**](manufacturing-powerbi-kpis.md#work-center-actual-efficiency-percent)
- [**Work Center Actual Total Cost**](manufacturing-powerbi-kpis.md#work-center-actual-total-cost)
- [**Work Center Allocated Time**](manufacturing-powerbi-kpis.md#work-center-allocated-time)
- [**Work Center Output**](manufacturing-powerbi-kpis.md#work-center-output)
- [**Work Center Scrap**](manufacturing-powerbi-kpis.md#work-center-scrap)
- [**Work Center Scrap %**](manufacturing-powerbi-kpis.md#work-center-scrap-percent)
- [**Work Center Load**](manufacturing-powerbi-kpis.md#work-center-load)

[!INCLUDE[click-on-a-kpi-link](includes/click-on-a-kpi-link.md)]

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]

## Data used in the report

The report uses data from the following tables in [!INCLUDE[prod_short](includes/prod_short.md)]:

- Capacity Ledger Entry
- Prod Order Capacity Need
- Calendar Entry
- Work Center
  
## Try the report

Try the report here: [Work Center Statistics](https://businesscentral.dynamics.com?page=)<!-- TODO Set page ID for link -->

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Track your business KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md)  
[Power BI Manufacturing app](manufacturing-powerbi-app.md)  
[Built-in production reports](production-reports.md)  
[Manufacturing overview](production-manage-manufacturing.md)
