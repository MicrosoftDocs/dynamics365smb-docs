---
title: FA Depreciation Calculation
description: Learn how to calculate fixed asset depreciation, including FA block, additional depreciation, and multiple shift scenarios for India in Business Central.
author: v-debapd
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English, FA depreciation calculation, FA block, multiple shifts
ms.date: 10/21/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# FA depreciation calculation

## FA depreciation calculation with FA block and additional depreciation

### FA block

Depreciation is allowed on block of assets. Block of assets is a group of assets falling within a class of assets. For Example:

- Tangible assets, being building, machinery, plant, or furniture,
- Intangible assets, being know how, patents, copyrights, trade-marks, licenses, franchises, or any other business or commercial rights of similar nature

### Additional depreciation

The historical additional-depreciation example for machinery or plant acquired and installed after March 31, 2005 uses 20% of actual cost. With a 180-day threshold and a 50% reduction, the example gives 10% in the first year and describes the remaining 10% as claimable in the next year. These are historical assumptions, not a statement of current eligibility or a guarantee that the calculation carries the remainder forward. Configure the block percentage, threshold, and reduction for your applicable requirements.

### Calculate depreciation with FA block and additional depreciation

1. Open the relevant **Fixed Asset Card**, and enable **Add. Depr. Applicable** on the **General** FastTab.
1. Select the relevant **FA Block Code** on the **Posting** FastTab. Enter **Add. Depreciation %** on the selected block.
1. Assign a depreciation book whose **FA Book Type** is **Income Tax**.
1. Choose **Calculate FA Depreciation**, select the depreciation book, and fill in the posting date and other options.
1. Choose **OK**, and review the resulting journal lines.
1. Choose **Post** in the journal.

The calculation creates lines in the **Fixed Asset G/L Journal** when depreciation is integrated with the general ledger. Otherwise, it uses the **Fixed Asset Journal**. Budgeted assets use the fixed asset journal.

## FA depreciation calculation with multiple shifts

Shift depreciation is used when manufacturing companies have multiple production shifts for parts of the year. For example, a company can have one, two, or three shifts during high production season but only one shift during the rest of the year. This means that some fixed assets are used more often than normal during the high production season and they would experience greater depreciation during that time. Being able to adjust the fixed asset's depreciation rates higher makes sense if the fixed asset is active for more than one shift. User can adjust the depreciation using calculated depreciation that is unique to each shift.

### Calculate depreciation with multiple shifts

1. Open the relevant **Fixed Asset Card**, and select a depreciation book with a blank **FA Book Type**. Shift calculation doesn't apply to **Income Tax** books.
1. Choose **Fixed Asset Shift**, and fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|
    |**Depreciation Book Code**|Specifies the depreciation book.|
    |**Fixed Asset Posting Group**|Specifies the fixed asset posting group.|
    |**Depreciation Starting Date**|Specifies the starting date of depreciation.|
    |**Depreciation Ending Date**|Specifies the ending date of depreciation.|
    |**No. of Depreciation Years**|Specifies the no. of years of depreciation.|
    |**Depreciation Method**|Specifies the depreciation calculation method.|
    |**Straight-Line %**|Specifies the percentage for straight-line depreciation methods.|
    |**Declining-Balance %**|Specifies the percentage for declining-balance depreciation methods.|
    |**Shift Type**|Specifies the shift type, for example Single, Double, Triple.|
    |**Industry Type**|Specifies the industry type, for example Normal, Seasonal, Non-Seasonal.|
    |**Used No. of Days**|Specifies the used number of days.|

1. Choose **Calculate FA Depreciation**, fill in the options, and choose **OK**.
1. Review the resulting journal lines, and choose **Post**.

Use **Normal** industry type for a **Single** shift. For **Double** or **Triple** shifts, select **Seasonal** or **Non Seasonal**. The calculation checks the shift end date, required depreciation percentages, and the configured seasonal or nonseasonal day limits. The journal destination depends on general ledger integration, as described earlier.

## Related information

[Fixed Asset Overview](FA_Overview.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]