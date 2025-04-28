---
title: Production Order WIP    
description: The Production Order WIP
author: kennienp
ms.author: kepontop
ms.reviewer:
ms.topic: conceptual
ms.search.keywords: reporting
# TODO correct page id must be added
# ms.search.form: 37042_Primary 
ms.date: 04/25/2024
ms.service: dynamics-365-business-central
---

# Production Order WIP (Power BI Report)

[!INCLUDE[applies-to-2025w1](includes/applies-to-2025w1.md)]

 The **Production Order WIP** report provides insights into the work-in-progress (WIP) inventory across production orders, displaying both trends and detailed valuation data.

:::image type="content" source="media/manufacturing/production-order-wip.png" alt-text="Screenshot of the Production Order WIP Power BI Report" lightbox="media/manufacturing/production-order-wip.png":::

The **Production Order WIP Report** consists of two key visuals designed to provide insights into work-in-progress (WIP) inventory. The top visual is a timeline chart that showcases the Ending Balance Value of WIP inventory over time. By plotting the Ending Balance Value as the Y-axis and the Month Year as the X-axis, this visual offers a clear trend analysis, allowing users to observe fluctuations and patterns in WIP inventory.

Below the timeline is the **Inventory Valuation - WIP** table, which provides a detailed breakdown of production order-related inventory valuation. The table includes essential columns such as Production Order, Description, Source Type, Source No., Starting and Ending Dates, Beginning Balance, Consumption, Capacity, Output, and Ending Balance Value. Together, these visuals provide both high-level and detailed perspectives on WIP inventory.

## Use the report

## Key Performance Indicators (KPIs)

The *Production Order WIP* report includes the following KPIs and measures:

- [Beginning Balance Value]()
- [Consumption Value]()
- [Output Value]()
- [Capacity Value]()
- [Ending Balance Value]()

[!INCLUDE[click-on-a-kpi-link](includes/click-on-a-kpi-link.md)]

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]

## Data used in the report

The report uses data from the following tables in [!INCLUDE[prod_short](includes/prod_short.md)]:

- Value Entry
- Production Order
  
## Try the report

Try the report here: [Production Order WIP](https://businesscentral.dynamics.com?page=)<!-- TODO Set page ID for link -->

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](includes/ctrl-right-click-to-open-in-new-tab.md)]

## See also

[Track your business KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md)  
[Power BI Manufacturing app](manufacturing-powerbi-app.md)  
[Built-in production reports](production-reports.md)  
[Manufacturing overview](production-manage-manufacturing.md)
