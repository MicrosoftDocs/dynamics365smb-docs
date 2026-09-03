---
title: Standard Sales - Return Receipt (report)
description: Print or email a standard-format return receipt document for posted sales returns, showing item lines, quantities, and customer and shipping details.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_1309_Primary
ms.date: 2026-09-03
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 2026-09-03
ai.usage: ai-assisted
---

# Standard Sales - Return Receipt (report)

The **Standard Sales - Return Rcpt.** report generates a printable or emailable document for a posted return receipt. It pulls data from the return receipt header and lines, including company and customer address information, shipment and document dates, the related return order number, and the individual item lines with quantities and units of measure. The report supports multiple layouts, including RDLC and Word formats, so it can be adapted to different branding needs.

You can filter the report by return receipt number, sell-to customer number, and whether the receipt has already been printed, using the request page filters on the Posted Return Receipt fields. You can also choose to hide lines with zero quantity, show correction lines from undone quantity postings, and enable interaction logging so the printed or emailed document is recorded against the customer or contact.

## Use cases

[!INCLUDE [report-1309-scenario](../includes/report-1309-scenario-include.md)]

Customer service representatives can use the report to:

* Print a return receipt to confirm to the customer exactly what items and quantities were received back.
* Reprint a previously issued return receipt by filtering on the return receipt number.
* Email the return receipt directly to the customer's contact using the built-in email body layout.
* Log the interaction against the customer or contact record for a complete communication history.,Warehouse and shipping staff can use the report to:

* Verify received item numbers, descriptions, quantities, and units of measure against the physical return.
* Hide lines with zero quantity to keep the printed document focused on items actually returned.
* Check the return order number and shipment date printed on the receipt to match it against warehouse records.,Controllers and finance teams can use the report to:

* Review posted return receipts filtered by customer to reconcile returned quantities before issuing credit memos.
* Use the document and shipment dates on the receipt to confirm the timing of the return for period-end reporting.
* Track whether correction lines from undone quantity postings are included when auditing return activity.

## Try the report

Try the report here: [Standard Sales - Return Receipt](https://businesscentral.dynamics.com?report=1309)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Finance reports](../finance-reports.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
