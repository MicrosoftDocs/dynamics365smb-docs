---
title: Depreciation methods for fixed assets
description: Learn about the different built-in methods to depreciate or write-down fixed assets.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: write down, depreciate, depreciation
ms.search.form: 5611, 5629, 5633
ms.date: 05/19/2025
ms.custom: bap-template
ms.service: dynamics-365-business-central
---

# Depreciation methods for fixed assets

[!INCLUDE [prod_short](includes/prod_short.md)] supports eight different methods of depreciation for fixed assets:

* Straight-Line (SL)
* Declining-Balance 1 (DB1)
* Declining-Balance 2 (DB2)
* DB1/SL
* DB2/SL
* Half-Year Convention
* Manual
* User-defined depreciation

## Straight-Line depreciation

With Straight-Line depreciation, you deprecate the asset value either with a fixed yearly percentage or with a fixed yearly amount over the depreciation period. When you use the straight-line method, you must specify one of the following options in the fixed asset depreciation book:  

* The depreciation period (years or months) or a depreciation ending date  
* A fixed yearly percentage  
* A fixed yearly amount  
* Depreciation period  

### Depreciation period

If you enter the depreciation period (the number of depreciation years, the number of depreciation months, or the depreciation ending date), the following formula calculates the depreciation amount:  

* Depreciation Amount = ((Book value - Salvage Value) x Number of Depreciation Days) / Remaining Depreciation Days*  

The remaining depreciation days are calculated as the number of depreciation days minus the number of days between the starting date and the last fixed asset entry date.  

Book value can be reduced by posted appreciation, write-down, custom 1, or custom 2 amounts depending on whether the **Include in Depr. Calculation** field is deactivated and whether the **Part of Book Value** field is activated on the **FA Posting Type Setup** page. This calculation ensures that the fixed asset is fully depreciated at the depreciation ending date.  

### Fixed yearly percentage

If you enter a fixed yearly percentage, [!INCLUDE [prod_short](includes/prod_short.md)] uses the following formula to calculate the depreciation amount:  

* Depreciation Amount = (Straight-Line % x Depreciable Basis x Number of Depr. Days) / (100 x 360)*  

### Fixed yearly amount

If you enter a fixed yearly amount, [!INCLUDE [prod_short](includes/prod_short.md)] uses the following formula to calculate the depreciation amount:  

* Depreciation Amount = (Fixed Depreciation Amount x Number of Depreciation Days) / 360*  

### Example - Straight-Line depreciation

A fixed asset has an acquisition cost of LCY 100,000. The estimated life is eight years. The **Calculate Depreciation** batch job is run biannually.  

For this example, the fixed asset ledger entry looks like this:  

| Date | FA Posting Type | Days | Amount | Book Value |
| ---- | --------------- | ---- | ------ | ---------- |
| 01/01/20 |Acquisition Cost |(Depreciation starting date) |100,000.00 |100,000.00 |
| 06/30/20 |Depreciation |180 |-6,250.00 |93,750.00 |
| 12/31/20 |Depreciation |180 |-6,250.00 |87,500.00 |
| 06/30/21 |Depreciation |180 |-6,250.00 |81,250.00 |
| 12/31/21 |Depreciation |180 |-6,250.00 |75,000.00 |
| ...      |             |    |          |          |
| 06/30/27 |Depreciation |180 |-6,250.00 |6,250.00  |
| 12/31/27 |Depreciation |180 |-6,250.00 |0         |

## Declining-Balance 1 depreciation

This depreciation method allocates the largest part of an asset's cost to the early years of its useful lifetime. If you use this method, you must enter a fixed yearly percentage.  

The following formula calculates depreciation amounts:  

* Depreciation Amount = (Declining-Bal. % x Number of Depreciation Days x Depr. Basis) / (100 x 360)*  

The depreciable basis is calculated as the book value at the beginning of the year. The number of depreciation days are the number of days between the posting date and the last depreciation date. [!INCLUDE [prod_short](includes/prod_short.md)] calculates depreciation assuming that any depreciation done in the fiscal year is done with this formula.  

