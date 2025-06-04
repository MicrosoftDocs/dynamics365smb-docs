---
title: How to Set Up and Close Income Statement Balances
description: You can use income statement balancing accounts to balance and track several accounts at the same time.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords:
ms.date: 04/01/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Set Up and Close Income Statement Balances
You can use income statement balancing accounts to balance and track several accounts at the same time. The **Close Income Statement** batch job transfers income statement accounts to an account in the balance sheet, and closes the income statement accounts. When the **Close Income Statement** batch job is run, the entries are automatically posted.  

> [!NOTE]  
>  The fiscal year must be closed before the batch job can run.  

## To set up the income statement balance account  

1.  Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Chart of Accounts**, and then choose the related link.  
2.  Select an existing general ledger account, and then choose the **Edit** action to open the **G/L Account Card** page.  
3.  Expand the **General** FastTab.  
4.  In the **Income Stmt. Bal. Acc.** field, select the adjustment account for the auxiliary commercial account.  

    > [!NOTE]  
    >  During adjustment, balances will be expensed or credited to this account.  

5.  Enter information into the required fields, and then choose the **OK** button.  

## To close income statement balances  

1.  Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Close Income Statement**, and then choose the related link.  
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

## Related information  
 [Spain Local Functionality](spain-local-functionality.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
