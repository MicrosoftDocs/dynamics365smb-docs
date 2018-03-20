---
    title: Reconciling Bank Accounts | Microsoft Docs
    description: In the **Bank Rec. Worksheet** window, you can reconcile bank account ledger entries with bank statements.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 16/03/2018
    ms.author: sgroespe

---
# Reconciling Bank Accounts

[!INCLUDE[d365fin](../../includes/d365fin_md.md)] provides the **Bank Rec. Worksheet**, which you can use to reconcile bank account ledger entries with bank statements.

> [!NOTE]  
> In the North American version, you can also use the standard bank reconciliation functionality. For more information, see [Reconcile Bank Accounts Separately](../../bank-how-reconcile-bank-accounts-separately.md).

## To reconcile bank accounts with bank statements  

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Bank Account Reconciliations**, and then choose the related link.
2. Choose the **New** action.  
3. On the **General** FastTab, fill in the required fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Bank Account No.**|The bank account number to reconcile.|  
    |**Statement No.**|The bank statement number to reconcile.|  
    |**Statement Date**|The bank statement date.|  
    |**Statement Balance**|The bank statement balance.|  

4. Choose the **Mark Lines** action.  
5. In the **Bank Rec. Process Lines** window, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Record type to process**|Specify the type as **Checks**, **Deposits**, or **Both**.|  
    |**Mark lines as cleared**|Select to process the option selected in the **Record type to process** field.|  

6. On the **Bank Rec. Line** FastTab, select the appropriate filters.  
7. Choose the **OK** button.  
8. In the **Bank Rec. Worksheet** window, on the **Bank Rec. Adj. Lines Subform** FastTab, enter information in the remaining fields to make adjustments.  

    > [!NOTE]  
    >  If needed, you can also use the **Bank Rec. Worksheet** window to view the **Bank Reconciliation Comments** card or the **Bank Reconciliation** card.

## To post a bank reconciliation
You can post bank reconciliation if you have reconciled the bank accounts in the **Bank Rec. Worksheet** window. After the bank reconciliation has been posted, a bank account statement is created, and can be viewed from the relevant bank account card.  

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Bank Account Reconciliations**, and then choose the related link.
2. Select the bank account reconciliation that you want to post, and then choose the **Edit** action.  

    > [!NOTE]  
    >  On the **General** FastTab, the **Difference** field be must be zero before you can post the bank reconciliation.  

When the bank reconciliation is posted, all of the related files are posted to the historical **Post Bank Rec. Worksheet** table. Any adjustments are posted to the **G/L Entry** table.  

3. Choose the **Post** action.  
4. To review a preliminary draft of the bank reconciliation statement, choose the **Test Report** action. The **Bank Rec. Test Report** shows the entries that will result if you post.  

## To view the posted bank account reconciliations  

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Bank Accounts**, and then choose the related link.
2. Select the bank account that you want to view the posted reconciliations for, and then choose the **Statements** action.  
3. Choose the **Close** button.  

## To print a bank reconciliation test report  
You can print the following bank reconciliation reports:  

-  **Bank Rec. Test Report** - Displays the list of errors that are found in the bank reconciliation statement. You can generate this report before you post the bank reconciliation statement to make sure that there are no errors in the statement.  

-  **Bank Account – Reconcile** - Displays the reconciliation details for each bank account. This report lists deposits, withdrawals, and adjustments for a bank account.  

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Bank Account Reconciliations**, and then choose the related link.  
2. Choose the **Bank Rec. Test Report** action.  
3.  On the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Print details**|Select to print reconciliation details in the report. If you select this check box, all of the other print check boxes are automatically selected. You can clear a check box if you do not want to include its details in the report.|  
    |**Print checks**|Select to print check details in the report.|  
    |**Print deposits**|Select to print deposit details in the report.|  
    |**Print adjustments**|Select to print adjustment details in the report.|  
    |**Print outstanding checks**|Select to print outstanding check details in the report.|  
    |**Print outstanding deposits**|Select to print outstanding deposit details in the report.|  

4. On the **Bank Rec. Header** FastTab, select the appropriate filters.  
5. Choose the **Print** button to print the report. Choose the **Preview** button to view it on the screen.  

## To print a bank reconciliation report  
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Bank Account Reconciliations**, and then choose the related link.  
2. Choose the **Bank Account – Reconcile** action.  
3. To print each bank account on a new page, select the **New Page per Bank Account** check box.  
4. On the **Bank Account** FastTab, select the appropriate filters.  
5. Choose the **Print** button to print the report. Choose the **Preview** button to view it on the screen.  

## See Also  
 [How to: Reconcile Bank Accounts by Using Bank Statements](../Topic/How%20to:%20Reconcile%20Bank%20Accounts%20by%20Using%20Bank%20Statements.md)   
 [How to: Post a Bank Reconciliation](../Topic/How%20to:%20Post%20a%20Bank%20Reconciliation.md)   
 [\($ N\_10124 Bank Rec. List $\)](../Topic/\($%20N_10124%20Bank%20Rec.%20List%20$\).md)   
 [\($ N\_370 Bank Account Card $\)](assetId:///c44f01ce-a89a-441e-a543-1a1e951edcaa)   
 [\($ T\_270 Bank Account $\)](assetId:///859a3a4a-835d-4443-9715-a8d79d986654)   
 [\($ R\_10407 Bank Rec. Test Report $\)](../Topic/\($%20R_10407%20Bank%20Rec.%20Test%20Report%20$\).md)   
 [\($ R\_10409 Bank Account \- Reconcile $\)](../Topic/\($%20R_10409%20Bank%20Account%20-%20Reconcile%20$\).md)


## See Also  
 [How to: Print Bank Reconciliation Reports](../Topic/How%20to:%20Print%20Bank%20Reconciliation%20Reports.md)   
 [How to: Reconcile Bank Accounts by Using Bank Statements](../Topic/How%20to:%20Reconcile%20Bank%20Accounts%20by%20Using%20Bank%20Statements.md)   
 [\($ N\_370 Bank Account Card $\)](assetId:///c44f01ce-a89a-441e-a543-1a1e951edcaa)   
 [\($ T\_270 Bank Account $\)](assetId:///859a3a4a-835d-4443-9715-a8d79d986654)   
 [\($ T\_17 G\/L Entry $\)](assetId:///2b5b8281-fbfa-4b7f-a154-a9ec61afadfe)   
 [\($ N\_10120 Bank Rec.Worksheet $\)](../Topic/\($%20N_10120%20Bank%20Rec.Worksheet%20$\).md)   
 [\($ R\_10407 Bank Rec. Test Report $\)](../Topic/\($%20R_10407%20Bank%20Rec.%20Test%20Report%20$\).md)   
 [\($ T\_10123 Posted Bank Rec. Header $\)](../Topic/\($%20T_10123%20Posted%20Bank%20Rec.%20Header%20$\).md)


## See Also  
[Reconcile Bank Accounts Separately](../../bank-how-reconcile-bank-accounts-separately.md)

## See Also  
[United States Local Functionality](united-states-local-functionality.md)  
[Finance](../../finance.md)  
[Setting Up Finance](../../finance.md)  
