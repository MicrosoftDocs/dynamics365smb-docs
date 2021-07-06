---
title: Depreciation Methods for Fixed Assets
description: Learn about the different built-in methods to depreciate or write-down fixed assets in the default version of Business Central which includes eight methods.
author: edupont04

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: write down
ms.date: 07/05/2021
ms.author: edupont

---
# Depreciation Methods for Fixed Assets

There are eight methods of depreciation available in the default version of [!INCLUDE [prod_short](includes/prod_short.md)]:  

* Straight-Line  
* Declining-Balance 1  
* Declining-Balance 2  
* DB1/SL  
* DB2/SL  
* User-defined  

  > [!NOTE]  
  > Specify your own depreciation method by defining depreciation tables. For information about applying a user defined depreciation method, see [Set Up User-Defined Depreciation Method](fa-how-setup-user-defined-depreciation-method.md).
* Manual  

  > [!NOTE]  
  > Use this method for assets that are not subject to depreciation, for example, land. You must enter depreciation in the fixed asset G/L journal. The **Calculate Depreciation** batch job omits fixed assets that use this depreciation method.  
* Half-Year Convention  

  > [!NOTE]  
  > When you use this method, a fixed asset is depreciated by the same amount each year.  

## Straight-Line Depreciation

When you use the straight-line method, you must specify one of the following options in the fixed asset depreciation book:  

* The depreciation period (years or months) or a depreciation ending date  
* A fixed yearly percentage  
* A fixed yearly amount  
* Depreciation period  

### Depreciation Period

If you enter the depreciation period (the number of depreciation years, the number of depreciation months, or the depreciation ending date), the following formula calculates the depreciation amount:  

*Depreciation Amount = ((Book value - Salvage Value) x Number of Depreciation Days) / Remaining Depreciation Days*  

Remaining depreciation days are calculated as the number of depreciation days minus the number of days between the depreciation starting date and the last fixed asset entry date.  

Book value may be reduced by posted appreciation, write-down, custom 1 or custom 2 amounts, depending on whether the **Include in Depr. Calculation** field is deactivated and whether the **Part of Book Value** field is activated on the **FA Posting Type Setup** page. This calculation ensures that the fixed asset is fully depreciated at the depreciation ending date.  

### Fixed Yearly Percentage

If you enter a fixed yearly percentage, application uses the following formula to calculate the depreciation amount:  

*Depreciation Amount = (Straight-Line % x Depreciable Basis x Number of Depr. Days) / (100 x 360)*  

### Fixed Yearly Amount

If you enter a fixed yearly amount, application uses this formula to calculate the depreciation amount:  

*Depreciation Amount = (Fixed Depreciation Amount x Number of Depreciation Days) / 360*  

### Example - Straight-Line Depreciation

A fixed asset has an acquisition cost of LCY 100,000. The estimated life is eight years. The **Calculate Depreciation** batch job is run biannually.  

For this example, the fixed asset ledger entry looks like this:  

| Date | FA Posting Type | Days | Amount | Book Value |
| --- | --- | --- | --- | --- |
| 01/01/20 |Acquisition Cost |(Depreciation starting date) |100,000.00 |100,000.00 |
| 06/30/20 |Depreciation |180 |-6,250.00 |93,750.00 |
| 12/31/20 |Depreciation |180 |-6,250.00 |87,500.00 |
| 06/30/21 |Depreciation |180 |-6,250.00 |81,250.00 |
| 12/31/21 |Depreciation |180 |-6,250.00 |75,000.00 |
| 06/30/27 |Depreciation |180 |-6,250.00 |6,250.00 |
| 12/31/27 |Depreciation |180 |-6,250.00 |0 |

## Declining-Balance 1 Depreciation

This accelerated depreciation method allocates the largest portion of the cost of an asset to the early years of its useful lifetime. If you use this method, you must enter a fixed yearly percentage.  

The following formula calculates depreciation amounts:  

