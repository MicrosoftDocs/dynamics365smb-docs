---
title: Import and Export Data in SIEE [SE]
description: You can import and export general ledger data according to the standard import export (SIE) format explained in this topic.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.search.form: 11212
ms.date: 06/24/2021
ms.author: bholtorf
---

# Import and Export Data in Standard Import Export Format in the Swedish Version

You can import and export general ledger data according to the standard import export (SIE) format. By specifying SIE dimensions and file types, you can specify the level of detail covered by import or export transactions. For more information, see [Standard Import Export Group](https://go.microsoft.com/fwlink/?LinkID=164870&clcid=0x41d).  

> [!NOTE]
> As of version 22.1, the Swedish localization has been moved to the extensions, and this feature is delocalized. Because the localization is now created as an extension, you must enable the feature to use it. For more information about this process, see [Import and export data in the standard import export (SIE) format](how-to-use-sie-audit-files-export.md).

## To import data in SIE format  

1.  Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **SIE Import**, and then choose the related link.  
2.  Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Gen. Journal Template**|Select a general journal template.|  
    |**Gen. Journal Batch**|Select a general journal batch.|  
    |**Dimensions**|Select the SIE dimensions to import.|  
    |**Insert G/L Account**|Select if the general ledger account in the import file is missing in the chart of accounts and needs to be set up during the import process.|  
    |**Use Number Series for Doc. No.**|Select if a document number is not provided in the import file.|  

3. Choose the **OK** button.
4. Select the file to import.  

## To export data in SIE format  

1.  Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **SIE Export**, and then choose the related link.  
2.  On the **G/L Account** FastTab, choose the appropriate filters.  
3.  On the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**File Type**|<p>Select the type of file to be created. Select from one of the following options:</p><ul><li>**Year - End Balances** - Contains the annual account balance carried forward for all accounts in the chart of accounts.</li><li>**Periodic Balances** - Contains the annual account balance carried forward and monthly changes for all accounts in the chart of accounts.</li><li>**Object Balances** - Contains the annual account balance carried forward, monthly changes, and balances on the object level, such as cost units and projects, for all accounts in the chart of accounts.</li><li>**Transactions** - Contains all the general ledger entries for the period.</li></ul>|  
    |**Contact**|Enter the contact person. This field is optional.|  
    |**Comments**|Describe the content of the file.|  
    |**Dimensions**|Select the dimensions to export.|  
    |**Fiscal Year**|Enter the fiscal tax year.|

4. Choose the **OK** button.
5. Choose the **Open** or **Save** button to decide where to place the exported file.

## See Also  
 [Standard Import Export Group](https://go.microsoft.com/fwlink/?LinkID=164870&clcid=0x41d)   
 [Sweden Local Functionality](sweden-local-functionality.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
