---
title: Standard Sales Pro Forma Invoice report
description: Print a pro forma invoice for a sales order to give customers cost and customs details before the actual invoice is issued.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_1302
ms.date: 09/18/2026
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 09/18/2026
ai-usage: ai-assisted
---

# Standard Sales - Pro Forma Inv (report)

The **Standard Sales - Pro Forma Inv** report prints a pro forma invoice for a sales order. It shows customer and company addresses, item lines with country/region of manufacture and tariff numbers, quantities, prices, net weight, VAT, and totals. You can use it for customs purposes or to give a customer a preview of charges before the actual invoice is created. The report can include the order's work description text and use either an RDLC layout or a Word layout.

You can filter the report by **No.**, **Sell-to Customer No.**, and **No. Printed** to select the sales orders to include. Turn on **Hide lines with zero quantity** to exclude lines that have no quantity to invoice.

## Use cases

[!INCLUDE [report-1302-scenario](../includes/report-1302-scenario-include.md)]

Sales administrators can use the report to:

* Generate a pro forma invoice for a customer before the sales invoice is posted to confirm pricing and terms.
* Print pro forma invoices with the sell-to and bill-to contact details, shipment method, and currency.
* Hide lines with zero quantity to keep the document focused on items that still need to be shipped or invoiced.

Export and customs coordinators can use the report to:

* Provide customs authorities with a document that lists each item's country/region of manufacture, tariff number, and net weight.
* Use the total weight and VAT amounts to support export declarations.
* Include the order's work description when additional shipment information is required.

## Try the report

Try the report here: [Standard Sales - Pro Forma Inv](https://businesscentral.dynamics.com?report=1302)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Sales reports](../sales-reports.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
