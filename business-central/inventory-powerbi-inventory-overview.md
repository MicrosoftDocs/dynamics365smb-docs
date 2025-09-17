---
title: Inventory Overview (Power BI report)
description: The Inventory Overview report provides a high-level summary of your organizations inventory.
author: kennienp
ms.author: kepontop
ms.reviewer: 
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: 37022_Primary
ms.date: 10/28/2024
ms.service: dynamics-365-business-central
---

# Inventory Overview (Power BI Report)

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

The **Inventory Overview** report provides a high-level summary of your inventory. It shows key metrics, such as:

- Inventory (Quantity)
- Scheduled receipts
- Gross requirements
- Project available balance

The report can give you a high-level understanding of your inventory on a location by location basis, along with quantities across different types of documents.

:::image type="content" source="media/inventory/inventory-overview.png" alt-text="Screenshot of the Inventory Overview Power BI Report" lightbox="media/inventory/inventory-overview.png":::

## Use the report

Leadership and management can gauge inventory levels across locations and get an idea about requirements versus receipts.

Management teams use the report to paint a picture of the stock information without having to drill down. The report gives a clear view of stock you're receiving and the demand that's currently in the system.

## Key Performance Indicators (KPIs)

The *Inventory Overview* report includes the following KPIs:

- [**Inventory (Quantity)**](inventory-powerbi-kpis.md#inventory-quantity)
- [**Scheduled Receipt**](inventory-powerbi-kpis.md#scheduled-receipt)
- [**Planned Order Receipt**](inventory-powerbi-kpis.md#planned-order-receipt)
- [**Gross Requirement**](inventory-powerbi-kpis.md#gross-requirement)
- [**Projected Available Balance**](inventory-powerbi-kpis.md#projected-available-balance)
- [**Qty. on Sales Order**](inventory-powerbi-kpis.md#qty-on-sales-order)
- [**Qty. on Purch. Return**](inventory-powerbi-kpis.md#qty-on-purch-return)
- [**Qty. on Service Order**](inventory-powerbi-kpis.md#qty-on-service-order)
- [**Qty. on Projects**](inventory-powerbi-kpis.md#qty-on-projects)
- [**Qty. on Prod. Order Comp Lines**](inventory-powerbi-kpis.md#qty-on-prod-order-comp-lines)
- [**Trans Order Shipment**](inventory-powerbi-kpis.md#trans-order-shipment-qty)
- [**Planning Issues**](inventory-powerbi-kpis.md#planning-issues-qty)
- [**Qty. on Asm. Component**](inventory-powerbi-kpis.md#qty-on-asm-component)
- [**FP Order Receipt (Qty.)**](inventory-powerbi-kpis.md#fp-order-receipt-qty)
- [**Rel. Order Receipt (Qty.)**](inventory-powerbi-kpis.md#rel-order-receipt-qty)
- [**Qty. on Purch. Order**](inventory-powerbi-kpis.md#qty-on-purch-order)
- [**Qty. in Transit**](inventory-powerbi-kpis.md#qty-in-transit)
- [**Trans. Order Receipt (Qty.)**](inventory-powerbi-kpis.md#trans-order-receipt-qty)
- [**Qty. on Assembly Order**](inventory-powerbi-kpis.md#qty-on-assembly-order)
- [**Qty. on Sales Return Order**](inventory-powerbi-kpis.md#qty-on-sales-return-order)

[!INCLUDE[click-on-a-kpi-link](includes/click-on-a-kpi-link.md)] 

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)] 

## Data used in the report

The report uses data from the following tables in [!INCLUDE [prod_short](includes/prod_short.md)]:

- Item
- Item Ledger Entries
- Job Planning Lines
- Purchase Lines
- Sales Lines
- Service Lines
- Assembly Header
- Assembly Lines
- Planning Component Lines
- Prod Order Component Lines
- Transfer Lines

## Try the report

Try the report here: [Inventory Overview](https://businesscentral.dynamics.com?page=37022)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Track KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md)  
[Power BI Inventory app](inventory-powerbi-app.md)  
[Ad hoc analysis of inventory data](ad-hoc-analysis-inventory.md)  
[Built-in inventory and warehouse reports](inventory-WMS-reports.md)  
[Inventory analytics overview](inventory-analytics-overview.md)  
[Inventory overview](inventory-manage-inventory.md)
