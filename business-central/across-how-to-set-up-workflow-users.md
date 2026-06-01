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

[!INCLUDE [workflow-requestor-approver](includes/workflow-requestor-approver.md)]

## Order of approvals

On the **Workflow User Groups** page, you can specify where a user engages in an approval workflow by entering a number in the **Sequence No.** field. Typically, sequence numbers are sequential for users in a workflow user group. That is, user A has sequence number 1, user B has 2, C has 3, and so on. However, multiple users can have the same sequence number. When that's the case:

- If all users in the group have the same sequence number, only one of them needs to approve the request. For example, users A, B, and C, all have the sequence number 1. If A approves the request, B and C don't need to.
- If some users have the same sequence number, their placement in the hierarchy affects what happens.
   - If there are users with a higher sequence number, only one needs to approve the request. For example, user A has the sequence number 1, B and C both have 2, and user D has 3. If B *or* C approve the request, it moves on to D.
   - If the users with the same sequence number are last in the hierarchy, however, all of them must approve the request. For example, if user A has the sequence number 1, B has 2, and C and D both have 3, both C and D must approve the request.

## Set up a workflow user group

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Workflow User Groups**, then choose the related link.  
2. Choose the **New** action. The **Workflow User Group** page opens.  
3. In the **Code** field, enter a maximum of 20 characters to identify the workflow.  
4. In the **Description** field, describe the workflow.  
5. On the **Workflow User Group Members** FastTab, fill in the fields on the first line, as described in the following table.  

   |Field|Description|
   |-----|-----------|
   |**User Name**|Specify the user who takes part in a workflow.<br /><br /> The user must exist on the **User Setup** page. Learn more at [Assign Permissions to Users and Groups](ui-define-granular-permissions.md).|
   |**Sequence No.**|Specify the order in which the workflow user engages in a workflow relative to other users. This field can specify, for example, when the user approves relative to other approvers by setting up the **Workflow User Group** option in the **Approver Type** field on the related workflow response.|

6. Repeat step 5 to add more workflow users to the workflow user group.  

## Related information

[Set Up Approval Users](across-how-to-set-up-approval-users.md)  
[Set Up Approval Workflows](across-set-up-workflows.md)  
[Use Approval Workflows](across-use-workflows.md)  
[Walkthrough: Setting Up and Using a Purchase Approval Workflow](walkthrough-setting-up-and-using-a-purchase-approval-workflow.md)  
[Workflow](across-workflow.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
