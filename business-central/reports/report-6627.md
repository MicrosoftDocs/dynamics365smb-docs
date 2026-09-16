---
title: SN Label Report in Business Central
description: Print labels that show item numbers and descriptions and encode serial numbers as Code 39 barcodes and QR codes for scanning.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_6627_Primary
ms.date: 09/16/2026
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 09/16/2026
ai-usage: ai-assisted
---

# SN Label (report)

The **SN Label** report generates printable labels for items tracked by serial number (SN). For each serial number information record, the report shows the item number and description. It encodes the serial number as a Code 39 barcode and a QR code, which makes it easier to identify and scan individual items throughout the warehouse.

You can filter the report by **Item No.** to limit label printing to serial numbers for a specific item or range of items.

## Use cases

[!INCLUDE [report-6627-scenario](../includes/report-6627-scenario-include.md)]

Warehouse staff can use the report to:

* Print labels for newly received serial-tracked items before put-away.
* Scan the barcode or QR code during picking, put-away, or shipping to identify the correct serial number.
* Reprint labels for items whose original labels are damaged or lost.

Inventory managers can use the report to:

* Generate labels for a specific item or item range by using the **Item No.** filter.
* Ensure that serial-tracked items are labeled to support accurate physical inventory counts.
* Standardize label output across the warehouse by using the predefined Word layout.

## Try the report

Try the report here: [SN Label](https://businesscentral.dynamics.com?report=6627)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Inventory and warehouse report overview](../inventory-WMS-reports.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
