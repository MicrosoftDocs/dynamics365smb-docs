---
    title: Insert topic title| Microsoft Docs
    description: Insert description
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

    ---
# How to: Display Reconciled Transactions
You can identify whether items are reconciled in the **Bank Account Reconciliations** window. You can also view the total value of all reconciled transactions.  
  
### To display reconciled transactions  
  
1.  In the **Search** box, enter **Bank Account Reconciliations**, and then choose the related link.  
  
2.  In the **Bank Account Reconciliations** window, select bank account. On the **Home** tab, choose **Edit**.  
  
3.  Expand the **Lines** FastTab.  
  
4.  Fill in the fields as described in the following table.  
  
    |FIX INCLUDE HERE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)] -->|FIX INCLUDE HERE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)] -->|  
    |---------------------------------|---------------------------------------|  
    |**Document No.**|Specifies the document number for the transaction.|  
    |**Check No.**|Specifies the check number for the transaction.|  
    |**Reconciled**|Specifies if the transaction has been reconciled.|  
    |**Applied Entries**|Specifies if the transaction has been applied to one or more bank accounts or check ledger entries.|  
  
5.  In the **Reconciled** field, view the value of the reconciled transaction.  
  
6.  In the **Total Reconciled** field, view the total value of all reconciled transactions.  
  
7.  To mark transactions as **Reconciled**, select a transaction. On the **Lines** toolbar, select the **Functions** menu, and then choose **Toggle Reconciled**.  
  
8.  Choose the **OK** button.  
  
 To apply a statement line to an entry in **BACS Ledger Entry** table, you must use the **Apply Entries** function, in the same way you would do it for check ledger entries. For more information, see Bank Acc. Reconciliation and [How to: Match Bank Statement Lines with Bank Account Ledger Entries](../../Finance/how-to-match-bank-statement-lines-with-bank-account-ledger-entries.md).  
  
## See Also  
 Bank Acc. Recon. Statement   
 [United Kingdom Local Functionality](../../LocalFunctionalityForMicrosoftDynamicsNav2016/UnitedKingdom/united-kingdom-local-functionality.md)   
 [Reconcile Bank Accounts](../../Finance/reconcile-bank-accounts.md)