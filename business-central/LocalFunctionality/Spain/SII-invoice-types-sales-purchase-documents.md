---
title: SII Invoice and Credit Memo Types for Spain
description: Learn how Business Central for Spain exports SII invoice and credit memo types, including simplified invoices and replacement corrective invoices.
author: brentholtorf   
ms.topic: reference
ms.devlang: al
ms.search.keywords: SII, SII requirements, invoice types, memo types, sales invoices, sales credit memos, purchase invoices, purchase credit memos, Spanish version
ms.search.form: 10751, 10752, 10753, 10770, 10771
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# SII - Invoice and credit memo types in sales and purchase documents

[!INCLUDE[prod_short](../../includes/prod_short.md)] supports the Spanish SII requirements for value-added tax (VAT) reporting (Immediate Information Supply).  

Learn more in [Set Up SII for VAT Reporting in the Spanish Version](sii-setup.md) for information about how to set up [!INCLUDE [prod_short](../../includes/prod_short.md)] for SII.

The following sections show the output of the various types that are used for invoices and credit memos and how they're implemented in the Spanish version of [!INCLUDE[prod_short](../../includes/prod_short.md)].

## Sales invoices

|Type|Description|Implementation|
|--|--|--|
|F1|Invoice|Normal invoice.|
|F2|Simplified invoice (ticket)|The `Contraparte` block is omitted. `ImporteTotal` and `Macrodato` are included when the export's total-node conditions are met.|
|F3|Invoice issued to replace simplified invoices issued and filed|Same as for F1.|
|F4|Invoice summary entry|Possible, but the XML file is same as for F1 because [!INCLUDE[prod_short](../../includes/prod_short.md)] doesn't support summary invoices.<br><br/>Submissions result in known error: Missing `NumSerieFacturaEmisorResumenFin` element.|
|R1|Corrected invoice (error based on art. 80.1, 80.2, and 80.6 LIVA)|Exported as a replacement corrective invoice.|
|R2|Corrected invoice (art. 80.3)|Exported as a replacement corrective invoice.|
|R3|Corrected invoice (art. 80.4)|Exported as a replacement corrective invoice.|
|R4|Corrected invoice (other)|Exported as a replacement corrective invoice.|
|R5|Corrected invoice in simplified invoices|Exported as a replacement corrective invoice, without `Contraparte`.|

## Sales credit memos

|Type|Description|Implementation|
|--|--|--|
|F1|Invoice|Same structure as for sales invoice type F1, but with negative values.|
|F2|Simplified invoice (ticket)|Same as for sales invoice type F2, but with negative values.|
|F3|Invoice issued to replace simplified invoices issued and filed|Same as for sales invoice type F3, but with negative values.|
|F4|Invoice summary entry|Not supported.|
|R1|Corrected invoice (error based on art. 80.1, 80.2, and 80.6 LIVA)|Normal credit memo.|
|R2|Corrected invoice (art. 80.3)|Same as for R1.|
|R3|Corrected invoice (Art. 80.4)|Same as for R1.|
|R4|Corrected invoice (other)|Same as for R1.|
|R5|Corrected invoice in simplified invoices|Same as for R1, except the `Contraparte` block is omitted.|

## Purchase invoices

|Type|Description|Implementation|
|--|--|--|
|F1|Invoice|Normal invoice.|
|F2|Simplified invoice (ticket)|Uses the purchase invoice export structure. `ImporteTotal` and `Macrodato` are included when the export's total-node conditions are met.|
|F3|Invoice issued to replace simplified invoices issued and filed|Same as for F1.|
|F4|Invoice summary entry|Possible, but the XML file is same as for F1 because [!INCLUDE[prod_short](../../includes/prod_short.md)] doesn't support Summary invoices.<br><br/>Submissions result in known error: Missing `NumSerieFacturaEmisorResumenFin` element.|
|F5|Imports (DUA)|Same as for F1.|
|F6|Accounting support material|Same as for F1.|
|R1|Corrected invoice (error based on art. 80.1, 80.2, and 80.6 LIVA)|Exported as a replacement corrective invoice.|
|R2|Corrected invoice (art. 80.3)|Exported as a replacement corrective invoice.|
|R3|Corrected invoice (art. 80.4)|Exported as a replacement corrective invoice.|
|R4|Corrected invoice (other)|Exported as a replacement corrective invoice.|
|R5|Corrected invoice in simplified invoices|Exported as a replacement corrective invoice.|

## Purchase credit memos

|Type|Description|Implementation|
|--|--|--|
|F1|Invoice|Same structure as for purchase invoice type F1, but with negative values.|
|F2|Simplified invoice (ticket)|Same as for purchase invoice type F1, but with negative values.|
|F3|Invoice issued to replace simplified invoices issued and filed|Not possible.|
|F4|Invoice summary entry|Not possible.|
|F5|Imports (DUA)|Not possible.|
|F6|Accounting support material|Not possible.|
|R1|Corrected invoice (error based on Art. 80.1, 80.2, and 80.6 LIVA)|Normal credit memo.|
|R2|Corrected invoice (art. 80.3)|Same as for R1.|
|R3|Corrected invoice (art. 80.4)|Same as for R1.|
|R4|Corrected invoice (other)|Same as for R1.|
|R5|Corrected invoice in simplified invoices|Uses the purchase corrective invoice export structure, including `Contraparte`.|

## Related information

- [Set Up SII for VAT Reporting in the Spanish Version](sii-setup.md)  
- [Spain Local Functionality](spain-local-functionality.md)  
<!--[Setup and user guide for electronic VAT information under SII in the Spanish version of Dynamics NAV](https://aka.ms/SIISetup)  -->

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
