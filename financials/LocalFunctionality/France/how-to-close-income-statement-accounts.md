---
    title: How to: Close Income Statement Accounts | Microsoft Docs
    description: Before you can run the **Close Income Statement** batch job, you must close the fiscal year. For more information, see [How to: Fiscally Close Years](how-to-fiscally-close-years.md).
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
# How to: Close Income Statement Accounts
Before you can run the **Close Income Statement** batch job, you must close the fiscal year. For more information, see [How to: Fiscally Close Years](how-to-fiscally-close-years.md).  
  
### To close the income statement accounts  
  
1.  In the **Search** box, enter **Close Income Statement**, and then choose the relevant link.  
  
2.  In the **Close Income Statement** window, on the **Options** FastTab, specify the conditions of the batch job.  
  
3.  Choose the **OK** button.  
  
     When the batch job is finished, you must close the accounts.  
  
4.  In the **Search** box, enter **General Journals**, and then choose the relevant link.  
  
5.  Select the general journal that contains the closing entries.  
  
6.  Enter one line with a balancing entry that posts the net income to the correct general ledger account under owners’ equity on the balance sheet.  
  
7.  On the **Home** tab, in the **Process** group, choose **Post** to post the journal.  
  
## See Also  
 [How to: Fiscally Close Years](how-to-fiscally-close-years.md)   
 Close Income Statement