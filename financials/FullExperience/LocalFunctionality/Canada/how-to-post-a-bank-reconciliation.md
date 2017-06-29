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
# How to: Post a Bank Reconciliation
You can post bank reconciliation if you have reconciled the bank accounts in the **Bank Rec.Worksheet** window. For more information, see [How to: Reconcile Bank Accounts by Using Bank Statements](../FullExperience/how-to-reconcile-bank-accounts-by-using-bank-statements.md).  
  
 After the bank reconciliation has been posted, a bank account statement is created, and can be viewed from the relevant bank account card.  
  
### To post a bank reconciliation  
  
1.  In the **Search** box, enter **Bank Account Reconciliations**, and then choose the related link.  
  
2.  Select the bank account reconciliation that you want to post. On the **Home** tab, in the **Manage** group, choose **Edit**.  
  
    > [!NOTE]  
    >  On the **General** FastTab, the **Difference** field be must be zero before you can post the bank reconciliation.  
  
     When the bank reconciliation is posted, all of the related files are posted to the historical **Post Bank Rec. Worksheet** table. Any adjustments are posted to the **G\/L Entry** table.  
  
3.  On the **Actions** tab, in the **Posting** group, choose **Post**.  
  
     The bank reconciliation is posted.  
  
4.  To review a preliminary draft of the bank reconciliation statement, run the Bank Rec. Test Report. To do this, on the **Actions** tab, in the **Posting** group, choose **Test Report**.  
  
### To view the posted bank account reconciliations  
  
1.  In the **Search** box, enter **Bank Accounts**, and then choose the related link.  
  
2.  Select the bank account for which you want to view the posted reconciliations. On the **Navigate** tab, in the **Bank Acc.** group, choose **Statements**.  
  
3.  Choose the **Close** button.  
  
## See Also  
 [How to: Print Bank Reconciliation Reports](../FullExperience/how-to-print-bank-reconciliation-reports.md)   
 [How to: Reconcile Bank Accounts by Using Bank Statements](../FullExperience/how-to-reconcile-bank-accounts-by-using-bank-statements.md)   
 Bank Account Card   
 Bank Account   
 G\/L Entry   
 Bank Rec.Worksheet   
 Bank Rec. Test Report   
 Posted Bank Rec. Header