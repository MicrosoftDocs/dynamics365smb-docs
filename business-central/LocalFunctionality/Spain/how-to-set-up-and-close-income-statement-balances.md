---
    title: How to Set Up and Close Income Statement Balances
    description: You can use income statement balancing accounts to balance and track several accounts at the same time.

    services: project-madeira 
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Set Up and Close Income Statement Balances
You can use income statement balancing accounts to balance and track several accounts at the same time. The **Close Income Statement** batch job transfers income statement accounts to an account in the balance sheet, and closes the income statement accounts. When the **Close Income Statement** batch job is run, the entries are automatically posted.  

> [!NOTE]  
>  The fiscal year must be closed before the batch job can run.  

## To set up the income statement balance account  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Chart of Accounts**, and then choose the related link.  
2.  Select an existing general ledger account, and then choose the **Edit** action to open the **G/L Account Card** page.  
3.  Expand the **General** FastTab.  
4.  In the **Income Stmt. Bal. Acc.** field, select the adjustment account for the auxiliary commercial account.  

    > [!NOTE]  
    >  During adjustment, balances will be expensed or credited to this account.  

5.  Enter information into the required fields, and then choose the **OK** button.  

## To close income statement balances  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Close Income Statement**, and then choose the related link.  
2.  In the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Fiscal Year Ending Date**|Select the date of the closed fiscal year.|  
    |**Gen. Journal Template**|Select the required general journal template.|  
    |**Gen. Journal Batch**|Select the required general journal batch.|  
    |**Document No.**|Enter the document number.|  
    |**Retained Earnings Acc.**|Select the account for the retained earnings entries.|  
    |**Posting Description**|Enter the required description.|  

3.  In the **Close by** section, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Business Unit Code**|Select to create an entry for each business code.|  
    |**Dimensions**|Select to create an entry for each general ledger dimension.|  
    |**Inventory Period Closed**|Select to indicate that the inventory period with ending dates equal to or greater than the last date of the accounting period is closed.|  

4.  Choose the **OK** button.  

## See Also  
 [Spain Local Functionality](spain-local-functionality.md)
