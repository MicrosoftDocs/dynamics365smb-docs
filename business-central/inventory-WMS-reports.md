---
title: Inventory and Warehouse Reports and Analytics
description: Explore the inventory and warehouse reports and analytics that are available in the standard version of Business Central.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_704, Report_707, Report_711, Report_713, Report_716, Report_723, Report_813, Report_1001, Report_5806, Report_5807, Report_5808, Report_5809, Report_6625, Report_6626, Report_6627, Report_6628, Report_7150, Report_7151, Report_7313, Report_7319, Report_7320
ms.date: 09/16/2026
ms.custom: bap-template
ms.service: dynamics-365-business-central
---
# Inventory and warehouse reports and analytical tasks

Inventory and warehouse reporting in [!INCLUDE [prod_short](includes/prod_short.md)] gives inventory and business professionals insights and statistics about current and past inventory and warehouse activities.  

## Explore inventory reports with Report Explorer

[!INCLUDE [inventory_reports_report_explorer](includes/inventory-reports-report-explorer-include.md)]

## Inventory and warehouse report overview

[!INCLUDE [inventory_WMS_reports](includes/inventory-WMS-reports-include.md)]

## Analytical tasks

The following articles describe some of the key tasks for analyzing the state of your business:

* [View the Availability of Items](inventory-how-availability-overview.md)
* [Create Analysis Reports](bi-how-create-analysis-views-reports.md)  

## Print and scan barcodes

Using one-dimensional (1D) and two-dimensional (2D) barcodes can help streamline your inbound, outbound, and internal warehouse processes.

[!INCLUDE [barcode-mobile-app](includes/barcode-mobile-app.md)]

You can use the **Print Label** action to print 1D and 2D barcodes from the pages listed in the following table.

| Pages where you can print labels | Fields shown as text | Value encoded in the Code 39 barcode and QR code |
|---------|---------|---------|
| **Items**, **Item Card** | **Item No.** and **Description** | **GTIN** |
| **Item Reference List**, **Item Reference Entries** | **Item No.**, **Description**, and **Unit of Measure** | **Reference No.** |
| **Lot No. Information List**, **Lot No. Information Card** | **Item No.** and **Description** | **Lot Number** |
| **Serial No. Information List**, **Serial No. Information Card** | **Item No.** and **Description** | **Serial Number** |

> [!NOTE]
> Some printers and barcode/QR code formats require a specific implementation. You might need to upload a different Word template or clone the report to create your own customized version.
>
> Check with your equipment supplier to learn how to print Word documents on your device.  

## Related information

[Ad-hoc analysis of inventory data](ad-hoc-analysis-inventory.md)  
[Inventory analytics overview](inventory-analytics-overview.md)  
[Setting Up Inventory](inventory-setup-inventory.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)  
[Warehouse Management Overview](design-details-warehouse-management.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