The posted depreciation amount can contain entries with various posting types (write-down, custom1, and custom2) posted since the starting date of the current fiscal year. These posting types are included in the posted depreciation amount if there are check marks in the **Depreciation Type** and the **Part of Book Value** fields on the **FA Posting Type Setup** page.  

### Example 1 - Declining-Balance 1 depreciation

A fixed asset has an acquisition cost of LCY 100,000. The **Declining-Balance %** field is 25. The **Calculate Depreciation** batch job is run biannually.  

The following table shows how the fixed asset ledger entries look.  

| Date | FA Posting Type | Days | Amount | Book Value |
| ---- | --------------- | ---- | ------ | ---------- |
| 01/01/20 |Acquisition Costs |(Depreciation starting date) |100,000.00 |100,000.00 |
| 06/30/20 |Depreciation |180 |-12,500.00 |87,500.00 |
| 12/31/20 |Depreciation |180 |-12,500.00 |75,000.00 |
| 06/30/21 |Depreciation |180 |-9,375.00 |65,625.00 |
| 12/31/21 |Depreciation |180 |-9,375.00 |56,250.00 |
| 06/30/22 |Depreciation |180 |-7,031.25 |49,218.75 |
| 12/31/22 |Depreciation |180 |-7,031.25 |42,187.50 |
| 06/30/23 |Depreciation |180 |-5,273.44 |36,914.06 |
| 12/31/23 |Depreciation |180 |-5,273.44 |31,640.62 |
| 06/30/24 |Depreciation |180 |-3,955.08 |27,685.54 |
| 12/31/24 |Depreciation |180 |-3,955.08 |23,730.46 |
| ...      |             |    |          |          |

Calculation method:  

* Year 1: *25% of 100,000 = 25,000 = 12,500 + 12,500*
* Year 2: *25% of 75,000 = 18,750 = 9,375 + 9,375*
* Year 3: *25% of 56,250 = 14,062.50 = 7,031.25 + 7,031.25*
* ...

The calculation continues until the book value equals the final rounding amount or the salvage value that you entered.  

### Example 2 - Declining-Balance 1 depreciation

An asset's book value is 100,000 on 12/31/2022. You post a depreciation of 1,778 on 2/2/23, which is the expected (proportional) amount of the year's depreciation at 32 days. If you run depreciation on 6/30/2023 [!INCLUDE [prod_short](includes/prod_short.md)] will suggest 8,222, because there are 148 days from 2/2/2023 until 6/30/2023. The expected remaining depreciation for 6/30/2023 is calculated using the following formula:

* *148/360 x 0.20 x 100,000 = 8,222*

### Example 3 - Declining-Balance 1 depreciation

If you post an amount that doesn't align with the Declining Balance 1 depreciation method, for example, 5,000, [!INCLUDE [prod_short](includes/prod_short.md)] suggests the remainder of the expected amount.

An asset's book value is 100,000 on 12/31/2022. You post a depreciation of 5,000 on 2/2/2023, which is more than the expected (proportional) amount on 2/2/2023 at 32 days. If you run depreciation on 6/30/2023, [!INCLUDE [prod_short](includes/prod_short.md)] will suggest 8,222, because there are 148 days from 2/2/2023 until 6/30/2023. The expected remaining depreciation for 6/30/2023 is calculated using the following formula:

* *148/360 x 0.20 x 100,000 = 8,222*

### Example 4 - Declining-Balance 1 depreciation

An asset's book value is 100,000 on 12/31/2023. You post a depreciation of 95,000 on 2/2/2023, which exceeds the allowed depreciation amount for the year. If you run depreciation on 6/30/2023, [!INCLUDE [prod_short](includes/prod_short.md)] will suggest 5000, because there are 148 days from 2/2/2023 until 6/30/2023. The expected remaining depreciation for 6/30/2023 is calculated using the following formula: 

* *148/360 x 0.20 x 100,000 = 8,222*

