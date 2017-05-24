---
title: "How to: Import Payroll Transactions"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "payroll, setting up integration"
  - "payroll, importing transactions"
ms.assetid: 65972941-ee1a-4403-aa00-ed4e8a97329c
caps.latest.revision: 3
ms.author: "edupont"
translation.priority.ht: 
  - "nb-no"
---
# How to: Import Payroll Transactions
You can import payroll transactions into a general journal from two external payroll solutions: Huldt & Lillevik and Hogia. You can then use the general journal to post the imported payroll transactions to general ledger accounts or bank accounts. To import payroll transactions, you must first set up payroll integration.  
  
### To set up payroll integration  
  
1.  In the **Search** box, enter **Payroll Integration Setup**, and then choose the related link.  
  
2.  On the **General** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_15000200\_10 Payroll System $\)**|Select a payroll system.|  
    |**\($ T\_15000200\_11 File Name $\)**|Enter the full path of the file.|  
    |**\($ T\_15000200\_14 Save Payroll File $\)**|Select to save the payroll file.|  
    |**\($ T\_15000200\_13 Import Department and Project $\)**|Select to import department and project information.|  
    |**\($ T\_15000200\_20 Journal Template Name $\)**|Select the name of the journal template.|  
    |**\($ T\_15000200\_21 Journal Name $\)**|Select a journal to receive the imported payroll transactions.|  
    |**\($ T\_15000200\_30 Post to $\)**|Select the account type to post the payroll transactions to. Account types include **G\/L Account** and **Bank Account**.|  
  
3.  Choose the **OK** button.  
  
### To import payroll transactions  
  
1.  In the **Search** box, enter **General Journals**, and then choose the related link.  
  
2.  On the **Home** tab, in the **Process** group, choose **Import Payroll**.  
  
3.  On the **Options** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Posting Date**|Select a payroll system.|  
    |**Document text**|Enter the full path of the file.|  
    |**File Name**|Specify the file name for the payroll file.|  
  
4.  Choose the **OK** button.  
  
## See Also  
 [Norway Local Functionality](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/norway-local-functionality.md)   
 [\($ N\_39 General Journal $\)](assetId:///a60a346f-f336-47bb-b046-55a1595e1555)   
 [\($ N\_15000200 Payroll Integration Setup $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/-$-n_15000200-payroll-integration-setup-$-.md)   
 [\($ B\_15000067 Import Hogia Windows Payroll $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/-$-b_15000067-import-hogia-windows-payroll-$-.md)   
 [\($ B\_15000066 Import Huldt & Lillevik $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/-$-b_15000066-import-huldt-lillevik-$-.md)