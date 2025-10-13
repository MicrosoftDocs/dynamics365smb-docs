---
title: Machine Center Load
description: The Machine Center Load report shows the load and the allocated capacity of each machine center.
author: kennienp
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: reporting
ms.search.form: 37096_Primary 
ms.date: 05/26/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Machine Center Load (Power BI Report)

[!INCLUDE[applies-to-2025w1](includes/applies-to-2025w1.md)]

The **Machine Center Load** report measures the load and the allocated capacity of each machine center. Use this report to ensure that machine centers aren't overloaded.

:::image type="content" source="media/manufacturing/machine-center-load-v26.png" alt-text="Screenshot of the Machine Center Load Power BI Report" lightbox="media/manufacturing/machine-center-load-v26.png":::

## Use the report

The report is meant for manufacturing managers and supervisors.

Manufacturing managers use this report to ensure that loads on machine centers don't exceed their available capacity. By analyzing the load percentage and allocated time, you can identify overloaded machine centers and take steps to reduce the workload. For example, you might adjust the production schedule or allocate more resources to a particular machine center. Additionally, by monitoring the machine center load, you can ensure room for contingencies in cases where a machine center is loaded to 100%.

Production supervisors use this report to analyze the load percentage and allocated time for machine center loads and report them to the manufacturing manager. This information helps ensure that the workload is distributed evenly across all machine centers so production runs smoothly.

## Key performance indicators (KPIs)

The Machine Center Load report includes the following KPIs and measures:

- [**Machine Center Capacity (Effective)**](manufacturing-powerbi-kpis.md#machine-center-capacity-effective)
- [**Machine Center Allocated Time**](manufacturing-powerbi-kpis.md#machine-center-allocated-time)
- [**Machine Center Availability After Orders**](manufacturing-powerbi-kpis.md#machine-center-availability-after-orders)
- [**Machine Center Load**](manufacturing-powerbi-kpis.md#machine-center-load)
- [**Machine Center Expected Efficiency %**](manufacturing-powerbi-kpis.md#machine-center-expected-efficiency-percent)

[!INCLUDE[click-on-a-kpi-link](includes/click-on-a-kpi-link.md)]

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]

## Data used in the report

The report uses data from the following tables in [!INCLUDE[prod_short](includes/prod_short.md)]:

- Calendar Entry
- Prod Order Capacity Need
- Machine Center
  
## Try the report

Try the report here: [Machine Center Load](https://businesscentral.dynamics.com?page=37096)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Track your business KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md)  
[Power BI Manufacturing app](manufacturing-powerbi-app.md)  
[Built-in production reports](production-reports.md)  
[Manufacturing overview](production-manage-manufacturing.md)
