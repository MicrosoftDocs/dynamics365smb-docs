---
title: Standard Sales Draft Invoice report
description: Generate a draft invoice from an unposted sales invoice to review internally or send to a customer before posting the final document.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_1303_Primary
ms.date: 09/18/2026
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 09/18/2026
ai-usage: ai-assisted
---

# Standard Sales - Draft Invoice (report)

The **Standard Sales - Draft Invoice** report creates a draft of a sales invoice that you can print or send by email before you post it. It shows customer and company addresses, document and reference numbers, salesperson, payment terms, shipment method, and invoice lines with quantities, prices, discounts, VAT percentages, and amounts. It also shows VAT specifications, VAT clauses, subtotal, invoice discount, VAT amount, and the total including VAT.

You can filter the report by **No.**, **Sell-to Customer No.**, and **No. Printed**. These filters let you generate a draft for a specific invoice, restrict the report to a customer's open invoices, or exclude documents that have already been printed.

## Use cases

[!INCLUDE [report-1303-scenario](../includes/report-1303-scenario-include.md)]

Accounts receivable clerks can use the report to:

* Print or email a draft invoice to a customer for review before the invoice is posted.
* Verify line amounts, discounts, and VAT calculations against the sales order.
* Confirm payment terms, payment method, and shipment method details before posting.
* Attach the draft invoice to an email by using an email body layout.

Salespeople can use the report to:

* Share a draft invoice with a customer to confirm pricing and quantities before finalizing the sale.
* Check that the customer's reference number and shipping address are correct.
* Review invoice discounts and VAT clauses before the invoice is posted.

Controllers and finance teams can use the report to:

* Audit VAT amount specifications and VAT clauses on draft invoices.
* Reconcile subtotal, invoice discount, and total amounts including VAT before posting.
* Log customer communications about draft invoices.

## Try the report

Try the report here: [Standard Sales - Draft Invoice](https://businesscentral.dynamics.com?report=1303)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Sales reports](../sales-reports.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
