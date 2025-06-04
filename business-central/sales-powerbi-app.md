---
title: Power BI Sales app
description: The Power BI Sales app provides comprehensive sales analytics to stakeholders at all levels of your organization.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: reporting
ms.search.form: 36998, 36999, 37000, 37001, 37002, 37003, 37004, 37005, 37006, 37007, 37008
ms.date: 10/26/2024
ms.service: dynamics-365-business-central
---

# Power BI Sales app

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

The reports in the Power BI Sales app provide comprehensive sales analytics to stakeholders at all levels of your organization.

Executives and the leadership team can use the [Sales Overview](sales-powerbi-sales-overview.md), [Period-Over-Period Growth](sales-powerbi-period-over-period-growth.md), and [Month-To-Date](sales-powerbi-month-to-date.md) reports to identify trends in sales performance.

Managers and team leaders can track individual sales team performance using the [Sales by Salesperson](sales-powerbi-sales-by-salesperson.md) report. They can also monitor overall team progress toward meeting sales goals by comparing actual results against targets in the [Actual vs. Budget](sales-powerbi-actual-vs-budget.md)  report.

Sales teams can use aggregated reports, such as the [Sales by Item](sales-powerbi-sales-by-item.md) and [Sales by Customer](sales-powerbi-sales-by-customer.md) reports, to identify top-selling items and the customers that generate the most revenue. You can drill down from these aggregated views into transaction-level data for more detailed analyses.

You can use the reports in the Power BI Sales app for different things, depending on your role. This article provides some examples of use cases for different roles in your organization.

## Sales analytics for the leadership team

The leadership team can use the app to gain a high-level overview of the organization's sales trends and financial health. The app helps leaders identify spending patterns, monitor budget adherence, and make strategic decisions to improve financial performance. It provides a clear picture of sales efficiency and highlights areas for potential cost reduction.

To fit this category, you might have a role such as:

- Executive
- Director
- Other high-level decision maker

### Example scenario: preparing for an upcoming board meeting

Imagine you're the CEO of a company, and you're preparing for an upcoming board meeting. You need to present an analysis of your company's sales performance for the current fiscal year. To better understand the company's current position, you can use the Power BI Sales app.

