---
title: Inventory by Item (Power BI report)
description: The Inventory by Item report shows inventory levels per item or item category.
author: kennieNP
ms.author: kepontop
ms.reviewer: 
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: 37024_Primary
ms.date: 10/28/2024
ms.service: dynamics-365-business-central
---

# Inventory by Item (Power BI Report)

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

The **Inventory by Item** shows inventory levels per item category. The report showcases different columns to identify inventory per item on different document types.

This report is meant to allow all users to explore the total inventory for an item along with the split of inventory across the business.

:::image type="content" source="media/inventory/inventory-by-item.png" alt-text="Screenshot of the Inventory by Item Power BI Report" lightbox="media/inventory/inventory-by-item.png":::

## Use the report

Inventory managers use the report to get clear and concise information regarding each item. The report helps ensure you maintain consistent stock levels across all items. It shows inventory levels across a range of documents so you can track receipt, requirement, and production levels.

## Key Performance Indicators (KPIs)

The *Inventory by Item* report includes the following KPIs:

- [**Inventory (Quantity)**](inventory-powerbi-kpis.md#inventory-quantity)
- [**Qty. on Purch. Order**](inventory-powerbi-kpis.md#qty-on-purch-order)
- [**Qty. on Prod. Order**](inventory-powerbi-kpis.md#qty-on-prod-order)
- [**Qty. on Prod. Order Comp Lines**](inventory-powerbi-kpis.md#qty-on-prod-order-comp-lines)
- [**Qty. on Sales Order**](inventory-powerbi-kpis.md#qty-on-sales-order)
- [**Qty. on Sales Return Order**](inventory-powerbi-kpis.md#qty-on-sales-return-order)
- [**Qty. on Service Order**](inventory-powerbi-kpis.md#qty-on-service-order)
- [**Qty. on Projects**](inventory-powerbi-kpis.md#qty-on-projects)
- [**Qty. on Assembly Order**](inventory-powerbi-kpis.md#qty-on-assembly-order)
- [**Qty. on Asm. Component**](inventory-powerbi-kpis.md#qty-on-asm-component)
- [**Qty. in Transit**](inventory-powerbi-kpis.md#qty-in-transit)

[!INCLUDE[click-on-a-kpi-link](includes/click-on-a-kpi-link.md)] 

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)] 


## Data used in the report

The report uses data from the following tables in [!INCLUDE [prod_short](includes/prod_short.md)]:

- Item
- Item Ledger Entries
- Assembly Header
- Assembly Lines
- Job Planning Lines
- Prod Order Component Line
- Production Order Lines
- Purchase Lines
- Sales Lines
- Service Lines
- Transfer Lines

## Try the report

Try the report here: [Inventory by Item](https://businesscentral.dynamics.com?page=37024)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Track KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md)  
[Power BI Inventory app](inventory-powerbi-app.md)  
[Ad hoc analysis of inventory data](ad-hoc-analysis-inventory.md)  
[Built-in inventory and warehouse reports](inventory-WMS-reports.md)  
[Inventory analytics overview](inventory-analytics-overview.md)  
[Inventory overview](inventory-manage-inventory.md)