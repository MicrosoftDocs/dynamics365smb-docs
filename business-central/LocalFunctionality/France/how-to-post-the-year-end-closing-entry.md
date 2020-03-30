---
    title: How to Post the Year-End Closing Entry
    description: After you use the Close Income Statement batch job to generate the year-end closing entry or entries, you must open the journal you specified in the batch job, and then review and post the entries.

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
# Post the Year-End Closing Entry
After you use the **Close Income Statement** batch job to generate the year-end closing entry or entries, you must open the journal you specified in the batch job, and then review and post the entries.  

## To post the year-end closing entry  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **General Journal**, and then choose the related link.  
2.  Review the entries.  
3.  Choose the **Post** action.  
4.  In the posting confirmation page, choose the **Yes** button.  

If an error is detected, an error message is displayed. If the posting is successful, the system removes the posted entries from the journal.  

Once posted, an entry is posted to each income statement account so that its balance becomes zero and the year's result is transferred to the balance sheet.  

## See Also  
 [Year End Processes Overview](year-end-processes-overview.md)   
 [Close Years](how-to-close-years.md)   
 [Fiscally Close Years](how-to-fiscally-close-years.md)
