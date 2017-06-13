---
title: "How to: Create and Print General Ledger Account Turnover"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "account turnover, printing"
  - "turnover, general ledger accounts"
  - "account turnover, creating"
  - "account turnover"
  - "general ledger, turnover accounts"
ms.assetid: fa45e5b7-b412-483d-bcb1-fc33a88349c7
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "ru-ru"
---
# How to: Create and Print General Ledger Account Turnover
[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] enables you to create general ledger account turnover information in the **G\/L Account Turnover** window.  
  
 You can then verify this information in the following reports:  
  
-   **G\/L Account Turnover**  
  
-   **G\/L Account Card**  
  
-   **G\/L Account Entries Analysis**  
  
### To create a general ledger account turnover entry  
  
1.  In the **Search** box, enter **G\/L Account Turnover**, and then choose the related link.  
  
2.  On the **General** FastTab, enter the following information.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Date Filter**|Enter the date filter for which you want to view account information.|  
    |**Business Unit Filter**|Select the business unit filter for which you want to view account information.|  
    |**Department Filter**|Select the department filter for which you want to view account information.|  
    |**Incexp Filter**|Select the income and expenses filter for which you want to view account information.|  
    |**Switch Debit\/Credit**|Specify if you want to show the debit and credit balance for the account.|  
  
     On the **Source** FastTab, enter the following information.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Source Type Filter**|Specify the source type filter for which you want to view account information.|  
    |**Source No. Filter**|Select the source number filter for which you want to view account information.|  
  
### To print the general ledger account turnover report  
  
1.  In the **Search** box, enter **G\/L Account Turnover**, and then choose the related link.  
  
2.  On the **Options** FastTab, enter the following information.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Rounding Precision**|Specify the interval that you want to use as the rounding difference for the relevant currency.|  
    |**Replace zero values by blanks**|Select if you want to replace zero values with a blank entry.|  
    |**Skip accounts without net changes**|Select to exclude the accounts that do not have net changes.|  
    |**Skip accounts without zero ending balance**|Select to exclude the accounts that do have zero ending balances.|  
    |**Skip zero lines**|Select to exclude lines with zero values.|  
  
### To print the general ledger account card report  
  
1.  In the **Search** box, enter **G\/L Account Card**, and then choose the related link.  
  
2.  On the **Options** FastTab, enter the following information.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Show Correspondence**|Select if you want to show general ledger correspondence information on the report.|  
    |**New Page for GL Acc**|Select if you want to print a new page for each general ledger account.|  
    |**Including Closing Period Entries**|Select if you want to include the closing period entries on the report.|  
  
### To print the general ledger account entries analysis report  
  
1.  In the **Search** box, enter **G\/L Account Entries Analysis**, and then choose the related link.  
  
2.  On the **Options** FastTab, enter the following information.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Without Zero Net Changes**|Select to include the entries that do not have zero net changes.|  
    |**Without Zero Lines**|Select to include the entries that do not have zero lines.|  
    |**Debit Credit Separately**|Select if you want to separate the debit and credit entries on the report.|  
    |**New Page for GL Acc**|Select if you want to print a new page for each general ledger account.|  
  
## See Also  
 [G\/L Account](assetId:///a65c2b09-9bb2-43db-8c53-c047bfc49777)   
 [G\-L Account Turnover](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/-$-r_12436-g-l-account-turnover-$-.md)   
 [G\-L Account Card](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/-$-r_12437-g-l-account-card-$-.md)   
 [G\-L Account Entries Analysis](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/-$-r_12438-g-l-account-entries-analysis-$-.md)