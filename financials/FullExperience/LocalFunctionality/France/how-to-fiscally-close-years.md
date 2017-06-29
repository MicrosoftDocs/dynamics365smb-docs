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
# How to: Fiscally Close Years
When a fiscal year is complete, you must fiscally close the periods that it comprises to make sure that no more general ledger entries can be posted.  
  
 Before fiscal closing is allowed the following must be done:  
  
-   The fiscal year has been closed first. For more information, see [How to: Close Years](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/how-to-close-years.md).  
  
-   All journal lines that are not posted and all simulation entries for the year are either posted or deleted before the year is fiscally closed.  
  
-   All closing entries are up-to-date.  
  
### To fiscally close years  
  
1.  In the **Search** box, enter **Accounting Periods**, and then choose the relevant link.  
  
2.  On the **Navigate** tab, in the **Fiscal Closing** group, choose **Fiscally Close Year**.  
  
     If more than one fiscal year is not fiscally closed, the earliest one should be fiscally closed. A message appears that identifies the year that should be closed and explains the consequences of closing it.  
  
3.  To fiscally close the year, choose the **Yes** button.  
  
 When the fiscal year is fiscally closed, the **Fiscally Closed** field for all the periods in the year is selected. The fiscally closed year cannot be opened again, and you cannot clear the **Fiscally Closed** field.  
  
## See Also  
 [How to: Close Years](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/how-to-close-years.md)   
 [Year End Processes Overview](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/year-end-processes-overview.md)   
 [How to: Post the Year-End Closing Entry](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/how-to-post-the-year-end-closing-entry.md)   
 [How to: Open a New Fiscal Year-duplicate](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/how-to-open-a-new-fiscal-year-duplicate.md)