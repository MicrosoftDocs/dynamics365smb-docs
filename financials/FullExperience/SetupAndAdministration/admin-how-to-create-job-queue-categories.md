---
    title: How to Create Job Queue Categories | Microsoft Docs
    description: You can use categories of job queues to help group and filter jobs.
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
# How to: Create Job Queue Categories
You can use categories of job queues to help group and filter jobs.  
  
### To create a job queue category  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Job Queue Category List**, and then choose the related link.  
  
2.  On the **Home** tab, choose **New**.  
  
3.  In the **Code** field, enter a code of up to 10 numbers and letters.  
  
4.  In the **Decription** field, enter a description of up to 30 numbers and letters.  
  
### To use a job queue category  
  
1.  Create a job queue entry.  
  
2.  Choose the **Job Queue Category Code** field, and then select a code from the list.  
  
3.  Create a job queue.  
  
4.  Choose the **Job Queue Category Filter** field, and then select a code from the list.  
  
5.  On the **Home** tab, choose **Start Job Queue**.  
  
     The job queue runs, and limits itself to job queue entries of the specified category.  
  
## See Also  
 [How to: Create Job Queue Entries](../how-to-create-job-queue-entries.md)   
 [How to: Set Up Job Queues](../how-to-set-up-job-queues.md)