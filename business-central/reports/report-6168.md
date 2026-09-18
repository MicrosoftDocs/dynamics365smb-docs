---
title: Posted Sales Crd Memo with QR report
description: Add a QR code and e-document layout support to the Standard Sales - Credit Memo report for posted sales credit memos sent to customers.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_6168_Primary
ms.date: 09/18/2026
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 09/18/2026
ai-usage: ai-assisted
---

# Posted Sales Crd Memo with QR (report)

The **PostedSalesCrdMemoWithQR** report extends the standard **Standard Sales - Credit Memo** report by adding a QR code field and two Word layouts that render the credit memo with e-document support. It adds the **QR Code Image** field to the report dataset and provides both a full page layout and a body-only layout, so the credit memo can display customer and company addresses, salesperson and reference details, item lines with pricing and VAT, and totals alongside a QR code for electronic verification.

You can filter the report by the same filters available on the base **Standard Sales - Credit Memo** report, such as customer, credit memo number, and posting date because this extension only appends the QR code column and layout options to the existing dataset. It doesn't add new filter fields.

## Use cases

[!INCLUDE [report-6168-scenario](../includes/report-6168-scenario-include.md)]

Accounts receivable clerks can use the report to:

* Print or export posted sales credit memos that include a QR code customers can scan to verify the document electronically.
* Use the body-only layout to embed the credit memo content into other communication templates, such as emails, while keeping the QR code visible.
* Confirm that customer address, salesperson, applies-to document, and due date print correctly alongside the QR code before sending to customers.

Finance and compliance teams can use the report to:

* Verify that credit memos issued to customers meet e-document requirements by including a machine-readable QR code on the printed or emailed document.
* Review item line details, such as the quantity, unit price, discount percentage, VAT percentage, and line amount together with VAT-inclusive totals for audit purposes.
* Plan migration away from this Word layout to the Document Report Experience, since this layout is marked obsolete and scheduled for removal.

## Try the report

Try the report here: [PostedSalesCrdMemoWithQR](https://businesscentral.dynamics.com?report=6168)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Sales reports](../sales-reports.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