*Depreciation Amount = (Declining-Bal. % x Number of Depreciation Days x Depr. Basis) / (100 x 360)*  

The depreciable basis is calculated as the book value less posted depreciation since the starting date of the current fiscal year.  

The posted depreciation amount can contain entries with various posting types (write-down, custom1, and custom2) posted since the starting date of the current fiscal year. These posting types are included in the posted depreciation amount if there are check marks in the **Depreciation Type** and the **Part of Book Value** fields on the **FA Posting Type Setup** page.  

### Example - Declining-Balance 1 Depreciation

A fixed asset has an acquisition cost of LCY 100,000. The **Declining-Balance %** field is 25. The **Calculate Depreciation** batch job is run biannually.  

The following table shows how the fixed asset ledger entries look.  

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

Calculation Method:  

* Year 1: *25% of 100,000 = 25,000 = 12,500 + 12,500*

* Year 2: *25% of 75,000 = 18,750 = 9,375 + 9,375*

* Year 3: *25% of 56,250 = 14,062.50 = 7,031.25 + 7,031.25*

The calculation continues until the book value equals the final rounding amount or the salvage value that you entered.  

## Declining-Balance 2 Depreciation

The Declining-Balance 1 and Declining-Balance 2 methods calculate the same total depreciation amount for each year. However, if you run the **Calculate Depreciation** batch job more than once a year, the Declining-Balance 1 method will result in equal depreciation amounts for each depreciation period. The Declining-Balance 2 method, on the other hand, will result in depreciation amounts that decline for each period.  

### Example - Declining-Balance 2 Depreciation

A fixed asset has an acquisition cost of LCY 100,000. The **Declining-Balance %** field is 25. The **Calculate Depreciation** batch job is run biannually. The fixed asset ledger entries look like this:  

| Date | FA Posting Type | Days | Amount | Book Value |
| --- | --- | --- | --- | --- |
| 01/01/20 |Acquisition Costs |(Depreciation starting date)|100,000.00 |100,000.00 |
| 06/30/20 |Depreciation |180 |-13,397.46 |86,602.54 |
| 12/31/20 |Depreciation |180 |-11,602.54 |75,000.00 |
| 06/30/21 |Depreciation |180 |-10,048.09 |64,951.91 |
| 12/31/21 |Depreciation |180 |-8,701.91 |56,250.00 |

Calculation Method:  

* *BV* = Book value  
* *ND* = Number of depreciation days  
* *DBP* = Declining-balance percent  
* *P* = *DBP*/100  
* *D* = *ND*/360  

The formula for calculating the depreciation amounts is:  

*DA* = *BV* x (1 – (1 –P)<sup>D</sup>)

The depreciation values are:  

| Date | Calculation |
| --- | --- |
| 06/30/20 |DA = 100,000.00 x (1 -(1 - 0.25)<sup>0.5</sup>) = 13,397.46 |
| 12/31/20 |DA = 86,602.54 x (1 - (1 - 0.25)<sup>0.5</sup>) = 11,602.54 |
| 06/30/21 |DA = 75,000.00 x (1 - (1 - 0.25)<sup>0.5</sup>) = 10,048.09 |
| 12/31/21 |DA = 64,951.91 x (1 - (1 - 0.25)<sup>0.5</sup>) = 8,701.91 |

## DB1/SL Depreciation

DB1/SL is an abbreviated combination of Declining-Balance 1 and Straight-Line. The calculation continues until the book value equals the final rounding amount, or the salvage value that you entered.  

The **Calculate Depreciation** batch job calculates a straight-line amount and a declining balance amount, but only the greater of the two amounts is transferred to the journal.  

You can use various percentages to calculate declining-balance.  

If you use this method, you must enter the estimated useful lifetime and a declining balance percentage on the **FA Depreciation Books** page.  

### Example - DB1-SL Depreciation

