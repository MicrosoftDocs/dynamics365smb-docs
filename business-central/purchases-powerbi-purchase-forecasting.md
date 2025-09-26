---
title: Purchase Forecasting (Power BI Report)
description: The Purchase Forecasting report predicts future purchasing trends to anticipate supply chain requirements.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: reporting
ms.search.form: 37112_Primary
ms.date: 10/31/2025
ms.service: dynamics-365-business-central
---

# Purchase Forecasting (Power BI Report)

[!INCLUDE[2025_releasewave2](includes/2025_releasewave2.md)]

The **Purchase Forecasting** report predicts future purchasing trends based on historical data. It uses advanced forecasting techniques to project purchase values across vendor, document, item category and purchaser dimensions.

The purchase forecast visualization predicts the next three months of purchases based on the previous six months, assuming a monthly seasonality.

> [!NOTE]
> The default forecasting options can be customized through the Forecast section in the Analytics Pane in Power BI Desktop. This includes modifying the forecast length, seasonality, period and confidence interval.

:::image type="content" source="media/purchases/purchase-forecasting.png" alt-text="Screenshot of the Purchases Forecasting Power BI report" lightbox="media/purchases/purchase-forecasting.png":::

## Use the report

Leadership and purchasing managers can use this report to anticipate purchase requirements and upcoming financial impacts on the organization.

CEOs need to track purchasing trends to implement strategic business decisions based on upcoming supply chain requirements. For example, you may identify that purchases are predicted to increase for a particular month. In response, you coordinate hiring additional staff to ensure sufficient workforce for managing increased purchasing operations.

Purchasing managers need to anticipate supply chain trends across key attributes, to inform future purchases. For example, the purchases by item category highlights a decreasing demand for a particular item category. You use this information to plan purchasing schedules accordingly to optimize inventory levels.

## Key Performance Indicators (KPIs)

The *Purchase Forecasting* report includes the following KPIs and measures:

- [**Purchase (LCY)**](purchases-powerbi-kpis.md#purchase-lcy)
- [**Purchase (LCY) Forecasting**](purchases-powerbi-kpis.md#purchase-lcy-forecasting)

[!INCLUDE[click-on-a-kpi-link](includes/click-on-a-kpi-link.md)] 

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]

## Data used in the report

The report uses data from the following tables in [!INCLUDE[prod_short](includes/prod_short.md)]:

- Value Entry
- Purchase Credit Line
- Purchase Invoice Line
- Vendor
- Item
- Salesperson/Purchaser

## Try the report

Try the report here: [Purchases Forecasting](https://businesscentral.dynamics.com?page=37112)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Track KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md)  
[Power BI Purchasing app](purchases-powerbi-app.md)  
[Ad hoc analysis of purchasing data](ad-hoc-analysis-purchasing.md)  
[Built-in purchasing reports](purchase-reports.md)  
[Purchasing analytics overview](purchasing-analytics-overview.md)  
[Purchasing overview](purchasing-manage-purchasing.md)  
