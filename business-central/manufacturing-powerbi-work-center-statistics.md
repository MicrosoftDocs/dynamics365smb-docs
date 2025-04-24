---
title: Work Center Statistics
description: The Work Center Statistics report shows key performance indicators for each work center.
author: kennienp
ms.author: kepontop
ms.reviewer:
ms.topic: conceptual
ms.search.keywords: reporting
# TODO correct page id must be added
# ms.search.form: 37042_Primary 
ms.date: 04/24/2024
ms.service: dynamics-365-business-central
---

# Machine Center Statistics (Power BI Report)

[!INCLUDE[applies-to-2025w1](includes/applies-to-2025w1.md)]

The **Machine Center Statistics** Power BI Report offers a comprehensive view of operational performance across all machine centers. Through a combination of high-level metrics and granular details, this report provides insights needed to evaluate efficiency, resource utilization, and production outcomes. The KPI Cards and Machine Center Efficiency Bar Chart provide concise summaries of key performance indicators (KPIs), enabling quick assessments of machine center performance. For a deeper analysis, users can leverage the detailed insights presented in the Statistic Details Table to support decision-making and drive operational improvements.

:::image type="content" source="media/manufacturing/work-center-statistics.png" alt-text="Screenshot of the Work Center Statistics Power BI Report" lightbox="media/manufacturing/work-center-statistics.png":::

The **Machine Center Scrap %** KPI Card highlights the Machine Center's Scrap Percentage, an essential measure of performance. It calculates the ratio of scrap generated to the total output processed by the machine center. Serving as a key indicator, this visual allows users to quickly assess operational efficiency and pinpoint areas for improvement

The **Machine Center Load** KPI Card provides a holistic view of the Machine Center's workload and capacity by showcasing three essential measures: Machine Center Load, Allocated Time, and Capacity (Effective). It enables users to assess resource utilization, identify bottlenecks, and evaluate operational efficiency within the machine center

The **Machine Center Efficiency** Bar Chart visualizes the actual efficiency of each machine center, organized by machine center number. It provides a visual comparison of efficiency levels, enabling users to identify performance variations and target areas for operational improvements.

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

The Machine Center Statistics report is designed for manufacturing managers and production supervisors to analyze machine center performance and efficiency.

Manufacturing managers use this report to assess key statistics related to machine center operations. By reviewing the performance metrics, managers can identify areas for improvement, optimize resource allocation, and ensure that machine centers operate at peak efficiency. This information helps with strategic planning and maintaining smooth production workflows.

Production supervisors rely on this report to monitor machine center performance. By analyzing data on output levels, scrap rates, capacity needs, and potential bottlenecks, supervisors can make informed decisions to address inefficiencies and maintain steady production.

## Key Performance Indicators (KPIs)

The *Machine Center Statistics* report includes the following KPIs and measures:

- [Machine Center Total Capacity]()
- [Machine Center Capacity Effective]()
- [Machine Center Expected Efficiency %]()
- [Machine Center Actual Need]()
- [Machine Center Actual Efficiency %]()
- [Machine Center Actual Total Cost]()
- [Machine Center Allocated Time]()
- [Machine Center Output]()
- [Machine Center Scrap]()
- [Machine Center Scrap %]()
- [Machine Center Run Time]()
- [Machine Center Stop Time]()
- [Machine Center Stop %]()
- [Machine Center Load]()

[!INCLUDE[click-on-a-kpi-link](includes/click-on-a-kpi-link.md)]

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]

## Data used in the report

The report uses data from the following tables in [!INCLUDE[prod_short](includes/prod_short.md)]:

- Capacity Ledger Entry
- Prod Order Capacity Need
- Calendar Entry
- Machine Center
  
## Try the report

Try the report here: [Machine Center Statistics](https://businesscentral.dynamics.com?page=)<!-- TODO Set page ID for link -->

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](includes/ctrl-right-click-to-open-in-new-tab.md)]

## See also

[Track your business KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md)  
[Power BI Manufacturing app](manufacturing-powerbi-app.md)  
[Built-in production reports](production-reports.md)  
[Manufacturing overview](production-manage-manufacturing.md)
