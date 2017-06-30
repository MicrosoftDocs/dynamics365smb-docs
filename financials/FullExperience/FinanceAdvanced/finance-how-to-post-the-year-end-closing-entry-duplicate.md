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
# How to: Post the Year-End Closing Entry-duplicate
After you use the **Close Income Statement** batch job to generate the year-end closing entry or entries, you must open the journal you specified in the batch job, and then review and post the entries.  
  
### To post the year end closing entry  
  
1.  In the **Search** box, enter **General Journal**, and then choose the related link.  
  
2.  In the **General Journal** window, in the **Batch Name** field, select the batch that contains the closing entries.  
  
3.  Review the entries.  
  
4.  On the **Home** tab, choose **Post** to post the journal.  
  
> [!NOTE]  
>  If an error is detected, an error message is displayed. If the posting is successful, the posted entries are removed from the journal. After posting is complete, an entry is posted to each income statement account so that its balance becomes zero and the year's result is transferred to the balance sheet.  
  
## See Also  
 Close Income Statement   
 [About Year-End Processes](../about-year-end-processes.md)   
 [How to: Close Accounting Periods](../how-to-close-accounting-periods.md)