---
title: "How to: Import and Reconcile Bank Statements"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "reconciling, bank statements"
  - "bank statements, importing"
  - "giro, importing"
  - "bank journals, importing"
  - "bank statements, reconciling"
ms.assetid: 393f4b25-dd6f-475d-943e-62f65847dc85
caps.latest.revision: 21
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "nl-nl"
---
# How to: Import and Reconcile Bank Statements
Banks provide electronic bank statements for all your financial interactions. You can import these statements into the bank or giro journals.  
  
 The import bank statement is supported by the following protocols:  
  
-   Rabobank mut.asc  
  
-   Rabobank vvmut.ac  
  
-   Rabobank ASCII  
  
-   SEPA CAMT  
  
 For more information, see [\($ T\_11000007 Import Protocol $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/-$-t_11000007-import-protocol-$-.md).  
  
### To import and reconcile bank statements  
  
1.  In the **Search** box, enter **Import Bank Statement**, and then choose the related link.  
  
2.  In the **\($ N\_11000016 Import Protocol List $\)** window, select the required import protocol, and then choose the **OK** button.  
  
3.  To reconcile the bank statements automatically when importing, on the **Options** FastTab, select the **Automatic Reconciliation** check box.  
  
    > [!NOTE]  
    >  This function does not work for bank statement files of type SEPA CAMT. Instead, use the **Match Automatically** action in the **\($ N\_379 Bank Acc. Reconciliation $\)** window. For more information, see [How to: Match Bank Statement Lines with Bank Account Ledger Entries](../../Finance/how-to-match-bank-statement-lines-with-bank-account-ledger-entries.md).  
  
4.  Choose the **OK** button.  
  
5.  To import the file that contains the electronic bank statement, specify the file name and path, and then choose the **Open** button.  
  
     The electronic bank statement is imported into the bank or giro journals. For more information, see [Dutch Electronic Banking](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/dutch-electronic-banking.md).  
  
## See Also  
 [Dutch Electronic Banking](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/dutch-electronic-banking.md)   
 [\($ T\_11000007 Import Protocol $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/-$-t_11000007-import-protocol-$-.md)   
 [\($ T\_11401\_11000001 Reconciliation Status Field $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/-$-t_11401_11000001-reconciliation-status-field-$-.md)   
 [\($ T\_11401 CBG Statement Line Table $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/-$-t_11401-cbg-statement-line-table-$-.md)   
 [\($ N\_11400 Bank\-Giro Journal Window $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/-$-n_11400-bank-giro-journal-window-$-.md)   
 [How to: Match Bank Statement Lines with Bank Account Ledger Entries](../../Finance/how-to-match-bank-statement-lines-with-bank-account-ledger-entries.md)