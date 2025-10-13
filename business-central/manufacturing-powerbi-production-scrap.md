---
title: Production Scrap (Power BI report)
description: The Production Scrap report shows the quantity of capacity scrap each month, with a breakdown by code, location, and item category.
author: kennienp
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: reporting
ms.search.form: 37055_Primary
ms.date: 05/26/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Production Scrap (Power BI Report)

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

The **Production Scrap** report presents important key performance indicators (KPIs) such as **Scrap %** and **Scrap Quantity by Work Center**, **Machine Center**, **Source No.**, and **Production Order**.

The **Production Order Scrap %** KPI card highlights the relationship between **Finished Quantity** and **Scrap Quantity** to help clarify the drivers behind the production order scrap percent.

The **Scrap Quantity Over Time** chart shows how scrap quantity changes over time. This chart allows you to identify trends in production scrap as processes change.

Work center and machine center statistics display in the KPI Bar. **Work Center Scrap %** and **Machine Center Scrap %** are derived from the **Work Center Scrap** and **Work Center Output** respectively. These figures help you understand the efficiency of your production facilities at a glance.

The **Scrap % by Production Order** chart gives you an easy way to compare scrap rates across different productions orders. Cross filter this report by the **Scrap Quantity vs. Expected Scrap Quantity by Source No.** chart to identify which production orders contribute to the scrap rate.

The **Scrap Quantity by Scrap Code** visual allows you to quickly compare and analyze why scrap occurred.

Used together, these visuals help uncover where and why waste is happening, so you can take steps to reduce it.

:::image type="content" source="media/manufacturing/production-scrap-v26.png" alt-text="Screenshot of the Production Scrap Power BI Report" lightbox="media/manufacturing/production-scrap-v26.png":::

## Use the report

The report is meant for business leaders and manufacturing managers.

COOs use the report to measure the effectiveness of manufacturing processes and resources. By analyzing the capacity scrap quantity, you can identify areas that need improvement and optimize resource use. For example, a high scrap rate at a particular location might indicate a problem with the machinery or the materials it uses. By addressing these issues, you can reduce waste and improve efficiency, leading to cost savings.

For manufacturing managers, this report reveals important measures about capacity scrap quantity. By analyzing the scrap rate, you can identify areas that need improvement, such as processes or materials. For example, a high scrap rate for a particular item category might indicate a problem with the materials it uses. By addressing these issues, you can optimize resource use to reduce waste and save costs.

## Key performance indicators (KPIs)

The Production Scrap report includes the following KPIs and measures:

- [**Production Order Scrap %**](manufacturing-powerbi-kpis.md#production-order-scrap-percent)
- [**Finished Quantity**](manufacturing-powerbi-kpis.md#finished-quantity)
- [**Scrap Quantity**](manufacturing-powerbi-kpis.md#scrap-quantity)
- [**Work Center Scrap %**](manufacturing-powerbi-kpis.md#work-center-scrap-percent)
- [**Work Center Scrap**](manufacturing-powerbi-kpis.md#work-center-scrap)
- [**Work Center Output**](manufacturing-powerbi-kpis.md#work-center-output)
- [**Machine Center Scrap %**](manufacturing-powerbi-kpis.md#machine-center-scrap-percent)
- [**Machine Center Scrap**](manufacturing-powerbi-kpis.md#machine-center-scrap)
- [**Machine Center Output**](manufacturing-powerbi-kpis.md#machine-center-output)
- [**Expected Production Order Scrap Quantity**](manufacturing-powerbi-kpis.md#expected-production-order-scrap-quantity)

[!INCLUDE[click-on-a-kpi-link](includes/click-on-a-kpi-link.md)]

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]

## Data used in the report

The report uses data from the following tables in [!INCLUDE[prod_short](includes/prod_short.md)]:

- Capacity Ledger Entry
- Production Order
- Machine Center
- Work Center

## Try the report

Try the report here: [Production Scrap](https://businesscentral.dynamics.com?page=37055)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Track your business KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md)  
[Power BI Manufacturing app](manufacturing-powerbi-app.md)  
[Built-in production reports](production-reports.md)  
[Manufacturing overview](production-manage-manufacturing.md)
