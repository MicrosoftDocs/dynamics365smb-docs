---
title: Item Availability (Power BI report)
description: The Item Availability report gives an overview of the availability of each item. 
author: kennienp
ms.author: kepontop
ms.reviewer: 
ms.topic: article
ms.search.keywords: reporting
ms.search.form: 37026_Primary
ms.date: 10/28/2024
ms.service: dynamics-365-business-central
---

# Item Availability (Power BI Report)

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

The **Item Availability** report gives an overview of the availability of each item in terms of supply and demand. Use the report to identify items where demand exceeds supply, so you can take action to avoid delayed orders.

:::image type="content" source="media/inventory/item-availability.png" alt-text="Screenshot of the Item Availability Power BI Report" lightbox="media/inventory/item-availability.png":::

## Use the report

The report is designed for management and customer service teams.

Customer service teams use this report to identify availability of specific items for your customers. By having up-to-date information for each item, you can provide quick, accurate, and informed answers to estimates and avoid disappointing customers.

For inventory management teams, the information in this report can help you keep adequate stock levels of each item. For example, the information can help you coordinate other teams to increase production of specific items, or create purchase orders to replenish stock.

## Key Performance Indicators (KPIs)

The *Item Availability* report includes the following KPIs:

- [**Projected Available Balance**](inventory-powerbi-kpis.md#projected-available-balance)
- [**Inventory (Quantity)**](inventory-powerbi-kpis.md#inventory-quantity)
- [**Gross Requirement**](inventory-powerbi-kpis.md#gross-requirement)
- [**Scheduled Receipt**](inventory-powerbi-kpis.md#scheduled-receipt)
- [**Planned Order Receipt**](inventory-powerbi-kpis.md#planned-order-receipt)
- [**Planned Order Release**](inventory-powerbi-kpis.md#planned-order-releases)

[!INCLUDE[click-on-a-kpi-link](includes/click-on-a-kpi-link.md)] 

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)] 


## Data used in the report

The report uses data from the following tables in [!INCLUDE [prod_short](includes/prod_short.md)]:

- Item
- Item Ledger Entries
- Sales Lines
- Service Lines
- Project Planning Lines
- Prod. Order Component Lines
- Transfer Lines
- Planning Component Lines
- Assembly Lines
- Purchase Lines

## Try the report

Try the report here: [Item Availability](https://businesscentral.dynamics.com?page=37026)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Track KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md)  
[Power BI Inventory app](inventory-powerbi-app.md)  
[Ad hoc analysis of inventory data](ad-hoc-analysis-inventory.md)  
[Built-in inventory and warehouse reports](inventory-WMS-reports.md)  
[Inventory analytics overview](inventory-analytics-overview.md)  
[Inventory overview](inventory-manage-inventory.md)
