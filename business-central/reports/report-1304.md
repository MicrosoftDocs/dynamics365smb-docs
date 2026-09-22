---
title: Standard Sales - Quote report
description: Generate a printed or emailed sales quote that presents item lines, prices, discounts, VAT, and totals to a prospective customer.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_1304
ms.date: 09/10/2026
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 09/10/2026
ai.usage: ai-assisted
---

# Standard Sales - Quote (report)

The **Standard Sales - Quote** report creates a customer-facing quote document based on a sales quote header and its lines. It includes company and customer address details, document identification such as quote number and validity date, salesperson and payment information, and a breakdown of item lines with quantities, prices, discounts, VAT percentages, and line amounts, followed by subtotal and VAT-inclusive total amounts. You can render the report as a Word or RDLC layout, or send it as an email body with a shorter summary layout. You can optionally archive the quote and log a marketing interaction when you print it.

Filter the report by quote number, sell-to customer number, and whether the quote is already printed (No. Printed). This filter lets you reprint a specific quote, generate quotes for one customer, or limit output to quotes that you didn't print yet. You must apply a filter before running the report. The filter prevents accidentally generating every quote in the system.

## Use cases

[!INCLUDE [report-1304-scenario](../includes/report-1304-scenario-include.md)]

Sales representatives can use the report to:

* Print or email a formal quote for a prospective customer before creating an order.
* Confirm the quote validity date, payment terms, and shipment method that you show to the customer.
* Send the quote as an email body by using the composite email layout with a greeting and cover text.
* Reprint a previously issued quote by filtering on the quote number.

Sales managers and administrators can use the report to:

* Automatically archive quotes when you print them, based on the **Archive Quotes** setup option.
* Log customer interactions for marketing and CRM tracking when you send a quote.
* Review VAT amount specifications and invoice discount breakdowns before finalizing a quote into an order.

## Try the report

Try the report here: [Standard Sales - Quote](https://businesscentral.dynamics.com?report=1304)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Sales reports](../sales-reports.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
