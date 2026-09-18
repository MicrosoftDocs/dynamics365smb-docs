---
title: Contract Standard Sales Quote report
description: Add subscription billing details to the standard sales quote so customers see recurring service commitments alongside one-time item charges.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_8011_Primary
ms.date: 09/18/2026
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 09/18/2026
ai-usage: ai-assisted
---

# Contract Standard Sales Quote (report)

The **Contract Standard Sales Quote** report extends the sales quote report to include subscription billing information. It adds a service commitment section under each sales line that shows the description, unit price, and line discount for any recurring charges tied to that line, and it appends a totals section that groups all service commitments by billing period. The report keeps the original quote layout, including company and customer addresses, document number, document date, valid-to date, salesperson, payment terms, and shipment method, while inserting the subscription details directly into the item line and totals areas.

You can filter the report by the same criteria as the standard sales quote, such as document number, customer, salesperson, and document date, to control which quotes are included in the printout. Because the subscription billing data is generated per sales line, you don't need a separate filter to include or exclude service commitments. The service commitments appear automatically whenever a line has associated recurring charges.

## Use cases

[!INCLUDE [report-8011-scenario](../includes/report-8011-scenario-include.md)]

Sales representatives can use the report to:

* Send customers a quote that shows both one-time item charges and recurring subscription fees.
* Confirm that discounts and unit prices on service commitment lines match what you negotiated before the quote is sent.
* Use the valid-to date and payment terms shown on the quote to set clear expectations for acceptance.

Billing and finance teams can use the report to:

* Review the grouped-by-period totals to verify recurring revenue amounts before a quote converts to an order.
* Check that VAT-inclusive totals correctly exclude items that are billed through subscription lines instead of standard sales totals.
* Use the report as a reference when reconciling quoted subscription charges against contract billing schedules.

## Try the report

Try the report here: [Contract Standard Sales Quote](https://businesscentral.dynamics.com?report=8011)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Sales reports](../sales-reports.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
