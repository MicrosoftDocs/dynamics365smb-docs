---
title: Purchases Return Overview (Power BI Report)
description: The Purchase Return Overview report gives a clear picture of your organization's purchase returns.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: reporting
ms.search.form: 37116_Primary
ms.date: 9/30/2025
ms.service: dynamics-365-business-central
---

# Purchases Return Overview (Power BI Report)

[!INCLUDE[2025_releasewave2](includes/2025_releasewave2.md)]

The **Purchase Return Overview** report tracks and analyzes purchase returns, showing 
reasons for return, return rate, purchase value and the financial impact on the organization. This report summarizes key return trends by vendor, reason and type, and visualizes return metrics over time.

:::image type="content" source="media/purchases/purchase-return-overview.png" alt-text="Screenshot of the Purchase Return Overview Power BI report" lightbox="media/purchases/purchase-return-overview.png":::

## Use the report

Leadership and purchasing teams use the report to identify the return trends contributing to return orders and credit memos.

For CEOs, you want to evaluate return trends to inform key business decisions. For example, you identify a particular vendor with the highest [Return Rate (Amount)](purchases-powerbi-kpis.md#return-rate-amount). In response, you engage with an alternative vendor to minimize returns and reduce time spent conducting product quality inspections.

As a purchasing manager, you want to identify key factors contributing to purchase returns to optimize purchasing operations. For example, you identify an increase in credits attributed to purchaser errors, impacting profit metrics. These insights empower you to invest in additional employee training to improve purchasing processes.

As a purchaser, you want to analyze return trends to ensure product quality while maintaining effective supplier relations. Using this report, you recognize a particular component has an increased credit amount over the past months, due to faulty products. Using this information, you engage with the supplier to switch to a more reliable component, decreasing return frequency.

## Key Performance Indicators (KPIs)

The *Purchase Return Overview* report includes the following KPIs and measures: 

- [**Return Rate (Amount)**](purchases-powerbi-kpis.md#return-rate-amount)
- [**Return Rate (Qty.)**](purchases-powerbi-kpis.md#return-rate-qty)
- [**Total Credit (Amount)**](purchases-powerbi-kpis.md#total-credit-amount)
- [**Total Credit (Qty.)**](purchases-powerbi-kpis.md#total-credit-qty)
- [**Total Purchase (Amount)**](purchases-powerbi-kpis.md#total-credit-amount)
- [**No. of Outstanding Return Orders**](purchases-powerbi-kpis.md#no-of-outstanding-return-orders)

[!INCLUDE[click-on-a-kpi-link](includes/click-on-a-kpi-link.md)] 

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]

## Data used in the report

The report uses data from the following tables in [!INCLUDE[prod_short](includes/prod_short.md)]:  

- Purchase Line
- Value Entry
- Purchase Credit Line
- Purchase Invoice Line
- Reason Code
- Vendor
- Item
- Resource
- G/L Account

## Try the report

Try the report here: [Purchases return overview](https://businesscentral.dynamics.com?page=37116)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Track KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md)  
[Power BI Purchasing app](purchases-powerbi-app.md)  
[Ad hoc analysis of purchasing data](ad-hoc-analysis-purchasing.md)  
[Built-in purchasing reports](purchase-reports.md)  
[Purchasing analytics overview](purchasing-analytics-overview.md)  
[Purchasing overview](purchasing-manage-purchasing.md)  
