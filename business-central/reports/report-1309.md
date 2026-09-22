---
title: Standard Sales - Return Rcpt. (report)
description: Print or email a standard-format return receipt for posted sales returns, showing customer, item, and quantity details.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_1309_Primary
ms.date: 09/10/2026
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 09/10/2026
ai.usage: ai-assisted
---

# Standard Sales - Return Rcpt. (report)

The **Standard Sales - Return Rcpt.** report prints a formatted document for one or more posted return receipts. It shows the company and customer addresses, document dates, and the return order number, followed by a list of the returned items with quantities and units of measure. You can render the report in RDLC or Word layouts. The report supports options to log the interaction with the customer contact and to hide lines with zero quantity.

You can filter the report by fields such as No., Sell-to Customer No., and No. Printed on the Posted Return Receipt table. Use these filters to select a specific return receipt, restrict output to a single customer, or limit results to receipts that are printed or unprinted. Apply a filter before running the report to avoid accidentally printing all posted return receipts at once.

## Use cases

[!INCLUDE [report-1309-scenario](../includes/report-1309-scenario-include.md)]

Customer service representatives can use the report to:

* Send a customer a copy of the return receipt confirming which items and quantities they returned.
* Reprint a return receipt for a specific customer by filtering on Sell-to Customer No.
* Enable the Log Interaction option to record that the receipt was sent to the customer contact.

Warehouse and shipping staff can use the report to:
* Verify posted return quantities against physically received goods by using the item lines on the receipt.
* Hide lines with zero quantity to keep the printed document focused on items actually returned.
* Check the ship-to and bill-to addresses printed on the document before mailing a copy to the customer.

## Try the report

Try the report here: [Standard Sales - Return Rcpt.](https://businesscentral.dynamics.com?report=1309)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Sales reports](../sales-reports.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
