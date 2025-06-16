---
title: Setting up VAT ledgers in Russia
description: Russian enhancements include VAT ledgers.
author: DianaMalina


ms.topic: how-to
ms.search.keywords:
ms.date: 04/01/2021
ms.reviewer: bholtorf
ms.author: soalex
ms.service: dynamics-365-business-central
---

# Set Up VAT Ledgers

VAT ledgers are used to store details about VAT in transactions that involve goods and services in Russia or goods imported into Russia. You can create and store different kinds of VAT ledgers. For example, you can create VAT ledgers for:  

- Sales to different groups of customers
- Sales amount differences and prepayments
- Purchases from different vendor groups

To use VAT ledgers, you must specify the relevant number series.

## To set up VAT ledgers

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Ledger Setup**, and then choose the related link.

2. In the **General Ledger Setup** window, on the **Numbering** FastTab, fill in the fields as described in the following table.

   | Field                            | Description                                                  |
   | :------------------------------- | :----------------------------------------------------------- |
   | **VAT Purch. Ledger No. Series** | Specifies the number series that you want to use for VAT ledgers for purchase documents. |
   | **VAT Sales Ledger No. Series**  | Specifies the number series that you want to use for VAT ledgers for sales documents. |

   You must ensure that vendor purchase documents cannot be posted without stating the invoice date and number.

3. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendor Posting Groups**, and then choose the related link.

4. In the **Vendor Posting Groups** window, for the relevant posting groups, select the **VAT Invoice Mandatory** field.

   Next, you must set up VAT posting. For each VAT posting setup you must specify if entries that use the setup must be included in VAT ledgers.

5. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Posting Setup**, and then choose the related link.

6. In the **VAT Posting Setup** window, for each VAT posting setup, fill in the fields as described in the following table.

   | Field                           | Description                                                  |
   | :------------------------------ | :----------------------------------------------------------- |
   | **Not Include into VAT Ledger** | Specifies if entries that use the setup must be included in VAT ledgers. For more information, see Not Include into VAT Ledger. |
   | **VAT Exempt**                  | Specifies if entries that use this posting setup are VAT exempt. For more information, see VAT Exempt. |

Now, you can create VAT ledgers for purchases and sales.

## Related information

[Report VAT to Tax Authorities](../../finance-how-report-vat.md)  
[Register VAT on Purchase Orders](How-to-Register-VAT-on-Purchase-Orders.md)  
[Prepare VAT Entries for Posting](How-to-Prepare-VAT-Entries-for-Posting.md)  
[Create VAT Ledgers](How-to-Create-VAT-Ledgers.md)  
[Create Additional Sheets](How-to-Create-Additional-Sheets.md)  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
