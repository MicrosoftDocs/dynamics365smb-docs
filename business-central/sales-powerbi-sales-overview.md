---
title: Sales Overview (Power BI report)
description: The Sales Overview report provides a high-level summary of your organization's sales activities.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: 36998_Primary
ms.date: 10/07/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---


# Sales Overview (Power BI Report)

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

The **Sales Overview** report provides a high-level summary of your organization's sales activities. The report showcases key performance metrics (KPIs), such as:

- The number of outstanding sales orders
- Shipped-but-not-invoiced orders
- Posted sales invoices

It shows the monetary values for each KPI.

This report also gives a quick view of sales amounts by salesperson, highlights the top five customers by sales amount, and shows the gross profit from the top five items.

:::image type="content" source="media/powerbi/sales/sales-overview.png" alt-text="Screenshot of the Sales Overview Power BI report" lightbox="media/powerbi/sales/sales-overview.png":::

## Use the report

The report is intended for the following roles:

- Executives
- Directors
- Other high-level decision makers

CEOs regularly monitor the organization's sales operations to ensure the business is meeting its goals and operating efficiently. To get a quick, high-level overview, you turn to the Power BI Sales Overview Report to review:

- [Number of Outstanding Sales Orders](sales-powerbi-sales-kpis.md#no-of-outstanding-sales-orders)
- [Number of Shipped Not Invoiced Sales Orders](sales-powerbi-sales-kpis.md#no-of-shipped-not-invoiced-sales-orders)
- [Number of Posted Sales Invoices](sales-powerbi-sales-kpis.md#no-of-posted-sales-invoices)

It shows the monetary values for each KPI.

:::image type="content" source="media/powerbi/sales/sales-overview-kpis.png" alt-text="Screenshot of the Sales Overview KPIs Power BI report" lightbox="media/powerbi/sales/sales-overview-kpis.png":::

## Key performance indicators

The report includes the following KPIs and measures:

- [Sales (LCY)](sales-powerbi-sales-kpis.md#sales-lcy)
- [Adjusted Cost (LCY)](sales-powerbi-sales-kpis.md#adjusted-cost-lcy)
- [Adjusted Profit (LCY)](sales-powerbi-sales-kpis.md#adjusted-profit-lcy)
- [Adjusted Profit Margin](sales-powerbi-sales-kpis.md#adjusted-profit-margin)
- [Outstanding Invoices (LCY)](sales-powerbi-sales-kpis.md#outstanding-invoices-lcy)
- [No. of Outstanding Sales Orders](sales-powerbi-sales-kpis.md#no-of-outstanding-sales-orders)
- [No. of Shipped Not Invoiced Orders](sales-powerbi-sales-kpis.md#no-of-shipped-not-invoiced-sales-orders)
- [Outstanding Orders (LCY)](sales-powerbi-sales-kpis.md#outstanding-orders-lcy)
- [Shipped Not Invoiced (LCY)](sales-powerbi-sales-kpis.md#shipped-not-invoiced-lcy)
- [No. of Outstanding Invoices](sales-powerbi-sales-kpis.md#no-of-outstanding-invoices)

[!INCLUDE[click-on-a-kpi-link](includes/click-on-a-kpi-link.md)]

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]

## Data used in the report

The report uses data from the following tables:

- Sales Line
- Value Entry
- Sales Invoice Lines
- Sales Credit Lines
- Project Ledger Entries
- Item
- Salesperson
- Customer

## Try the report

Try the report here: [Sales Overview](https://businesscentral.dynamics.com?page=36998)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Track your business KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md)  
[Ad hoc analysis of sales data](ad-hoc-analysis-sales.md)  
[Built-in sales reports](sales-reports.md)  
[Sales analytics overview](sales-analytics-overview.md)  
[Sales overview](sales-manage-sales.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
