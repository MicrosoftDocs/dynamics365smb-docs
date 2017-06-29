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
# How to: Define Accounting Periods for Straight Line Depreciation of Fixed Assets
You can define 13 accounting periods to calculate straight line depreciation. You must calculate depreciation daily and distribute across the relevant periods. You can also define these accounting periods in the **FA \- Projected Value** report.  
  
> [!NOTE]  
>  To calculate depreciation using both the old \(360 days\) and the new methods \(365 or 366 days\), create separate depreciation books; one for the old method, and one for the new method. Attach these books to the relevant assets.  
  
### To define accounting periods to calculate straight line depreciation  
  
1.  In the **Search** box, enter **Depreciation Books**, and then choose the related link.  
  
2.  To open a new **Depreciation Book Card** window, on the **Home** tab, choose **New**.  
  
3.  On the **General** FastTab, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Code**|Specify a unique code that identifies the depreciation book. You can enter a maximum of 10 alphanumeric characters.|  
    |**Description**|Specify a description for the depreciation book.|  
    |**Use Accounting Period**|Specify if you want to define 13 accounting periods \(365 or 366 days\) for calculation. **Note:**  To use 360 days for calculation, do not select this field.|  
  
4.  Enter information into the required fields.  
  
5.  Choose the **OK** button.  
  
### To define accounting periods in the FA \- Projected Value report  
  
1.  In the **Search** box, enter **FA \- Projected Value**, and then choose the related link.  
  
2.  On the **Options** FastTab, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**\($ R\_10560\_N\_2\_3 Depreciation Book $\)**|Specify the depreciation book code that must be included in the report.|  
    |**\($ R\_10560\_N\_2\_14 First Depreciation Date $\)**|Enter the start date for the period for which you must calculate projected depreciation.|  
    |**\($ R\_10560\_N\_2\_15 Last Depreciation Date $\)**|Enter the end date for the period for which you must calculate projected depreciation. **Note:**  This date must be later than the last depreciation date.|  
    |**\($ R\_10560\_N\_2\_1040000 Number of Days $\)**|Enter the number of days between the first depreciation date and the last depreciation date. **Note:**  If this field is blank, the contents of this field will be set to equal the number of days in a fiscal year, typically 360.|  
    |**\($ R\_10560\_N\_2\_11 Posted Entries From $\)**|Enter a date if you must include posted entries in the report. The report will include all the posted entries that have been posted from that fixed asset posting date.|  
  
3.  Choose the **Print** button to print the report or choose the **Preview** button to view it on the screen.  
  
## See Also  
 Accounting Period   
 Fixed Asset \- Projected Value   
 [United Kingdom Local Functionality](../../LocalFunctionalityForMicrosoftDynamicsNav2016/UnitedKingdom/united-kingdom-local-functionality.md)