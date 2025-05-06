---
title: Work Center Load
description: The Work Center Load report shows the load and the allocated capacity of each work center.
author: kennienp
ms.author: kepontop
ms.reviewer:
ms.topic: article
ms.search.keywords: reporting
ms.search.form: 37042_Primary
ms.date: 11/01/2024
ms.service: dynamics-365-business-central
---

# Work Center Load (Power BI Report)

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

The **Work Center Load** report measures the load and the allocated capacity of each work center. Use this report to ensure that work centers aren't overloaded.

:::image type="content" source="media/manufacturing/work-center-load.png" alt-text="Screenshot of the Work Center Load Power BI Report" lightbox="media/manufacturing/work-center-load.png":::

## Use the report

The report is meant for manufacturing managers and supervisors.

Manufacturing managers use this report to ensure that loads on work centers don't exceed their available capacity. By analyzing the load percentage and allocated time, you can identify overloaded work centers and take steps to reduce the workload. For example, you might adjust the production schedule or allocate more resources to a particular work center. Additionally, by monitoring the work center load, you can ensure room for contingencies in cases where a work center is loaded to 100%.

Production supervisors use this report to analyze the load percentage and allocated time for work center loads and report them to the manufacturing manager. This information helps ensure that the workload is distributed evenly across all work centers so production runs smoothly.

## Key Performance Indicators (KPIs)

The *Work Center Load* report includes the following KPIs and measures: 

- [Load %](manufacturing-powerbi-kpis.md#load)
- [Allocated Time (Hours)](manufacturing-powerbi-kpis.md#allocated-time-hours)
- [Capacity Available (Hours)](manufacturing-powerbi-kpis.md#capacity-available-hours)

[!INCLUDE[click-on-a-kpi-link](includes/click-on-a-kpi-link.md)] 

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]

## Data used in the report

The report uses data from the following tables in [!INCLUDE[prod_short](includes/prod_short.md)]:

- Calendar Entry
- Production Order Routing Line
- Work Center
  
## Try the report

Try the report here: [Work Center Load](https://businesscentral.dynamics.com?page=37042)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Track your business KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md)  
[Power BI Manufacturing app](manufacturing-powerbi-app.md)  
[Built-in production reports](production-reports.md)  
[Manufacturing overview](production-manage-manufacturing.md)
