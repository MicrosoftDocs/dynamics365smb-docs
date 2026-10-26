---
title: VAT Recalculation and Cash-Basis VAT in Mexico
description: Set up cash-basis VAT in Business Central to recognize VAT on customer payments and account for exchange-rate differences on foreign-currency invoices.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: exchange rate, foreign currency, invoice payment
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# VAT recalculation

Use cash-basis VAT to recognize VAT when an invoice is paid. For a foreign-currency invoice, the VAT calculation can also account for exchange-rate differences when the payment is applied.

When you post the invoice, VAT is recorded as unrealized VAT. When you apply and post the payment, the relevant amount moves to the realized VAT account. With **Cash Basis** selected, foreign-currency applications with an exchange gain or loss also adjust the realized VAT amount using the payment's currency factor.

## Set up cash-basis VAT

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **General Ledger Setup**, and then choose the related link.
1. Turn on **Unrealized VAT**.
1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **VAT Posting Setup**, and then choose the related link.
1. For the relevant posting-group combinations, set **Unrealized VAT Type** to **Cash Basis**. Specify **Sales VAT Account** and **Sales VAT Unreal. Account**.
1. On **Currencies**, verify **Realized Gains Acc.** and **Realized Losses Acc.** for each foreign currency you use.

Learn more in [Set up unrealized VAT](../../finance-setup-unrealized-vat.md).

## Post and review payments

1. Post the foreign-currency sales invoice using the configured VAT posting groups.
1. Register the customer payment with the appropriate exchange rate for the payment date.
1. Apply the payment to the invoice and post it. [!INCLUDE[prod_short](../../includes/prod_short.md)] posts the VAT realization and applicable exchange-rate adjustment automatically.
1. Review the resulting VAT and G/L entries and use a VAT statement to report the relevant amounts.

## Related information

[Report VAT to Tax Authorities](../../finance-how-report-vat.md)   
[Mexico Local Functionality](mexico-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
