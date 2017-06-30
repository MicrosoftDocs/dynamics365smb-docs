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
# How to: Set Up Alternate Depreciation Methods
Alternate depreciation methods include the following:  
  
-   Anticipated depreciation.  
  
-   Accelerated depreciation.  
  
-   Reduced depreciation.  
  
 You must create depreciation tables to set up these depreciation methods.  
  
### To set up alternate depreciation methods  
  
1.  In the **Search** box, enter **Depreciation Tables**, and then choose the related link.  
  
2.  In the **Depreciation Table List** window, in the **Home** tab, choose **New**.  
  
3.  On the **General** FastTab, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Code**|The code for the depreciation table.|  
    |**Description**|The description for the depreciation table.|  
    |**Period Length**|The length of the period to which each of the depreciation table lines will apply.|  
    |**Total No. of Units**|The total number of units that the asset is expected to produce in its lifetime.|  
  
4.  On the **Lines** FastTab, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Period Depreciation %**|The depreciation percentage to apply to the period.|  
    |**No. of Units in Period**|The number of units produced by the asset to which this depreciation table applies.|  
    |**Anticipated %**|The anticipated depreciation percentage.|  
    |**Accelerated\/Reduced %**|The actual depreciation percentage.|  
  
5.  In the **Total Depreciation %** field, enter the total depreciation percentage.  
  
6.  Choose the **OK** button.  
  
## See Also  
 [How to: Set Up User-Defined Depreciation Methods](../how-to-set-up-user-defined-depreciation-methods.md)   
 [Italian Fixed Assets](../italian-fixed-assets.md)   
 [How to: Create Multiple Fixed Asset Cards](../how-to-create-multiple-fixed-asset-cards.md)   
 [How to: Set Up Compressed Depreciation of Fixed Assets](../how-to-set-up-compressed-depreciation-of-fixed-assets.md)   
 [How to: Print Depreciation Book Reports](../how-to-print-depreciation-book-reports.md)