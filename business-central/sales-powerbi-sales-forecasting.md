---
title: Sales Forecasting (Power BI Report)
description: The Sales Forecasting report provides insights into your organization's sales trends and future sales performance.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: reporting
ms.search.form: 37109_Primary
ms.date: 9/30/2025
ms.service: dynamics-365-business-central
---

# Sales Forecasting (Power BI Report)

[!INCLUDE[2025_releasewave2](includes/2025_releasewave2.md)]

The **Sales Forecasting** report predicts future sales trends based on historical data. It uses advanced forecasting techniques to project sales values across customer, document type, item and salesperson dimensions, helping users anticipate demand and future profits.

The sales forecasting visualization predicts the next three months of purchases based on the previous six months, assuming a monthly seasonality.

> [!NOTE]
> The default forecasting options can be customized through the Forecast section of the Analytics Pane in Power BI Desktop. This includes modifying the forecast length, seasonality, period and confidence interval.

:::image type="content" source="media/powerbi/sales/sales-forecasting.png" alt-text="Screenshot of the Sales Forecasting Power BI report" lightbox="media/powerbi/sales/sales-forecasting.png":::

## Use the report

Leadership, sales managers and salespeople can use this report to anticipate stock requirements and predicted sales performance for the organization.

CEOs need to anticipate sales trends to implement strategies based on forecasted sales metrics and predicted financial impacts. For example, you identify that sales are predicted to decrease in a future month. Using this knowledge, you invest in marketing strategies to drive future sales and maintain consistent income.

Sales managers need to monitor projected sales to anticipate product demand and manage workload of their salespeople. Using the sales by item visual, you foresee higher demand for an item in the upcoming months. In response, you communicate with the purchasing team to plan sufficient inventory availability for that item and avoid stockouts. Additionally,  the sales by salesperson visual might highlight a salesperson who is predicted to be over-utilized in the next week. Using this information, you redistribute workload accordingly to available salespeople, improving wellbeing and productivity.

Salespeople want to track customer sales patterns to effectively manage customer relations.
For example, using the sales by customer visual you identify a customer is projected to increase sales in a future month. In response, you proactively engage with the customer to encourage sales and maintain an effective customer relationship.

## Key Performance Indicators (KPIs)

The *Sales Forecasting* report includes the following KPIs and measures:

- [**Sales (LCY)**](sales-powerbi-sales-kpis.md#sales-lcy)
- [**Sales (LCY) Forecasting**](sales-powerbi-sales-kpis.md#sales-lcy-forecasting)

[!INCLUDE[click-on-a-kpi-link](includes/click-on-a-kpi-link.md)]

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]

## Data used in the report

The report uses data from the following tables in [!INCLUDE[prod_short](includes/prod_short.md)]:

- Sales Value Entries
- Sales Invoice Lines
- Sales Credit Lines
- Project Ledger Entries
- Salesperson/Purchaser
- Item
- Customer

## Try the report

Try the report here: [Sales Forecasting](https://businesscentral.dynamics.com?page=37109)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Track your business KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md)  
[Ad-hoc analysis of sales data](ad-hoc-analysis-sales.md)  
[Built-in sales reports](sales-reports.md)  
[Sales analytics overview](sales-analytics-overview.md)  
[Sales overview](sales-manage-sales.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
