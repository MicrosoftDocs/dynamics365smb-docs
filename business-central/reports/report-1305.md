---
title: Standard Sales - Order Conf. (report)
description: Generate a sales order confirmation document that communicates order details, pricing, and delivery information to customers.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_1305_Primary
ms.date: 09/10/2026
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 09/10/2026
ai.usage: ai-assisted
---

# Standard Sales - Order Conf. (report)

The **Standard Sales - Order Conf.** report creates a customer-facing confirmation for a sales order. It combines company and customer address information, order header details such as document number, external document number, salesperson, and shipment method, with a full breakdown of order lines including item numbers, quantities, unit prices, line discounts, VAT percentages, and line amounts. It calculates and prints VAT amount specifications, VAT clauses, and total amounts including VAT. It can optionally include assembly component details for assemble-to-order lines and a work description. The report is available in RDLC and Word rendering layouts, including versions designed for print and for use as email body text.

You can filter the report by sales order number, sell-to customer number, and number printed to control which orders are included. The report requires at least one filter to run and doesn't print all orders unprompted. On the request page, you can also choose to show assembly components for linked assembly orders, log the customer interaction in the interaction log, and specify whether the printed document should be archived after printing.

## Use cases

[!INCLUDE [report-1305-scenario](../includes/report-1305-scenario-include.md)]

Sales order processors can use the report to:

* Print or email an order confirmation to a customer immediately after entering or changing a sales order.
* Confirm quoted prices, line discounts, VAT percentages, and shipment method before the order ships.
* Include assembly component details on lines linked to assemble-to-order assembly orders so the customer sees what was used to fulfill the order.
* Archive the confirmation and log the customer interaction for later reference in the interaction log.
Customer service representatives can use the report to:

* Resend or reprint a confirmation for a specific customer or order number when a customer requests a copy.
* Verify shipment date, ship-to address, and payment terms shown to the customer match what was agreed.
* Use the email body layout to send a short cover message with the order number, due date, and total amount including VAT.

## Try the report

Try the report here: [Standard Sales - Order Conf.](https://businesscentral.dynamics.com?report=1305)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Sales reports](../sales-reports.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
