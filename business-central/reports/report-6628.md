---
title: Lot No Label Report in Business Central
description: Print labels that show item numbers and descriptions and encode lot numbers as Code 39 barcodes and QR codes for reliable scanning.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_6628_Primary
ms.date: 09/16/2026
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 09/16/2026
ai-usage: ai-assisted
---

# Lot No Label (report)

The **Lot No Label** report generates printable labels for lot-tracked items. The labels show the item number and description. The report encodes the lot number as a Code 39 barcode and a QR code, so that you can scan labels with either type of barcode reader. The report uses a Word layout that you can adapt to specific printers or label stock.

You can filter the report by **Item No.**, **Lot No.**, and other fields. For example, you can limit the print run to a specific item, a range of items, or specific lots that require new labels.

## Use cases

[!INCLUDE [report-6628-scenario](../includes/report-6628-scenario-include.md)]

Warehouse staff can use the report to:

* Print labels for newly received lots before putting them away in storage.
* Reprint a label for a lot whose original tag was damaged or lost.
* Scan the barcode or QR code during picking or put-away to confirm the correct lot.

Production and quality personnel can use the report to:

* Generate lot labels for items produced in a batch to support traceability requirements.
* Attach QR code labels to sample containers used for quality testing.
* Filter by **Item No.** to print labels for lots of a specific item used in production.

## Try the report

Try the report here: [Lot No Label](https://businesscentral.dynamics.com?report=6628)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Inventory and warehouse report overview](../inventory-WMS-reports.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