Start by reviewing the [Period-Over-Period Growth](sales-powerbi-period-over-period-growth.md) report, which provides a quick, comparative view of the current year versus the previous year. Sales are up by 35%, outlined by the [Sales Amount MATG % (Fiscal)](sales-powerbi-sales-kpis.md#sales-amount-matg--fiscal) metric shown in the following image.

:::image type="content" source="media/powerbi/sales/sales-period-over-period-fiscal-year.png" alt-text="Screenshot of the Sales Period-Over-Period Power BI report" lightbox="media/powerbi/sales/sales-period-over-period-fiscal-year.png":::

Next, you review the [Sales by Customer](sales-powerbi-sales-by-customer.md) report to identify which group of customers contributed most to sales. The **Sales by Customer** matrix shows that domestic customers outperformed foreign customers by contributing 56.59% to the total annual sales, as the following image shows.

:::image type="content" source="media/powerbi/sales/sales-by-customer-matrix.png" alt-text="Screenshot of the Sales by Customer matrix" lightbox="media/powerbi/sales/sales-by-customer-matrix.png":::

Finally, you review the [Moving Averages](sales-powerbi-moving-average.md) report, which visualizes [Sales Amount](sales-powerbi-sales-kpis.md#sales-amount) and [Sales Amount Average 30D](sales-powerbi-sales-kpis.md#sales-amount-avg-30d-fiscal). The 30 day average smooths out the sales trend for the year and provides more good news for the company. On average, sales were stable through the first half of the year and then increased through the second half of the year.

:::image type="content" source="media/powerbi/sales/30-Day-Moving-Average.png" alt-text="Screenshot from the Moving Average Power BI report" lightbox="media/powerbi/sales/30-Day-Moving-Average.png":::

The insights you gained from this report let you confidently present your organization's sales performance to the board, armed with data-driven analysis and a deeper understanding of your company's current position.

## Sales analytics for the management team

The goal of the sales management team is to effectively oversee and manage sales processes. <!--This app allows you to track -->

To fit this category, your job title might be:

- Sales Manager
- Sales Team Leader

### Example scenario: driving sales over the next two quarters

As a Sales Manager, you're tasked with driving sales over the next two quarters. You turn to the Power BI Sales app to understand the sales team's current standing.

Start by reviewing the [Sales by Salesperson](sales-powerbi-sales-by-salesperson.md) report to evaluate individual team performance. You quickly identify Jim Olive as the top performer, generating 83% of the total sales for the year. You also see that Helena Ray was the most profitable salesperson on the team, but only by a small margin.

:::image type="content" source="media/powerbi/sales/sales-by-salesperson-matrix.png" alt-text="Screenshot of the Sales by Salesperson matrix" lightbox="media/powerbi/sales/sales-by-salesperson-matrix.png":::

You know that clear targets help Lina and Helena reach their maximum potential. By establishing a new sales budget with revised targets for each salesperson, you can provide your team with the tools they need to progress. Using the [Actual vs. Budget](sales-powerbi-actual-vs-budget.md) report, you monitor progress to ensure the team is on track to meet their new goals.

The [Daily Sales](sales-powerbi-daily-sales.md) report lets you monitor the team's progress over the next two quarters. You can use the heat map to gauge which day of the week the team performs best, and when the company should roll out marketing incentives to help drive customer engagement.

:::image type="content" source="media/powerbi/sales/sales-daily-sales-heat-map.png" alt-text="Screenshot of the heatmap in the Daily Sales Power BI report" lightbox="media/powerbi/sales/sales-daily-sales-heat-map.png":::

## Sales analytics for daily sales work

People who work with sales on a daily basis often focus on handling day-to-day sales tasks with greater accuracy and efficiency.

To fit this category, you might have a job title such as:

- Account Manager
- Sales Person

### Example scenario: using data to drive day-to-day sales

After the sales team receives the new sales targets from the sales manager, they're eager to improve their performance and meet the revised goals. To shape an effective strategy as a salesperson, you turn to the Power BI Sales app for insights into the company's sales patterns.

Start by analyzing the [Sales by Item](sales-powerbi-sales-by-item.md) and [Sales by Customer](sales-powerbi-sales-by-customer.md) reports to identify high-potential products and key customers. These aggregated reports provide a clear view of where opportunities lie. That information helps you focus on the customers and items most likely to generate growth and help your team achieve their targets.

:::image type="content" source="media/powerbi/sales/sales-by-customer-matrix-2.png" alt-text="Screenshot of the Sales by Customer matrix version 2" lightbox="media/powerbi/sales/sales-by-customer-matrix-2.png":::

The [Sales by Item](sales-powerbi-sales-by-item.md) report highlights product performance by clearly identifying which items generate the most revenue and, conversely, which items experienced a decline in sales. Targeting key products lets you and your team prioritize your efforts on highly profitable items and items with growing demand.

:::image type="content" source="media/powerbi/sales/sales-by-item-matrix.png" alt-text="Screenshot of the Sales by Item matrix" lightbox="media/powerbi/sales/sales-by-item-matrix.png":::

## Report overview in the Power BI Sales app

[!INCLUDE [power-bi-sales-app](includes/power-bi-sales-app.md)]


## Related information

[Installing Power BI apps for Business Central](across-powerbi-install-business-central-apps.md)   
[Track your business KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md)  
[Ad hoc analysis of sales data](ad-hoc-analysis-sales.md)  
[Built-in sales reports](sales-reports.md)  
[Sales analytics overview](sales-analytics-overview.md)  
[Sales overview](sales-manage-sales.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
