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
# How to: Create Job Queue Entries
A job queue can have many entries, which are the jobs that the queue manages and runs. Information in the entry specifies what codeunit or report is run, when and how often the entry is run, in what category the job runs, and how it runs.  
  
### To create job queue entries  
  
1.  In the **Search** box, enter **Job Queue Entries**, and then choose the related link.  
  
2.  On the **Home** tab, choose **New**. The **Job Queue Entry Card** window opens.  
  
3.  On the **General** FastTab, specify which report \(batch job\) or codeunit that you want to run.  
  
4.  Fill in other fields on the **General** FastTab to specify a start time for the job queue entry and the expiration time for the job queue entry.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Object Type to Run**|Specifies the type of the object to run: codeunit or report.|  
    |**Object ID to Run**|Specifies the ID of the codeunit or report.<br /><br /> If you specify Report as the object type to run, all object IDs of that type will be available in the list. However, you can only select reports whose **ProcessingOnly** property is set to Yes. **Note:**  The user who sets up the job queue entry must have a permission set that includes explicit permissions run the specified object.|  
    |**Parameter String**|Specifies a text string that you use to define to reduce the scope of the job. For example, you can specify a document type such as sales order. The codeunit has to read the parameters from this field.|  
    |**Maximum No. of Attempts to Run**|Specifies how many times, after a run has failed, that ADD INCLUDE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)]--> is to attempt to run the job.|  
    |**Expiration Date\/Time**|Specifies the last date and time on which the job runs. The job will not run after this date.|  
    |**Earliest Date\/Time**|Specifies the first date and time on which the job runs.|  
    |**Priority**|Specifies the priority of the job queue entry compared to other entries in the job queue. For example, **1**. The lower the number, the higher the priority. The default priority is set to 1000.|  
  
5.  On the **Recurrence** FastTab, specify whether the job is recurring, and other information, such as what day of the week the job is to run. By default, the job queue entry runs one time, unless you select the **Recurring Job** check box.  
  
     Choose the **OK** button.  
  
6.  ADD INCLUDE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)]--> sets the initial status of a job to **On Hold**. This allows time for you to finish set up before a job is run. To change the status, on the **Home** tab, in the **Process** group, choose **Set Status to Ready**. After job queues are set up and running, ADD INCLUDE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)]--> gives you updated status information. The following is a list of the available **Status** codes:  
  
    -   **On Hold**  
  
    -   **Ready**  
  
    -   **In Process**  
  
    -   **Error**  
  
    -   **Finished**  
  
     After a job is run successfully, it is removed from the list of job queue entries unless it is a recurring job. If it is a recurring job, the earliest start time field is adjusted to be the next time that the job is expected to run.  
  
 After you have set up your job queue entries, you can activate the job queues to run.  
  
> [!NOTE]  
>  If you have set up your job queues to run automatically, you do not have to activate the job queue.  
  
## See Also  
 [How to: Set Up Job Queues](../SetupAndAdministration/how-to-set-up-job-queues.md)