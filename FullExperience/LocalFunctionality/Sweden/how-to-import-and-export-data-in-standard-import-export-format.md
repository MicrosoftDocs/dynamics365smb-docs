---
title: "How to: Import and Export Data in Standard Import Export Format"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "import, SIE format"
  - "standard import export (SIE)"
  - "export data, SIE format"
ms.assetid: 9ec17b81-5ed2-41d0-9dd8-34711c5506cf
caps.latest.revision: 23
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "sv-se"
---
# How to: Import and Export Data in Standard Import Export Format
You can import and export general ledger data according to the standard import export \(SIE\) format. By specifying SIE dimensions and file types, you can specify the level of detail covered by import or export transactions. For more information, see [Standard Import Export Group](http://go.microsoft.com/fwlink/?LinkID=164870&clcid=0x41d).  
  
### To import data in SIE format  
  
1.  In the **Search** box, enter **SIE Import**, and then choose the related link.  
  
2.  Fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**File Name**|Enter the name and path of the file that you want to import.|  
    |**Gen. Journal Template**|Select a general journal template.|  
    |**Gen. Journal Batch**|Select a general journal batch.|  
    |**Dimensions**|Select the SIE dimensions to import.|  
    |**Insert G\/L Account**|Select if the general ledger account in the import file is missing in the chart of accounts and needs to be set up during the import process.|  
    |**Use Number Series for Doc. No.**|Select if a document number is not provided in the import file.|  
  
3.  Choose the **OK** button.  
  
### To export data in SIE format  
  
1.  In the **Search** box, enter **SIE Export**, and then choose the related link.  
  
2.  On the **G\/L Account** FastTab, choose the appropriate filters.  
  
3.  On the **Options** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**File Type**|Select the type of file to be created. Select from one of the following options:<br /><br /> -   **Year \- End Balances** \- Contains the annual account balance carried forward for all accounts in the chart of accounts.<br />-   **Periodic Balances** \- Contains the annual account balance carried forward and monthly changes for all accounts in the chart of accounts.<br />-   **Object Balances** \- Contains the annual account balance carried forward, monthly changes, and balances on the object level, such as cost units and projects, for all accounts in the chart of accounts.<br />-   **Transactions** \- Contains all the general ledger entries for the period.|  
    |**File Name**|Enter the name and path of the file that you want to create.|  
    |**Contact**|Enter the contact person. This field is optional.|  
    |**Comments**|Describe the content of the file.|  
    |**Dimensions**|Select the dimensions to export.|  
    |**Fiscal Year**|Enter the fiscal tax year.|  
  
4.  Choose the **OK** button.  
  
## See Also  
 [Standard Import Export Group](http://go.microsoft.com/fwlink/?LinkID=164870&clcid=0x41d)   
 [SIE Dimensions](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Sweden/-$-n_11212-sie-dimensions-$-.md)   
 [SIE Import](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Sweden/-$-b_11208-sie-import-$-.md)   
 [SIE Export](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Sweden/-$-b_11207-sie-export-$-.md)   
 [Sweden Local Functionality](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Sweden/sweden-local-functionality.md)