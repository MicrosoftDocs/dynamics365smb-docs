---
title: Purchases by Location Power BI Report
description: Analyze purchase amounts and quantities by warehouse location in Power BI to compare purchasing patterns and explore item and vendor details.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: 37019_Primary
ms.date: 11/12/2026
ms.service: dynamics-365-business-central
ai-usage: ai-assisted
---

# Purchases by location (Power BI report)

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

The **Purchases by Location** report provides an overview of purchasing activities for each warehouse location. It helps you find out which item categories and items are most frequently purchased in each location, and how much money you're spending on the purchases.

:::image type="content" source="media/purchases/purchases-by-location.png" alt-text="Screenshot of the Purchases by Location Power BI report" lightbox="media/purchases/purchases-by-location.png":::

## Use the report

The report is especially useful for purchasing managers and purchasers.

Purchasing managers can use the report to analyze purchasing trends across different warehouse locations. For example, you can use the report to find the most frequently bought items and item categories in each warehouse. You and the warehousing team can gain insights into warehouses with consistently high or low purchasing activities.

Purchasers can use this report to monitor purchasing activities across warehouse locations. For example, you can identify items with low purchased quantities for further investigation. These quantities represent purchases, not current inventory levels. Review inventory availability before deciding whether to replenish an item.


## Key performance indicators (KPIs)

The *Purchases by Location* report includes the following KPIs and measures: 

- [**Purchase (LCY)**](purchases-powerbi-kpis.md#purchase-lcy)
- [**Purchase Quantity**](purchases-powerbi-kpis.md#purchase-quantity)
- [**% GT Purchase (LCY)**](purchases-powerbi-kpis.md#purchase-lcy)
- [**% GT Purchase Quantity**](purchases-powerbi-kpis.md#purchase-quantity)

[!INCLUDE[click-on-a-kpi-link](includes/click-on-a-kpi-link.md)] 

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]

## Data used in the report

The report uses data from the following tables in [!INCLUDE[prod_short](includes/prod_short.md)]:

- Location
- Item
- Vendor
- Purchase Value Entry
- Purchase Invoice Lines
- Purchase Credit Lines

## Try the report

Try the report here: [Purchases by Location](https://businesscentral.dynamics.com?page=37019)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Track KPIs with Power BI goals](track-kpis-with-power-bi-metrics.md)  
[Power BI Purchasing app](purchases-powerbi-app.md)  
[Ad hoc analysis of purchasing data](ad-hoc-analysis-purchasing.md)  
[Built-in purchasing reports](purchase-reports.md)  
[Purchasing analytics overview](purchasing-analytics-overview.md)  
[Purchasing overview](purchasing-manage-purchasing.md)  
