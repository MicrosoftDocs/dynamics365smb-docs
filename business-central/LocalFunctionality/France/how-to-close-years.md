---
    title: How to Close Years
    description: When a fiscal year is over, you must close the periods that it comprises.

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
# Close Years
When a fiscal year is over, you must close the periods that it comprises.  

## To close a year  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Accounting Periods**, and then choose the relevant link.  
2.  Choose the **Close Year** action.  

    If more than one fiscal year is open, the earliest one should be closed. A message appears to identify the year that should be closed and explains the consequences of closing it.  

3.  To close the year, choose the **Yes** button.  

When the fiscal year is closed, the **Closed** and **Date Locked** fields are selected for all the periods in the year. At this point the fiscal year cannot be opened again, and you cannot clear the **Closed** or **Date Locked** fields.  

> [!WARNING]  
> You cannot close a fiscal year before you create a new one. When a fiscal year has been closed, you cannot change the starting date of the following fiscal year.  

Even though a fiscal year has been closed, you can still post general ledger entries to it until you fiscally close the fiscal year. When you do this, the entries will be marked as posted to a closed fiscal year, and the Prior-Year Entry field will be selected. For more information, see [Fiscally Close Years](how-to-fiscally-close-years.md).  

After a fiscal year is closed, you must close the income statement accounts and transfer the year's results to an account in the balance sheet. You can repeat this each time you post to the closed fiscal year.  

After a fiscal year is fiscally closed, it cannot be opened again, and general ledger entries cannot be posted.  

## See Also  
 [Fiscally Close Years](how-to-fiscally-close-years.md)   
 [Year End Processes Overview](year-end-processes-overview.md)   
 [Post the Year-End Closing Entry](how-to-post-the-year-end-closing-entry.md)   
 [Closing Years and Periods](../../year-close-years-periods.md)
