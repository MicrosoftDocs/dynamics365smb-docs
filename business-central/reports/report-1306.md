---
title: Standard Sales Invoice report
description: Print or email a posted sales invoice that shows customer and company details, item lines, VAT breakdown, and payment amounts.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_1306
ms.date: 09/18/2026
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 09/18/2026
ai-usage: ai-assisted
---

# Standard Sales - Invoice (report)

The **Standard Sales - Invoice** report produces version of a posted sales invoice that you can print or send by email. It combines company and customer addresses, invoice details such as due date and payment terms, invoice lines with quantities, prices, discounts, and VAT, and totals for the subtotal, VAT, and amount including VAT. The report supports RDLC and Word layouts, so you can choose a format for printing or emailing.

You can filter the report by **No.**, **Sell-to Customer No.**, and **No. Printed**. The report requires at least one filter. You can also show assembly components or shipment information, display an extra fee note, hide lines with zero quantity, and log the printing as a customer interaction.

## Use cases

[!INCLUDE [report-1306-scenario](../includes/report-1306-scenario-include.md)]

Accounts receivable and billing staff can use the report to:

* Reprint a posted sales invoice for a customer who lost the original copy.
* Email the invoice directly to the customer by using a Word body layout.
* Check the remaining amount due on a partially paid invoice before following up.
* Include shipment or assembly component details when the customer needs proof of what was shipped or assembled.

Controllers and finance teams can use the report to:

* Verify that VAT amounts, clauses, and identifiers match what was posted.
* Review invoice discounts and totals during period-end reconciliation.
* Produce invoices with a VAT specification broken down by VAT identifier.

## Try the report

Try the report here: [Standard Sales - Invoice](https://businesscentral.dynamics.com?report=1306)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Sales reports](../sales-reports.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
