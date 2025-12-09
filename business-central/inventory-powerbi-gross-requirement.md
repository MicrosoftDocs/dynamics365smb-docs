---
title: Gross Requirement (Power BI report)
description: The Gross Requirement report looks at all outbound transactions within the system to identify the quantity required per item. 
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: 37027_Primary
ms.date: 10/28/2024
ms.service: dynamics-365-business-central
---

# Gross Requirement (Power BI Report)

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

The **Gross Requirement** report looks at all outbound transactions to determine the quantity required per item.

The report shows the gross requirement for an item and the different documents that include it. This information is coupled with the **Project Available Balance** that calculates the balance at any point in time.

:::image type="content" source="media/inventory/gross-requirement.png" alt-text="Screenshot of the Gross Requirement Power BI Report" lightbox="media/inventory/gross-requirement.png":::

## Use the report

The report helps management and procurement officers to determine whether the organization is keeping up with demand.

Managers can use the report to ensure that stock levels are high enough to maintain the production schedule and sales demand for each item. The report helps identify bottlenecks in production by showing items where the available inventory doesn't meet the gross requirement.

Procurement officers can view sales and production volumes and ensure your available balance meets the requirements for each item. With this information, you can make informed decisions on the items you should replenish.

## Key Performance Indicators (KPIs)

The *Gross Requirement* report includes the following KPIs:

- [**Gross Requirement**](inventory-powerbi-kpis.md#gross-requirement)
- [**Project Available Balance**](inventory-powerbi-kpis.md#projected-available-balance)
- [**Qty. on Sales Order**](inventory-powerbi-kpis.md#qty-on-sales-order)
- [**Qty. on Purch. Return**](inventory-powerbi-kpis.md#qty-on-purch-return)
- [**Qty. on Service Order**](inventory-powerbi-kpis.md#qty-on-service-order)
- [**Qty. on Projects**](inventory-powerbi-kpis.md#qty-on-projects)
- [**Qty. on Prod. Order Comp Lines**](inventory-powerbi-kpis.md#qty-on-prod-order-comp-lines)
- [**Trans. Order Shipment (Qty)**](inventory-powerbi-kpis.md#trans-order-shipment-qty)
- [**Planning Issues (Qty)**](inventory-powerbi-kpis.md#planning-issues-qty)
- [**Qty. on Asm. Component**](inventory-powerbi-kpis.md#qty-on-asm-component)

[!INCLUDE[click-on-a-kpi-link](includes/click-on-a-kpi-link.md)] 

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)] 


## Data used in the report

The report uses data from the following tables in [!INCLUDE [prod_short](includes/prod_short.md)]:

- Item
- Item Ledger Entries
- Assembly Lines
- Job Planning Lines
- Prod Order Component Line
- Production Order Lines
- Purchase Lines
- Sales Lines
- Service Lines
- Transfer Lines

## Try the report

Try the report here: [Gross Requirement](https://businesscentral.dynamics.com?page=37027)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Track KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md)  
[Power BI Inventory app](inventory-powerbi-app.md)  
[Ad hoc analysis of inventory data](ad-hoc-analysis-inventory.md)  
[Built-in inventory and warehouse reports](inventory-WMS-reports.md)  
[Inventory analytics overview](inventory-analytics-overview.md)  
[Inventory overview](inventory-manage-inventory.md)