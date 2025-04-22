---
title: Production Scrap (Power BI report)
description: The Production Scrap report shows the quantity of capacity scrap each month, with a breakdown by code, location, and item category.
author: kennienp
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: reporting
ms.search.form: 37055_Primary
ms.date: 11/01/2024
ms.service: dynamics-365-business-central
---

# Production Scrap (Power BI Report)

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

The **Production Scrap** report presents key KPIs like Scrap % and Scrap Quantity by Work Center, Machine Center, Source No. and Production Order.

The Production Order Scrap % KPI card highlights the relationship between Finished Quantity and Scrap Quantity, giving you an intuitive understanding of the drivers behind the production order scrap percent.

The Scrap Quantity Over Time line chart shows how scrap quantity changes over time. This allows you to identify trends in production scrap as processes change.

Work Center and Machine Center statistics are displayed in the KPI Bar. Work Center Scrap % and Machine Center Scrap % are derived from the Work Center Scrap and Work Center Output respectively. These figures help you understand the efficiency of your production facilities at a glance.

The Scrap % by Production Order bar chart gives you an easy way to compare scrap rates across different productions orders. Cross filter this report by the Scrap Quantity vs. Expected Scrap Quantity by Source No. bar chart to identify which production orders contribute to the scrap rate.

The Scrap Quantity by Scrap Code allows you to quickly compare and analyze why scrap occurred.

Used in conjunction, these report visuals work together to inform you. They help uncover where and why waste is happening, so you can take steps to reduce it.

:::image type="content" source="media/manufacturing/production-scrap.png" alt-text="Screenshot of the Production Scrap Power BI Report" lightbox="media/manufacturing/production-scrap.png":::

## Use the report

The report is meant for business leaders and manufacturing managers.

COOs use the report to measure the effectiveness of manufacturing processes and resources. By analyzing the capacity scrap quantity, you can identify areas that need improvement and optimize resource use. For example, a high scrap rate at a particular location might indicate a problem with the machinery or materials it uses. By addressing these issues, you can reduce waste and improve efficiency, leading to cost savings.

For manufacturing managers, this report reveals important measures about capacity scrap quantity. By analyzing the scrap rate, you can identify areas that need improvement, such as processes or materials. For example, a high scrap rate for a particular item category might indicate a problem with the materials it uses. By addressing these issues, you can optimize resource use to reduce waste and save costs.

## Key Performance Indicators (KPIs)

The *Production Scrap* report includes the following KPIs and measures:

- [Production Order Scrap %]()
- [Finished Quantity]()
- [Scrap Quantity]()
- [Work Center Scrap %]()
- [Work Center Scrap]()
- [Work Center Output]()
- [Machine Center Scrap %]()
- [Machine Center Scrap]()
- [Machine Center Output]()
- [Expected Production Order Scrap Quantity]()

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

## See also

[Track your business KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md)  
[Power BI Manufacturing app](manufacturing-powerbi-app.md)  
[Built-in production reports](production-reports.md)  
[Manufacturing overview](production-manage-manufacturing.md)
