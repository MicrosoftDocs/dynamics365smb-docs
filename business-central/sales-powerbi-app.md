---
title: Sales Power BI app
description: The Power BI app for Sales in Business Central provides comprehensive sales analytics to stakeholders at all levels of your organization.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: reporting
ms.search.form: 36998, 36999, 37000, 37001, 37002, 37003, 37004, 37005, 37006, 37007, 37008
ms.date: 10/26/2024
ms.service: dynamics-365-business-central
---

# Sales Power BI app

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

The reports in the Power BI sales app provide comprehensive sales analytics to stakeholders at all levels of your organization. 

Executives and the leadership team can use the [Sales Overview](sales-powerbi-sales-overview.md), [Period-Over-Period Growth](sales-powerbi-period-over-period-growth.md), and [Month-To-Date](sales-powerbi-month-to-date.md) reports to identify trends in sales performance.

Managers and team leaders can track individual sales team performance using the  [Sales by Salesperson](sales-powerbi-sales-by-salesperson.md) report. They can also monitor overall team progress toward meeting sales goals by comparing actual results against targets in the [Actual vs. Budget](sales-powerbi-actual-vs-budget.md)  report.

Sales teams and other operational staff can use aggregated reports, like the [Sales by Item](sales-powerbi-sales-by-item.md) and [Sales by Customer](sales-powerbi-sales-by-customer.md) reports, to understand which items sells best and which customers are generating the most revenue. By drilling down from these aggregated views, users can seamlessly dive deep into transaction-level data for even more detailed analysis.

The different reports in the sales Power BI app can be used for different things depending on your role. Below, you can read some examples of use cases for different roles in your organization. 


## Sales analytics for the leadership team

For the leadership team, the purpose of using this app is to gain a high-level overview of your organization's sales trends and financial health. The app helps leaders identify spending patterns, monitor budget adherence, and make strategic decisions to improve financial performance. It provides a clear picture of sales efficiency and highlights areas for potential cost reduction.

To fit this category, you might have a role such as 
- Executive
- Director
- Other high-level decision maker

### Example scenario: preparing for an upcoming board meeting #### 
As a user, imagine you are the CEO of a company, you are preparing for an upcoming board meeting. You need to present an analysis of your company's sales performance for the current fiscal year. To better understand the company's current position, you can use the Power BI Sales report.

