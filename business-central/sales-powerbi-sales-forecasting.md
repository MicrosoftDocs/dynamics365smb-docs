---
title: Sales Forecasting Power BI Report
description: Explore a sales forecast based on historical sales in the Power BI Sales app, alongside breakdowns by customer, document type, item, and salesperson.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: 37109_Primary
ms.date: 11/12/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template
ai-usage: ai-assisted
---

# Sales forecasting (Power BI report)

[!INCLUDE[2025_releasewave2](includes/2025_releasewave2.md)]

The **Sales Forecasting** report predicts future sales trends based on historical data. It combines an overall sales forecast with historical sales breakdowns by customer, document type, item, and salesperson to help you anticipate demand.

The sales forecasting visualization predicts the next three months of sales based on the previous six fiscal months, using a seasonality setting of 30 data points and a 95% confidence interval.

> [!NOTE]
> You can customize forecasting options in the **Forecast** section of the **Analytics** pane in Power BI Desktop. For example, you can modify the forecast length and confidence interval.

:::image type="content" source="media/powerbi/sales/sales-forecasting.png" alt-text="Screenshot of the Sales Forecasting Power BI report" lightbox="media/powerbi/sales/sales-forecasting.png":::

## Use the report

Leadership, sales managers, and salespeople can use this report to anticipate stock requirements and predicted sales performance for the organization.

CEOs need to anticipate sales trends to implement strategies based on forecasted sales metrics and predicted financial impacts. For example, you identify that sales are predicted to decrease in a future month. Using this knowledge, you invest in marketing strategies to drive future sales and maintain consistent income.

Sales managers can use the overall sales forecast to anticipate sales trends. The item and salesperson visuals show historical sales amounts, not separate forecasts or workload predictions. Use these breakdowns to identify sales patterns before discussing inventory requirements with the purchasing team.

Salespeople can use the sales by customer visual to review historical customer sales patterns. For example, you might identify a customer with increasing sales and proactively engage with the customer to maintain the relationship. This visual doesn't provide a separate forecast for each customer.

## Key performance indicators (KPIs)

The **Sales Forecasting** report includes the following KPIs and measures:

- [Sales (LCY)](sales-powerbi-sales-kpis.md#sales-lcy)
- [Sales (LCY) Forecasting](sales-powerbi-sales-kpis.md#sales-lcy-forecasting)

[!INCLUDE[click-on-a-kpi-link](includes/click-on-a-kpi-link.md)]

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]

## Data used in the report

The report uses data from the following tables:

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

[Track your business KPIs with Power BI goals](track-kpis-with-power-bi-metrics.md)  
[Ad-hoc analysis of sales data](ad-hoc-analysis-sales.md)  
[Built-in sales reports](sales-reports.md)  
[Sales analytics overview](sales-analytics-overview.md)  
[Sales overview](sales-manage-sales.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
