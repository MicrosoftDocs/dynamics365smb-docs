---
title: Production Order Overview
description: The Production Order Overview report provides a high-level summary of your organization's production order activities.
author: kennienp
ms.author: kepontop
ms.reviewer:
ms.topic: conceptual
ms.search.keywords: reporting
# TODO correct page id must be added
# ms.search.form: 37042_Primary 
ms.date: 04/22/2024
ms.service: dynamics-365-business-central
---

# Production Order Overview (Power BI Report)

[!INCLUDE[applies-to-2025w1](includes/applies-to-2025w1.md)]

The **Production Order Overview** report provides a high-level summary of your organization's production order activities. This report filters out finished production orders so that only current production order data is included. The report showcases key performance metrics (KPIs), such as:

- The number of production orders
- Completion rate measured as Finished %
- Actual Total Cost
- Total Expected Cost
- Total Standard Cost

:::image type="content" source="media/manufacturing/production-order-overview-v26.png" alt-text="Screenshot of the Production Order Overview Power BI Report" lightbox="media/manufacturing/production-order-overview-v26.png":::

The **No. of Production Orders by Status** bar chart breaks down productions orders by status, allowing you to quickly see the volume of documents at different stages of production.

The **Completion Ratios by Source No** is a 100% stacked bar chart that shows the completion rate of each source item by visualizing the percentage of quantity finished vs. remaining. Each bar represents a source item, making it easy to see which source items are fully complete, partially complete, or yet to start. This helps you monitor progress at a glance and prioritize follow-ups for delayed or underperforming orders.

The **Total Actual Cost Breakdown** pie chart divides [Total Actual Cost]() into its sub-components: [Actual Capacity Cost Overhead](), [Actual Material Cost](), [Actual Capacity Cost](), [Actual Subcontracted Cost](), and [Actual Manufacturing Overhead Cost](). This visualization helps manufacturing managers quickly understand where costs are concentrated and supports more informed cost control decisions.

The **Current Production Orders** table lists detailed information for each production order, including the Production Order Number and Status, Source No., Planned Quantity, Finished Quantity, and Starting Date. It provides additional context when interacting with other visuals in the report, helping you drill into specific orders for deeper analysis.

## Use the report

Manufacturing managers and supervisors use this report to monitor the progress, cost, and status of production orders to ensure efficient and balanced operations.

Manufacturing managers rely on this report to track production order completion rates, evaluate actual production costs, and identify potential delays or cost overruns. The Completion Ratios by Source Number chart highlights which orders are progressing as expected and which may require follow-up. The Total Actual Cost Breakdown pie chart provides a clear view of cost distribution, helping managers pinpoint major cost drivers and make informed decisions to control expenses.

Production supervisors use the Number of Production Orders by Status chart to keep track of order volumes across different stages of production, helping them identify workflow bottlenecks. The Current Production Orders table serves as a detailed reference for ongoing orders, allowing supervisors to provide updates to management, verify progress, and support production scheduling.

Cross-highlighting between visuals provides additional context and insight—for example, selecting a specific status or production order dynamically updates the related charts and tables. This interactive capability allows users to drill down into specific areas of interest and better understand how individual orders contribute to overall performance.

Together, these visuals offer a comprehensive snapshot of production health, empowering teams to maintain output targets, control costs, and ensure timely delivery.

## Key Performance Indicators (KPIs)

The *Machine Center Load* report includes the following KPIs and measures:

- [Actual Capacity Cost](manufacturing-powerbi-kpis.md#actual-capacity-cost)
- [Actual Capacity Cost Overhead](manufacturing-powerbi-kpis.md#actual-capacity-overhead-cost)
- [Actual Manufacturing Overhead Cost](manufacturing-powerbi-kpis.md#actual-manufacturing-overhead-cost)
- [Actual Material Cost](manufacturing-powerbi-kpis.md#actual-material-cost)
- [Actual Subcontracted Cost](manufacturing-powerbi-kpis.md#actual-subcontracted-cost)
- [Total Actual Cost](manufacturing-powerbi-kpis.md#total-actual-cost)
- [Total Expected Cost](manufacturing-powerbi-kpis.md#total-expected-cost)
- [Total Standard Cost](manufacturing-powerbi-kpis.md#total-standard-cost)
- [No. of Production Orders](manufacturing-powerbi-kpis.md#no-of-production-orders)
- [Finished %](manufacturing-powerbi-kpis.md#finished-percent)
- [Remaining %](manufacturing-powerbi-kpis.md#remaining-percent)

[!INCLUDE[click-on-a-kpi-link](includes/click-on-a-kpi-link.md)]

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]

## Data used in the report

The report uses data from the following tables in [!INCLUDE[prod_short](includes/prod_short.md)]:

- Production Order Line
- Capacity Ledger Entry
- Item Ledger Entry
- Value Entry
- Inventory Adjustment Entry Order Line
- Production Order
  
## Try the report

Try the report here: [Production Order Overview](https://businesscentral.dynamics.com?page=)<!-- TODO Set page ID for link -->

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](includes/ctrl-right-click-to-open-in-new-tab.md)]

## See also

[Track your business KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md)  
[Power BI Manufacturing app](manufacturing-powerbi-app.md)  
[Built-in production reports](production-reports.md)  
[Manufacturing overview](production-manage-manufacturing.md)
