---
title: SII Invoice Types in Sales and Purchase Documents
description: Learn how Business Central supports SII and the different invoice and credit memo types used in the Spanish version.
author: brentholtorf   
ms.topic: article
ms.devlang: al
ms.search.keywords: SII, SII requirements, invoice types, memo types, sales invoices, sales credit memos, purchase invoices, purchase credit memos, Spanish version
ms.search.form: 10751, 10752, 10753, 10770, 10771
ms.date: 05/29/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# SII - Invoice and credit memo types in sales and purchase documents

[!INCLUDE[prod_short](../../includes/prod_short.md)] supports the Spanish SII requirements for value-added tax (VAT) reporting (Immediate Information Supply).  

Learn more in [Set Up SII for VAT Reporting in the Spanish Version](sii-setup.md) for information about how to set up [!INCLUDE [prod_short](../../includes/prod_short.md)] for SII.

The following sections show the output of the various types that are used for invoices and credit memos and how they're implemented in the Spanish version of [!INCLUDE[prod_short](../../includes/prod_short.md)].

## Sales invoices

|Type|Description|Implementation|
|--|--|--|
|F1|Invoice|Normal invoice.|
|F2|Simplified invoice (ticket)|Same structure as for F1, except a non-existing block is called `Contraparte` and other nodes are called `ImporteTotal` and `Macrodato`.|
|F3|Invoice issued to replace simplified invoices issued and filed|Same as for F1.|
|F4|Invoice summary entry|Possible, but the XML file is same as for F1 because [!INCLUDE[prod_short](../../includes/prod_short.md)] doesn't support summary invoices.<br><br/>Submissions result in known error: Missing `NumSerieFacturaEmisorResumenFin` element.|
|R1|Corrected invoice (error based on art. 80.1, 80.2, and 80.6 LIVA)|Not supported. Only used for credit memos.|
|R2|Corrected invoice (art. 80.3)|Not supported. Only used for credit memos.|
|R3|Corrected invoice (art. 80.4)|Not supported. Only used for credit memos.|
|R4|Corrected invoice (other)|Not supported. Only used for credit memos.|
|R5|Corrected invoice in simplified invoices|Not supported. Only used for credit memos.|

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
|R5|Corrected invoice in simplified invoices|Same as for R1 except the block is called `Contraparte`.|

## Purchase invoices

|Type|Description|Implementation|
|--|--|--|
|F1|Invoice|Normal invoice.|
|F2|Simplified invoice (ticket)|Same structure as for F1, except a non-existing block is called `Contraparte` and other nodes are called `ImporteTotal` and `Macrodato`.|
|F3|Invoice issued to replace simplified invoices issued and filed|Same as for F1.|
|F4|Invoice summary entry|Possible, but the XML file is same as for F1 because [!INCLUDE[prod_short](../../includes/prod_short.md)] doesn't support Summary invoices.<br><br/>Submissions result in known error: Missing `NumSerieFacturaEmisorResumenFin` element.|
|F5|Imports (DUA)|Same as for F1.|
|F6|Accounting support material|Same as for F1.|
|R1|Corrected invoice (error based on art. 80.1, 80.2, and 80.6 LIVA)|Not supported. Only used for credit memos.|
|R2|Corrected invoice (art. 80.3)|Not supported. Only used for credit memos.|
|R3|Corrected invoice (art. 80.4)|Not supported. Only used for credit memos.|
|R4|Corrected invoice (other)|Not supported. Only used for credit memos.|
|R5|Corrected invoice in simplified invoices|Not supported. Only used for credit memos.|

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
|R5|Corrected invoice in simplified invoices|Same as for R1 except the block is called `Contraparte`.|

## Related information

- [Set Up SII for VAT Reporting in the Spanish Version](sii-setup.md)  
- [Spain Local Functionality](spain-local-functionality.md)  
<!--[Setup and user guide for electronic VAT information under SII in the Spanish version of Dynamics NAV](https://aka.ms/SIISetup)  -->

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
