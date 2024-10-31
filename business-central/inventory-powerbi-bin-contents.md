---
title: Bin Contents (Power BI report)
description: The Bin Contents shows an organizations bin contents per location.
author: kennienp
ms.author: kepontop
ms.reviewer: 
ms.topic: conceptual
ms.search.keywords: reporting
ms.search.form: 37031_Primary
ms.date: 10/28/2024
ms.service: dynamics-365-business-central
---

# Bin Contents (Power BI Report)

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

The *Bin Contents* breaks down an organizations inventory levels on a bin by bin basis. This can be used to identify high and low volume bins and can inform inventory movement requirements if bins need additional inventory. 

The report additional highlights quantity available along with quantity metrics across different warehouse activities such as Pick, Put-Away and general adjustments.

:::image type="content" source="media/inventory/bin-contents.png" alt-text="Screenshot of the Bin Contents Power BI Report" lightbox="media/inventory/bin-contents.png":::


## How to use the report

The *Bin Contents* can be used by managers and manufacturing or procurement staff to be able to identify item volumes allocated to each bin.

As a Warehouse or Inventory Manager, the *Bin Contents* report provides you a clear picture of the stock levels of each bin across your organization. With this you can make decisions on procurement or further production. Alternatively, this could prompt you to transfer stock to a specific bin to maintain supply. 

As Manufacturing team member, you can use this report to gauge your inventory levels across all bins and plan production schedules based on the inventory in each bin. 

As a member of the procurement team, you can use this report to gauge your inventory levels across all bins and plan purchase orders to ensure bins stay at a reasonable level.


<!-- ## Key Performance Indicators (KPIs)

The *Bin Contents* report includes the following KPIs:

- [**Quantity in Adjustment Bin**](###)
- [**Available Quantity to Take**](###)
- [**Warehouse Quantity**](####)
- [**Pick Quantity (Base)**](####)
- [**ATO Components Pick Qty.**](####)
- [**Put-Away Quantity (Base)**](####)
- [**Negative Adjmt. Qty. (Base)**](####)
- [**Positive Adjmt. Qty. (Base)**](###)

Click on the link for a KPI to learn more about what it means, how it is calculated, and what data was used in the calculations. 

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)] -->

## Data used in the report

Data from the following tables are used on the *Bin Contents* report
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

## See also

[Track KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md)   
[Power BI Inventory app](inventory-powerbi-app.md)   
[Ad-hoc analysis of inventory data](ad-hoc-analysis-inventory.md)   
[Built-in inventory and warehouse reports](inventory-WMS-reports.md)  
[Inventory analytics overview](inventory-analytics-overview.md)   
[Inventory overview](inventory-manage-inventory.md)  