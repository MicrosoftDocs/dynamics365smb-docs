---
title: Depreciation Methods| Microsoft Docs
description: Learn about the different methods to depreciate or write-down fixed assets.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: write down
ms.date: 04/01/2020
ms.author: sgroespe

---
# Depreciation Methods
There are eight methods of depreciation available:  

* Straight-Line  
* Declining-Balance 1  
* Declining-Balance 2  
* DB1/SL  
* DB2/SL  
* User-defined  
* Manual  

  > [!NOTE]  
  >   Use this method for assets that are not subject to depreciation, for example, land. You must enter depreciation in the fixed asset G/L journal. The **Calculate Depreciation** batch job omits fixed assets that use this depreciation method.  
* Half-Year Convention  

  > [!NOTE]  
  >    When you use this method, a fixed asset is depreciated by the same amount each year.  

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

Depreciation Amount = (Straight-Line % x Depreciable Basis x Number of Depr. Days) / (100 x 360)  

### Fixed Yearly Amount
If you enter a fixed yearly amount, application uses this formula to calculate the depreciation amount:  

Depreciation Amount = (Fixed Depreciation Amount x Number of Depreciation Days) / 360  

### Example - Straight-Line Depreciation
A fixed asset has an acquisition cost of LCY 100,000. The estimated life is eight years. The **Calculate Depreciation** batch job is run biannually.  

For this example, the fixed asset ledger entry looks like this:  

| Date | FA Posting Type | Days | Amount | Book Value |
| --- | --- | --- | --- | --- |
| 01/01/10 |Acquisition Cost |* |100,000.00 |100,000.00 |
| 06/30/10 |Depreciation |180 |-6,250.00 |93,750.00 |
| 12/31/10 |Depreciation |180 |-6,250.00 |87,500.00 |
| 06/30/11 |Depreciation |180 |-6,250.00 |81,250.00 |
| 12/31/11 |Depreciation |180 |-6,250.00 |75,000.00 |
| 06/30/17 |Depreciation |180 |-6,250.00 |6,250.00 |
| 12/31/17 |Depreciation |180 |-6,250.00 |0 |

* Depreciation starting date  

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
| 01/01/10 |Acquisition Costs |* |100,000.00 |100,000.00 |
| 06/30/10 |Depreciation |180 |-12,500.00 |87,500.00 |
| 12/31/10 |Depreciation |180 |-12,500.00 |75,000.00 |
| 06/30/11 |Depreciation |180 |-9,375.00 |65,625.00 |
| 12/31/11 |Depreciation |180 |-9,375.00 |56,250.00 |
| 06/30/12 |Depreciation |180 |-7,031.25 |49,218.75 |
| 12/31/12 |Depreciation |180 |-7,031.25 |42,187.50 |
| 06/30/13 |Depreciation |180 |-5,273.44 |36,914.06 |
| 12/31/13 |Depreciation |180 |-5,273.44 |31,640.62 |
| 06/30/14 |Depreciation |180 |-3,955.08 |27,685.54 |
| 12/31/14 |Depreciation |180 |-3,955.08 |23,730.46 |

* Depreciation starting date  

    Calculation Method:  

    *1st Year: 25% of 100,000 = 25,000 = 12,500 + 12,500*

    *2nd Year: 25% of 75,000 = 18,750 = 9,375 + 9,375*

    *3rd Year: 25% of 56,250 = 14,062.50 = 7,031.25 + 7,031.25*

    The calculation continues until the book value equals the final rounding amount or the salvage value that you entered.   

## Declining-Balance 2 Depreciation
The Declining-Balance 1 and Declining-Balance 2 methods calculate the same total depreciation amount for each year. However, if you run the **Calculate Depreciation** batch job more than once a year, the Declining-Balance 1 method will result in equal depreciation amounts for each depreciation period. The Declining-Balance 2 method, on the other hand, will result in depreciation amounts that decline for each period.  

### Example - Declining-Balance 2 Depreciation
A fixed asset has an acquisition cost of LCY 100,000. The **Declining-Balance %** field is 25. The **Calculate Depreciation** batch job is run biannually. The fixed asset ledger entries look like this:  

