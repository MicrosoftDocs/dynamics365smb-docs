---
    title: How to Close Income Statement Accounts
    description: Before you can run the Close Income Statement batch job, you must close the fiscal year.

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
# Close Income Statement Accounts
Before you can run the **Close Income Statement** batch job, you must close the fiscal year. For more information, see [Fiscally Close Years](how-to-fiscally-close-years.md).  

## To close the income statement accounts  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Close Income Statement**, and then choose the relevant link.  
2.  On the **Close Income Statement** page, on the **Options** FastTab, specify the conditions of the batch job.  
3.  Choose the **OK** button.  

    When the batch job is finished, you must close the accounts.  

4.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **General Journals**, and then choose the relevant link.  
5.  Select the general journal that contains the closing entries.  
6.  Enter one line with a balancing entry that posts the net income to the correct general ledger account under owners’ equity on the balance sheet.  
7.  Choose the **Post** action to post the journal.  

## See Also  
 [Fiscally Close Years](how-to-fiscally-close-years.md)
