---
title: How to set up workflow users
description: Set up users who participate in workflows before creating workflow processes.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: v-soumramani
ms.topic: how-to
ms.search.keywords: reject, delegate, request, workflow users
ms.search.form: 1533_Primary
ms.date: 10/16/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Set up a sequence of workflow users

Before you can create approval workflows, you must set up the users who can submit requests and their approvers. For example, you can specify who receives a notification to act on a workflow step. You set up approval workflow participants on the **Approval User Setup** page. Learn more at [Set Up Approval Users](across-how-to-set-up-approval-users.md).

On the **Workflow User Groups** page, you can specify where a participant engages in an approval workflow by entering a number in the **Sequence No.** field. For example, you can specify that users engage in a sequential order, such as a chain of approvers. You can also specify a flat list of approvers by entering the same number. In the latter case, only one of the approvers must approve a request.

[!INCLUDE [workflow-requestor-approver](includes/workflow-requestor-approver.md)]

## To set up a workflow user group

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Workflow User Groups**, then choose the related link.  
2. Choose the **New** action. The **Workflow User Group** page opens.  
3. In the **Code** field, enter a maximum of 20 characters to identify the workflow.  
4. In the **Description** field, describe the workflow.  
5. On the **Workflow User Group Members** FastTab, fill in the fields on the first line, as described in the following table.  

   |Field|Description|
   |-----|-----------|
   |**User Name**|Specify the user who takes part in a workflow.<br /><br /> The user must exist on the **User Setup** page. Learn more at [Assign Permissions to Users and Groups](ui-define-granular-permissions.md).|
   |**Sequence No.**|Specify the order in which the workflow user engages in a workflow relative to other users. This field can specify, for example, when the user approves relative to other approvers by setting up the **Workflow User Group** option in the **Approver Type** field on the related workflow response.|

   > [!NOTE]
   > Typically, sequence numbers are sequential for users in a workflow user group. However, multiple users can have the same sequence number. When that's the case, only one of the users must approve a request before the workflow goes to the next step. For example, if user A and user B are both number two in the sequence, the workflow goes to the step 3 when either user A or user B approves the request.
6. Repeat step 5 to add more workflow users to the workflow user group.  

## Related information

[Set Up Approval Users](across-how-to-set-up-approval-users.md)  
[Set Up Approval Workflows](across-set-up-workflows.md)  
[Use Approval Workflows](across-use-workflows.md)  
[Walkthrough: Setting Up and Using a Purchase Approval Workflow](walkthrough-setting-up-and-using-a-purchase-approval-workflow.md)  
[Workflow](across-workflow.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
