---
title: "How to: Reconcile Bank Accounts by Using Bank Statements"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "bank reconciliation, using statements"
  - "worksheets, reconciling"
  - "statements, reconciling bank"
  - "bank reconciliation, accounts"
  - "bank accounts, bank statements"
ms.assetid: 0ea5ba10-929e-4385-aff9-b7f237e9f628
caps.latest.revision: 28
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "en-ca"
  - "es-mx"
  - "fr-ca"
---
# How to: Reconcile Bank Accounts by Using Bank Statements
[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] provides a **\($ N\_10120 Bank Rec.Worksheet $\)** that you can use to reconcile bank account ledger entries with bank statements.  
  
### To reconcile bank accounts with bank statements  
  
1.  In the **Search** box, enter **Bank Account Reconciliations**, and then choose the related link.  
  
2.  On the **Home** tab, in the **New** group, choose **New**.  
  
3.  On the **General** FastTab, fill in the required fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_10120\_1 Bank Account No. $\)**|The bank account number to reconcile.|  
    |**\($ T\_10120\_2 Statement No. $\)**|The bank statement number to reconcile.|  
    |**\($ T\_10120\_3 Statement Date $\)**|The bank statement date.|  
    |**\($ T\_10120\_4 Statement Balance $\)**|The bank statement balance.|  
  
4.  On the **Actions** tab, in the **Functions** group, choose **Mark Lines**.  
  
    > [!NOTE]  
    >  In the **Functions** group, you can also select the following bank reconciliation functions: suggest lines, clear lines, record adjustments, and recalculate the general ledger balance.  
  
5.  In the **\($ B\_10406 Bank Rec. Process Lines $\)** batch job, on the **[!INCLUDE[bp_optionsheading](../../DesignAndEngineering/includes/bp_optionsheading_md.md)]** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Record type to process**|Specify the type as **Checks**, **Deposits**, or **Both**.|  
    |**Mark lines as cleared**|Select to process the option selected in the **Record type to process** field.|  
  
6.  On the **Bank Rec. Line** FastTab, select the appropriate filters.  
  
7.  Choose the **OK** button.  
  
8.  In the **\($ N\_10120 Bank Rec.Worksheet $\)** window, on the **Adjustments** FastTab, on the **Bank Rec. Adj. Lines Subform** FastTab, enter information into the remaining fields to make adjustments.  
  
    > [!NOTE]  
    >  If needed, you can also use the [\($ N\_10120 Bank Rec.Worksheet $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Canada/-$-n_10120-bank-rec.worksheet-$-.md) window to view the **Bank Reconciliation Comments** card or the **Bank Reconciliation** card. This feature is available on the **Navigate** tab.  
  
9. On the **Actions** tab, in the **Posting** group, choose **Post**.  
  
## See Also  
 [How to: Fill In Bank Reconciliations](../../Finance/how-to-fill-in-bank-reconciliations.md)   
 [How to: Post Bank Reconciliations](../../Finance/how-to-post-bank-reconciliations.md)   
 [How to: Post a Bank Reconciliation](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Canada/how-to-post-a-bank-reconciliation.md)   
 [How to: Print Bank Reconciliation Reports](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Canada/how-to-print-bank-reconciliation-reports.md)   
 [\($ N\_372 Bank Account Ledger Entries $\)](assetId:///938660e6-9a0a-4be0-b063-f82dc7bcd9af)