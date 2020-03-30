---
    title: How to Set Up Alternate Depreciation Methods
    description: Alternate depreciation methods include anticipated depreciation, accelerated depreciation, and reduced depreciation.

    services: project-madeira 
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Set Up Alternate Depreciation Methods
Alternate depreciation methods include the following:  

- Anticipated depreciation.  
- Accelerated depreciation.  
- Reduced depreciation.  

You must create depreciation tables to set up these depreciation methods.  

## To set up alternate depreciation methods  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Depreciation Tables**, and then choose the related link.  
2.  On the **Depreciation Table List** page, choose the **New** action.  
3.  On the **General** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Code**|The code for the depreciation table.|  
    |**Description**|The description for the depreciation table.|  
    |**Period Length**|The length of the period to which each of the depreciation table lines will apply.|  
    |**Total No. of Units**|The total number of units that the asset is expected to produce in its lifetime.|  

4.  On the **Lines** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Period Depreciation %**|The depreciation percentage to apply to the period.|  
    |**No. of Units in Period**|The number of units produced by the asset to which this depreciation table applies.|  
    |**Anticipated %**|The anticipated depreciation percentage.|  
    |**Accelerated/Reduced %**|The actual depreciation percentage.|  

5.  In the **Total Depreciation %** field, enter the total depreciation percentage.  
6.  Choose the **OK** button.  

## See Also  
 [Set Up Fixed Asset Depreciation](../../fa-how-setup-depreciation.md)   
 [Italian Fixed Assets](italian-fixed-assets.md)   
 [Create Multiple Fixed Asset Cards](how-to-create-multiple-fixed-asset-cards.md)   
 [Set Up Compressed Depreciation of Fixed Assets](how-to-set-up-compressed-depreciation-of-fixed-assets.md)   
 [Print Depreciation Book Reports](how-to-print-depreciation-book-reports.md)
