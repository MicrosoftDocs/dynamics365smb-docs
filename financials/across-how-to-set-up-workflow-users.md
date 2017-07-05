---
    title: How to: Set Up Workflow Users | Microsoft Docs
    description: Before you can create workflows, you must set up the users who take part in workflows. This is necessary, for example, to specify who will receive a notification to act on a workflow step.
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
# How to: Set Up Workflow Users
Before you can create workflows, you must set up the users who take part in workflows. This is necessary, for example, to specify who will receive a notification to act on a workflow step.  
  
 In the **Workflow User Group** window, you set up users under workflow user groups, and you specify the users’ number in a process sequence, such as an approver chain.  
  
 Workflow users that function as approval users, both approval requesters and approvers, must also be set up in the **Approval User Setup** window. For more information, see [How to: Set Up Approval Users](across-how-to-set-up-approval-users.md).  
  
> [!NOTE]  
>  To define that an approval request is not approved until multiple approvers in an approval chain have approved it, set up approvers in a hierarchy. For approver type **Approver**, set approvers up in the **Approval User Setup** window. For approver type, **Workflow User Group**, set approvers up in the **Workflow User Groups** window and define the hierarchy by assigning incremental numbers to each approver in the **Sequence No.** field. For more information, see [How to: Set Up Approval Users](across-how-to-set-up-approval-users.md) and this topic.  
>   
>  To define that an approval request is not approved until multiple equal approvers have approved it, regardless of a hierarchy, set up a flat workflow user group. For approver type, **Workflow User Group**, set up approvers in the **Workflow User Groups** window and assign the same number to each approver in the **Sequence No.** field. For more information, see this topic.  
  
### To set up a workflow user  
  
1.  In the **Search** box, enter **Workflow User Groups**, and then choose the related link.  
  
2.  On the **Home** tab, in the **New** group, choose **New**. The **Workflow User Group** window opens.  
  
3.  In the **Code** field, enter a maximum of 20 characters to identify the workflow.  
  
4.  In the **Description** field, describe the workflow.  
  
5.  On the **Workflow User Group Members** FastTab, fill the fields on the first line as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**User Name**|Specify the user who will take part in workflows.<br /><br /> The user must exist in the **User Setup** window. For more information, see User Setup.|  
    |**Sequence No.**|Specify the order in which the workflow user engages in a workflow relative to other users. This field can be used, for example, to specify when the user approves relative to other approvers when you use the **Workflow User Group** option in the **Approver Type** field on the related workflow response. For more information, see Approver Type. **Tip:**  To define that an approval request is not approved until multiple equal approvers have approved it, irrespective of a hierarchy, set up a flat workflow user group by assigning the same sequence number to the relevant approvers.|  
  
6.  Repeat step 5 to add more workflow users to the user group.  
  
7.  Repeat steps 2 through 6 to add more workflow user groups.  
  
## See Also  
 Workflow User Group   
 [How to: Set Up Approval Users](across-how-to-set-up-approval-users.md)   
 [Set Up Workflows](across-set-up-workflows.md)   
 [Use Workflows](across-use-workflows.md)   
 [Walkthrough: Setting Up and Using a Purchase Approval Workflow](across-walkthrough-setting-up-and-using-a-purchase-approval-workflow.md)   
 [Workflow](across-workflow.md)   
 [Business Functionality](across-Business%20Functionality.md)