---
title: Setting Up VAT Ledgers in Russia
description: Learn how to configure VAT ledgers in Russia for tracking VAT transactions on goods, services, and imports.
author: DianaMalina
ms.topic: how-to
ms.search.keywords: VAT ledgers, Russia
ms.date: 10/23/2026
ms.reviewer: jswymer
ms.author: jswymer
ms.service: dynamics-365-business-central
ai-usage: ai-assisted
---

# Set up VAT ledgers

VAT ledgers are used to store details about VAT in transactions that involve goods and services in Russia or goods imported into Russia. You can create and store different kinds of VAT ledgers. For example, you can create VAT ledgers for:  

- Sales to different groups of customers
- Sales amount differences and prepayments
- Purchases from different vendor groups

To use VAT ledgers, you must specify the relevant number series.

## Steps to set up VAT ledgers

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Ledger Setup**, and then choose the related link.

1. In the **General Ledger Setup** window, on the **Numbering** FastTab, fill in the fields as described in the following table.

   | Field | Description |
   |:-|:-|
   | **VAT Purch. Ledger No. Series** | Specifies the number series that you want to use for VAT ledgers for purchase documents. |
   | **VAT Sales Ledger No. Series** | Specifies the number series that you want to use for VAT ledgers for sales documents. |

   You must ensure that vendor purchase documents can't be posted without stating the invoice date and number.

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendor Posting Groups**, and then choose the related link.

1. In the **Vendor Posting Groups** window, for the relevant posting groups, select the **VAT Invoice Mandatory** field.

   Next, you must set up VAT posting. For each VAT posting setup, you must specify if entries that use the setup must be included in VAT ledgers.

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Posting Setup**, and then choose the related link.

1. In the **VAT Posting Setup** window, for each VAT posting setup, fill in the fields as described in the following table.

   | Field | Description |
   |:-|:-|
   | **Not Include into VAT Ledger** | Specifies which VAT ledgers exclude entries that use this setup. Choose **Purchases**, **Sales**, or **Purchases & Sales**, or leave the field blank to exclude neither ledger type. |
   | **VAT Exempt** | Specifies whether entries that use this posting setup are VAT exempt. When you select this field, **VAT %** must be zero. |

Now, you can create VAT ledgers for purchases and sales.

## Related information

- [Report VAT to Tax Authorities](../../finance-how-report-vat.md)  
- [Register VAT on Purchase Orders](how-to-register-vat-on-purchase-orders.md)  
- [Prepare VAT Entries for Posting](how-to-prepare-vat-entries-for-posting.md)  
- [Create VAT Ledgers](how-to-create-vat-ledgers.md)  
- [Create Additional Sheets](how-to-create-additional-sheets.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
