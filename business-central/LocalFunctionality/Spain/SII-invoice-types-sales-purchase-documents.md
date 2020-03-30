---
    title: Overview of SII Invoice Types in Sales and Purchase Documents
    description: Shows the output of the various types that are used for invoices and credit memos in connection with SII and how they are implemented.

    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# SII - Invoice and Credit Memo Types in Sales and Purchase Documents
[!INCLUDE[d365fin](../../includes/d365fin_md.md)] supports the Spanish SII requirements for VAT reporting (Immediate Information Supply). For more information, see [Setup and user guide for electronic VAT information under SII in the Spanish version of Dynamics NAV](https://aka.ms/SIISetup).

The following table shows the output of the various types that are used for invoices and credit memos in connection with SII and how they are implemented in [!INCLUDE[d365fin](../../includes/d365fin_md.md)].

## Sales Invoices
|Type|Description|Implementation|
|--|--|--|
|F1|Invoice|Normal invoice|
|F2|Simplified invoice (ticket)|Implemented as for F1, except a non-existing block is called “Contraparte” and additional nodes are called “ImporteTotal” and “Macrodato”.|
|F3|Invoice issued to replace simplified invoices issued and filed|Same as Normal invoice|
|F4|Invoice summary entry|Possible, but the XML file is same as for F1 because [!INCLUDE[d365fin](../../includes/d365fin_md.md)] does not support Summary invoices. <br /><br />Submissions will result in known error: Missing “NumSerieFacturaEmisorResumenFin” element.|
|R1|Corrected invoice (Error based on Art. 80.1, 80.2, and 80.6 LIVA)|Not supported. Only used for credit memos.|
|R2|Corrected invoice (Art. 80.3)|Not supported. Only used for credit memos|
|R3|Corrected invoice (Art. 80.4)|Not supported. Only used for credit memos|
|R4|Corrected invoice (other)|Not supported. Only used for credit memos|
|R5|Corrected invoice in simplified invoices|Not supported. Only used for credit memos|

## Sales Credit Memos
|Type|Description|Implementation|
|--|--|--|
|F1|Invoice|Same structure as sales invoice, type F1, but with negative values|
|F2|Simplified invoice (ticket)|Same structure as sales invoice type F2, but with negative values|
|F3|Invoice issued to replace simplified invoices issued and filed|Not supported|
|F4|Invoice summary entry|Not supported|
|R1|Corrected invoice (Error based on Art. 80.1, 80.2, and 80.6 LIVA)|Normal credit memo|
|R2|Corrected invoice (Art. 80.3)|Same as normal credit memo|
|R3|Corrected invoice (Art. 80.4)|Same as normal credit memo|
|R4|Corrected invoice (other)|Same as normal credit memo|
|R5|Corrected invoice in simplified invoices|Same as normal credit memo except the block is called “Contraparte”.|

## Purchase Invoices
|Type|Description|Implementation|
|--|--|--|
|F1|Invoice|Normal invoice|
|F2|Simplified invoice (ticket)|Implemented as for F1, except a non-existing block is called “Contraparte” and additional nodes are called “ImporteTotal” and “Macrodato”.|
|F3|Invoice issued to replace simplified invoices issued and filed|Sames as for Normal invoice|
|F4|Invoice summary entry|Possible, but the XML file is same as for F1 because [!INCLUDE[d365fin](../../includes/d365fin_md.md)] does not support Summary invoices. <br /><br />Submissions will result in known error: Missing “NumSerieFacturaEmisorResumenFin” element.|
|F5|Imports (DUA)|Same as for Normal invoice|
|F6|Accounting support material|Sames as for Normal invoice|
|R1|Corrected invoice (Error based on Art. 80.1, 80.2, and 80.6 LIVA)|Not supported. Only used for credit memos|
|R2|Corrected invoice (Art. 80.3)|Not supported. Only used for credit memos|
|R3|Corrected invoice (Art. 80.4)|Not supported. Only used for credit memos|
|R4|Corrected invoice (other)|Not supported. Only used for credit memos|
|R5|Corrected invoice in simplified invoices|Not supported. Only used for credit memos|

## Purchase Credit Memos
|Type|Description|Implementation|
|--|--|--|
|F1|Invoice|Same structure as for purchase invoice, type F1, but with negative values|
|F2|Simplified invoice (ticket)|Same structure as for purchase invoice, type F1, but with negative values|
|F3|Invoice issued to replace simplified invoices issued and filed|Not possible|
|F4|Invoice summary entry|Not possible|
|F5|Imports (DUA)|Not possible|
|F6|Accounting support material|Not possible|
|R1|Corrected invoice (Error based on Art. 80.1, 80.2, and 80.6 LIVA)|Normal credit memo|
|R2|Corrected invoice (Art. 80.3)|Same as normal credit memo|
|R3|Corrected invoice (Art. 80.4)|Same as normal credit memo|
|R4|Corrected invoice (other)|Same as normal credit memo|
|R5|Corrected invoice in simplified invoices|Same as for normal credit memo except the block is called “Contraparte”|

## See Also  
[Spain Local Functionality](spain-local-functionality.md)
