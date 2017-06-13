---
title: "How to: Set Up Workflow Users"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: d01328a1-5c12-45d0-851d-be541e1304f9
caps.latest.revision: 7
ms.author: "sgroespe"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
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
# How to: Set Up Workflow Users
Before you can create workflows, you must set up the users who take part in workflows. This is necessary, for example, to specify who will receive a notification to act on a workflow step.  
  
 In the **Workflow User Group** window, you set up users under workflow user groups, and you specify the users’ number in a process sequence, such as an approver chain.  
  
 Workflow users that function as approval users, both approval requesters and approvers, must also be set up in the **Approval User Setup** window. For more information, see [How to: Set Up Approval Users](../../BusinessFunctionality/Workflow/how-to-set-up-approval-users.md).  
  
> [!NOTE]  
>  To define that an approval request is not approved until multiple approvers in an approval chain have approved it, set up approvers in a hierarchy. For approver type **Approver**, set approvers up in the **Approval User Setup** window. For approver type, **Workflow User Group**, set approvers up in the **Workflow User Groups** window and define the hierarchy by assigning incremental numbers to each approver in the **Sequence No.** field. For more information, see [How to: Set Up Approval Users](../../BusinessFunctionality/Workflow/how-to-set-up-approval-users.md) and this topic.  
>   
>  To define that an approval request is not approved until multiple equal approvers have approved it, regardless of a hierarchy, set up a flat workflow user group. For approver type, **Workflow User Group**, set up approvers in the **Workflow User Groups** window and assign the same number to each approver in the **Sequence No.** field. For more information, see this topic.  
  
### To set up a workflow user  
  
1.  In the **Search** box, enter **Workflow User Groups**, and then choose the related link.  
  
2.  On the **Home** tab, in the **New** group, choose **New**. The **Workflow User Group** window opens.  
  
3.  In the **Code** field, enter a maximum of 20 characters to identify the workflow.  
  
4.  In the **Description** field, describe the workflow.  
  
5.  On the **Workflow User Group Members** FastTab, fill the fields on the first line as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**User Name**|Specify the user who will take part in workflows.<br /><br /> The user must exist in the **User Setup** window. For more information, see [User Setup](../Topic/\($%20T_91%20User%20Setup%20$\).md).|  
    |**Sequence No.**|Specify the order in which the workflow user engages in a workflow relative to other users. This field can be used, for example, to specify when the user approves relative to other approvers when you use the **Workflow User Group** option in the **Approver Type** field on the related workflow response. For more information, see [Approver Type](../Topic/\($%20T_1523_12%20Approver%20Type%20$\).md). **Tip:**  To define that an approval request is not approved until multiple equal approvers have approved it, irrespective of a hierarchy, set up a flat workflow user group by assigning the same sequence number to the relevant approvers.|  
  
6.  Repeat step 5 to add more workflow users to the user group.  
  
7.  Repeat steps 2 through 6 to add more workflow user groups.  
  
## See Also  
 [Workflow User Group](../Topic/\($%20N_1531%20Workflow%20User%20Group%20$\).md)   
 [How to: Set Up Approval Users](../../BusinessFunctionality/Workflow/how-to-set-up-approval-users.md)   
 [Set Up Workflows](../../BusinessFunctionality/Workflow/set-up-workflows.md)   
 [Use Workflows](../../BusinessFunctionality/Workflow/use-workflows.md)   
 [Walkthrough: Setting Up and Using a Purchase Approval Workflow](../../BusinessFunctionality/Workflow/walkthrough-setting-up-and-using-a-purchase-approval-workflow.md)   
 [Workflow](../../BusinessFunctionality/Workflow/workflow.md)   
 [Business Functionality](../Topic/Business%20Functionality.md)