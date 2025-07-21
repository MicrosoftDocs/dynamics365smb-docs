---
title: FA Depreciation Calculation 
description: Learn how to calculate fixed asset depreciation, including FA block, additional depreciation, and multiple shift scenarios for India in Business Central.
author: v-debapd
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English, FA depreciation calculation, FA block, multiple shifts
ms.date: 06/19/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# FA depreciation calculation

## FA depreciation calculation with FA block and additional depreciation

### FA block

Depreciation is allowed on block of assets. Block of assets is a group of assets falling within a class of assets. For Example:

- Tangible assets, being building, machinery, plant, or furniture,
- Intangible assets, being know how, patents, copyrights, trade-marks, licenses, franchises, or any other business or commercial rights of similar nature

### Additional depreciation

In case of any new machinery or plant acquired and installed after March 31, 2005 by an assessee who is engaged in the business of manufacturing or production of any article or thing - additional depreciation under Income Tax Act of 20% of actual cost shall be allowed. Where the asset is used for less than 180 days then 50% depreciation,  i.e, 1/2 of 20% (that is, 10%) is available (Balance 50% of Additional Depreciation can be claimed in next year)

### Calculate depreciation with FA block and additional Depreciation

1. Go to relevant **Fixed Asset** and **Add. Depr. Applicable** field should be marked true on General Tab.
1. Select the relevant **FA Block Code** on Posting Tab of **Fixed Asset** card, **Add. Depreciation %** should have a value on the selected block code.
1. Select **Depreciation Book** as Income Tax on **Depreciation Book** of **Fixed Asset** Card.
1. Run the Calculate Depreciation batch job, fill the necessary fields and select ok to calculate depreciation. 
1. The batch job calculates the depreciation and creates lines in the fixed asset journal.
1. Choose the Post action.

## FA depreciation calculation with Multiple shifts

Shift depreciation is used when manufacturing companies have multiple production shifts for parts of the year. For example, a company can have one, two, or three shifts during high production season but only one shift during the rest of the year. This means that some fixed assets are used more often than normal during the high production season and they would experience greater depreciation during that time. Being able to adjust the fixed asset's depreciation rates higher makes sense if the fixed asset is active for more than one shift. User can adjust the depreciation using calculated depreciation that is unique to each shift.

### Calculate depreciation with multiple shifts

1. Go to relevant **Fixed Asset**, select **Depreciation Book** as Company on **Depreciation Book** of **Fixed Asset** Card.
1. Go to Related Information > **Fixed Asset Shift**, fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|
    |**Depreciation Book Code**|Specifies the depreciation book.|
    |**FA Posting Group**|Specifies the fixed asset posting group.|
    |**Depreciation Starting Date**|Specifies the starting date of depreciation.|
    |**Depreciation Ending Date**|Specifies the ending date of depreciation.|
    |**No. of Depreciation Years**|Specifies the no. of years of depreciation.|
    |**Depreciation Method**|Specifies the depreciation calculation method.|
    |**Straight Line %**|Specifies the the Straight Line % if the depreciation method is selected as straight line.|
    |**Declining-Balance %**|Specifies the the Declining-Balance % if the depreciation method is selected as straight line.|
    |**Shift Type**|Specifies the shift type, for example Single, Double, Triple.|
    |**Industry Type**|Specifies the industry type, for example Normal, Seasonal, Non-Seasonal.|
    |**Used No. of Days**|Specifies the used number of days.|

1. Run the Calculate Depreciation batch job, fill the necessary fields and select ok to calculate depreciation.
1. The batch job calculates the depreciation and creates lines in the fixed asset G/L journal.
1. Choose the Post action.

## Related information

[Fixed Asset Overview](FA_Overview.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]