---
    title: How to Calculate Accelerated Depreciation
    description: In Business Central, you calculate periodic depreciation for fixed assets by using the Calculate Depreciation batch job. The fixed asset depreciation book that is linked to the fixed asset defines the depreciation method, the starting date for depreciation, and the fixed asset posting group that is used in the batch job.

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
# Calculate Accelerated Depreciation
In [!INCLUDE[d365fin](../../includes/d365fin_md.md)], you calculate periodic depreciation for fixed assets by using the **Calculate Depreciation** batch job. The fixed asset depreciation book that is linked to the fixed asset defines the depreciation method, the starting date for depreciation, and the fixed asset posting group that is used in the batch job.  

If a fixed asset depreciation book is integrated with the general ledger, then it is called an *accounting depreciation book*. If a fixed asset depreciation book is not integrated with the general ledger, then it is called a *tax depreciation book*.  

You can only calculate the accelerated depreciation for fixed assets that have an accounting depreciation book and a tax depreciation book. For more information about setting up tax depreciation books and accounting depreciation books for fixed assets, see [Set Up Accelerated Depreciation](how-to-set-up-accelerated-depreciation.md).  

Entries are transferred to the fixed asset general journal when you select an accounting depreciation book in the batch job. Entries are transferred to the fixed asset journal when you select the tax depreciation book.  

## To calculate accelerated depreciation  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Calculate Depreciation**, and then choose the relevant link.  
2.  On the **Calculate Depreciation** page, on the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Depreciation Book**|The unique identification code for the accounting depreciation book.|  
    |**FA Posting Date**|Specify the ending date for the depreciation calculation, if this is the first depreciation entry for the asset. The depreciation starting date that is defined on the **FA Depreciation Books** page is used as the starting date for the depreciation calculation. If you have already depreciated the asset, the fixed asset posting date of the last depreciation entry is used as the starting date for the depreciation calculation.|  
    |**Use Force No. of Days**|Select to use the number of days in the **Force No. of Days** field for the depreciation calculation.|  
    |**Force No. of Days**|The number of days for the depreciation calculation. You can only enter a number in this field if the **Use Force No of Days** check box is selected.|  
    |**Posting Date**|The posting date for the calculated depreciation.<br /><br /> You can leave this field blank if the **Use Same FA + G/L Posting Dates** field in the accounting depreciation book is selected. The posting date is copied to the resulting journal lines.|  
    |**Document No.**|The document number for the fixed asset journal batch. Leave this field blank if you have set up a numbering series for the fixed asset journal batch on the **No. Series** page. For more information, see No. Series.|  
    |**Posting Description**|The posting description for the fixed asset journal entries.|  
    |**Insert Bal. Account**|Select to automatically insert balancing accounts in the resulting journal. The **Calculate Depreciation** batch job only uses balancing accounts that are defined in the FA Posting Group.|  

3.  On the **Fixed Asset** FastTab, select the appropriate filters.  
4.  Choose the **OK** button.  

The accelerated depreciation for the fixed asset is calculated.  

## See Also  
 [Accelerated Depreciation](accelerated-depreciation.md)   
 [Set Up Accelerated Depreciation](how-to-set-up-accelerated-depreciation.md)   
 [Set Up Fixed Asset Depreciation](../../fa-how-setup-depreciation.md)  
 [Fixed Assets](../../fa-manage.md)
