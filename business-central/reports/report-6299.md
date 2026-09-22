---
title: Sust. Standard Sales Invoice report
description: Add CO2e emissions data and a sustainability disclaimer to the standard sales invoice so customers see the environmental impact of what they purchased.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_6299_Primary
ms.date: 09/18/2026
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 09/18/2026
ai-usage: ai-assisted
---

# Sust. Standard Sales Invoice (report)

The **Sust. Standard Sales Invoice** report extends the standard sales invoice with sustainability data. The report adds a CO2e-per-unit column to each invoice line, a total CO2e figure to the totals section, and a configurable disclaimer text pulled from the sustainability disclaimer setup for posted sales invoices. The emission values are formatted according to the decimal places and unit of measure you define on the **Sustainability Setup** page, so the invoice layout matches the company's chosen emission reporting standard.

You can filter the report by the same criteria as the underlying **Standard Sales - Invoice** report. For example, by customer, invoice number, and posting date because the report only adds sustainability columns and totals to whichever invoices are selected. It doesn't introduce more filters.

## Use cases

[!INCLUDE [report-6299-scenario](../includes/report-6299-scenario-include.md)]

Sustainability and compliance teams can use the report to:

* Verify that CO2e per unit and total CO2e values print correctly on customer-facing invoices before rollout.
* Confirm the disclaimer text configured in the Sustainability Disclaimer setup appears on posted sales invoices.
* Check that emission figures use the unit of measure and decimal precision defined on the **Sustainability Setup** page.

Accounts receivable and sales teams can use the report to:

* Issue sales invoices that include emissions data without changing the standard invoice workflow.
* Answer customer questions about the CO2e impact of individual line items directly from the invoice.
* Provide invoices that support customers' own sustainability and emissions reporting requirements.

## Try the report

Try the report here: [Sust. Standard Sales Invoice](https://businesscentral.dynamics.com?report=6299)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Sales reports](../sales-reports.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
