---
title: Inventory and Warehouse Reports and Analytics
description: See which inventory and warehouse reports and analytics are available in the standard version of Business Central so that you can keep track of your business.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: andreipa
ms.topic: conceptual
ms.search.keywords: reporting
ms.search.form: Report_707, Report_716, Report_813, Report_1001, Report_5807, Report_5808, Report_5809, Report_7313, Report_7319, Report_7320
ms.date: 04/13/2023
ms.custom: bap-template

---
# Inventory and Warehouse Reports and Analytics

Inventory and warehouse reporting in [!INCLUDE [prod_short](includes/prod_short.md)] gives inventory and business professionals insights and statistics about current and past inventory and warehouse activities.  

## Reports

[!INCLUDE [inventory_WMS_reports](includes/inventory-WMS-reports-include.md)]

## Tasks

The following articles describe some of the key tasks for analyzing the state of your business:

* [Create Analysis Reports](bi-how-create-analysis-views-reports.md)  
* [View the Availability of Items](inventory-how-availability-overview.md)

## Print and scan barcodes

Using barcodes can help streamline your inbound, outbound, and internal warehouse processes. 

[!INCLUDE [barcode-mobile-app](includes/barcode-mobile-app.md)]

After you install the app, you can use the **Print Label** action to print 1D and 2D barcodes from the pages listed in the following table.

|Page  |Field values barcodes can include  |
|---------|---------|
|Items, Item Card     |Item No., Description, and GTIN         |
|Item Reference List, Item Reference     |Item No., Description, Unit of Measure, and Reference No.         |
|Lot No. Information List, Lot No. Label     |Item No., Description, and Lot Number       |
|SN Label     |No., Description, and Serial Number         |

> [!NOTE]
> Some printers and barcode/QR code formats require a specific implementation. You might need to upload a different Word template or clone the report to create your own customized version.

## See also

[Setting Up Inventory](inventory-setup-inventory.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)  
[Warehouse Management Overview](design-details-warehouse-management.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