| Date | FA Posting Type | Days | Amount | Book Value |
| --- | --- | --- | --- | --- |
| 01/01/10 |Acquisition Costs |* |100,000.00 |100,000.00 |
| 06/30/10 |Depreciation |180 |-13,397.46 |86,602.54 |
| 12/31/10 |Depreciation |180 |-11,602.54 |75,000.00 |
| 06/30/11 |Depreciation |180 |-10,048.09 |64,951.91 |
| 12/31/11 |Depreciation |180 |-8,701.91 |56,250.00 |

* Depreciation starting date  

Calculation Method:  

* BV = Book value  
* ND = Number of depreciation days  
* DBP = Declining-balance percent  
* P = DBP/100  
* D = ND/360  

The formula for calculating the depreciation amounts is:  

*DA = BV x (1 – (1 –P)<sup>D<sup>*  

The depreciation values are:  

| Date | Calculation |
| --- | --- |
| 06/30/10 |DA = 100,000.00 x (1 -(1 - 0.25)<sup>0.5<sup>) = 13,397.46 |
| 12/31/10 |DA = 86,602.54 x (1 - (1 - 0.25)<sup>0.5<sup>) = 11,602.54 |
| 06/30/11 |DA = 75,000.00 x (1 - (1 - 0.25)<sup>0.5<sup>) = 10,048.09 |
| 12/31/11 |DA = 64,951.91 x (1 - (1 - 0.25)<sup>0.5<sup>) = 8,701.91 |

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
| 01/01/10 |Acquisition Costs |* |100,000.00 |100,000.00 |
| 06/30/10 |Depreciation |180 |-12,500.00 |87,500.00 |
| 12/31/10 |Depreciation |180 |-12,500.00 |75,000.00 |
| 06/30/11 |Depreciation |180 |-9,375.00 |65,625.00 |
| 12/31/11 |Depreciation |180 |-9,375.00 |56,250.00 |
| 06/30/12 |Depreciation |180 |-7,031.25 |49,218.75 |
| 12/31/12 |Depreciation |180 |-7,031.25 |42,187.50 |
| 06/30/13 |Depreciation |180 |-5,273.44 |36,914.06 |
| 12/31/13 |Depreciation |180 |-5,273.44 |31,640.62 |
| 06/30/14 |Depreciation |180 |-3,955.08 |27,685.54 |
| 12/31/14 |Depreciation |180 |-3,955.08 |23,730.46 |
| 06/30/15 |Depreciation |180 |-3,955.08 |19,775.38 SL |
| 12/31/15 |Depreciation |180 |-3,955.08 |15,820.30 SL |
| 06/30/16 |Depreciation |180 |-3,955.08 |11,865.22 SL |
| 12/31/16 |Depreciation |180 |-3,955.07 |7,910.15 SL |
| 06/30/17 |Depreciation |180 |-3,955.08 |3,955.07 SL |
| 12/31/17 |Depreciation |180 |-3,955.07 |0.00 SL |

* Depreciation starting date  

"SL" after the book value means that the straight-line method has been used.  

Calculation method:  

1st year:  

*Declining-balance amount: 25% of 100,000 = 25,000 = 12,500 + 12,500*  

*Straight-line amount = 100,000 / 8 = 12,500 = 6,250 + 6,250*  

The declining-balance amount is used because it is the greater amount.  

6th year (2015):  

*Declining-balance amount: 25% of 23,730.46 = 4,943.85= 2,471.92 + 2,471.92*  

*Straight-line amount = 23,730.46/3 = 7,910.15 = 3,995.07 + 3,995.08*  

The straight-line amount is used because it is the greater amount.  

## User-defined Depreciation
The application has a facility that allows you to set up user-defined depreciation methods.  

With a user-defined method, you use the **Depreciation Tables** page, where you must enter a depreciation percentage for each period (month, quarter, year, or accounting period).  

The formula for calculating the depreciation amounts is:  

Depreciation Amount = (Depreciation % x Number of Depreciation Days x Depr. Basis) / (100 x 360)  

### Depreciation Based on Number of Units
This user-defined method can also be used to depreciate based on number of units, for example, in the case of production machines with an established lifetime capacity. On the **Depreciation Tables** page, you can enter the number of units that can be produced in each period (month, quarter, year,or accounting period).  

### To set up user-defined depreciation methods
On the **Depreciation Table** page, you can set up user-defined depreciation methods. For example, you can set up depreciation based on number of units.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Depreciation Tables**, and then choose the related link.  
2. On the **Depreciation Table List** page, choose the **New** action.  
3. **Depreciation Table Card** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

### Example - User-defined Depreciation
You use a depreciation method that allows you to depreciate assets in an accelerated manner for income tax purposes.  

You would use the following depreciation rates for a fixed asset with a three-year lifetime for tax purposes:  

* year 1: 25%  
* year 2: 38%  
* year 3: 37%  

The acquisition cost is LCY 100,000, and the depreciable lifetime is five years. Depreciation is calculated annually.  

| Date | FA Posting Type | Days | Amount | Book Value |
| --- | --- | --- | --- | --- |
| 01/01/10 |Acquisition Cost |* |100,000.00 |100,000.00 |
| 12/31/10 |Depreciation |360 |-25,000.00 |75,000.00 |
| 12/31/11 |Depreciation |360 |-38,000.00 |37,000.00 |
| 12/31/12 |Depreciation |360 |-37,000.00 |0 |
| 12/31/13 |Depreciation |None |None |0 |
| 12/31/14 |Depreciation |None |None |0 |

* Depreciation starting date  

If you use a user-defined method, the **First User-Defined Depr. Date** and **Depreciation Starting Date** fields must be filled in on the **FA Depreciation Books** page. The **First User-Defined Depr. Date** field and the contents in the **Period Length** field on the **Depreciation Tables** page are used to determine the time intervals to be used for depreciation calculations. This ensures that application will start using the specified percentage on the same day for all assets. The **Depreciation Starting Date** field is used to calculate the number of depreciation days.  

In the previous example, both the **First User-Defined Depr. Date** and **Depreciation Starting Date** fields contain 01/01/01. If, however, the **First User-Defined Depr. Date** field contained 01/01/10 and the **Depreciation Starting Date** field contained 04/01/11, the result would be:  

| Date | FA Posting Type | Days | Amount | Book Value |
| --- | --- | --- | --- | --- |
| 01/01/10 |Acquisition Cost |* |100,000.00 |100,000.00 |
| 12/31/10 |Depreciation |270 |-18,750.00 |81,250.00 |
| 12/31/11 |Depreciation |360 |-38,000.00 |42,250.00 |
| 12/31/12 |Depreciation |360 |-37,000.00 |6,250.00 |
| 12/31/13 |Depreciation |90 |-6,250.00 |0 |
| 12/31/14 |Depreciation |None |None |0 |

* Depreciation starting date  

## Half-Year Convention Depreciation
The Half-Year Convention method will only be applied if you have placed a check mark in the **Use Half-Year Convention** field in the fixed **FA Depreciation Book** page.  

This depreciation method can be used in conjunction with the following depreciation methods in application:  

* Straight-Line  
* Declining-Balance 1  
* DB1/SL  

When you apply the Half-Year Convention, a fixed asset has six months of depreciation in the first fiscal year, regardless of the contents of the **Depreciation Starting Date** field.  

> [!NOTE]  
>   The estimated life of the fixed asset that is remaining after the first fiscal year will always contain a half-year using the Half-Year Convention Method. Thus, for the Half-Year Convention method to be applied correctly, the **Depreciation Ending Date** field on the **FA Depreciation Book** page must always contain a date which is exactly six months before the final date of the fiscal year in which the fixed asset will fully depreciate.  

### Example - Half-Year Convention Depreciation
A fixed asset has an acquisition cost of LCY 100,000. The **Depreciation Starting Date** is 03/01/10. The estimated life is five years, so the **Depreciation Ending Date** must be 06/30/15. The **Calculate Depreciation** batch job is run annually. This example is based on a calendar fiscal year.  

The fixed asset ledger entries look like this:  

| Date | FA Posting Type | Days | Amount | Book Value |
| --- | --- | --- | --- | --- |
| 03/01/10 |Acquisition Cost |* |100,000.00 |100,000.00 |
| 12/31/10 |Depreciation |270 |-10,000.00 |90,000.00 |
| 12/31/11 |Depreciation |360 |-20,000.00 |70,000.00 |
| 12/31/12 |Depreciation |360 |-20,000.00 |50,000.00 |
| 12/31/13 |Depreciation |360 |-20,000.00 |30,000.00 |
| 12/31/14 |Depreciation |360 |-20,000.00 |10,000.00 |
| 12/31/15 |Depreciation |180 |-10,000.00 |0.00 |

* Depreciation starting date  

## Example - DB1/SL Depreciation Using Half-Year Convention
A fixed asset has an acquisition cost of LCY 100,000. The **Depreciation Starting Date** is 11/01/10. The estimated life is five years, so the **Depreciation Ending Date** must be 06/30/15. On the **FA Depreciation Books** page, the **Declining-Balance %** field contains 40. The **Calculate Depreciation** batch job is run annually. This example is based on a calendar fiscal year.  

The fixed asset ledger entries look like this:  

| Date | FA Posting Type | Days | Amount | Book Value |
| --- | --- | --- | --- | --- |
| 11/01/10 |Acquisition Cost |* |100,000.00 |100,000.00 |
| 12/31/10 |Depreciation |60 |-20,000.00 |80,000.00 |
| 12/31/11 |Depreciation |360 |-32,000.00 |48,000.00 |
| 12/31/12 |Depreciation |360 |-19,200.00 |28,800.00 |
| 12/31/13 |Depreciation |360 |-11,520.00 |17,280.00 |
| 12/31/14 |Depreciation |360 |-11,520.00 |5,760.00 SL |
| 12/31/15 |Depreciation |180 |-5,760.00 |0.00 SL |

* Depreciation starting date  

"SL" after the book value means that the straight-line method has been used.  

Calculation method:  

1st year:  

*Declining-balance amount = Full year amount = 40% of 100,000 = 40,000. Thus, for half a year 40,000 / 2 = 20,000*  

*Straight-line amount = Full year amount = 100,000 / 5 = 20,000. Thus, for half a year = 20,000 / 2 = 10,000*  

The declining-balance amount is used because it is the greater amount.  

5th year (2004):  

*Declining-balance amount = 40% of 17,280.00 = 6,912.00*  

*Straight-line amount = 28,800 / 1.5 = 11,520.00*  

The straight-line amount is used because it is the greater amount.  

## Duplicating Entries to More Depreciation Books
If you have three depreciation books, B1, B2 and B3, and you want to duplicate entries from B1 to B2 and B3, you can place a check mark in the **Part of Duplication List** field on the depreciation book cards for B2 and B3. This can be useful if depreciation book B1 is integrated with the general ledger and uses the fixed asset G/L journal, and depreciation books B2 and B3 are not integrated with the general ledger and use the fixed asset journal.  

When you enter an entry in B1 in the fixed asset G/L journal and place a check mark in the **Use Duplication List** field, application will duplicate the entry in book B2 and B3 in the fixed asset journal when the entry is posted.  

> [!NOTE]  
>   You cannot duplicate in the same journal and journal batch as you are duplicating from. If you post entries in the fixed asset G/L journal, you can duplicate them in the fixed asset journal or in the fixed asset G/L journal using another batch.  

> [!NOTE]  
>   You cannot use the same number series in the fixed asset G/L journal and the fixed asset journal. When you post entries in the fixed asset G/L journal, you must leave the **Document No.** field empty. If you enter a number in the field, the the number is duplicated in the fixed asset journal. You'll have to manually change the document number before you can post the journal.  

## See Also
[Fixed Assets](fa-manage.md)  
[Setting Up Fixed Assets](fa-setup.md)  
[Finance](finance.md)  
[Getting Started](product-get-started.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
