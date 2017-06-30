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
# How to: Use My Job Queue Part
The **My Job Queue** part shows the job queues entries that a user has started, but which are not yet finished. By default, the part is not visible, so you have to add it to your role center. For more information, see [How to: Change Role Centers](../how-to-change-role-centers.md).  
  
 In this part, you can see those documents that are being processed or that are queued for which your ID is specified in the **Assigned User ID** field. The part helps you keep track of all job queue entries, including those related to background posting. The part can tell you at a glance whether there has been an error in the posting of a document or if there are errors in a job queue entry. The part also lets you cancel a document posting if it is not running.  
  
 The following procedure assumes that you have added the **My Job Queue** part to your role center.  
  
### To use the My Job Queue part  
  
1.  In the navigation pane, choose **Role Center**.  
  
2.  In the **My Job Queue** part, review the job queue entries. You can review information about the job queue in the **Status** field.  
  
3.  To review the document related to an entry, select the entry, and then choose **Show Record**. The list window opens, On the **Navigate** tab, choose **Card**.  
  
4.  If an entry has the status **Error**, choose **Show Error** to display the error message..  
  
     After you fix the error, choose **Restart**.  
  
5.  If an entry has the status **Ready**, choose **Delete** to cancel the job queue entry.  
  
## See Also  
 [How to: Background Post with Job Queues](../how-to-background-post-with-job-queues.md)