You first begin by reviewing the [Period-Over-Period Growth](sales-powerbi-period-over-period-growth.md) report which provides a quick comparitive view of the current year versus the previous year. You see that sales are up by 35%, outlined by the [Period-over-Period Growth %](sales-powerbi-sales-kpi.md#period-over-period-growth) metric. 

:::image type="content" source="media/powerbi/sales/sales-period-over-period-fiscal-year.png" alt-text="Screenshot of the Sales Period-Over-Period Power BI report" lightbox="media/powerbi/sales/sales-period-over-period-fiscal-year.png":::

Next, you review the [Sales by Customer](sales-powerbi-sales-by-customer.md) report, to see which group of customers contributed most to sales. by analyzing the Sales by Customer matrix, you can see that domestic customers outperformed foreign customers by contributing 56.59% to the total annual sales. 

:::image type="content" source="media/powerbi/sales/sales-by-customer-matrix.png" alt-text="Screenshot of the Sales by Customer matrix" lightbox="media/powerbi/sales/sales-by-customer-matrix.png":::


Finally, you review the [Moving Averages](sales-powerbi-moving-average.md) report, which visualizes [Sales Amount](sales-powerbi-sales-kpis.md#sales-amount) and [Sales Amount Average 30D](sales-powerbi-sales-kpis.md#sales-amount-avg-30d-fiscal). The 30 day average smoothes out the sales trend for the year and provides more good news for the company. This report reveals that on average, sales were stable through the first half of the year and then increased through the second half of the year. 

:::image type="content" source="media/powerbi/sales/30-Day-Moving-Average.png" alt-text="Screenshot from the Moving Average Power BI report" lightbox="media/powerbi/sales/30-Day-Moving-Average.png":::

With the insights gained from this report, you can confidently present your organization's sales performance to the board, armed with data-driven analysis and a deeper understanding of your company's current position.


## Sales analytics for the management team

For the sales management team, the goal is to oversee and manage the sales processes effectively. This app allows you to track 

To fit this category, you might have a job title such as 
- Sales Manager
- Sales Team Leader


### Example scenario: driving sales over the next two quarters #### 

As a Sales Manager, you are tasked with driving sales over the next two quarters. You turn to the Power BI Sales app to understand the sales team's current standing. 

You begin by reviewing the [Sales by Salesperson](sales-powerbi-sales-by-salesperson.md) report to evaluate individual team performance. You quickly identify Jim Olive as the top performer, generating 83% of the total sales for the year. Using the report, you also see that Helena Ray has been the most profitable salesperson on the team but only by a small margin. 

:::image type="content" source="media/powerbi/sales/sales-by-salesperson-matrix.png" alt-text="Screenshot of the Sales by Salesperson matrix" lightbox="media/powerbi/sales/sales-by-salesperson-matrix.png":::

You know that without clear targets Lina and Helena won't reach their maximum potential. By establishing a new sales budget with revised targets for each salesperson, you can provide your team with the tools they need to progress. Using the [Actual vs. Budget](sales-powerbi-actual-vs-budget.md) report, you monitor progress to ensure the team is on track to meet their new goals.

Using the [Daily Sales](sales-powerbi-daily-sales.md) report, you can monitor the team's progress over the next two quarters. You can use the heat map to guage which day of the week the team performs best and when the company should roll out marketing incentives to help drive customer engagement.

:::image type="content" source="media/powerbi/sales/sales-daily-sales-heat-map.png" alt-text="Screenshot of the heatmap in the Daily Sales Power BI report" lightbox="media/powerbi/sales/sales-daily-sales-heat-map.png":::


## Sales analytics for daily sales work

For people working with sales on a daily basis, the focus is on handling day-to-day sales tasks with greater accuracy and efficiency. TODO

To fit this category, you might have a job title such as 
- Account Manager
- Sales Person


### Example scenario: using data to drive day-to-day sales #### 

After receiving new sales targets from the Sales Manager, the sales team is eager to improve their performance and meet these revised goals. To strategize effectively, as a salesperson, you turn to the Power BI Sales app for insights into the company's sales patterns. 

You begin by analyzing the [Sales by Item](sales-powerbi-sales-by-item.md) and [Sales by Customer](sales-powerbi-sales-by-customer.md) reports to identify high-potential products and key customers. These aggregated reports provide a clear view of where opportunities lie, allowing you to focus your efforts on customers and items most likely to generate growth and help your team achieve the targets. 

:::image type="content" source="media/powerbi/sales/sales-by-customer-matrix-2.png" alt-text="Screenshot of the Sales by Customer matrix version 2" lightbox="media/powerbi/sales/sales-by-customer-matrix-2.png":::

The [Sales by Item](sales-powerbi-sales-by-item.md) report highlights product performance by clearly identifying which items generate the most revenue and conversely which items have experienced a decline in sales. Targeting key products will allow you and your team to prioritize your efforts on highly profitable items and those with growing demand. 

:::image type="content" source="media/powerbi/sales/sales-by-item-matrix.png" alt-text="Screenshot of the Sales by Item matrix" lightbox="media/powerbi/sales/sales-by-item-matrix.png":::


## Report overview in the Power BI sales app

The following table describes the different Power BI reports in the sales app and how you can use them.

| To... | Open in Business Central (CTRL+select) | Learn more |
| ----- | -------------------------------------- | ---------- | 
| Analyze high level information on sales activities. Identify sales figures relating to quantity or amounts from both posted and unposted documents.| [Sales Overview]( https://businesscentral.dynamics.com?page=36998) | [About Sales Overview](sales-powerbi-sales-overview.md) |
| Analyze sales by week day over different periods. The heatmaps highlights which days have the most sales helping you identify patterns in your sales.|[Daily Sales]( https://businesscentral.dynamics.com?page=36999)| [About Daily Sales](sales-powerbi-daily-sales.md) |
| Analyze sales trends by smoothing out spikes and drops in Sales using the 30 Day Moving Averages report. | [Moving Average]( https://businesscentral.dynamics.com?page=37000) | [About Moving Average](sales-powerbi-moving-average.md) |
| Analyze the aggregated sales over a rolling 12-month period. Use this as an alternative to a Year-to-Date report. |[Moving Annual Total]( https://businesscentral.dynamics.com?page=37001) | [About Moving Annual Total](sales-powerbi-moving-annual-total.md) |
| Compare sales in one period with the same period in a prior year, quarter, or month. |[Period-Over-Period Growth]( https://businesscentral.dynamics.com?page=37002) | [About Period-Over-Period Growth](sales-powerbi-period-over-period-growth.md) |
| Analyze accumulating sales for a desired period. | [Month-To-Date]( https://businesscentral.dynamics.com?page=37003) | [About Month-To-Date](sales-powerbi-month-to-date.md)|
| Analyze sales by item and view key sales metrics as a percentage of total sales. | [Sales by Item]( https://businesscentral.dynamics.com?page=37004) | [About Sales by Item](sales-powerbi-sales-by-item.md) |
| Analyze sales by customer and view key metrics like Sales Amount, Sales Quantity, Cost Amount, Gross Profit, Gross Profit Margin and Sales Amount as a percent of total sales.  | [Sales by Customer]( https://businesscentral.dynamics.com?page=37005)  | [About Sales by Customer](sales-powerbi-sales-by-customer.md) |
| Analyze sales by salesperson and view key metrics like Sales Amount, Sales Quantity, Cost Amount, Gross Profit, Gross Profit Margin and Sales Amount as a percent of total sales.  | [Sales by Salesperson]( https://businesscentral.dynamics.com?page=37006) | [About Sales by Salesperson](sales-powerbi-sales-by-salesperson.md) |
| Analyze sales by location and view key metrics like Sales Amount, Sales Quantity, Cost Amount, Gross Profit, Gross Profit Margin and Sales Amount as a percent of total sales.  | [Sales by Location]( https://businesscentral.dynamics.com?page=ID)  | [About Sales by Location](sales-powerbi-sales-by-location.md)  |
| Analyze item sales budgets against actual sales. View target variances for both sales amounts and sales quantity. | [Actual vs. Budget]( https://businesscentral.dynamics.com?page=37008) | [About Actual vs. Budget](sales-powerbi-actual-vs-budget.md) | 


[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]

## TODO

Placeholder section until we find the direct links

## See also

[Track your business KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md)   
[Ad-hoc analysis of sales data](ad-hoc-analysis-sales.md)   
[Built-in sales reports](sales-reports.md)   
[Sales analytics overview](sales-analytics-overview.md)  
[Sales overview](sales-manage-sales.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
