---
title: Power BI Manufacturing app
description: The Power BI Manufacturing app provides insights into your manufacturing activities.
author: kennienp
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: 37063_Primary, 37042, 37043, 37044, 37045, 37046, 37047, 37048, 37049, 37055, 37094, 37095, 37096, 37097, 37098, 37099, 37107, 36951,
ms.date: 11/03/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Manufacturing Power BI app

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

The Power BI Manufacturing app gives insights into your manufacturing activities. Its detailed analytics and visualizations of manufacturing data help:

- Streamline manufacturing processes
- Improve decision-making at all levels of the organization
- Optimize production efficiency

## Manufacturing analytics for the leadership team

To fit this category, you might have a role such as:

- Chief Operating Officer
- Chief Manufacturing Officer
  
### Example scenario: analyze capacity and efficiency

As a COO, you need to understand how efficiently your manufacturing plant uses its resources. Use the [Work Center Statistics](manufacturing-powerbi-work-center-statistics.md) report to compare work center efficiency, capacity, and allocated time, and identify areas for improvement.

You can also use the [Work Center Load](manufacturing-powerbi-work-center-load.md) report to identify bottlenecks in your production process, and make informed decisions to increase efficiency and productivity.

## Manufacturing analytics for the management team

To fit this category, you might have a role such as:

- Manufacturing Manager
- Operations Manager

### Example scenario: improving resource usage

Manufacturing managers ensure that all production orders are completed on time and within budget. Using the [Finished Production Order Breakdown](manufacturing-powerbi-finished-production-order-breakdown.md) and [Average Production Times](manufacturing-powerbi-average-production-times.md) reports, you can analyze the production time for each order and identify opportunities to optimize the production process.

The [Allocated Hours](manufacturing-powerbi-allocated-hours.md) report provides a detailed breakdown of allocated hours and aggregates them by work center. This report can help you catch unexpected spikes in resource usage.

By using the [Released Production Orders](manufacturing-powerbi-released-production-orders.md) report, you can also identify discrepancies in production patterns across different orders and make decisions.

## Manufacturing analytics for warehouse staff

To fit this category, you might have a role such as:

- Manufacturing Supervisor
- Production Operator

### Example scenario: tracking production lines

Manufacturing supervisors ensure that goods and materials flow smoothly through the manufacturing facility. Your role is critical in maintaining the production schedule and meeting customer demand. Use the [Work Center Load](manufacturing-powerbi-work-center-load.md) report to compare allocated time with available capacity and identify overloaded work centers.

You notice that one work center is overloaded, while others have available capacity. Use the [Work Center Statistics](manufacturing-powerbi-work-center-statistics.md) report to compare capacity and efficiency across work centers. Use these insights to review the production schedule and resource allocation.

To improve production efficiency, you track the allocated hours for each work center using the [Allocated Hours](manufacturing-powerbi-allocated-hours.md) report. This report helps you understand workloads and adjust staffing levels accordingly.

## Use the reports

The **Current Utilization** and **Historical Utilization** report pages are obsolete. To review work center capacity and performance, use the **Work Center Load** and **Work Center Statistics** reports in the following table.

[!INCLUDE [power-bi-manufacturing-app](includes/power-bi-manufacturing-app.md)]

## Manage subcontractors in manufacturing reports

The Manufacturing Power BI App includes subcontracted costs and subcontractor work centres by default. To exclude subcontracted costs from manufacturing reporting, a **Subcontracting** filter is available on each report page. You can choose to exclude, include, or only show manufacturing insights for work centers assigned a subcontractor.

> [!NOTE]
> The Subcontracting filter is based on the work center configuration, rather than historical subcontractor status. If you change the subcontractor assignment on a work center, the historical capacity ledger entry insights might be inaccurate.

## Related information

[Installing Power BI apps for Business Central](across-powerbi-install-business-central-apps.md)   
[Track your business KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md)  
[Built-in production reports](production-reports.md)  
[Manufacturing overview](production-manage-manufacturing.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
