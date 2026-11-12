---
title: Average Production Times Power BI Report
description: Compare actual production time per finished unit by item, work center, and production order with the Average Production Times Power BI report.
author: kennienp
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: 37048_Primary
ms.date: 11/12/2026
ai-usage: ai-assisted
ms.service: dynamics-365-business-central
---

# Average production times (Power BI report)

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

The **Average Production Times** report shows the detailed average production times for each item. The report can help you make informed decisions and optimize your production processes.

The average divides actual capacity time by finished output quantity. Time values use the **Show Capacity In** unit from **Manufacturing Setup**.

:::image type="content" source="media/manufacturing/avergage-production-times-v26.png" alt-text="Screenshot of the Average Production Times Power BI Report" lightbox="media/manufacturing/avergage-production-times-v26.png":::

## Use the report

The report is meant for manufacturing managers and supervisors.

Manufacturing managers use the report to understand the average time it takes to produce each item. For example, you might want to identify the items that take the longest to produce and schedule their production process.

Production supervisors use this report to monitor the production time for a particular item and the quantity produced on production orders. For example, you notice that the production time for a particular item is longer than expected. You can use the report to identify the cause of the delay and optimize the production process to increase efficiency.

## Key performance indicators (KPIs)

The *Average Production Times* report includes the following KPIs and measures:

- [**Average Production Time Per Finished Quantity**](manufacturing-powerbi-kpis.md#average-production-time-per-finished-quantity)
- [**Actual Time Used**](manufacturing-powerbi-kpis.md#actual-time-used)
- [**Finished Quantity**](manufacturing-powerbi-kpis.md#finished-quantity)

[!INCLUDE[click-on-a-kpi-link](includes/click-on-a-kpi-link.md)]

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]

## Data used in the report

The report uses data from the following tables in [!INCLUDE[prod_short](includes/prod_short.md)]:

- Item
- Production Order
- Capacity Ledger Entry
- Item Ledger Entry
- Prod. Order Line
- Work Center
- Manufacturing Setup
  
## Try the report

Try the report here: [Average Production Times](https://businesscentral.dynamics.com?page=37048)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Track your business KPIs with Power BI goals](track-kpis-with-power-bi-metrics.md)  
[Power BI Manufacturing app](manufacturing-powerbi-app.md)  
[Built-in production reports](production-reports.md)  
[Manufacturing overview](production-manage-manufacturing.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
