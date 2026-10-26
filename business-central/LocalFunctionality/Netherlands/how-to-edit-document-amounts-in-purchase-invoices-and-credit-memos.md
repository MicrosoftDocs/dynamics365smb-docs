---
title: Edit Dutch Purchase Invoice and Credit Memo Document Amounts
description: Enter expected purchase invoice and credit memo totals in the Dutch version of Business Central to check the document and VAT amounts before posting.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: purchase invoices, edit credit memos, document amounts, Dutch version, Netherlands
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Edit document amounts in purchase invoices and credit memos in the Dutch version

[!INCLUDE[prod_short](../../includes/prod_short.md)] lets you enter the total amount and VAT amount from a vendor's invoice or credit memo. These amounts are used to check the purchase document totals before posting.

Enable **Check Doc. Total Amounts** on the **Purchases & Payables Setup** page to display the document amount fields. Learn more in [Set up validation of purchase amounts](../../how-to-set-up-validation-of-purchase-amounts.md).

## Edit document amounts  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Purchase Invoices** or **Purchase Credit Memos**, and then choose the related link.
1. Open the invoice or credit memo that you want to edit.
1. Edit the document amount in the **Doc. Amount Incl. VAT** field and the **Doc. Amount VAT** field.  

For purchase lines that use normal VAT, changing **Doc. Amount Incl. VAT** can recalculate **Doc. Amount VAT** proportionally from the purchase line totals. The VAT amount is checked against the calculated amount and the allowed VAT difference.

These fields record the expected document totals. They don't replace the purchase lines. Review the lines and VAT setup if the calculated totals don't match the vendor's document. An e-document service can make the imported document amount fields read-only.

## Related information

- [Create Recurring Sales and Purchase Lines](../../sales-how-work-standard-lines.md)   
- [Netherlands Local Functionality](netherlands-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
