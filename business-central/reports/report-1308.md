---
title: Standard Sales - Shipment (report)
description: Print or email a formatted posted sales shipment document that shows shipped items, quantities, and optional lot or serial number tracking.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_1308_Primary
ms.date: 09/10/2026
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 09/10/2026
ai.usage: ai-assisted
---

# Standard Sales - Shipment (report)

The **Standard Sales - Shipment** report generates a printable document for one or more posted sales shipments. It shows company and customer address information, shipment and order references, and the shipped item lines with quantities and units of measure. It can also include assembly component details for items supplied through linked assembly orders, and an appendix listing lot and serial numbers used in the shipment. The report supports RDLC and Word rendering layouts, and it logs the printing action and, optionally, an interaction record against the customer or contact.

You can filter the report by the posted shipment **No.**, **Sell-to Customer No.**, and **No. Printed** to select which shipments to include. On the request page you can also choose to log the interaction with the customer, show assembly components used to supply the shipped items, show correction lines from undone quantity postings, print a lot/serial number appendix, and hide lines that have zero quantity.

## Use cases

[!INCLUDE [report-1308-scenario](../includes/report-1308-scenario-include.md)]

Warehouse and shipping staff can use the report to:

* Print a shipment confirmation immediately after posting to hand to the driver or include with the package.
* Include the lot/serial number appendix to give the customer traceability information for tracked items.
* Hide zero-quantity lines to keep the printed document focused on items that actually shipped.
* Show assembly components when a shipped item was supplied through a linked assembly order.,Customer service and sales representatives can use the report to:

* Reprint a specific posted shipment by filtering on the shipment number when a customer requests a copy.
* Filter by Sell-to Customer No. to reprint all recent shipments for one account.
* Enable Log Interaction so a record of sending the document is stored against the customer or contact.
* Review shipping agent code and package tracking number on the document before responding to a customer inquiry.

## Try the report

Try the report here: [Standard Sales - Shipment](https://businesscentral.dynamics.com?report=1308)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Sales reports](../sales-reports.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
