---
title: Print VAT Summary Information on Documents in Iceland
description: Learn how to show VAT summary information on supported purchase and blanket sales order reports with the Icelandic IS Core app in Business Central.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: VAT, VAT summary information, sales document, purchase document
ms.date: 10/23/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Print VAT summary information on documents in the Icelandic version

On supported reports, the Icelandic **IS Core** app normally suppresses the VAT summary when the document uses only one VAT identifier. Select **Always Show VAT Summary** to include the summary in that case.

The app adds this option to the following reports:

- **Order** for purchase orders.
- **Purchase - Invoice**.
- **Purchase - Credit Memo**.
- **Blanket Sales Order**.

The following procedure uses **Purchase - Invoice**. Available print options depend on the report selected for the document.

## Show VAT summary information  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Posted Purchase Invoices**, and then choose the related link.
1. In the list, select the relevant document, and then choose the **Print** action.  
1. On the report request page, select **Always Show VAT Summary**.
1. Choose **Print** or **Preview**.

## Related information

[Report VAT to Tax Authorities](../../finance-how-report-vat.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
