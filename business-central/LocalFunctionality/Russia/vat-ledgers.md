---
title: VAT ledgers in Russia
description: Russian localization provides features for managing and reporting VAT ledgers.
author: DianaMalina
ms.topic: article
ms.search.keywords: VAT ledgers, VAT purchase ledger, VAT sales ledger, VAT purchase ledger additional sheet, VAT sales ledger additional sheet, Russia
ms.date: 10/23/2026
ms.reviewer: jswymer
ms.author: jswymer
ms.service: dynamics-365-business-central
ai-usage: ai-assisted
---

# VAT ledgers

The VAT ledger feature enables you to create and print the following windows:

- VAT Purchase Ledger
- VAT Sales Ledger
- VAT Purchase Ledger Additional Sheet
- VAT Sales Ledger Additional Sheet

## VAT purchase ledgers and VAT sales ledgers

Before you can create VAT ledgers, you must set up number series and vendor posting groups. You must also set up VAT posting groups to identify how VAT entries must be included in VAT ledgers. Also, for each VAT posting setup, you must specify if entries that use the setup must be included in VAT ledgers, and if the entries are VAT exempt. For more information, see [Set Up VAT Ledgers](how-to-set-up-vat-ledgers.md).

You can create and store any number of VAT ledgers. For example, you can create the following:

- Sales ledgers for different groups of customers.
- Additional sales ledgers for amount differences and prepayments.
- Joint sales ledgers for the whole company.

To create a VAT ledger, first you must define a VAT ledger type, and then you must add lines to the VAT purchase ledger or VAT sales ledger by using the **Create VAT Purchase Ledger** and **Create VAT Sales Ledger** batch jobs. When you have added lines to the VAT ledger, you can print it.

For more information, see [Create VAT Ledgers](how-to-create-vat-ledgers.md).

## Marking a VAT purchase ledger

The VAT for purchase documents must be reflected in the purchase ledger. Return orders of the customers must be reflected in purchase books.

The following procedure shows how to mark a VAT purchase ledger.

In the **Sales Return Order** window or the **Sales Credit Memo** window, select the **Include in Purch. VAT Ledger** check box.

These marked documents are reflected in the purchase book or in the sales book. Sales return orders are marked by default.

## Related information

- [Set Up VAT Ledgers](how-to-set-up-vat-ledgers.md)  
- [Create VAT Ledgers](how-to-create-vat-ledgers.md)  
- [Create Additional Sheets](how-to-create-additional-sheets.md)  
- [Posting VAT on Sales](posting-vat-on-sales.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
