---
title: Inventory Power BI App Page (Power BI report)
description: The Inventory Power BI contains different reports for an organizations inventory reporting needs
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: 37064_Primary, 37022, 37024, 37023, 37025, 37026, 37027, 37028, 37029, 37030, 37031, 37032, 37110
ms.date: 10/28/2024
ms.service: dynamics-365-business-central
---

# Inventory Power BI app

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

The Power BI Inventory app is designed to pull data directly from [!INCLUDE [prod_short](includes/prod_short.md)] to give leadership, managers, and warehouse staff key information about inventory. This app has various reports that offer insights into business operations. Use the information from these reports to make informed decisions that ensure you meet demand, keep costs low, and don't delay production.

## Inventory analytics for the leadership team

To fit this category, you might have a role such as:

- Chief Operations Officer
- Chief Finance Officer

### Example scenario: maintaining stock turnover

COOs want to ensure that stock moves so you don't have aging stock on hand. The [Inventory by Lot](inventory-powerbi-inventory-by-lot.md) report shows how much stock is in each lot and where stock is expired. You can also compare this report with the information on the [Purchase and Sales Quantity](inventory-powerbi-purchase-and-sales-qty.md) report to ensure you aren't over-purchasing and increasing storage costs.

## Inventory analytics for the management team

To fit this category, you might have a role such as:

- Warehouse Manager
- Procurement Manager
- Supply Chain Manager
- Production Manager

### Example scenario: maintaining stock on hand

Warehouse managers want to ensure that each location has adequate stock levels. The [Inventory by Location](inventory-powerbi-inventory-by-location.md) report helps you ensure adequate stock levels at each location. It also indicates where to move stock around to supply locations.

Production or procurement managers can use the [Gross Requirement](inventory-powerbi-gross-requirement.md) to ensure that production planning is supplied by stock.

## Inventory analytics for the warehouse team

To fit this category, you might have a role such as:

- Order picker
- Order shipping

### Example scenario: tracking stock

Order pickers in a warehouse want to ensure that each bin contains enough stock to meet orders. Use the [Bin Contents](inventory-powerbi-bin-contents.md) report to be sure that bins contain the right amount of stock. To see tracking information, use the [Bin Contents by Item Tracking](inventory-powerbi-bin-contents-by-item-tracking.md) report.

To see lot and serial information on an item by item basis, other staff in the warehouse can use either the [Inventory by Lot](inventory-powerbi-inventory-by-lot.md) or [Inventory by Serial](inventory-powerbi-inventory-by-serial-no.md) reports.

## Use the reports

The following table provides descriptions on how you can use each report in the Power BI Inventory app.

|To... | Open in Business Central (CTRL+select) | Learn more |
|------|---------------------------------------|----------- |
|Get a high-level view of your organizations inventory and view statistics on scheduled receipt, gross requirements, and inventory across locations. | [Inventory Overview](https://businesscentral.dynamics.com?page=37022) | [About Inventory Overview](inventory-powerbi-inventory-overview.md)|
|Review inventory levels for items and gauge how many of an item are on different document types. | [Inventory by Item](https://businesscentral.dynamics.com?page=37024) | [About Inventory by Item](inventory-powerbi-inventory-by-item.md)|
|Review inventory levels at a Location to identify where you keep stock. | [Inventory by Location](https://businesscentral.dynamics.com?page=37023) | [About Inventory by Location](inventory-powerbi-inventory-by-location.md)|
|Analyze sales and purchase quantities to meet supply and demand. | [Purchase and Sales Quantity](https://businesscentral.dynamics.com?page=37025) | [About Purchase and Sales Quantity](inventory-powerbi-purchase-and-sales-qty.md)|
|Get a high-level view of inventory along with the gross requirements, scheduled receipts, and planned production volume. | [Item Availability](https://businesscentral.dynamics.com?page=37026) | [About Item Availability](inventory-powerbi-item-availability.md)|
|Analyze the volume of stock required to meet demand broken down by document type. | [Gross Requirement](https://businesscentral.dynamics.com?page=37027) | [About Gross Requirement](inventory-powerbi-gross-requirement.md)|
|Analyze the volume of stock you received broken down by document type. | [Scheduled Receipt](https://businesscentral.dynamics.com?page=37028) | [About Scheduled Receipt](inventory-powerbi-scheduled-receipt.md)|
|View inventory quantities based on lot numbers. | [Inventory by Lot](https://businesscentral.dynamics.com?page=37029) | [About Inventory by Lot](inventory-powerbi-inventory-by-lot.md)|
|View inventory quantities based on serial numbers. | [Inventory by Serial No.](https://businesscentral.dynamics.com?page=37030) | [About Inventory by Serial No.](inventory-powerbi-inventory-by-serial-no.md)|
|Analyze inventory levels across different bins and identify bins that have active picks. | [Bin Contents](https://businesscentral.dynamics.com?page=37031) | [About Bin Contents](inventory-powerbi-bin-contents.md)|
|Analyze inventory levels across bins and tracking information for the items. | [Bin Contents by Item Tracking](https://businesscentral.dynamics.com?page=37032) | [About Bin Contents by Item Tracking](inventory-powerbi-bin-contents-by-item-tracking.md)|
|Analyze forecasted inventory quantities across location, item and entry type. | [Inventory Forecasting](https://businesscentral.dynamics.com?page=37110) | [About Inventory Forecasting](inventory-powerbi-inventory-forecasting.md)|

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]

## Related information

[Installing Power BI apps for Business Central](across-powerbi-install-business-central-apps.md)   
[Track KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md)  
[Ad hoc analysis of inventory data](ad-hoc-analysis-inventory.md)  
[Built-in inventory and warehouse reports](inventory-WMS-reports.md)  
[Inventory analytics overview](inventory-analytics-overview.md)  
[Inventory overview](inventory-manage-inventory.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
