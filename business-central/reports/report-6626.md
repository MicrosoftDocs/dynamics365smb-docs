---
title: Reference No. Label Report in Business Central
description: Print item labels that show item numbers, descriptions, and units of measure and encode reference numbers as Code 39 barcodes and QR codes for scanning.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_6626_Primary
ms.date: 09/16/2026
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 09/16/2026
ai-usage: ai-assisted
---

# Reference No. Label (report)

The **Reference No. Label** report generates printable labels for items based on their item reference records. Each label shows the item number, description, and unit of measure. It encodes the reference number as a Code 39 linear barcode and a QR code. Warehouse staff can scan the label with a linear barcode scanner or a QR code scanner. The report merges data into a Word layout designed for label printing. If the item reference doesn't have a description, the report gets the description from the related item record.

You can filter the report by **Item No.** to limit the labels to specific items. You can also run the report without filters to print labels for all item reference records.

## Use cases

[!INCLUDE [report-6626-scenario](../includes/report-6626-scenario-include.md)]

Warehouse and inventory staff can use the report to:

* Print labels for incoming items that use a vendor or customer reference number instead of the internal item number.
* Generate scannable item-reference labels for boxes or pallets to speed up picking and put-away.
* Verify that item descriptions and units of measure on labels match the item card.

Production and shop floor teams can use the report to:

* Print reference number labels for components tracked by an external catalog or cross-reference number.
* Use the QR code on the label to scan and look up item information on handheld devices.
* Print labels for a range of items before a production run by using the **Item No.** filter.

## Try the report

Try the report here: [Reference No. Label](https://businesscentral.dynamics.com?report=6626)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Inventory and warehouse report overview](../inventory-WMS-reports.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
