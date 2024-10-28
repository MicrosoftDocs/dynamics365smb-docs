---
title: Sales Overview (Power BI report)
description: The *Sales Overview* report provides a high-level summary of your organization's sales activities.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: reporting
ms.search.form: 36998_Primary
ms.date: 10/26/2024
ms.service: dynamics-365-business-central
---


# Sales Overview (Power BI Report)

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

The *Sales Overview* report provides a high-level summary of your organization's sales activities, showcasing key metrics such as the number of outstanding sales orders, shipped-but-not-invoiced orders, and posted sales invoices, along with their respective monetary values. 

Additionally, this report give you a quick view of sales amount by salesperson, highlights the top 5 customers by sales amount, and shows the gross profit from the top 5 items.

:::image type="content" source="media/powerbi/sales/sales-overview.png" alt-text="Screenshot of the Sales Overview Power BI report" lightbox="media/powerbi/sales/sales-overview.png":::

## How to use the report

The target audience for the *Sales Overview* report is
- Executives
- Directors
- Other high-level decision makers

As a CEO, you regularly monitor the organization's sales operations to ensure the business is meeting its goals and operating efficiently. To get a quick, high-level overview, you turn to the Power BI Sales Overview Report. 

This report gives you key performance indicators such as the [No. of Outstanding Sales Orders](sales-powerbi-sales-kpis.md#no-of-outstanding-sales-orders), [No. of Shipped Not Invoiced Sales Orders](sales-powerbi-sales-kpis.md#no-of-shipped-not-invoiced-sales), and [No. of Posted Sales Invoices](sales-powerbi-sales-kpis.md#no-of-posted-sales-invoices) along with their associated monetary values. 

:::image type="content" source="media/powerbi/sales/sales-overview-kpis.png" alt-text="Screenshot of the Sales Overview KPIs Power BI report" lightbox="media/powerbi/sales/sales-overview-kpis.png":::


## Key Performance Indicators (KPIs)

The *Sales Overview* report includes the following KPIs and measures: 

- [**Sales Amount**](sales-powerbi-sales-kpis.md#sales-amount)
- [**Outstanding Amount**](sales-powerbi-sales-kpis.md#outstanding-amount)
- [**Shipped Not Invoiced Amount**](sales-powerbi-sales-kpis.md#shipped-not-invoiced-amount)
- [**Invoiced Amount**](sales-powerbi-sales-kpis.md#invoiced-amount)
- [**Gross Profit**](sales-powerbi-sales-kpis.md#gross-profit)
- [**Gross Profit Margin**](sales-powerbi-sales-kpis.md#gross-profit-margin)
- [**No. of New Customers**](sales-powerbi-sales-kpis.md#no-of-new-customers)
- [**No. of Outstanding Sales Orders**](sales-powerbi-sales-kpis.md#no-of-outstanding-sales-orders)
- [**No. of Shipped Not Invoiced Orders**](sales-powerbi-sales-kpis.md#no-of-shipped-not-invoiced-sales)
- [**No. of Posted Sales Invoices**](sales-powerbi-sales-kpis.md#no-of-posted-sales-invoices)

Click on the link for a KPI to learn more about what it means, how it is calculated, and what data was used in the calculations. 

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]


## Data used in the report

The *Sales Overview* report use data from the following tables in [!INCLUDE[prod_short](includes/prod_short.md)]

- Sales Line
- Value Entry
- Customer
- Item
- Location
- Salesperson

## Try the report

Try the report here: [Sales Overview](https://businesscentral.dynamics.com?page=36998)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](includes/ctrl-right-click-to-open-in-new-tab.md)]

## See also

[Track your business KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md)   
[Ad-hoc analysis of sales data](ad-hoc-analysis-sales.md)   
[Built-in sales reports](sales-reports.md)   
[Sales analytics overview](sales-analytics-overview.md)  
[Sales overview](sales-manage-sales.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
