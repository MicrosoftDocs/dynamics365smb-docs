---
title: Register VAT on Purchase Orders in Russia
description: Learn how to register VAT on purchase orders in Russia using Business Central's enhanced tracking features to maintain accurate VAT invoice records
author: DianaMalina
ms.topic: how-to
ms.search.keywords: VAT registration, purchase orders, Russia
ms.date: 07/16/2025
ms.reviewer: v-soumramani
ms.author: soalex
ms.service: dynamics-365-business-central
---

# Register VAT on purchase orders

In Russia, organizations are required to keep a journal of received and issued VAT invoices. [!INCLUDE[prod_short](../../includes/prod_short.md)] enables you to register VAT on purchase orders so that the information is tracked in the VAT invoices journal.

## Steps to register VAT on a purchase order

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Order**, and then choose the related link. Select the relevant purchase order.

1. On the **Shipping** FastTab, fill in the fields as described in the following table.

   | Field | Description |
   |:-|:-|
   | **Vendor Receipts No.** | Enter the identification number from the vendor receipt. |
   | **Vendor Receipts Date** | Enter the date from the vendor receipt. |

1. On the **VAT** FastTab, fill in the fields as described in the following table.

   | Field | Description |
   |:-|:-|
   | **Vendor VAT Invoice No.** | Enter the invoice number from the original VAT transaction. |
   | **Vendor VAT Invoice Date** | Enter the invoice date from the original VAT transaction. |
   | **Vendor VAT Invoice Rcvd Date** | Enter the date that the purchase was received. |

   The VAT transaction is now registered and will be tracked in the VAT invoices journal after the purchase order is posted.

## Related information

- [Set Up VAT Ledgers](How-to-Set-Up-VAT-Ledgers.md)  
- [Prepare VAT Entries for Posting](How-to-Prepare-VAT-Entries-for-Posting.md)  
- [Report VAT to Tax Authorities](../../finance-how-report-vat.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
