---
title: Vendor Quality Analysis (Power BI Report)
description: The Vendor Quality Analysis report provides insights into your organization's vendor performance and quality metrics.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: reporting
ms.search.form: 37115_Primary
ms.date: 9/30/2025
ms.service: dynamics-365-business-central
---

# Vendor Quality Analysis (Power BI Report)

[!INCLUDE[2025_releasewave2](includes/2025_releasewave2.md)]

The **Vendor Quality Analysis** report analyzes vendor performance, showcasing vendor quality, returns, reliance and purchase discount trends. By visualizing key purchasing metrics over time, item distribution and spending diversity, this report provides a breakdown of vendor behaviors to continuously improve supplier performance and mitigate  purchasing risks.

:::image type="content" source="media/purchases/purchases-vendor-quality-analysis.png" alt-text="Screenshot of the Vendor Quality Analysis Power BI report" lightbox="media/purchases/purchases-vendor-quality-analysis.png":::

## Use the report

This report is designed for executives, purchasing managers and purchasers, to highlight effective vendor relationships and minimize supply chain risks.

As a CEO, you want to monitor vendor performance and identify trusted vendors and supplier risks, to inform key business decisions. For example, by reviewing the vendor analysis details, you identify a vendor with the highest [Spend Reliance %](purchases-powerbi-kpis.md#spend-reliance-) who consistently performs poorly across returns and discounts. Using these insights, you decide to pursue an alternate supplier to improve supply-chain reliability, product quality and profit metrics.

For purchasing managers, you want to track vendor performance and item dependence, to ensure a reliable supply-chain pipeline. Using the vendor reliance analysis, you identify a single-supplier item with the highest purchase amount. In response, you engage with additional vendors to diversify product supply and reduce over-reliance on a specific vendor. 

As a purchaser, you want to analyze vendor behaviors to manage effective supplier relationships. Using the purchase discount amount over time, you might identify a vendor who is not consistently delivering discounts compared to other vendors. With this information, you are empowered to negotiate discounted purchase prices to improve profit metrics.

## Key Performance Indicators (KPIs)

The *Vendor Quality Analysis* report includes the following KPIs and measures: 

- [**Purchase (LCY)**](purchases-powerbi-kpis.md#purchase-lcy)
- [**Purchase Quantity**](purchases-powerbi-kpis.md#purchase-quantity)
- [**No. of Vendors**](purchases-powerbi-kpis.md#no-of-vendors)
- [**No. of Distinct Items**](purchases-powerbi-kpis.md#no-of-distinct-items)
- [**No. of Single Supplier Items**](purchases-powerbi-kpis.md#no-of-single-supplier-items)
- [**Purchase Value Entries Discount %**](purchases-powerbi-kpis.md#purchase-value-entries-discount-)
- [**Purchase Value Entries Discount Amount**](purchases-powerbi-kpis.md#purchase-value-entries-discount-amount)
- [**Return Rate (Amount)**](purchases-powerbi-kpis.md#return-rate-amount)
- [**Spend Reliance %**](purchases-powerbi-kpis.md#spend-reliance-)
- [**Item Reliance %**](purchases-powerbi-kpis.md#item-reliance-)

[!INCLUDE[click-on-a-kpi-link](includes/click-on-a-kpi-link.md)] 

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]

## Data used in the report

The report uses data from the following tables in [!INCLUDE[prod_short](includes/prod_short.md)]:

- Value Entries
- Purchase Invoice Lines
- Purchase Credit Lines
- Item
- Vendor

## Try the report

Try the report here: [Vendor Quality Analysis](https://businesscentral.dynamics.com?page=37115)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Track KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md)  
[Power BI Purchasing app](purchases-powerbi-app.md)  
[Ad hoc analysis of purchasing data](ad-hoc-analysis-purchasing.md)  
[Built-in purchasing reports](purchase-reports.md)  
[Purchasing analytics overview](purchasing-analytics-overview.md)  
[Purchasing overview](purchasing-manage-purchasing.md)  
