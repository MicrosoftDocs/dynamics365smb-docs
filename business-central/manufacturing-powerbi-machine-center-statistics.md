---
title: Machine Center Statistics
description: The Machine Center Statistics report shows key performance indicators for each machine center.
author: kennienp
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: 37095_Primary 
ms.date: 05/26/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Machine Center Statistics (Power BI Report)

[!INCLUDE[applies-to-2025w1](includes/applies-to-2025w1.md)]

The **Machine Center Statistics** report offers a comprehensive view of operational performance across all machine centers. Through a combination of high-level metrics and granular details, this report provides the insights needed to evaluate efficiency, resource utilization, and production outcomes. The key performance indicator (KPI) cards and **Machine Center Efficiency** chart provide concise summaries of KPIs, enabling quick assessments of machine center performance. For a deeper analysis, you can leverage the detailed insights in the **Statistic Details** table to support decision-making and drive operational improvements.

:::image type="content" source="media/manufacturing/machine-center-statistics-v26.png" alt-text="Screenshot of the Machine Center Statistics Power BI Report" lightbox="media/manufacturing/machine-center-statistics-v26.png":::

The **Machine Center Scrap %** KPI card highlights the **Machine Center's Scrap Percentage**, an essential measure of performance. It compares the ratio of scrap generated to the total output processed by the machine center. This visual lets you quickly assess operational efficiency and pinpoint areas for improvement.

The **Machine Center Load** KPI card provides a holistic view of the machine center's workload and capacity by showcasing three essential measures: 

- Machine Center Load
- Allocated Time
- Capacity (Effective)

The card enables you to assess resource utilization, identify bottlenecks, and evaluate operational efficiency in the machine center.

The **Machine Center Efficiency** chart shows the actual efficiency of each machine center, organized by machine center number. The chart provides a comparison of efficiency levels so you can identify performance variations and target areas for operational improvements.

The **Statistics Details** table provides a detailed summary of each machine center, including its associated work center and a range of key performance indicators (KPIs). The listed KPIs cover various aspects of performance, such as capacity, efficiency, cost, time allocation, output, scrap metrics, and runtime statistics. These include:

- Machine Center Total Capacity
- Machine Center Capacity Effective
- Machine Center Expected Efficiency %
- Machine Center Actual Need
- Machine Center Actual Efficiency %
- Machine Center Actual Total Cost
- Machine Center Allocated Time
- Machine Center Output
- Machine Center Scrap
- Machine Center Scrap %
- Machine Center Run Time
- Machine Center Stop Time
- Machine Center Stop %

## Use the report

Manufacturing managers and production supervisors use the report to analyze machine center performance and efficiency.

Manufacturing managers use this report to assess key statistics related to machine center operations. By reviewing the performance metrics, managers can identify areas for improvement, optimize resource allocation, and ensure that machine centers operate at peak efficiency. This information helps with strategic planning and maintaining smooth production workflows.

Production supervisors rely on this report to monitor machine center performance. By analyzing data on output levels, scrap rates, capacity needs, and potential bottlenecks, supervisors can make informed decisions to address inefficiencies and maintain steady production.

## Key performance indicators (KPIs)

The Machine Center Statistics report includes the following KPIs and measures:

- [**Machine Center Capacity (Total)**](manufacturing-powerbi-kpis.md#machine-center-capacity-total)
- [**Machine Center Capacity (Effective)**](manufacturing-powerbi-kpis.md#machine-center-capacity-effective)
- [**Machine Center Expected Efficiency %**](manufacturing-powerbi-kpis.md#machine-center-expected-efficiency-percent)
- [**Machine Center Actual Need**](manufacturing-powerbi-kpis.md#machine-center-actual-need)
- [**Machine Center Actual Efficiency %**](manufacturing-powerbi-kpis.md#machine-center-actual-efficiency-percent)
- [**Machine Center Actual Total Cost**](manufacturing-powerbi-kpis.md#machine-center-actual-total-cost)
- [**Machine Center Allocated Time**](manufacturing-powerbi-kpis.md#machine-center-allocated-time)
- [**Machine Center Output**](manufacturing-powerbi-kpis.md#machine-center-output)
- [**Machine Center Scrap**](manufacturing-powerbi-kpis.md#machine-center-scrap)
- [**Machine Center Scrap %**](manufacturing-powerbi-kpis.md#machine-center-scrap-percent)
- [**Machine Center Run Time**](manufacturing-powerbi-kpis.md#machine-center-run-time)
- [**Machine Center Stop Time**](manufacturing-powerbi-kpis.md#machine-center-stop-time)
- [**Machine Center Stop %**](manufacturing-powerbi-kpis.md#machine-center-stop-percent)
- [**Machine Center Load**](manufacturing-powerbi-kpis.md#machine-center-load)

[!INCLUDE[click-on-a-kpi-link](includes/click-on-a-kpi-link.md)]

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]

## Data used in the report

The report uses data from the following tables in [!INCLUDE[prod_short](includes/prod_short.md)]:

- Capacity Ledger Entry
- Prod Order Capacity Need
- Calendar Entry
- Machine Center
  
## Try the report

Try the report here: [Machine Center Statistics](https://businesscentral.dynamics.com?page=37095)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Track your business KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md)  
[Power BI Manufacturing app](manufacturing-powerbi-app.md)  
[Built-in production reports](production-reports.md)  
[Manufacturing overview](production-manage-manufacturing.md)