However, the remaining book value is only 5,000, so [!INCLUDE [prod_short](includes/prod_short.md)] suggests 5,000 because a book value can't be negative.

## Declining-Balance 2 depreciation

The Declining-Balance 1 and Declining-Balance 2 methods calculate the same total depreciation amount for each year. However, if you run the **Calculate Depreciation** batch job more than once a year, the Declining-Balance 1 method results in equal depreciation amounts for each depreciation period. The Declining-Balance 2 method, on the other hand, results in depreciation amounts that decline for each period.  

### Example - Declining-Balance 2 depreciation

A fixed asset has an acquisition cost of LCY 100,000. The **Declining-Balance %** field is 25. The **Calculate Depreciation** batch job is run biannually. The fixed asset ledger entries look like this:  

| Date     | FA Posting Type  | Days                       | Amount    | Book Value |
| -------- | ---------------- | -------------------------  | --------- | ---------- |
| 01/01/20 |Acquisition Costs |(Depreciation starting date)|100,000.00 |100,000.00 |
| 06/30/20 |Depreciation      |180                         |-13,397.46 | 86,602.54 |
| 12/31/20 |Depreciation      |180                         |-11,602.54 | 75,000.00 |
| 06/30/21 |Depreciation      |180                         |-10,048.09 | 64,951.91 |
| 12/31/21 |Depreciation      |180                         |-8,701.91  | 56,250.00 |
| ...      |                  |                            |           |           |

Calculation Method:  

* *BV* = Book value  
* *ND* = Number of depreciation days  
* *DBP* = Declining-balance percent  
* *P* = *DBP*/100  
* *D* = *ND*/360  

The formula to calculate the depreciation amounts is:  

* *DA* = *BV* x (1 – (1 –P)<sup>D</sup>)

The depreciation values are:  

| Date     | Calculation                                                |
| -------- | -----------                                                |
| 06/30/20 |DA = 100,000.00 x (1 -(1 - 0.25)<sup>0.5</sup>) = 13,397.46 |
| 12/31/20 |DA = 86,602.54 x (1 - (1 - 0.25)<sup>0.5</sup>) = 11,602.54 |
| 06/30/21 |DA = 75,000.00 x (1 - (1 - 0.25)<sup>0.5</sup>) = 10,048.09 |
| 12/31/21 |DA = 64,951.91 x (1 - (1 - 0.25)<sup>0.5</sup>) = 8,701.91  |
| ...      |                                                            |

## DB1/SL depreciation

DB1/SL is an abbreviated combination of Declining-Balance 1 and Straight-Line. The calculation continues until the book value equals the final rounding amount, or the salvage value that you entered.  

The **Calculate Depreciation** batch job calculates a straight-line amount and a declining balance amount, but only the greater of the two amounts are transferred to the journal.  

You can use various percentages to calculate declining-balance.  

If you use this method, you must enter the estimated useful lifetime and a declining balance percentage on the **FA Depreciation Books** page.  

> [!NOTE]
> If you use any of the declining balance depreciation methods, and you want to run depreciation for multiple years, you must run each year's depreciation separately. If you run depreciation for the whole period from acquisition date to the end of the last fiscal year or last accounting period, it's likely that the results are incorrect. For example, if you imported legacy data and you use the actual acquisition dates for your assets and want to catch up on accumulated depreciation. For declining balance methods, [!INCLUDE [prod_short](includes/prod_short.md)] calculates the allowed depreciation per year, starting with the registered book value for each year. It can't do a multi-year depreciation in one step.
>
> The **Fixed asset - Projected Value** report can project depreciations for multi-year periods, which might be confusing compared to the results you get if you run depreciations for multiple years using one of the declining balance methods. 

### Example - DB1-SL depreciation

A fixed asset has an acquisition cost of LCY 100,000. On the **FA Depreciation Books** page, the **Declining-Balance %** field contains 25 and the **No. of Depreciation Years** field contains **8**. The **Calculate Depreciation** batch job is run biannually.  

The fixed asset ledger entries look like this:  

