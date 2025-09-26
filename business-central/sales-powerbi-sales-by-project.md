---
title: Sales by Project (Power BI Report)
description: The Sales by Project report provides an overview of sales performance broken down by project.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: reporting
ms.search.form: 37119_Primary 
ms.date: 9/30/2025
ms.service: dynamics-365-business-central
---

# Sales by Project (Power BI Report)

[!INCLUDE[2025_releasewave2](includes/2025_releasewave2.md)]

The **Sales by Project** report provides a high-level overview of sales performance for each project. It showcases key metrics such as total sales amount and quantity for each project and customer. These metrics can be analyzed further through the type dimension, encompassing resources, items, and general ledger accounts.

:::image type="content" source="media/powerbi/sales/sales-by-project.png" alt-text="Screenshot of the Sales by Project Power BI report" lightbox="media/powerbi/sales/sales-by-project.png":::

## Use the report

This report helps sales and project management teams to track the sales amounts that each project generates and their contribution to the overall revenue.

Project managers can track the sales impact of projects across key factors, including status, type and customer. By reviewing the project sales by type or by customer, this report provides a high-level overview of project sales performance. These metrics can be used to optimize planning and sales expectations for future project proposals. For more detailed analysis of the underlying project ledger entries, the cross-report drillthrough can be used to navigate to the dedicated 
[Power BI Projects app](projects-powerbi-app.md).

> [!NOTE]
> To enable cross-report drillthrough, ensure the source and target reports are published to the same workspace. Also note, the back button will only work for navigation between pages within the same report.

Sales managers can use this report to analyze ongoing and completed projects and identify key projects. Using the report, you may notice an emerging trend in recent projects contributing to increased sales. In response, you conduct dedicated training to implement new sales strategies to include project offerings, enhancing sales pitches to customers.

Salespeople can monitor the contribution of projects to sales performance and review project sales for individual customers. For example, you identify a recently completed project was highly profitable. Using this information, you initiate new opportunities and engage with customers in similar demographics to empower future sales.

## Key performance indicators

The report includes the following key performance indicators (KPIs) and measures:

- [**Sales LCY**](sales-powerbi-sales-kpis.md#sales-lcy)
- [**Sales Quantity**](sales-powerbi-sales-kpis.md#sales-quantity)
- [**Adjusted Profit (LCY)**](sales-powerbi-sales-kpis.md#adjusted-profit-lcy)
- [**Adjusted Profit Margin**](sales-powerbi-sales-kpis.md#adjusted-profit-margin)

[!INCLUDE[click-on-a-kpi-link](includes/click-on-a-kpi-link.md)] 

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]

## Data used in the report

The report uses data from the following tables in [!INCLUDE[prod_short](includes/prod_short.md)]:

- Value Entries
- Sales Invoice Lines
- Sales Credit Lines
- Project Ledger Entries
- Customer
- Project
- Item
- G/L Account
- Resource

## Try the report

Try the report here: [Sales by Project](https://businesscentral.dynamics.com?page=37119)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Track your business KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md)  
[Ad hoc analysis of sales data](ad-hoc-analysis-sales.md)  
[Built-in sales reports](sales-reports.md)  
[Sales analytics overview](sales-analytics-overview.md)  
[Sales overview](sales-manage-sales.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
