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
# How to: Set Up Job Queues
You can set up a job queue and specify the order in which designated reports, batch jobs, and codeunits are set up to run. The ADD INCLUDE<!--[!INCLUDE[nav_server](../BusinessFunctionality/IntegratingWithMicrosoftOffice/includes/nav_server_md.md)]--> reads from the job queue and determines which job to run next. When you set up a job queue, you can specify on which computer and on which service the job queue is to run.  
  
 You can also create a NAV server instance that is dedicated to your job queue. This is useful when a job will need specific permissions, when a job has a heavy usage of resources, or when you want to separate of job queues. To do so, you specify startup parameters for NAS services.  
  
### To create a job queue  
  
1.  In the **Search** box, enter **Job Queues**, and then choose the related link.  
  
2.  On the **Home** tab, choose **New**. The **Job Queue Card** window opens.  
  
3.  On the **General** FastTab, in the **Code** field, enter a code for the job queue. In the **Description** field, enter a description of the job queue. You can enter up to 30 characters.  
  
4.  Optionally, in the **Job Queue Category Filter** field, choose a filter that applies. For more information, see [How to: Create Job Queue Categories](../SetupAndAdministration/how-to-create-job-queue-categories.md).  
  
     The remaining fields on the **General** FastTab are informational, and will be filled in after you start the job queue.  
  
### To activate a job queue  
  
1.  In the **Search** box, enter **Job Queues**, and then choose the related link.  
  
2.  Select the job queue that you want to start, and on the **Home** tab, choose **Start Job Queue**.  
  
     To stop the job queue, on the **Home** tab, choose **Stop Job Queue**.  
  
 On the **NAS Settings** FastTab, you can set fields if you want to specify on which computer and which server instance the NAS that you want to run the job queue will be running. This can be important when you are fine tuning performance or when a server instance or computer is set up to handle specific ADD INCLUDE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)]--> functionality. If you do not specify a server or computer, the job queue will run with the services that the client is running on.  
  
### To specify NAS settings  
  
1.  To start a job queue on any server instance on a computer, choose the **Start on this NAS Computer** field. The **Server Instance List** window opens. Select the computer on the server instance on which you want to run the job queue. Choose the **OK** button.  
  
     -or-  
  
     To start a job queue on a specific server instance, choose the **Start on this NAS Instance** field. Select the server instance on which you want to run the job queue. Choose the **OK** button.  
  
2.  Start the job queue. You can specify that the job queue start automatically when the NAS service is started, or you can start a job queue manually.  
  
     Automatically: On the **NAS Settings** FastTab, select the **Start Automatically from NAS** check box.  
  
     -or-  
  
     Manually: On the **Process** tab, choose **Start Job Queue**. To stop the job queue, choose **Stop Job Queue**.  
  
 The next step is to create entries for your job queue. A job queue can have many entries, which are the jobs that the queue manages and runs. Information in the entry specifies how often the job should run, and when it should run. For more information, see [How to: Create Job Queue Entries](../SetupAndAdministration/how-to-create-job-queue-entries.md).  
  
## See Also  
 Job Queues   
 [About Job Queues](../SetupAndAdministration/about-job-queues.md)   
 Job Queue Entries   
 [Configuring NAS Services](../Topic/Configuring%20NAS%20Services.md)