| Date | FA Posting Type | Days | Amount | Book Value |
| --- | --- | --- | --- | --- |
| 01/01/20 |Acquisition Costs |(Depreciation starting date) |100,000.00 |100,000.00 |
| 06/30/20 |Depreciation |180 |-12,500.00 |87,500.00 |
| 12/31/20 |Depreciation |180 |-12,500.00 |75,000.00 |
| 06/30/21 |Depreciation |180 |-9,375.00 |65,625.00 |
| 12/31/21 |Depreciation |180 |-9,375.00 |56,250.00 |
| 06/30/22 |Depreciation |180 |-7,031.25 |49,218.75 |
| 12/31/22 |Depreciation |180 |-7,031.25 |42,187.50 |
| 06/30/23 |Depreciation |180 |-5,273.44 |36,914.06 |
| 12/31/23 |Depreciation |180 |-5,273.44 |31,640.62 |
| 06/30/24 |Depreciation |180 |-3,955.08 |27,685.54 |
| 12/31/24 |Depreciation |180 |-3,955.08 |23,730.46 |
| 06/30/25 |Depreciation |180 |-3,955.08 |19,775.38 SL |
| 12/31/25 |Depreciation |180 |-3,955.08 |15,820.30 SL |
| 06/30/26 |Depreciation |180 |-3,955.08 |11,865.22 SL |
| 12/31/26 |Depreciation |180 |-3,955.07 |7,910.15 SL |
| 06/30/27 |Depreciation |180 |-3,955.08 |3,955.07 SL |
| 12/31/27 |Depreciation |180 |-3,955.07 |0.00 SL |

`SL` after the book value means that the straight-line method was used.  

Calculation method:  

* Year 1 (2020):  

    *Declining-balance amount: 25% of 100,000 = 25,000 = 12,500 + 12,500*  

    *Straight-line amount = 100,000 / 8 = 12,500 = 6,250 + 6,250*  

    The declining-balance amount is used because it's the greater amount.  
* ...
* Year 5 (2025):  

    *Declining-balance amount: 25% of 23,730.46 = 4,943.85= 2,471.92 + 2,471.92*  

    *Straight-line amount = 23,730.46/3 = 7,910.15 = 3,995.07 + 3,995.08*  

    The straight-line amount is used because it's the greater amount.  

## Half-Year Convention depreciation

The Half-Year Convention method is only applied if you turn on the **Use Half-Year Convention** toggle for the fixed asset on the **Fixed Asset Card** page.  

You can use this depreciation method with the following depreciation methods:  

* Straight-Line  
* Declining-Balance 1  
* DB1/SL  

When you apply the Half-Year Convention method, a fixed asset has six months of depreciation in the first fiscal year, regardless of the contents of the **Depreciation Starting Date** field.  

> [!NOTE]  
> The estimated life of the fixed asset that is remaining after the first fiscal year always contains a half-year using the Half-Year Convention Method. Thus, for the Half-Year Convention method to be applied correctly, the **Depreciation Ending Date** field on the **FA Depreciation Book** page must always contain a date which is exactly six months before the final date of the fiscal year in which the fixed asset fully depreciates.  

### Example - Half-Year Convention depreciation

A fixed asset has an acquisition cost of LCY 100,000. The **Depreciation Starting Date** is 03/01/20. The estimated life is five years, so the **Depreciation Ending Date** must be 06/30/25. The **Calculate Depreciation** batch job is run annually. This example is based on a calendar fiscal year.  

The fixed asset ledger entries look like this:  

| Date | FA Posting Type | Days | Amount | Book Value |
| --- | --- | --- | --- | --- |
| 03/01/20 |Acquisition Cost |(Depreciation starting date) |100,000.00 |100,000.00 |
| 12/31/20 |Depreciation |270 |-10,000.00 |90,000.00 |
| 12/31/21 |Depreciation |360 |-20,000.00 |70,000.00 |
| 12/31/22 |Depreciation |360 |-20,000.00 |50,000.00 |
| 12/31/23 |Depreciation |360 |-20,000.00 |30,000.00 |
| 12/31/24 |Depreciation |360 |-20,000.00 |10,000.00 |
| 12/31/25 |Depreciation |180 |-10,000.00 |0.00 |

