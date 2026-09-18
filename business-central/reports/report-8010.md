---
title: Contract Sales Order Conf. report
description: Add subscription billing details, such as service commitment lines and per-period totals, to the standard sales order confirmation.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_8010_Primary
ms.date: 09/18/2026
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 09/18/2026
ai-usage: ai-assisted
---

# Contract Sales Order Conf. (report)

The **Contract Sales Order Conf.** report extends the **Sales - Order Confirmation** report to include subscription billing information. It adds a service commitment section under each sales line that lists the description, unit price, and line discount for any recurring service commitments tied to that line, and it appends a summary section that groups and totals service commitments by billing period. The report also excludes subscription billing items from the standard subtotal, discount, VAT, and total amount calculations on the confirmation so that recurring charges are represented separately from one-time sales amounts.

You can filter the report by the same options as the **Sales - Order Confirmation** report, such as sales order number, customer, and document date because this report reacts to the sales lines and service commitments already linked to the selected order. The report doesn't add filters.

## Use cases

[!INCLUDE [report-8010-scenario](../includes/report-8010-scenario-include.md)]

Sales employees can use the report to:

* Send order confirmations to customers that clearly separate one-time sales amounts from recurring subscription billing charges.
* Verify that service commitment details, such as unit price and discount, are correctly reflected on the line before the confirmation is sent.
* Confirm orders that mix standard items and subscription billing items without the subscription amounts distorting the printed subtotal or total.

Controllers and finance teams can use the report to:

* Review the per-period grouping of service commitments to validate expected recurring revenue before invoicing begins.
* Check that subscription billing items are correctly excluded from VAT and total calculations on the sales order confirmation.
* Use the printed confirmation as supporting documentation when reconciling contract values to the sales order.

## Try the report

Try the report here: [Contract Sales Order Conf.](https://businesscentral.dynamics.com?report=8010)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Sales reports](../sales-reports.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
