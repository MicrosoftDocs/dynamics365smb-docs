---
title: Capacity Variance Manufacturing Power BI Report
description: Compare actual capacity costs and usage with expected and standard values for released and finished orders in the Capacity Variance Power BI report.
author: kennienp
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: 37047_Primary
ms.date: 11/12/2026
ai-usage: ai-assisted
ms.service: dynamics-365-business-central
---

# Capacity variance (Power BI report)

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

The **Capacity Variance** report compares actual capacity costs and usage with expected and standard values for released and finished production orders. It groups cost deviations by source item and lists variances by production order. This report helps you identify areas where costs are overrunning. You can optimize production processes, reduce costs, and improve overall performance.

:::image type="content" source="media/manufacturing/capacity-variance-v26.png" alt-text="Screenshot of the Capacity Variance Power BI Report" lightbox="media/manufacturing/capacity-variance-v26.png":::

## Use the report

The report is meant for manufacturing managers and supervisors.

Manufacturing managers use the report to track and manage capacity costs for production operations. By analyzing the variance between expected and actual capacity costs by production order and source item, you can find areas where costs are overrunning and take corrective action.

Production supervisors use this report to monitor the performance of production lines and ensure they operate within budget. By tracking the actual capacity costs against the expected costs, you can quickly uncover deviations. For example, higher actual capacity usage than expected can prompt you to investigate production inefficiencies. To analyze raw material costs, use the [Consumption Variance report](manufacturing-powerbi-consumption-variance.md).

## Key performance indicators (KPIs)

The *Capacity Variance* report includes the following KPIs and measures:

- [**Actual Capacity Cost**](manufacturing-powerbi-kpis.md#actual-capacity-cost)
- [**Expected Capacity Cost**](manufacturing-powerbi-kpis.md#expected-capacity-cost)
- [**Standard Capacity Cost**](manufacturing-powerbi-kpis.md#standard-capacity-cost)
- [**Expected Capacity Cost Variance**](manufacturing-powerbi-kpis.md#expected-capacity-cost-variance)
- [**Standard Capacity Cost Variance**](manufacturing-powerbi-kpis.md#standard-capacity-cost-variance)
- [**Expected Capacity Cost Dev %**](manufacturing-powerbi-kpis.md#expected-capacity-cost-dev-percent)
- [**Standard Capacity Cost Dev %**](manufacturing-powerbi-kpis.md#standard-capacity-cost-dev-percent)
- [**Prod Order Actual Capacity Need**](manufacturing-powerbi-kpis.md#prod-order-actual-capacity-need)
- [**Prod Order Expected Capacity Need**](manufacturing-powerbi-kpis.md#prod-order-expected-capacity-need)
- [**Prod Order Capacity Need Variance**](manufacturing-powerbi-kpis.md#prod-order-capacity-need-variance)

[!INCLUDE[click-on-a-kpi-link](includes/click-on-a-kpi-link.md)]

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]

## Data used in the report

The report uses data from the following tables in [!INCLUDE[prod_short](includes/prod_short.md)]:

- Production Order Routing Line
- Production Order
- Capacity Ledger Entry
- Prod. Order Line
- Prod. Order Capacity Need
- Inventory Adjmt. Entry (Order)
- Value Entry
- Item
- Work Center
- Manufacturing Setup
  
## Try the report

Try the report here: [Capacity Variance](https://businesscentral.dynamics.com?page=37047)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Track your business KPIs with Power BI goals](track-kpis-with-power-bi-metrics.md)  
[Power BI Manufacturing app](manufacturing-powerbi-app.md)  
[Built-in production reports](production-reports.md)  
[Manufacturing overview](production-manage-manufacturing.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