## Example - DB1/SL depreciation using Half-Year Convention

A fixed asset has an acquisition cost of LCY 100,000. The **Depreciation Starting Date** is 11/01/20. The estimated life is five years, so the **Depreciation Ending Date** must be 06/30/25. On the **FA Depreciation Books** page, the **Declining-Balance %** field contains 40. The **Calculate Depreciation** batch job is run annually. This example is based on a calendar fiscal year.  

The fixed asset ledger entries look like this:  

| Date | FA Posting Type | Days | Amount | Book Value |
| --- | --- | --- | --- | --- |
| 11/01/20 |Acquisition Cost |(Depreciation starting date) |100,000.00 |100,000.00 |
| 12/31/20 |Depreciation |60 |-20,000.00 |80,000.00 |
| 12/31/21 |Depreciation |360 |-32,000.00 |48,000.00 |
| 12/31/22 |Depreciation |360 |-19,200.00 |28,800.00 |
| 12/31/23 |Depreciation |360 |-11,520.00 |17,280.00 |
| 12/31/24 |Depreciation |360 |-11,520.00 |5,760.00 SL |
| 12/31/25 |Depreciation |180 |-5,760.00 |0.00 SL |

`SL` after the book value means that the straight-line method was used.  

Calculation method:  

* Year 1:  

    *Declining-balance amount = Full year amount = 40% of 100,000 = 40,000.* Thus, for half a year 40,000 / 2 = 20,000  

    *Straight-line amount = Full year amount = 100,000 / 5 = 20,000.* Thus, for half a year = 20,000 / 2 = 10,000  

    The declining-balance amount is used because it's the greater amount.  
* ...
* Year 5 (2024):  

    *Declining-balance amount = 40% of 17,280.00 = 6,912.00*  

    *Straight-line amount = 28,800 / 1.5 = 11,520.00*  

    The straight-line amount is used because it's the greater amount.  

## Duplicate entries to other depreciation books

If you have three depreciation books, B1, B2 and B3, and you want to duplicate entries from B1 to B2 and B3, you can turn on the **Part of Duplication List** toggle on the depreciation book cards for B2 and B3. For example, this setting can be useful in the following situations:

* Depreciation book B1 integrates with the general ledger and uses the fixed asset G/L journal.
* Depreciation books B2 and B3 don't integrate with the general ledger and use the fixed asset journal.  

When you make an entry in B1 in the fixed asset G/L journal, and turn on the **Part of Duplication List** toggle, [!INCLUDE [prod_short](includes/prod_short.md)] duplicates the entry in book B2 and B3 in the fixed asset journal when you post the entry.  

> [!NOTE]  
> You can't duplicate in the same journal and journal batch as you're duplicating from. If you post entries in the fixed asset G/L journal, you can duplicate them in the fixed asset journal or in the fixed asset G/L journal using another batch.  

> [!NOTE]  
> You can't use the same number series in the fixed asset G/L journal and the fixed asset journal. When you post entries in the fixed asset G/L journal, you must leave the **Document No.** field empty. If you enter a number in the field, the number is duplicated in the fixed asset journal. You must manually change the document number before you can post the journal.  

## Manual depreciation

Use the manual method for assets that aren't subject to depreciation, for example, land. You must enter depreciation in the fixed asset G/L journal. The **Calculate Depreciation** batch job omits fixed assets that use the manual depreciation method.

## User-defined depreciation

If the built-in depreciation methods don't meet your needs, you can define your own depreciation method by using depreciation tables. To learn more about applying a user-defined depreciation method, go to [Set Up User-Defined Depreciation Method](fa-how-setup-user-defined-depreciation-method.md).

## Related information

[Fixed Assets overview](fa-manage.md)  
[Setting Up Fixed Assets](fa-setup.md)  
[Finance](finance.md)  
[Getting Ready for Doing Business](ui-get-ready-business.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
