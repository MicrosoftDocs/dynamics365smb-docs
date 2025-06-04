---
title: Electronic Invoicing [FatturaPA]
description: Business Central enables you to export sales invoices and credit memos as electronic documents (FatturaPA) in compliance with Italian regulations.
author: altotovi
ms.author: altotovi
ms.reviewer: v-soumramani
ms.search.keywords: FatturaPA, electronic invoicing setup, Italian version
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.date: 05/20/2025
ms.custom: bap-template
---

# Electronic invoicing (FatturaPA) in the Italian version

This article provides information that helps you to get started with Electronic invoicing for Italy in [!INCLUDE[prod_short](../../includes/prod_short.md)].

Electronic invoice in Italy is named as FatturaPA. **FatturaPA** stands for **Fatturazione Elettronica verso la Pubblica Amministrazione** and translated means: “Electronic invoice to the public administration”. The term covers all technical and organizational measures for electronic invoicing to public administration. Authorities only accept e-invoices through the Sistema di Interscambio (SDI) platform, which is the official exchange system.

## Set up electronic invoicing

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Fattura Setup**, and then choose the related link.
1. On the **Fattura Setup** page, on the **General** FastTab, in the **Self-Billing VAT Bus. Group** field, specify the **VAT Business Posting Group** that is used for VAT entries related to self-billing documents.
1. In the **Company PA Code** field, specify the code to be reported in the **CodiceDestinetario XML** node for self-billing documents.
1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Fattura Document Type List**, and then choose the related link.  
1. Create the different type of electronic documents using the following columns:

   |Field|Description|  
   |------------------------------------|---------------------------------------|
   |**No.**| Specifies the document type code that is exported to the XML file.|
   |**Description**|Specifies a description of the document type. You can enter a maximum of 250 characters, both numbers and letters.|
   |**Invoice**|Specifies the document type that is the default for invoices.|
   |**Credit Memo**|Specifies the document type that is the default for credit memos.|
   |**Self-Billing**|Specifies the document type that is the default for self-billing documents.|
   |**Prepayment**|Specifies the document type that is the default for prepayments.|

## Related information

[Italy Local Functionality](italy-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
