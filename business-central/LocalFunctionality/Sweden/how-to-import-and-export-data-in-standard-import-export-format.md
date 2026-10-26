---
title: Import and Export SIE Data in Earlier Swedish Versions [SE]
description: Find the earlier SIE import and export report procedures for the Swedish version of Business Central, with a link to the current extension.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: import, export, standard import export, SIE, general ledger data
ms.search.form: 11212
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Import and export SIE data in earlier Swedish versions

Earlier Swedish versions provide **SIE Import** and **SIE Export** reports for general ledger data. By specifying SIE dimensions and file types, you can specify the level of detail covered by import or export transactions. Learn more at the [Standard Import Export Group website](https://go.microsoft.com/fwlink/?LinkID=164870&clcid=0x41d).

> [!NOTE]
> The procedures below describe the earlier reports. The current Standard Import Export (SIE) extension uses **Import SIE** for imports and **Audit File Export Documents** for exports. Learn about the current setup and procedures in [Import and export data in the standard import export (SIE) format](how-to-use-sie-audit-files-export.md).

## Import data in SIE format  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **SIE Import**, and then choose the related link.  
1. Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Gen. Journal Template**|Select a general journal template.|  
    |**Gen. Journal Batch**|Select a general journal batch.|  
    |**Dimensions**|Select the SIE dimensions to import.|  
    |**Insert G/L Account**|Select if the general ledger account in the import file is missing in the chart of accounts and needs to be set up during the import process.|  
    |**Use Number Series for Doc. No.**|Select if a document number isn't provided in the import file.|  

1. Choose the **OK** button.
1. Select the file to import.  

## Export data in SIE format  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **SIE Export**, and then choose the related link.  
1. On the **G/L Account** FastTab, choose the appropriate filters.  
1. On the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**File Type**|<p>Select the type of file to be created. Select from one of the following options:</p><ul><li>**Year - End Balances** - Contains the annual account balance carried forward for all accounts in the chart of accounts.</li><li>**Periodic Balances** - Contains the annual account balance carried forward and monthly changes for all accounts in the chart of accounts.</li><li>**Object Balances** - Contains the annual account balance carried forward, monthly changes, and balances on the object level, such as cost units and projects, for all accounts in the chart of accounts.</li><li>**Transactions** - Contains all the general ledger entries for the period.</li></ul>|  
    |**Contact**|Enter the contact person. This field is optional.|  
    |**Comments**|Describe the content of the file.|  
    |**Dimensions**|Select the dimensions to export.|  
    |**Fiscal Year**|Enter the fiscal tax year.|

1. Choose the **OK** button.
1. Choose the **Open** or **Save** button to decide where to place the exported file.

## Related information

- [Standard Import Export Group](https://go.microsoft.com/fwlink/?LinkID=164870&clcid=0x41d)   
- [Sweden Local Functionality](sweden-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
