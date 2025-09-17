---
title: Setting up tax difference calculation in Russia
description: Enables calculation of tax differences for fixed assets as part of Russian localization enhancements.
author: DianaMalina
ms.topic: how-to
ms.search.keywords: tax difference calculation, tax difference journal, posting groups, tax difference setup, Russia
ms.date: 07/21/2025
ms.reviewer: v-soumramani
ms.author: soalex
ms.service: dynamics-365-business-central
---

# Set up tax difference calculation

Tax difference calculations must be set up if there's a tax difference for the presentation of fixed asset entries, item cost entries, or finance transactions in bookkeeping and tax accounting for which expenses to write off must be fixed. To set tax difference, choose the **Setup** action, and then choose the **Tax Differences** action.

## Set up posting groups

In the **Tax Difference Posting Groups** you must determine finance accounts from the set-up chart of accounts, where finance transactions with tax differences are accounted for.

If there are journal lines that must be normalized before writing off expenses, those journals can't be posted without running a periodic job of normalizing.

The following procedure shows how to process a normalization function.

1. In the **Future Expenses Journal** window, choose the **Calculate Depreciation by Norm.** action
1. In the **Calculate FE Depr. With Norm** window, on the **Tax Difference** FastTab, enter the filter for the tax difference.
1. On the **Options** FastTab, enter the accounting period for which the counting is done.
1. Choose the **Print** action to print the report.
1. Post the future expenses journal.

## Related information

- [Tax Registers](Tax-Registers.md)  
- [Tax Differences](Tax-Differences.md)  
- [Tax Difference Registers](Tax-Difference-Registers.md)  
- [Set Up Norm Jurisdictions](How-to-Set-Up-Norm-Jurisdictions.md)  
- [Post Tax Differences](How-to-Post-Tax-Differences.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
