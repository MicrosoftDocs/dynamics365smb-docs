---
title: "How to: Check Job Queues Entries"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "job queues, checking logs"
  - "logs, job queue entries"
ms.assetid: ddd474ea-a7b7-4e14-84f8-8525c43d225c
caps.latest.revision: 6
ms.author: "edupont"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-nz"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# How to: Check Job Queues Entries
The **\($ N\_672 Job Queue Entries $\)** window lists all current job queue entries. The list displays the **\($ T\_472\_13 Status $\)** of the job, the **\($ T\_472\_2 User ID $\)** of the user who initiated the job, and the **\($ T\_472\_8 Object ID.to Run $\)**. If the status is set to **Ready**, then the scheduled job can run.  
  
### To check the state of a job queue entry  
  
1.  In the **Search** box, enter **Job Queue Entries**, and then choose the related link. The **\($ N\_672 Job Queue Entries $\)** window opens.  
  
2.  In the list, select the job queue entry that you want to check.  
  
3.  On the **Home** tab, in the **Process** group, choose **Log Entries**. The **\($ N\_674 Job Queue Log Entries $\)** window opens and displays the status of jobs that have run:  
  
    -   **Success**  
  
    -   **In Process**  
  
    -   **Error**  
  
     The **\($ N\_674 Job Queue Log Entries $\)** window also displays any error messages. Each line represents a job queue entry or the occurrence of a recurring entry. If a job ended with an error, the error message is displayed.  
  
## See Also  
 [How to: Create Job Queue Entries](../SetupAndAdministration/how-to-create-job-queue-entries.md)