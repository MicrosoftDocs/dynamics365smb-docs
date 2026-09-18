---
title: E-Doc Sample Purchase Invoice report
description: Generate a sample purchase invoice PDF to preview how an incoming e-document will look before it's posted and validate the layout.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_6102_Primary
ms.date: 09/18/2026
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 09/18/2026
ai-usage: ai-assisted
---

# E-Doc Sample Purchase Invoice (report)

The **E-Doc Sample Purchase Invoice** report generates a preview PDF of a purchase invoice using data from a temporary E-Document Purchase Header and Line. You can check how the vendor address, company details, invoice lines, and totals render in a chosen layout before using the layout for actual incoming e-documents.

You can filter the report by the E-Document Purchase Header and Line records supplied to it at runtime through the SetData procedure. Because the report has no request page, the vendor address, invoice and posting dates, line items, and totals shown are determined by the sample or actual e-document data passed in, rather than by user-entered filters.

## Use cases

[!INCLUDE [report-6102-scenario](../includes/report-6102-scenario-include.md)]

E-document administrators can use the report to:

* Preview how a purchase invoice looks in a specific Word layout before activating it for production use.
* Compare the three built-in sample layouts to decide which one best fits the company's invoice format.
* Verify that vendor address, company information, and bank details are correctly formatted before rolling out e-document processing.

Accounts payable clerks can use the report to:

* Check that item lines display the correct quantity, unit of measure, unit cost, and line amount.
* Confirm that subtotal, tax, and total amounts calculate and display correctly on the invoice.
* Validate the invoice number, posting date, and due date fields before an e-document layout is trusted for real vendor invoices.

## Try the report

Try the report here: [E-Doc Sample Purchase Invoice](https://businesscentral.dynamics.com?report=6102)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Purchasing reports](../purchase-reports.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
