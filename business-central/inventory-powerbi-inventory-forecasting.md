---
title: Inventory Forecasting (Power BI report)
description: The Inventory Forecasting report provides insights into your organization's inventory trends and future stock requirements.
author: kennienp
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: reporting
ms.search.form: 37110_Primary
ms.date: 10/31/2025
ms.service: dynamics-365-business-central
---

# Inventory Forecasting (Power BI Report)

[!INCLUDE[2025_releasewave2](includes/2025_releasewave2.md)]

The **Inventory Forecasting** report predicts future inventory trends based on historical data. It uses advanced techniques to project quantity values across location, item and entry type dimensions, helping users optimize inventory levels.

The inventory forecasting visualization predicts the next three months of quantity based on the previous six months, assuming a monthly seasonality.

> [!NOTE]
> The default forecasting options can be customized through the Forecast section in the Analytics Pane in Power BI Desktop. This includes modifying the forecast length, seasonality, period and confidence interval.

:::image type="content" source="media/inventory/inventory-forecasting.png" alt-text="Screenshot of the Inventory Forecasting Power BI Report" lightbox="media/inventory/inventory-forecasting.png":::

## Use the report

The *Inventory Forecasting* report is designed for inventory managers and procurement officers to track projected stock levels.

As an inventory manager, you can use this report to monitor projected inventory and anticipate significant stock movements. For example, using the quantity by location forecasting, you identify a future period with increased incoming stock. In response, you proactively schedule warehouse employees to ensure adequate staffing to optimize shipping and receiving processes.

As a procurement officer, this report provides key insights into inventory supply and demand, helping users make informed decisions about stock levels and procurement. For example, you recognize a trend of decreased quantity in the same period each month. Using this information, you coordinate replenishment accordingly to ensure stock availability and optimal inventory levels.

## Key Performance Indicators (KPIs)

The *Inventory Forecasting* report includes the following KPIs:  

- [**Quantity**](inventory-powerbi-kpis.md#quantity)
- [**Quantity (Forecasting)**](inventory-powerbi-kpis.md#quantity-forecasting)

[!INCLUDE[click-on-a-kpi-link](includes/click-on-a-kpi-link.md)] 

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)] 


## Data used in the report

The report uses data from the following tables in [!INCLUDE [prod_short](includes/prod_short.md)]:

- Item Ledger Entries
- Location
- Item

## Try the report

Try the report here: [Inventory Forecasting](https://businesscentral.dynamics.com?page=37110)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Track KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md)  
[Power BI Inventory app](inventory-powerbi-app.md)  
[Ad hoc analysis of inventory data](ad-hoc-analysis-inventory.md)  
[Built-in inventory and warehouse reports](inventory-WMS-reports.md)  
[Inventory analytics overview](inventory-analytics-overview.md)  
[Inventory overview](inventory-manage-inventory.md)
