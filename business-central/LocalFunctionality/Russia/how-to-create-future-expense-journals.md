---
title: Creating future expense journals in Russia
description: Russian localization includes functionality for managing future expenses in Business Central.
author: DianaMalina
ms.topic: how-to
ms.search.keywords: future expense journals, Russia, localization
ms.date: 07/14/2025
ms.reviewer: v-soumramani
ms.author: soalex
ms.service: dynamics-365-business-central
---

# Create future expense journals

Future expense journals are used to post expenses to a special account on a monthly basis. These future expenses are later included as expenses. VAT is deducted when future expenses are included in current expenses.

You must select **Future Expenses** in the **Type** field of the **General Journal Templates** window. In addition, be sure you select the **Recurring** and **Copy VAT Setup to Jnl. Lines** check boxes in the **General. Journal Templates** window.

## Steps to create future expense journals

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Posting Setup**, and then choose the related link.

   Use the **VAT Posting Setup** window to create VAT posting groups. For more information, see [Report VAT to Tax Authorities](../../finance-how-report-vat.md).

1. On the **Settlement** FastTab, in the **VAT Settlement Template** field, select a template.

1. Select a batch in the **VAT Settlement Batch** field. This determines the batch where future expenses and VAT are produced.

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Invoices**, and then choose the related link.

1. Create a purchase invoice for the Deferral general ledger account (97).

1. Create and post the payment and apply the invoice and payment.

   VAT isn't deducted at this time. It's deducted later, on a monthly basis through the Future Expense Journal.

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Future Expense Journals**, and then choose the related link.

1. In the **Future Expense Journal** window, fill in the fields as described in the following table.

   | Field | Description |
   |:-|:-|
   | **FA Posting Date** | Specifies the fixed asset posting date that is associated with the future expense journal. |
   | **Document No.** | Specifies the document number that is associated with the future expense journal. |
   | **FA No.** | Specifies the fixed asset number that is associated with the future expense journal. |
   | **Depreciation Book Code** | Specifies the depreciation book code that is associated with the future expense journal. |
   | **FA Posting Type** | Specifies the fixed asset posting type that is associated with the future expense journal. Fixed asset posting types include **Acquisition Cost**, **Depreciation**, **Write-Down**, **Appreciation**, **Custom 1**, **Custom 2**, **Disposal**, **Maintenance**, **Salvage Value**, and **Transfer**. |
   | **Description** | Specifies the description that is associated with the future expense journal. |
   | **Location Code** | Specifies the location code that is associated with the future expense journal. |
   | **Amount** | Specifies the amount that is associated with the future expense journal. |
   | **Depr. Amount w/o Normalization** | Specifies the depreciation amount without normalizations that is associated with the future expense journal. |
   | **Actual Quantity** | Specifies the actual quantity that is associated with the future expense journal. |
   | **Calc. Quantity** | Specifies the calculated quantity that is associated with the future expense journal. |
   | **Actual Amount** | Specifies the actual amount that is associated with the future expense journal. |
   | **Calc. Amount** | Specifies the calculated amount that is associated with the future expense journal. |
   | **Actual Remaining Amount** | Specifies the actual remaining amount that is associated with the future expense journal. |
   | **Salvage Amount** | Specifies the salvage amount that is associated with the future expense journal. |
   | **No. of Depreciation Days** | Specifies the number of depreciation days that is associated with the future expense journal. |
   | **Depr. Until FA Posting Date** | Specifies if the depreciation until fixed asset posting date is used with the future expense journal. |
   | **Depr. Acquisition Cost** | Specifies if the depreciation acquisition cost is used with the future expense journal. |
   | **Duplicate in Depreciation Book** | Specifies the duplicate in depreciation book that is associated with the future expense journal. |
   | **FA Error Entry No.** | Specifies the fixed asset error entry number that is associated with the future expense journal. |

1. Choose the **Post** action.

The amount entered in the **Amount** field is transferred from the Future Expenses account to the Current Expenses account. VAT is calculated according to VAT setup (percentage) on the basis of the posted amount, and VAT deduction (realized VAT) is posted.

## Related information

[Fixed Assets](fixed-assets.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
