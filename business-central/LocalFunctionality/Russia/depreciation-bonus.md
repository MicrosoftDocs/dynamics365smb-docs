---
title: Depreciation bonus in Russia
description: Learn about the depreciation bonus feature for fixed assets in Russian tax accounting.
author: DianaMalina
ms.topic: article
ms.search.keywords: depreciation, depreciation bonus, bonus calculation, selecting depreciation bonus, canceling depreciation bonus, bonus transactions, Russia
ms.date: 10/23/2026
ms.reviewer: jswymer
ms.author: jswymer
ms.service: dynamics-365-business-central
ai-usage: ai-assisted
---

# Depreciation bonus

Depreciation bonus lets you include a configured percentage of fixed asset and capital investment expenses in the current period for tax accounting. Confirm the applicable percentage and eligibility under current requirements before you configure the calculation.

## Depreciation bonus calculation

A depreciation bonus can be calculated and applied for the following types of transactions:

- Acquisition costs of fixed assets.
- Acquisition costs and appreciation of capital investments for all previous periods excluding the current period.

Set the percentage for a depreciation group in the **Depr. Bonus %** field. The percentage is transferred to the fixed asset depreciation book when you assign the depreciation group.

After depreciation bonus is posted, the processed base entries are no longer marked as depreciation bonus base entries. The ledger entries aren't deleted.

## Depreciation bonus settings

Before depreciation bonus is calculated, you have to make sure that the appropriate settings have been applied in the **Tax Register Setup** window. Use the information in the following table to apply depreciation bonus settings.

| Field | Description |
|:---|:---|
| **Rel. Act as Depr. Bonus Base** | Select if you want fixed asset releases to be used to calculate the depreciation bonus base. |
| **Depr. Bonus TD Code** | Enter a tax difference code that is used to calculate the depreciation bonus. The selected tax difference code should be identified as a depreciation bonus during tax difference setup. |
| **Depr. Bonus Recovery from** | Enter the starting date from which depreciation is recovered if the fixed asset is sold. If the fixed asset is sold before this date and the depreciation bonus has already been applied, the depreciation bonus isn't recovered. |
| **Depr. Bonus Recov. Per. (Year)** | Enter the period in which the depreciation bonus is recovered if the fixed asset is sold. |
| **Depr. Bonus Recovery TD Code** | Enter the tax difference code that is used to calculate the depreciation bonus recovery amount in tax accounting. |

## Select and cancel depreciation bonus transactions

Depreciation bonus transactions should be posted before the monthly depreciation amount is calculated and posted.

To select depreciation bonus transactions for posting for a period, select **Depr. Bonus** in the **Fixed Asset Journal** window and the **Fixed Asset G/L Journal** window.

You can cancel depreciation bonus transactions by running the **Cancel FA Ledger Entries** batch job. After posting the depreciation bonus cancellation, all operations that are included in the depreciation bonus base must be manually selected as the depreciation bonus base.

## Related information

[Fixed Assets](fixed-assets.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
