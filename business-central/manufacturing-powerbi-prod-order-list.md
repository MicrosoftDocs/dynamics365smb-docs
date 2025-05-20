---
title: Prod.Order List
description: The Prod. Order List report 
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

# Prod. Order List (Power BI Report)

[!INCLUDE[applies-to-2025w1](includes/applies-to-2025w1.md)]

The **Prod. Order List** page organizes all production orders and offers a mix of high-level summaries, categorical insights, and detailed records. It helps you efficiently evaluate key metrics, including costs and order counts, while enabling deeper exploration of specific details like statuses, source items, and document-level dates. Additionally, this page allows you to track planned versus finished output and analyze variances across production orders for better decision-making.

:::image type="content" source="media/manufacturing/prod-order-list-v26.png" alt-text="Screenshot of the Prod Order List Power BI Report" lightbox="media/manufacturing/prod-order-list-v26.png":::

The **Total Actual Cost** KPI card presents key performance indicators (KPIs) related to cost analysis. The primary KPI displayed is the *Actual Total Cost*, serving as the central metric for monitoring actual manufacturing costs. Below this metric, comparative measures like *Total Expected Cost* and *Total Standard Cost* are provided, offering context for evaluating cost performance. Additionally, variance percentages are displayed beneath these measures, highlighting the deviations relative to the *Actual Total Cost*.

The **No. of Production Orders by Status** bar chart represents the distribution of production orders based on their statuses. It uses the measure 'No. of Production Orders' to calculate the distinct count of production orders, while the production order status field acts as the dimension, classifying orders into categories such as "Released," "Planned," and "Finished."

The **No. of Production Orders by Source Item** bar chart displays the distribution of production orders based on their originating source items. It uses the measure 'No. of Production Orders' to calculate the distinct count of production orders, while the Source No. field serves as the dimension, classifying orders by their respective source items.

The **Prod. Order List Details** table serves as the final visual on the page, offering document-level details for each production order. Key fields included are the status, production order no., source no., routing no., starting, ending, and due dates, planned quantity, finished quantity, and variance quantity. When used in conjunction with the bar charts, this table provides deeper context, allowing users to analyze the highlighted dimensions in greater detail and gain a more comprehensive understanding of the data.

## Use the report

Manufacturing managers use the **Prod. Order List** page to monitor key metrics and ensure efficient production operations. The **Total Actual Cost** KPI card helps them analyze manufacturing costs by comparing *Actual Total Cost* with *Total Expected Cost* and *Total Standard Cost*, while the variance percentages highlight any significant deviations. The **No. of Production Orders by Status** and **No. of Production Orders by Source Item** bar charts enable managers to quickly assess production progress and resource allocation. By analyzing these visuals together with the **Prod. Order List Details** table, managers can evaluate planned versus finished output, identify variances, and make data-driven decisions to address issues like cost overruns or production delays.

Production supervisors rely on the **Prod. Order List** page to manage day-to-day operations and keep production on schedule. The **No. of Production Orders by Status** bar chart helps supervisors monitor the distribution of orders across different stages, enabling them to spot bottlenecks or delays. The **Prod. Order List Details** table provides document-level details, such as planned and finished quantities, starting and due dates, and routing information, allowing supervisors to track specific orders closely. Using the **No. of Production Orders by Source Item** bar chart, supervisors can assess how production orders are distributed across source items, facilitating better resource planning. Together, these insights support more effective coordination and progress updates for smooth production workflows.

## Key Performance Indicators (KPIs)

The *Prod. Order List* report includes the following KPIs and measures:

- [Actual Total Cost](manufacturing-powerbi-kpis.md#total-actual-cost)
- [Expected Total Cost](manufacturing-powerbi-kpis.md#total-expected-cost)
- [Standard Total Cost](manufacturing-powerbi-kpis.md#total-standard-cost)
- [Total Expected Cost Dev %](manufacturing-powerbi-kpis.md#total-expected-cost-dev-percent)
- [Total Standard Cost Dev %](manufacturing-powerbi-kpis.md#total-standard-cost-dev-percent)
- [No. of Production Orders](manufacturing-powerbi-kpis.md#no-of-production-orders)
- [Planned Quantity](manufacturing-powerbi-kpis.md#planned-quantity)
- [Finished Quantity](manufacturing-powerbi-kpis.md#finished-quantity)
- [Variance Quantity](manufacturing-powerbi-kpis.md#variance-quantity)

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