A fixed asset has an acquisition cost of LCY 100,000. On the **FA Depreciation Books** page, the **Declining-Balance %** field contains 25 and the **No. of Depreciation Years** field contains 8. The **Calculate Depreciation** batch job is run biannually.  

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

`SL` after the book value means that the straight-line method has been used.  

Calculation method:  

* Year 1 (2020):  

    *Declining-balance amount: 25% of 100,000 = 25,000 = 12,500 + 12,500*  

    *Straight-line amount = 100,000 / 8 = 12,500 = 6,250 + 6,250*  

    The declining-balance amount is used because it is the greater amount.  

* Year 5 (2025):  

    *Declining-balance amount: 25% of 23,730.46 = 4,943.85= 2,471.92 + 2,471.92*  

    *Straight-line amount = 23,730.46/3 = 7,910.15 = 3,995.07 + 3,995.08*  

    The straight-line amount is used because it is the greater amount.  

## Half-Year Convention Depreciation

The Half-Year Convention method will only be applied if you have placed a check mark in the **Use Half-Year Convention** field in the fixed **FA Depreciation Book** page.  

This depreciation method can be used in conjunction with the following depreciation methods in application:  

* Straight-Line  
* Declining-Balance 1  
* DB1/SL  

When you apply the Half-Year Convention, a fixed asset has six months of depreciation in the first fiscal year, regardless of the contents of the **Depreciation Starting Date** field.  

> [!NOTE]  
> The estimated life of the fixed asset that is remaining after the first fiscal year will always contain a half-year using the Half-Year Convention Method. Thus, for the Half-Year Convention method to be applied correctly, the **Depreciation Ending Date** field on the **FA Depreciation Book** page must always contain a date which is exactly six months before the final date of the fiscal year in which the fixed asset will fully depreciate.  

### Example - Half-Year Convention Depreciation

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

## Example - DB1/SL Depreciation Using Half-Year Convention

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

`SL` after the book value means that the straight-line method has been used.  

Calculation method:  

* Year 1:  

    *Declining-balance amount = Full year amount = 40% of 100,000 = 40,000.* Thus, for half a year 40,000 / 2 = 20,000  

    *Straight-line amount = Full year amount = 100,000 / 5 = 20,000.* Thus, for half a year = 20,000 / 2 = 10,000  

    The declining-balance amount is used because it is the greater amount.  

* Year 5 (2024):  

    *Declining-balance amount = 40% of 17,280.00 = 6,912.00*  

    *Straight-line amount = 28,800 / 1.5 = 11,520.00*  

    The straight-line amount is used because it is the greater amount.  

## Duplicating Entries to More Depreciation Books

If you have three depreciation books, B1, B2 and B3, and you want to duplicate entries from B1 to B2 and B3, you can place a check mark in the **Part of Duplication List** field on the depreciation book cards for B2 and B3. This can be useful if depreciation book B1 is integrated with the general ledger and uses the fixed asset G/L journal, and depreciation books B2 and B3 are not integrated with the general ledger and use the fixed asset journal.  

When you enter an entry in B1 in the fixed asset G/L journal and place a check mark in the **Use Duplication List** field, application will duplicate the entry in book B2 and B3 in the fixed asset journal when the entry is posted.  

> [!NOTE]  
> You cannot duplicate in the same journal and journal batch as you are duplicating from. If you post entries in the fixed asset G/L journal, you can duplicate them in the fixed asset journal or in the fixed asset G/L journal using another batch.  

> [!NOTE]  
> You cannot use the same number series in the fixed asset G/L journal and the fixed asset journal. When you post entries in the fixed asset G/L journal, you must leave the **Document No.** field empty. If you enter a number in the field, the the number is duplicated in the fixed asset journal. You'll have to manually change the document number before you can post the journal.  

## See Also

[Fixed Assets](fa-manage.md)  
[Setting Up Fixed Assets](fa-setup.md)  
[Finance](finance.md)  
[Getting Ready for Doing Business](ui-get-ready-business.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
