---
title: "Set Up Workflows"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: cb718001-5310-43d0-a791-5dee86df0e1a
caps.latest.revision: 27
ms.author: "sgroespe"

---
# Set Up Workflows
You can set up and use workflows that connect business\-process tasks performed by different users. System tasks, such as automatic posting, can be included as steps in workflows, preceded or followed by user tasks. Requesting and granting approval to create new records are typical workflow steps. For more information, see [Use Workflows](../../BusinessFunctionality/Workflow/use-workflows.md).  
  
 Before you begin to use workflows, you must set up workflow users and approval users, specify how users receive notifications about workflow steps, and then create the workflows, potentially preceded by code customization.  
  
 In the **Workflow** window, you create a workflow by listing the involved steps on the lines. Each step consists of a workflow event, moderated by event conditions, and a workflow response, moderated by response options. You define workflow steps by filling fields on workflow lines from fixed lists of event and response values representing scenarios that are supported by the application code.  
  
 If a business scenario requires a workflow event or response that is not supported, a Microsoft partner must implement them by customizing the application code. For more information, see [Walkthrough: Implementing New Workflow Events and Responses](../../BusinessFunctionality/Workflow/walkthrough-implementing-new-workflow-events-and-responses.md).  
  
 The following table describes a sequence of tasks, with links to the topics that describe them.  
  
|**To**|**See**|  
|------------|-------------|  
|Set up workflow users and user groups.|[How to: Set Up Workflow Users](../../BusinessFunctionality/Workflow/how-to-set-up-workflow-users.md)|  
|Set up workflow users who take part in approval workflows.|[How to: Set Up Approval Users](../../BusinessFunctionality/Workflow/how-to-set-up-approval-users.md)|  
|Specify how workflow users are notified of workflow steps, including approval requests.|[Setting Up Workflow Notifications](../../BusinessFunctionality/Workflow/setting-up-workflow-notifications.md)|  
|Specify when users receive notifications and whether to aggregate notifications in a period to minimize the number of notifications.|[How to: Specify When and How to Receive Notifications](../../BusinessFunctionality/Workflow/how-to-specify-when-and-how-to-receive-notifications.md)|  
|Set up the layout and general content of new workflow notifications emails, or export, modify, and reimport existing templates.|[How to: Manage Notification Templates](../../BusinessFunctionality/Workflow/how-to-manage-notification-templates.md)|  
|Set up an SMTP server to enable email communication in and out of ADD INCLUDE<!--[!INCLUDE[dyn_nav](../../ApplicationDesign/includes/dyn_nav_md.md)]-->.|[How to: Set Up SMTP Email](../../BusinessFunctionality/Workflow/how-to-set-up-smtp-email.md)|  
|Specify the different steps of a workflow by connection workflow events with workflow responses.|[How to: Create Workflows](../../BusinessFunctionality/Workflow/how-to-create-workflows.md)|  
|Use workflow templates to create new workflows.|[How to: Create Workflows from Workflow Templates](../../BusinessFunctionality/Workflow/how-to-create-workflows-from-workflow-templates.md)|  
|Share workflows with other ADD INCLUDE<!--[!INCLUDE[dyn_nav](../../ApplicationDesign/includes/dyn_nav_md.md)]--> databases by exporting and importing workflows.|[How to: Export and Import Workflows](../../BusinessFunctionality/Workflow/how-to-export-and-import-workflows.md)|  
|Learn how to set up a workflow for approving sales documents by following an end\-to\-end procedure.|[Walkthrough: Setting Up and Using a Purchase Approval Workflow](../../BusinessFunctionality/Workflow/walkthrough-setting-up-and-using-a-purchase-approval-workflow.md)|  
|Add support for a business scenario that requires new workflow events or responses by customizing the application code. \(This topic is in English language.\)|[Walkthrough: Implementing New Workflow Events and Responses](../../BusinessFunctionality/Workflow/walkthrough-implementing-new-workflow-events-and-responses.md) in Developer and IT Pro Help.|  
  
## See Also  
 [Use Workflows](../../BusinessFunctionality/Workflow/use-workflows.md)   
 [Workflow](../../BusinessFunctionality/Workflow/workflow.md)   
 [Business Functionality](../Topic/Business%20Functionality.md)   
 [Walkthrough: Setting Up and Using a Purchase Approval Workflow](../../BusinessFunctionality/Workflow/walkthrough-setting-up-and-using-a-purchase-approval-workflow.md)