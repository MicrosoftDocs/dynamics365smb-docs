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
# How to: Print Bank Reconciliation Reports
In [!INCLUDE[d365fin](../../includes/d365fin_md.md)], you can print the following bank reconciliation reports:  
  
-   **Bank Rec. Test Report** - Displays the list of errors that are found in the bank reconciliation statement. You can generate this report before you post the bank reconciliation statement to make sure that there are no errors in the statement.  
  
-   **Bank Account – Reconcile** - Displays the reconciliation details for each bank account. This report lists deposits, withdrawals, and adjustments for a bank account.  
  
### To print a bank reconciliation test report  
  
1.  In the **Search** box, enter **Bank Account Reconciliations**, and then choose the related link.  
  
2.  On the **Report** tab, in the **General** group, choose **Bank Rec. Test Report**.  
  
3.  On the **Options** FastTab, fill in the fields as described in the following table.  
  
    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Print details**|Select to print reconciliation details in the report. If you select this check box, all of the other print check boxes are automatically selected. You can clear a check box if you do not want to include its details in the report.|  
    |**Print checks**|Select to print check details in the report.|  
    |**Print deposits**|Select to print deposit details in the report.|  
    |**Print adjustments**|Select to print adjustment details in the report.|  
    |**Print outstanding checks**|Select to print outstanding check details in the report.|  
    |**Print outstanding deposits**|Select to print outstanding deposit details in the report.|  
  
4.  On the **Bank Rec. Header** FastTab, select the appropriate filters.  
  
5.  Choose the **Print** button to print the report or choose the **Preview** button to view it on the screen.  
  
### To print a bank reconciliation report  
  
1.  In the **Search** box, enter **Bank Account Reconciliations**, and then choose the related link.  
  
2.  On the **Report** tab, in the **General** group, choose **Bank Account – Reconcile**.  
  
3.  To print each bank account on a new page, on the **Options** FastTab, select the **New Page per Bank Account** check box.  
  
4.  On the **Bank Account** FastTab, select the appropriate filters.  
  
5.  Choose the **Print** button to print the report or choose the **Preview** button to view it on the screen.  
  
## See Also  
 [How to: Reconcile Bank Accounts by Using Bank Statements](how-to-reconcile-bank-accounts-by-using-bank-statements.md)   
 [How to: Post a Bank Reconciliation](how-to-post-a-bank-reconciliation.md)   
 Bank Rec. List   
 Bank Account Card   
 Bank Account   
 Bank Rec. Test Report   
 Bank Account - Reconcile