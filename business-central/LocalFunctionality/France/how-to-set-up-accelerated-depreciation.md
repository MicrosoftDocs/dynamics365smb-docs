---
    title: How to Set Up Accelerated Depreciation
    description: To use the accelerated depreciation calculation, you must set up depreciation books for fixed assets.

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
# Set Up Accelerated Depreciation
To use the accelerated depreciation calculation, you must set up the following depreciation books for fixed assets:  

- The accounting depreciation book (integrated with the general ledger).  
- The tax depreciation book (not integrated with the general ledger).  

> [!NOTE]  
>  When you post an acquisition, depreciation, or disposal for the accounting depreciation book, the transaction is duplicated and posted in the tax depreciation book when the fixed asset journal is posted.  

## To set up the accounting depreciation book  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Depreciation Books**, and then choose the relevant link.  
2.  On the **Depreciation Book List** page, choose ¨the **New** action.  
3.  On the **General** FastTab, fill in the required fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Code**|The unique identification code for the accounting depreciation book. You can enter a maximum of 10 alphanumeric characters.|  
    |**Description**|The depreciation book description.|  

    > [!IMPORTANT]  
    >  Leave the **Derogatory Calculation** field blank.  

4.  On the **Integration** FastTab, select the **Derogatory** check box to integrate accelerated depreciation with the general ledger.  

    For more information, see [Set Up Fixed Asset Depreciation](../../fa-how-setup-depreciation.md).  

5.  Choose the **OK** button.  

## To set up the tax depreciation book  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Depreciation Books**, and then choose the relevant link.  
2.  On the **Depreciation Book List** page, choose the **New** action.  
3.  On the **General** FastTab, fill in the required fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Code**|The unique identification code for the tax depreciation book. You can enter a maximum of 10 alphanumeric characters.|  
    |**Description**|The tax depreciation book description.|  

4.  In the **Derogatory Calculation** field, select the accounting depreciation book code to indicate that this is a tax depreciation book to calculate derogatory depreciation.  

    For more information, see [Set Up Fixed Asset Depreciation](../../fa-how-setup-depreciation.md).  

5.  Choose the **OK** button.  

The **Used with Derogatory Book** field in the accounting depreciation book is updated with the tax depreciation book code.  

## See Also  
 [Accelerated Depreciation](accelerated-depreciation.md)   
 [Calculate Accelerated Depreciation](how-to-calculate-accelerated-depreciation.md)   
[Set Up Fixed Asset Depreciation](../../fa-how-setup-depreciation.md)
