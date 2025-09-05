---
title: Depreciation bonus in Russia
description: Learn about the depreciation bonus feature for fixed assets in Russian tax accounting.
author: DianaMalina
ms.topic: article
ms.search.keywords: depreciation, depreciation bonus, bonus calculation, selecting depreciation bonus, canceling depreciation bonus, bonus transactions, Russia
ms.date: 07/11/2025
ms.reviewer: v-soumramani
ms.author: soalex
ms.service: dynamics-365-business-central
---

# Depreciation bonus

Depreciation bonus is an accelerated depreciation method applied in tax accounting because of provisions in the Russian tax laws. A depreciation bonus enables you to include fixed asset and capital investment expenses in the current period at the rate of 10 percent or 30 percent.

## Depreciation bonus calculation

A depreciation bonus can be calculated and applied for the following types of transactions:

- Acquisition costs of fixed assets.
- Acquisition costs and appreciation of capital investments for all previous periods excluding the current period.

The rate of the depreciation bonus is 10 percent or 30 percent, depending on the class of the fixed asset. The rate is set for a depreciation group using the **Depr. Bonus Percentage** field in the **Depreciation Group** window.

After the depreciation bonus is calculated and posted for a period, all transactions are cleared in preparation for the next period.

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
