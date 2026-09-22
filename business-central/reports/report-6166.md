---
title: Posted Sales Invoice with QR report
description: Add a payment QR code to the posted sales invoice layout so customers can pay directly from the printed or PDF document.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_6166_Primary
ms.date: 09/18/2026
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 09/18/2026
ai-usage: ai-assisted
---

# Posted Sales Invoice with QR (report)

The **Posted Sales Invoice with QR** report extends the standard **Standard Sales - Invoice** report by adding a **QR Code Image** field to the header, and provides Word layouts that render the posted sales invoice with an embedded payment QR code. It includes both a full layout and a body-only layout for use in composite document scenarios, showing customer and company addresses, document references, payment and shipment terms, item lines with pricing and VAT detail, and VAT-inclusive totals.

You can filter the report by posted sales invoice number and customer to control which documents are printed or exported. You can also filter by document date or posting date ranges to select invoices for a specific period. These filters let you generate QR-enabled invoice copies for a single customer, a batch of invoices, or a defined time range.

## Use cases

[!INCLUDE [report-6166-scenario](../includes/report-6166-scenario-include.md)]

Accounts receivable teams can use the report to:

* Print or export posted sales invoices that include a scannable payment QR code to speed up customer payments.
* Send e-document-compliant invoice copies that combine standard invoice details with QR-based payment information.
* Reissue invoice copies for specific customers or invoice numbers when a customer requests a duplicate with payment details.

Controllers and finance teams can use the report to:

* Verify that VAT amounts, payment terms, and shipment details are correctly reflected on the QR-enabled invoice layout before it's sent.
* Review batches of posted invoices over a date range to confirm QR code data matches the underlying payment reference.
* Use the body-only layout to embed the QR-enabled invoice content into composite document packages sent to customers.

## Try the report

Try the report here: [PostedSalesInvoiceWithQR](https://businesscentral.dynamics.com?report=6166)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Sales reports](../sales-reports.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
