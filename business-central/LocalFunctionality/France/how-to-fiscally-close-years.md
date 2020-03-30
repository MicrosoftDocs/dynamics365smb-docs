---
    title: How to Fiscally Close Years
    description: When a fiscal year is complete, you must fiscally close the periods that it comprises to make sure that no more general ledger entries can be posted.

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
# Fiscally Close Years
When a fiscal year is complete, you must fiscally close the periods that it comprises to make sure that no more general ledger entries can be posted.  

Before fiscal closing is allowed the following must be done:  

- The fiscal year has been closed first. For more information, see [Close Years](how-to-close-years.md).  
- All journal lines that are not posted for the year are either posted or deleted before the year is fiscally closed.
- All closing entries are up-to-date.  

## To fiscally close years  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Accounting Periods**, and then choose the relevant link.  
2.  Choose the **Fiscally Close Year** check box.  

    If more than one fiscal year is not fiscally closed, the earliest one should be fiscally closed. A message appears that identifies the year that should be closed and explains the consequences of closing it.  

3.  To fiscally close the year, choose the **Yes** button.  

When the fiscal year is fiscally closed, the **Fiscally Closed** field for all the periods in the year is selected. The fiscally closed year cannot be opened again, and you cannot clear the **Fiscally Closed** field.  

## See Also  
 [Close Years](how-to-close-years.md)   
 [Year End Processes Overview](year-end-processes-overview.md)   
 [Post the Year-End Closing Entry](how-to-post-the-year-end-closing-entry.md)   
 [Closing Years and Periods](../../year-close-years-periods.md)
