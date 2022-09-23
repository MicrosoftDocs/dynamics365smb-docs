---
title: How to Set Up Workflow Users
description: Before you can create workflows, you must set up the users who take part in them on the Workflow User Group page.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: reject, delegate, request
ms.search.form: 1533
ms.date: 09/09/2022
ms.author: edupont

---
# Set Up Workflow Users

Before you can create approval workflows, you must set up the users who take part in workflows. This is necessary, for example, to specify who will receive a notification to act on a workflow step.  

On the **Workflow User Groups** page, you can set up users in workflow user groups, and specify the users' number in a process sequence, such as an approver chain. 

Workflow users functioning as approval users, including both approval requesters and approvers, must also be set up on the **Approval User Setup** page. Learn more at [Set Up Approval Users](across-how-to-set-up-approval-users.md).  

> [!NOTE]  
> To define an approval request as not approved until multiple users have approved it, set approvers up in a hierarchy. For approver type **Approver**, set approvers up on the **Approval User Setup** page. For approver type **Workflow User Group**, set approvers up on the **Workflow User Groups** page and define the hierarchy by assigning incremental numbers to each approver in the **Sequence No.** field. Learn more below and at [Set Up Approval Users](across-how-to-set-up-approval-users.md). 

## To set up a workflow user

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Workflow User Groups**, then choose the related link.  
2. Choose the **New** action. The **Workflow User Group** page opens.  
3. In the **Code** field, enter a maximum of 20 characters to identify the workflow.  
4. In the **Description** field, describe the workflow.  
5. On the **Workflow User Group Members** FastTab, fill in the fields on the first line as described in the following table.  

   |Field|Description|
   |-----|-----------|
   |**User Name**|Specify the user to take part in workflows.<br /><br /> The user must exist on the **User Setup** page. Learn more at [Assign Permissions to Users and Groups](ui-define-granular-permissions.md).|
   |**Sequence No.**|Specify the order in which the workflow user engages in a workflow relative to other users. This field can specify, for example, when the user approves relative to other approvers by setting up the **Workflow User Group** option in the **Approver Type** field on the related workflow response.| 

   > [!TIP]
   > To define that an approval request requires that multiple equal users approve it, irrespective of a hierarchy, set up a flat workflow user group by assigning the same sequence number to all the relevant approvers.

6. Repeat step 5 to add more workflow users to the workflow user group.  
7. Repeat steps 2 through 6 to add more workflow user groups.  

## See related [Microsoft training](/training/modules/create-workflows/)

## See also

[Set Up Approval Users](across-how-to-set-up-approval-users.md)  
[Setting Up Approval Workflows](across-set-up-workflows.md)  
[Use Approval Workflows](across-use-workflows.md)  
[Walkthrough: Setting Up and Using a Purchase Approval Workflow](walkthrough-setting-up-and-using-a-purchase-approval-workflow.md)  
[Workflow](across-workflow.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
