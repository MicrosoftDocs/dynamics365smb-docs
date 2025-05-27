---
title: Setting up tax difference calculation in Russia
description: Russian enhancements include calculation of tax differences for fixed assets.
author: DianaMalina


ms.topic: how-to
ms.search.keywords:
ms.date: 04/01/2021
ms.reviewer: bholtorf
ms.author: soalex
ms.service: dynamics-365-business-central
---

# Setting up Tax Difference Calculation

Tax difference calculations must be set up if there is a tax difference for the presentation of fixed asset entries, item cost entries, or finance transactions in bookkeeping and tax accounting for which expenses to write off must be fixed. To set tax difference, choose the **Setup** action, and then choose the **Tax Differences** action.

## Setting Up Posting Groups

In the **Tax Difference Posting Groups** you must determine finance accounts from the set up chart of accounts, where finance transactions with tax differences are accounted for.

If there are journal lines that must be normalized before writing off expenses, those journals cannot be posted without running a periodic job of normalizing.

The following procedure shows how to process a normalization function.

1. In the **Future Expenses Journal** window, choose the **Calculate Depreciation by Norm.** action
2. In the **Calculate FE Depr. With Norm** window, on the **Tax Difference** FastTab, enter the filter for the tax difference.
3. On the **Options** FastTab, enter the accounting period for which the counting is done.
4. Choose the **Print** action to print the report.
5. Post the future expenses journal.

## Related information

[Tax Registers](Tax-Registers.md)  
[Tax Differences](Tax-Differences.md)  
[Tax Difference Registers](Tax-Difference-Registers.md)  
[Set Up Norm Jurisdictions](How-to-Set-Up-Norm-Jurisdictions.md)  
[Post Tax Differences](How-to-Post-Tax-Differences.md)  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
