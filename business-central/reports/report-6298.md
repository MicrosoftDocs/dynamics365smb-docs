---
title: Sust. Standard Sales Quote report
description: Add CO2e emissions data to the standard sales quote so customers see per-unit and total carbon impact alongside pricing.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_6298_Primary
ms.date: 09/18/2026
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 09/18/2026
ai-usage: ai-assisted
---

# Sust. Standard Sales Quote (report)

The **Sust. Standard Sales Quote** report extends the standard sales quote layout by adding sustainability data to the document. It shows CO2e per unit on each item line and a total CO2e figure in the report totals, using the emission unit of measure configured in the Sustainability Setup. The report also pulls in a document-specific disclaimer for sales quotes and reuses the existing quote layout. For example, it includes customer and company addresses, document number and date, your reference, quote valid-to date, salesperson, payment terms, and shipment method.

You can filter the report by the same filters as the **Standard Sales - Quote** report, such as sales quote number and customer because this extension only adds sustainability columns and doesn't introduce new filter fields. The line data and the emission unit of measure and emission decimal places you set up on the **Sustainability Setup** page determine the CO2e values.

## Use cases

[!INCLUDE [report-6298-scenario](../includes/report-6298-scenario-include.md)]

Sales representatives can use the report to:

* Send a sales quote to a customer that includes CO2e per unit and total CO2e alongside price, discount, and VAT for each line.
* Show customers a carbon disclaimer relevant to sales quotes if you configure a sustainability disclaimer setup.
* Reuse the existing quote header details, including the valid-to date, payment terms, and shipment method, without extra manual entry.

Sustainability and environmental, social, and governance coordinators can use the report to:

* Verify that emission data per unit and cumulative CO2e totals are correctly reflected on outgoing sales quotes.
* Confirm the Emission Unit of Measure Code and Emission Decimal Places settings in Sustainability Setup produce the expected formatting on customer-facing documents.
* Review or update the sales quote disclaimer text used to communicate emissions data to customers.

## Try the report

Try the report here: [Sust. Standard Sales Quote](https://businesscentral.dynamics.com?report=6298)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Sales reports](../sales-reports.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
