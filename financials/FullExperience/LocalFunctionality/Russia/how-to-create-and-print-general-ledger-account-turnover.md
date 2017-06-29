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
ADD INCLUDE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]--> enables you to create general ledger account turnover information in the **G\/L Account Turnover** window.  
  
 You can then verify this information in the following reports:  
  
-   **G\/L Account Turnover**  
  
-   **G\/L Account Card**  
  
-   **G\/L Account Entries Analysis**  
  
### To create a general ledger account turnover entry  
  
1.  In the **Search** box, enter **G\/L Account Turnover**, and then choose the related link.  
  
2.  On the **General** FastTab, enter the following information.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Date Filter**|Enter the date filter for which you want to view account information.|  
    |**Business Unit Filter**|Select the business unit filter for which you want to view account information.|  
    |**Department Filter**|Select the department filter for which you want to view account information.|  
    |**Incexp Filter**|Select the income and expenses filter for which you want to view account information.|  
    |**Switch Debit\/Credit**|Specify if you want to show the debit and credit balance for the account.|  
  
     On the **Source** FastTab, enter the following information.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Source Type Filter**|Specify the source type filter for which you want to view account information.|  
    |**Source No. Filter**|Select the source number filter for which you want to view account information.|  
  
### To print the general ledger account turnover report  
  
1.  In the **Search** box, enter **G\/L Account Turnover**, and then choose the related link.  
  
2.  On the **Options** FastTab, enter the following information.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**\($ R\_12436\_N\_2\_5 Rounding Precision $\)**|Specify the interval that you want to use as the rounding difference for the relevant currency.|  
    |**\($ R\_12436\_N\_2\_7 Replace zero values by blanks $\)**|Select if you want to replace zero values with a blank entry.|  
    |**\($ R\_12436\_N\_2\_9 Skip accounts without net changes $\)**|Select to exclude the accounts that do not have net changes.|  
    |**\($ R\_12436\_N\_2\_11 Skip accounts without zero ending balance $\)**|Select to exclude the accounts that do have zero ending balances.|  
    |**\($ R\_12436\_N\_2\_13 Skip zero lines $\)**|Select to exclude lines with zero values.|  
  
### To print the general ledger account card report  
  
1.  In the **Search** box, enter **G\/L Account Card**, and then choose the related link.  
  
2.  On the **Options** FastTab, enter the following information.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**\($ R\_12437\_N\_2\_1210004 Show Correspondence $\)**|Select if you want to show general ledger correspondence information on the report.|  
    |**\($ R\_12437\_N\_2\_1210002 New Page for GL Acc $\)**|Select if you want to print a new page for each general ledger account.|  
    |**\($ R\_12437\_N\_2\_1210000 Including Closing Period Entries $\)**|Select if you want to include the closing period entries on the report.|  
  
### To print the general ledger account entries analysis report  
  
1.  In the **Search** box, enter **G\/L Account Entries Analysis**, and then choose the related link.  
  
2.  On the **Options** FastTab, enter the following information.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**\($ R\_12438\_N\_2\_7 Without Zero Net Changes $\)**|Select to include the entries that do not have zero net changes.|  
    |**\($ R\_12438\_N\_2\_9 Without Zero Lines $\)**|Select to include the entries that do not have zero lines.|  
    |**\($ R\_12438\_N\_2\_11 Debit Credit Separately $\)**|Select if you want to separate the debit and credit entries on the report.|  
    |**\($ R\_12438\_N\_2\_1 New Page for GL Acc $\)**|Select if you want to print a new page for each general ledger account.|  
  
## See Also  
 G\/L Account   
 G\-L Account Turnover   
 G\-L Account Card   
 G\-L Account Entries Analysis