---
title: Standard Sales Credit Memo report
description: Print or email a posted sales credit memo that shows customer information, credited items, VAT details, and document totals.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_1307
ms.date: 09/18/2026
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 09/18/2026
ai-usage: ai-assisted
---

# Standard Sales - Credit Memo (report)

The **Standard Sales - Credit Memo** report generates a document for posted sales credit memos that you can print or send by email. It shows company and customer addresses, the credit memo number, references, salesperson, applies-to document, due date, and credited lines with quantities, prices, discounts, VAT, and amounts. It also includes VAT specifications, VAT clauses, and totals. You can optionally show shipment and assembly component information.

You can filter the report by **No.**, **Sell-to Customer No.**, and **No. Printed**. The report requires at least one filter. You can show or hide customer shipments, show assembly components from linked assembly orders, hide lines with zero quantity, and log the printing as a customer interaction.

## Use cases

[!INCLUDE [report-1307-scenario](../includes/report-1307-scenario-include.md)]

Accounts receivable and finance teams can use the report to:

* Print or email a posted credit memo as proof of the credited amount and VAT breakdown.
* Verify VAT amounts, clauses, and totals before sending the document.
* Reissue a copy of a credit memo by filtering on its number.
* Log the document send as a customer interaction.

Sales and customer service representatives can use the report to:

* Confirm the applied invoice or return order reference before contacting the customer.
* Include shipment quantities when the credit relates to a returned shipment.
* Show assembly component details on credited lines that originated from an assembly order.
* Check the ship-to address and shipment method to resolve customer questions.

## Try the report

Try the report here: [Standard Sales - Credit Memo](https://businesscentral.dynamics.com?report=1307)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Sales reports](../sales-reports.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
