---
title: Allocated Hours
description: The Allocated Hours report provides an overview of the allocated time, in hours, for each work center.
author: kennienp
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: reporting
ms.search.form: 37043_Primary
ms.date: 11/01/2024
ms.service: dynamics-365-business-central
---

# Allocated Time (Power BI Report)

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

The **Allocated Time** report gives an overview of the allocated time, in hours, for each work center. The view of allocated hours can help you identify over and underused work centers. Additionally, the report includes indicators such as the load percentage, allocated time (hours), and capacity available (hours) for a quick summary of resource use.

:::image type="content" source="media/manufacturing/allocated-hours-v26.png" alt-text="Screenshot of the Allocated Hours Power BI Report" lightbox="media/manufacturing/allocated-hours-v26.png":::

## Use the report

Manufacturing managers use the report to plan and allocate resources effectively. The data shows which work centers are over or underutilized, so you can make informed decisions about how to allocate resources.

For example, if you notice that a work center is underused, you can assign more work orders to that center to optimize the use of its resources. Conversely, if a work center is over utilized, you can reallocate work orders or consider adding more resources to that work center.

Manufacturing workers use this report to optimize the use of resources. You can analyze the allocated time in hours of each work center, and then plan your work accordingly.

## Key Performance Indicators (KPIs)

The *Allocated Hours* report includes the following KPIs and measures:

- [Allocated Time](manufacturing-powerbi-kpis.md#allocated-time)
- [Prod Order Expected Capacity Need](manufacturing-powerbi-kpis.md#prod-order-expected-capacity-need)

[!INCLUDE[click-on-a-kpi-link](includes/click-on-a-kpi-link.md)]

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]

## Data used in the report

The report uses data from the following tables in [!INCLUDE[prod_short](includes/prod_short.md)]:

- Production Order Capacity Need
- Work Center
- Work Center Group

## Try the report

Try the report here: [Allocated Hours](https://businesscentral.dynamics.com?page=37043)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Track your business KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md)  
[Power BI Manufacturing app](manufacturing-powerbi-app.md)  
[Built-in production reports](production-reports.md)  
[Manufacturing overview](production-manage-manufacturing.md)
