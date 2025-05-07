---
title: Bin Contents (Power BI report)
description: The Bin Contents report shows bin contents per location.
author: kennienp
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: reporting
ms.search.form: 37031_Primary
ms.date: 10/28/2024
ms.service: dynamics-365-business-central
---

# Bin Contents (Power BI Report)

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

The **Bin Contents** report breaks down an organization's inventory levels on a bin-by-bin basis. Use this information to identify high and low volume bins and inform inventory movement requirements if bins need more inventory.

The report also shows the available quantity and quantity metrics across different warehouse activities. For example, picks, put-aways, and general adjustments.

:::image type="content" source="media/inventory/bin-contents.png" alt-text="Screenshot of the Bin Contents Power BI Report" lightbox="media/inventory/bin-contents.png":::

## Use the report

The report helps managers and manufacturing or procurement staff to identify item volumes in each bin.

For warehouse or inventory managers, the report provides a clear picture of the stock levels of each bin across your organization. The report can help you make decisions on procurement or production. It might also prompt you to transfer stock to a specific bin to maintain supply.

Manufacturing team members can use this report to gauge inventory levels across all bins and plan production schedules based on the inventory in each bin.

The procurement team can use this report to gauge inventory levels across all bins and plan purchase orders to ensure that quantities in bins stay at a reasonable level.

## Key Performance Indicators (KPIs)

The *Bin Contents* report includes the following KPIs:

- [**Quantity in Adjustment Bin**](inventory-powerbi-kpis.md#quantity-in-adjustment-bin)
- [**Available Quantity to Take**](inventory-powerbi-kpis.md#available-qty-to-take)
- [**Warehouse Quantity**](inventory-powerbi-kpis.md#warehouse-quantity)
- [**Pick Quantity (Base)**](inventory-powerbi-kpis.md#pick-quantity-base)
- [**ATO Components Pick Qty.**](inventory-powerbi-kpis.md#ato-components-pick-qty)
- [**Put-Away Quantity (Base)**](inventory-powerbi-kpis.md#put-away-quantity-base)
- [**Negative Adjmt. Qty. (Base)**](inventory-powerbi-kpis.md#negative-adjmt-qty-base)
- [**Positive Adjmt. Qty. (Base)**](inventory-powerbi-kpis.md#positive-adjmt-qty-base)

[!INCLUDE[click-on-a-kpi-link](includes/click-on-a-kpi-link.md)] 

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)] 


## Data used in the report

The report uses data from the following tables in [!INCLUDE [prod_short](includes/prod_short.md)]:

- Item
- Bin
- Location
- Item Ledger Entries
- Warehouse Entries
- Warehouse Activity Lines
- Warehouse Journal Lines
- Zone

## Try the report

Try the report here: [Bin Contents](https://businesscentral.dynamics.com?page=37031)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Track KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md)  
[Power BI Inventory app](inventory-powerbi-app.md)  
[Ad hoc analysis of inventory data](ad-hoc-analysis-inventory.md)  
[Built-in inventory and warehouse reports](inventory-WMS-reports.md)  
[Inventory analytics overview](inventory-analytics-overview.md)  
[Inventory overview](inventory-manage-inventory.md)
