---
title: Scheduled Receipt (Power BI report)
description: The Scheduled Receipt report lets you view inbound inventory per document type. 
author: kennienp
ms.author: kepontop
ms.reviewer: 
ms.topic: article
ms.search.keywords: reporting
ms.search.form: 37028_Primary
ms.date: 10/28/2024
ms.service: dynamics-365-business-central
---

# Scheduled Receipt (Power BI Report)

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

The **Scheduled Receipt** report shows inbound inventory for items or item categories for different types of documents types or processes. The information also includes internal assembly or production accounting for when the finished good becomes available along with purchase and sales return documents.

:::image type="content" source="media/inventory/scheduled-receipt.png" alt-text="Screenshot of the Scheduled Receipt Power BI Report" lightbox="media/inventory/scheduled-receipt.png":::

## Use the report

Managers and warehousing staff use the report to know when to expect to receive inventory.

Managers use the report to track inventory levels and ensure that stock levels keep up with the requirements shown in the [Gross Requirement (Power BI Report)](inventory-powerbi-gross-requirement.md) report. Use this information to optimize your inventory and ensure you aren't over buying or over producing a specific item.

For warehouse receipt workers, this report offers detailed information about inbound stock from internal and external sources. This information can help you coordinate future purchasing and production levels.

## Key Performance Indicators (KPIs)

The *Scheduled Receipt* report includes the following KPIs:

- [**Scheduled Receipt**](inventory-powerbi-kpis.md#scheduled-receipt)
- [**Projected Available Balance**](inventory-powerbi-kpis.md#projected-available-balance)
- [**FP Order Receipt (Qty.)**](inventory-powerbi-kpis.md#fp-order-receipt-qty)
- [**Rel. Order Receipt (Qty.)**](inventory-powerbi-kpis.md#rel-order-receipt-qty)
- [**Qty. On Purchase Order**](inventory-powerbi-kpis.md#qty-on-purch-order)
- [**Qty. in Transit**](inventory-powerbi-kpis.md#qty-in-transit)
- [**Trans. Order Receipt (Qty.)**](inventory-powerbi-kpis.md#trans-order-receipt-qty)
- [**Qty. on Assembly Order**](inventory-powerbi-kpis.md#qty-on-assembly-order)
- [**Qty. on Sales Return Order**](inventory-powerbi-kpis.md#qty-on-sales-return-order)

[!INCLUDE[click-on-a-kpi-link](includes/click-on-a-kpi-link.md)] 

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)] 


## Data used in the report

The report uses data from the following tables in [!INCLUDE [prod_short](includes/prod_short.md)]:

- Item
- Purchase Line
- Sales Line
- Assembly Header
- Production Order Lines
- Transfer Lines

## Try the report

Try the report here: [Scheduled Receipt](https://businesscentral.dynamics.com?page=37028)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Track KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md)  
[Power BI Inventory app](inventory-powerbi-app.md)  
[Ad hoc analysis of inventory data](ad-hoc-analysis-inventory.md)  
[Built-in inventory and warehouse reports](inventory-WMS-reports.md)  
[Inventory analytics overview](inventory-analytics-overview.md)  
[Inventory overview](inventory-manage-inventory.md)
