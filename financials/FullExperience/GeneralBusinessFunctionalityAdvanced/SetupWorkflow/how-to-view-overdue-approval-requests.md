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
# How to: View Overdue Approval Requests
All approval requests have a due date by which they must be approved. If an approver has not acted on a request by the due date, then the related approval request becomes overdue.  
  
 The due date is either the date when the request was made or it a date calculated from the value in the **Due Date Formula** field on the workflow response that represents the approvers action. For more information, see step 9.b. in [How to: Create Workflows](../../BusinessFunctionality/Workflow/how-to-create-workflows.md).  
  
 At regular intervals, you must remind approval workflow users of overdue approval requests that they must react on. For more information, see [How to: Send Overdue Approval Notifications](../../BusinessFunctionality/Workflow/how-to-send-overdue-approval-notifications.md).  
  
 Approval of records must be set up as workflows, one workflow for each scenario, such as the Purchase Invoice Approval Workflow. The generic version of ADD INCLUDE<!--[!INCLUDE[dyn_nav](../../ApplicationDesign/includes/dyn_nav_md.md)]--> includes workflow templates for approval of all types of sales and purchase documents and for other records, such as customer cards. For more information, see the list of workflow templates in the Workflow Templates window.  
  
### To view overdue approval requests  
  
1.  In the **Search** box, enter **Overdue Approval Requests**, and then choose the related link.  
  
     The **Overdue Notification Entries** window opens.  
  
## See Also  
 Overdue Notification Entries   
 Due Date Formula   
 [Setting Up Workflow Notifications](../../BusinessFunctionality/Workflow/setting-up-workflow-notifications.md)   
 [How to: Manage Notification Templates](../../BusinessFunctionality/Workflow/how-to-manage-notification-templates.md)   
 [How to: Create Workflows](../../BusinessFunctionality/Workflow/how-to-create-workflows.md)   
 [How to: Set Up Job Queues](../../SetupAndAdministration/how-to-set-up-job-queues.md)   
 [Walkthrough: Setting Up and Using a Purchase Approval Workflow](../../BusinessFunctionality/Workflow/walkthrough-setting-up-and-using-a-purchase-approval-workflow.md)   
 [Workflow](../../BusinessFunctionality/Workflow/workflow.md)   
 [Business Functionality](../Topic/Business%20Functionality.md)