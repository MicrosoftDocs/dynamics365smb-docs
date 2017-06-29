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
# How to: Check Job Queues Entries
The **Job Queue Entries** window lists all current job queue entries. The list displays the **Status** of the job, the **User ID** of the user who initiated the job, and the **Object ID.to Run**. If the status is set to **Ready**, then the scheduled job can run.  
  
### To check the state of a job queue entry  
  
1.  In the **Search** box, enter **Job Queue Entries**, and then choose the related link. The **Job Queue Entries** window opens.  
  
2.  In the list, select the job queue entry that you want to check.  
  
3.  On the **Home** tab, in the **Process** group, choose **Log Entries**. The **Job Queue Log Entries** window opens and displays the status of jobs that have run:  
  
    -   **Success**  
  
    -   **In Process**  
  
    -   **Error**  
  
     The **Job Queue Log Entries** window also displays any error messages. Each line represents a job queue entry or the occurrence of a recurring entry. If a job ended with an error, the error message is displayed.  
  
## See Also  
 [How to: Create Job Queue Entries](../FullExperience/how-to-create-job-queue-entries.md)