---
title: Czech Local Functionality VAT correction in Local Currency
description: Learn how to use the VAT correction in local currency feature in the Czech version of Business Central.
author: v-pejano
ms-service: dynamics-365-business-central
ms.topic: article
ms.search.keywords: Czech, Finance, VAT, Localization, CZ
ms.date: 03/30/2026
ms.reviewer: v-soumramani
ms.author: v-jurxova
---

# VAT correction in local currency in the Czech version

The current system allows you to adjust input VAT only in the currency of the document, not in the local currency. According to domestic legislation, the conversion of the VAT amount to CZK must be stated on domestic documents issued in a foreign currency, and the recipient of the invoice is obliged to comply with these amounts. Therefore, the option to make a VAT correction in the local currency is added to the process of posting a purchase invoice, or to post this correction from an already posted document.

You can adjust VAT amounts in local currency on posted sales invoices issued in foreign currency as well. The functionality mirrors the existing process for purchase invoices:

- The action Correct VAT in Local Currency is available on posted sales invoices in foreign currency (hidden for invoices in local currency).
- Users can increase or decrease the VAT amount and post the difference to a dedicated rounding account defined in VAT Posting Setup.
- A new field Rounding Account for VAT Correction in Local Currency has been added to the Sales tab in VAT Posting Setup.
- The correction entries are filtered by document number and posted using the same logic as purchase corrections.

> [!Note]  
> When posting a sales document in a foreign currency, the VAT LCY Correction page is displayed only if the field **Show VAT Corr When Posting** is enabled in Sales & Receivables Setup.  

## Related information

- [Core localization pack for Czech](ui-extensions-core-localization-pack-cz.md)  
- [Czech local functionality](czech-local-functionality.md)  
- [Finance](../../finance.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
