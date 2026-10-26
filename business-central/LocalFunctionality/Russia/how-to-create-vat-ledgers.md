---
title: Creating VAT Ledgers in Russia
description: Learn how to create VAT ledgers in Business Central for Russian businesses, including sales and purchase ledgers for different customer groups.
author: DianaMalina
ms.topic: how-to
ms.search.keywords: VAT ledger, sales ledger, purchase ledger, Russia
ms.date: 10/23/2026
ms.reviewer: jswymer
ms.author: jswymer
ms.service: dynamics-365-business-central
ai-usage: ai-assisted
---

# Create VAT ledgers

You can create and store any number of VAT ledgers. For example, you can create the following:

- Sales ledgers for different groups of customers
- Additional sales ledgers for amount differences and prepayments
- Joint sales ledgers for the whole company

## Create a VAT ledger

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Ledger List**, and then choose the related link.

1. In the **VAT Ledger List** window, fill in the fields as described in the following table.

   | Field | Description |
   |:-|:-|
   | **Type** | Select the type of VAT ledger. |
   | **Code** | Specifies the VAT ledger identifier. New ledger codes are assigned from the purchase or sales VAT ledger number series in **General Ledger Setup**. |
   | **Description** | Enter a description for the VAT ledger. |
   | **Accounting Period** | Enter the accounting period of the VAT ledger. You can view the available accounting periods in the **Accounting Periods** window. |
   | **Start Date** | Specifies the start date of the accounting period of the VAT ledger. |
   | **End Date** | Specifies the end date of the accounting period of the VAT ledger. |

1. To add lines to the VAT ledger, choose the **Create Ledger** action.

1. In the **Create VAT Purchase Ledger** or the **Create VAT Sales Ledger** window, fill in the fields, and then choose the **OK** button.

   The VAT ledger is now created and available for use.

1. To view the VAT ledger, choose the **Card** action.

Now, you can print the VAT ledger as a VAT ledger or as an additional sheet.

## Related information

- [VAT Ledgers](vat-ledgers.md)  
- [Set Up VAT Ledgers](how-to-set-up-vat-ledgers.md)  
- [Create Additional Sheets](how-to-create-additional-sheets.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
