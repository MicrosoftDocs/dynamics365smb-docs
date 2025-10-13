---
title: Production Order WIP    
description: Learn how to benefit from using the Production Order WIP report.
author: kennienp
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: reporting
ms.search.form: 37107_Primary
ms.date: 05/26/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Production Order WIP (Power BI Report)

[!INCLUDE[applies-to-2025w1](includes/applies-to-2025w1.md)]

 The **Production Order WIP** report provides insights into the work-in-progress (WIP) inventory across production orders, displaying both trends and detailed valuation data.

:::image type="content" source="media/manufacturing/production-order-wip-v26.png" alt-text="Screenshot of the Production Order WIP Power BI Report" lightbox="media/manufacturing/production-order-wip-v26.png":::

The **Production Order WIP Report** consists of two key visuals that give insights into work-in-progress (WIP) inventory. The top visual is a timeline chart that showcases the **Ending Balance Value of WIP** inventory over time. The visual plots the **Ending Balance Value** as the Y-axis and the **Month Year** as the X-axis to offer a clear trend analysis and lets you find fluctuations and patterns in WIP inventory.

The **Inventory Valuation - WIP** table gives you a detailed breakdown of production order-related inventory valuation. The table includes essential columns, such as:

- Production Order
- Description
- Source Type
- Source No.
- Starting and Ending Dates
- Beginning Balance
- Consumption
- Capacity
- Output
- Ending Balance Value

Together, these visuals provide both high-level and detailed perspectives on WIP inventory.

## Use the report

## Key performance indicators (KPIs)

The Production Order WIP report includes the following KPIs and measures:

- [**Beginning Balance Value**](manufacturing-powerbi-kpis.md#beginning-balance-value)
- [**Consumption Value**](manufacturing-powerbi-kpis.md#consumption-value)
- [**Output Value**](manufacturing-powerbi-kpis.md#output-value)
- [**Capacity Value**](manufacturing-powerbi-kpis.md#capacity-value)
- [**Ending Balance Value**](manufacturing-powerbi-kpis.md#ending-balance-value)

[!INCLUDE[click-on-a-kpi-link](includes/click-on-a-kpi-link.md)]

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]

## Data used in the report

The report uses data from the following tables in [!INCLUDE[prod_short](includes/prod_short.md)]:

- Value Entry
- Production Order
  
## Try the report

Try the report here: [Production Order WIP](https://businesscentral.dynamics.com?page=37107)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Track your business KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md)  
[Power BI Manufacturing app](manufacturing-powerbi-app.md)  
[Built-in production reports](production-reports.md)  
[Manufacturing overview](production-manage-manufacturing.md)
