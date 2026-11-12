---
title: Finished Production Order Breakdown Power BI Report
description: The Finished Production Order Breakdown report provides insights into the expected quantity versus the finished quantity of production orders.
author: kennienp
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: 37045_Primary
ms.date: 11/12/2026
ai-usage: ai-assisted
ms.service: dynamics-365-business-central
---

# Finished production order breakdown (Power BI report)

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

The **Finished Production Order Breakdown** report compares planned and finished quantities for production orders with the **Finished** status. It also breaks down actual costs and compares them with expected and standard costs.

:::image type="content" source="media/manufacturing/finished-production-order-breakdown-v26.png" alt-text="Screenshot of the Finished Production Order Breakdown Power BI Report" lightbox="media/manufacturing/finished-production-order-breakdown-v26.png":::

## Use the report

The report is meant for manufacturing managers and supervisors.

Manufacturing managers use the report to review completed production orders. Comparing planned and finished quantities helps identify output variances. The cost breakdown helps you evaluate the cost of completed production.

Production supervisors use this report to investigate discrepancies between planned and finished quantities on completed production orders.

## Key performance indicators (KPIs)

The *Finished Production Order Breakdown* report includes the following KPIs and measures:

- [**Planned Quantity**](manufacturing-powerbi-kpis.md#planned-quantity)
- [**Finished Quantity**](manufacturing-powerbi-kpis.md#finished-quantity)
- [**Variance Quantity**](manufacturing-powerbi-kpis.md#variance-quantity)
- [**Actual Material Cost**](manufacturing-powerbi-kpis.md#actual-material-cost)
- [**Actual Capacity Cost**](manufacturing-powerbi-kpis.md#actual-capacity-cost)
- [**Actual Capacity Overhead Cost**](manufacturing-powerbi-kpis.md#actual-capacity-overhead-cost)
- [**Actual Manufacturing Overhead Cost**](manufacturing-powerbi-kpis.md#actual-manufacturing-overhead-cost)
- [**Actual Subcontracted Cost**](manufacturing-powerbi-kpis.md#actual-subcontracted-cost)
- [**Total Actual Cost**](manufacturing-powerbi-kpis.md#total-actual-cost)
- [**Total Expected Cost Variance**](manufacturing-powerbi-kpis.md#total-expected-cost-variance)
- [**Total Standard Cost Variance**](manufacturing-powerbi-kpis.md#total-standard-cost-variance)
- [**Total Expected Cost Dev %**](manufacturing-powerbi-kpis.md#total-expected-cost-dev-percent)
- [**Total Standard Cost Dev %**](manufacturing-powerbi-kpis.md#total-standard-cost-dev-percent)

[!INCLUDE[click-on-a-kpi-link](includes/click-on-a-kpi-link.md)]

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]

## Data used in the report

The report uses data from the following tables in [!INCLUDE[prod_short](includes/prod_short.md)]:

- Item
- Production Order
- Prod. Order Line
- Capacity Ledger Entry
- Item Ledger Entry
- Value Entry
- Inventory Adjmt. Entry (Order)
- Prod. Order Component
- Prod. Order Routing Line
- Work Center

## Try the report

Try the report here: [Finished Production Order Breakdown](https://businesscentral.dynamics.com?page=37045)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Track your business KPIs with Power BI goals](track-kpis-with-power-bi-metrics.md)  
[Power BI Manufacturing app](manufacturing-powerbi-app.md)  
[Built-in production reports](production-reports.md)  
[Manufacturing overview](production-manage-manufacturing.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
