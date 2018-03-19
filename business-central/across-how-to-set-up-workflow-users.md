---
title: How to Set Up Workflow Users | Microsoft Docs
description: Before you can create workflows, you must set up the users who take part in workflows. This is necessary, for example, to specify who will receive a notification to act on a workflow step.
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: reject, delegate, request
ms.date: 08/01/2017
ms.author: sgroespe

---
# Set Up Workflow Users
Before you can create workflows, you must set up the users who take part in workflows. This is necessary, for example, to specify who will receive a notification to act on a workflow step.  

In the **Workflow User Group** window, you set up users under workflow user groups, and you specify the users’ number in a process sequence, such as an approver chain.  

Workflow users that function as approval users, both approval requesters and approvers, must also be set up in the **Approval User Setup** window. For more information, see [Set Up Approval Users](across-how-to-set-up-approval-users.md).  

> [!NOTE]  
>  To define that an approval request is not approved until multiple approvers in an approval chain have approved it, set up approvers in a hierarchy. For approver type **Approver**, set approvers up in the **Approval User Setup** window. For approver type, **Workflow User Group**, set approvers up in the **Workflow User Groups** window and define the hierarchy by assigning incremental numbers to each approver in the **Sequence No.** field. For more information, see [Set Up Approval Users](across-how-to-set-up-approval-users.md) and this topic.  
>   
>  To define that an approval request is not approved until multiple equal approvers have approved it, regardless of a hierarchy, set up a flat workflow user group. For approver type, **Workflow User Group**, set up approvers in the **Workflow User Groups** window and assign the same number to each approver in the **Sequence No.** field. For more information, see this topic.  

### To set up a workflow user  

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Workflow User Groups**, and then choose the related link.  
2. Choose the **New** action. The **Workflow User Group** window opens.  
3. In the **Code** field, enter a maximum of 20 characters to identify the workflow.  
4. In the **Description** field, describe the workflow.  
5. On the **Workflow User Group Members** FastTab, fill the fields on the first line as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**User Name**|Specify the user who will take part in workflows.<br /><br /> The user must exist in the **User Setup** window. For more information, see [Manage Users and Permissions](ui-how-users-permissions.md).|  
    |**Sequence No.**|Specify the order in which the workflow user engages in a workflow relative to other users. This field can be used, for example, to specify when the user approves relative to other approvers when you use the **Workflow User Group** option in the **Approver Type** field on the related workflow response. **TIP:**  To define that an approval request is not approved until multiple equal approvers have approved it, irrespective of a hierarchy, set up a flat workflow user group by assigning the same sequence number to the relevant approvers.|  
6. Repeat step 5 to add more workflow users to the user group.  
7. Repeat steps 2 through 6 to add more workflow user groups.  

## See Also  
[Set Up Approval Users](across-how-to-set-up-approval-users.md)   
[Setting Up Workflows](across-set-up-workflows.md)   
[Using Workflows](across-use-workflows.md)   
[Walkthrough: Setting Up and Using a Purchase Approval Workflow](walkthrough-setting-up-and-using-a-purchase-approval-workflow.md)   
[Workflow](across-workflow.md)   
