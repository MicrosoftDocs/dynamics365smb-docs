---
title: Prod. Order List
description: Learn about how to benefit from using the Prod. Order List report.
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

# Prod. Order List (Power BI Report)

[!INCLUDE[applies-to-2025w1](includes/applies-to-2025w1.md)]

The **Prod. Order List** report organizes production orders and offers a mix of high-level summaries, categorical insights, and access to detailed records. It helps you efficiently evaluate key metrics, including costs and order counts, while enabling deeper exploration of specific details. For example, statuses, source items, and document-level dates. This report also lets you track planned versus finished output and analyze variances across production orders.

:::image type="content" source="media/manufacturing/prod-order-list-v26.png" alt-text="Screenshot of the Prod Order List Power BI Report" lightbox="media/manufacturing/prod-order-list-v26.png":::

The **Total Actual Cost** key performance indicator (KPI) card presents KPIs related to cost analysis. The primary KPI is the **Actual Total Cost**, serving as the central metric for monitoring actual manufacturing costs. Below this metric, comparative measures such as **Total Expected Cost** and **Total Standard Cost** are provided, offering context for evaluating cost performance. Additionally, variance percentages display for these measures, highlighting the deviations relative to the actual total cost.

The **No. of Production Orders by Status** chart shows the distribution of production orders based on their statuses. The chart uses the **No. of Production Orders** measure to calculate the distinct count of production orders, while the production order **Status** field acts as the dimension to classify orders into categories such as **Released**, **Planned**, and **Finished**.

The **No. of Production Orders by Source Item** chart displays the distribution of production orders based on their originating source items. It uses the **No. of Production Orders** measure to calculate the distinct count of production orders, while the **Source No.** field serves as the dimension to classify orders by their source items.

The **Prod. Order List Details** table serves as the final visual on the page, offering document-level details for each production order. The key fields in the table are:

- Status
- Production Order No.
- Source No.
- Routing No.
- Starting, ending, and due dates
- Planned Quantity
- Finished Quantity
- Variance quantity

When used in conjunction with the bar charts, this table provides deeper context and lets you analyze the highlighted dimensions in greater detail and gain a more comprehensive understanding of the data.

## Use the report

Manufacturing Managers use the **Prod. Order List** report to monitor key metrics and ensure efficient production operations. The **Total Actual Cost** KPI card helps you analyze manufacturing costs by comparing **Actual Total Cost** with **Total Expected Cost** and **Total Standard Cost**. The variance percentages highlight any significant deviations. The **No. of Production Orders by Status** and **No. of Production Orders by Source Item** charts let you quickly assess production progress and resource allocation. By analyzing these visuals together with the **Prod. Order List Details** table, you can evaluate planned versus finished output, identify variances, and make data-driven decisions to address issues like cost overruns or production delays.

Production supervisors rely on the **Prod. Order List** report to manage day-to-day operations and keep production on schedule. The **No. of Production Orders by Status** chart helps you monitor the distribution of orders across different stages, enabling you to spot bottlenecks or delays. The **Prod. Order List Details** table provides document-level details, such as planned and finished quantities, starting and due dates, and routing information, allowing you to track specific orders closely. Using the **No. of Production Orders by Source Item** chart, you can assess how production orders are distributed across source items, facilitating better resource planning. Together, these insights support more effective coordination and progress updates for smooth production workflows.

## Key performance indicators (KPIs)

The Prod. Order List report includes the following KPIs and measures:

- [**Total Actual Cost**](manufacturing-powerbi-kpis.md#total-actual-cost)
- [**Total Expected Cost**](manufacturing-powerbi-kpis.md#total-expected-cost)
- [**Total Standard Cost**](manufacturing-powerbi-kpis.md#total-standard-cost)
- [**Total Expected Cost Dev %**](manufacturing-powerbi-kpis.md#total-expected-cost-dev-percent)
- [**Total Standard Cost Dev %**](manufacturing-powerbi-kpis.md#total-standard-cost-dev-percent)
- [**No. of Production Orders**](manufacturing-powerbi-kpis.md#no-of-production-orders)
- [**Planned Quantity**](manufacturing-powerbi-kpis.md#planned-quantity)
- [**Finished Quantity**](manufacturing-powerbi-kpis.md#finished-quantity)
- [**Variance Quantity**](manufacturing-powerbi-kpis.md#variance-quantity)

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

## Related information

[Track your business KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md)  
[Power BI Manufacturing app](manufacturing-powerbi-app.md)  
[Built-in production reports](production-reports.md)  
[Manufacturing overview](production-manage-manufacturing.md)
