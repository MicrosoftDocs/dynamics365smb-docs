---
    title: Insert topic title| Microsoft Docs
    description: Insert description
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# Depreciation Methods-duplicate
There are three depreciation methods that are unique to Russia that can be used in ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/navnow_md.md)]-->.  
  
-   Straight-line method **\(SL-RU\)**  
  
-   Non-linear method **\(DB\/SL-RU\)**  
  
-   Non-linear method for a group of fixed assets **\(DB\/SL-RU Tax Group\)**  
  
## Straight-line Method  
 To use this method, select the **\(SL-RU\)** option in the appropriate fixed asset depreciation book.  
  
 The main calculation formula for the straight-line method is K \= 1\/N \* 100%, where K is the monthly rate of depreciation, and N is the number of depreciation in months. The straight line method works as follows:  
  
-   The calculation of depreciation is based on the month’s principle, and every depreciation month has 30 days. These parameters are automatically set up during calculation of depreciation.  
  
-   The start date of depreciation for any fixed asset acquisition is the first day of the month that follows the month in which the acquisition is released into operation.  
  
-   The end date of depreciation is the end of the month when the fixed asset is disposed, written off, or sold.  
  
-   During depreciation calculation, the depreciation of the previous month will be checked to see if it has been posted for the particular fixed asset. This feature enables you to avoid skipping depreciation periods.  
  
## Non-linear Method  
 To use this method, select the **\(DB\/SL-RU\)** option in the appropriate fixed asset depreciation book.  
  
 The calculation for the non-linear method consists of two formulas—one for the start of the depreciation and another for the end of the depreciation.  
  
 The formula for the non-linear method is K \= 2\/N \* 100%, where K is the monthly rate of depreciation, and N is the number of depreciation months. The constant in this formula, 2, is fixed in the code and should not be set up manually.  
  
 When the book value of the fixed asset becomes equal to or less than 20 percent of the acquisition cost, the monthly depreciation will be calculated differently. From this point on, the straight line formula is used to calculate depreciation until the fixed asset is fully depreciated.  
  
 The constant of the acquisition cost, 20 percent, is fixed in the code and should not be set up manually.  
  
## Non-linear Method for a Group of Fixed Assets  
 To use this method, select the **\(DB\/SL-RU Tax Group\)** option in the appropriate fixed asset depreciation book.  
  
 The non-linear depreciation method can be applied to groups of fixed assets using the depreciation groups set up in the **Depreciation Group** window. Each depreciation group should have a defined **Tax Depreciation Rate** and a **Depreciation Factor** with a value of **1**.  
  
 Before you use this method, you will have to make sure that the appropriate settings have been applied in the **Tax Register Setup** window. Use the information in the following table to apply the correct settings.  
  
|ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
|---------------------------------|---------------------------------------|  
|**Use Group Depr. Method from**|Enter the start date from which the non-linear depreciation method can be applied. The date should be the first day of the calendar year.|  
|**Min. Group Balance**|Enter the minimum amount that is valid as the balance for the depreciation group. If the book value for the fixed assets is less than this amount, the depreciation can be written off in this period.|  
|**Write-off in Charges**|Select if you want to write off fixed asset charges if the book value of the fixed assets is written off in the period when the book value is less than or equal to the **Min. Group Balance** amount. Otherwise, the book value will be written off in the next period.|  
  
## See Also  
 [Depreciation Bonus](../depreciation-bonus.md)   
 [How to: Create Fixed Assets](../how-to-create-fixed-assets.md)   
 Fixed Asset Card   
 Fixed Asset Journal   
 Fixed Asset G-L Journal   
 FA Depreciation Book   
 Depreciation Group   
 Tax Register Setup