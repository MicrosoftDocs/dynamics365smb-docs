---
title: Item GTIN Label Report in Business Central
description: Print item labels that show item numbers and descriptions and encode Global Trade Item Number (GTIN) values as Code 39 barcodes and QR codes for scanning.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_6625_Primary
ms.date: 09/16/2026
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 09/16/2026
ai-usage: ai-assisted
---

# Item GTIN Label (report)

The **Item GTIN Label** report generates printable labels for items. The labels show the item number, description, and the item's Global Trade Item Number (GTIN) as a one-dimensional (1D) barcode and a two-dimensional (2D) QR code. The report uses a Word layout designed for label printing. You can attach the labels to physical items or shelves for scanning at receiving, picking, or point-of-sale stations.

You can filter the report by **No.** to control which items are included. For example, you can print labels for a single item, a range of items, or your entire item list.

## Use cases

[!INCLUDE [report-6625-scenario](../includes/report-6625-scenario-include.md)]

Warehouse and inventory staff can use the report to:

* Print shelf labels for a range of items so that the items can be scanned during put-away and picking.
* Generate labels for newly received items that include a scannable GTIN for use with handheld barcode readers.
* Reprint labels for damaged or missing tags on existing inventory without regenerating other item data.

Retail and point-of-sale teams can use the report to:

* Produce item labels with GTIN barcodes for checkout scanning at the register.
* Print QR code labels for items that must be scanned by mobile devices or self-checkout kiosks.
* Print labels for a product line before it goes on the sales floor.

## Try the report

Try the report here: [Item GTIN Label](https://businesscentral.dynamics.com?report=6625)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Inventory and warehouse report overview](../inventory-WMS-reports.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
