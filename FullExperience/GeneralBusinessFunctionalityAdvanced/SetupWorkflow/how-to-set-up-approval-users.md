---
title: "How to: Set Up Approval Users"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "approvers, setting up users"
  - "substitutes, setting up users"
  - "substitutes, setting up approvers"
ms.assetid: a6ada9b1-7fe6-45b3-a6ef-d69fdee224e6
caps.latest.revision: 14
ms.author: "sgroespe"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
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
# How to: Set Up Approval Users
Before you can create workflows that involve approval steps, you must set up the workflow users who are involved in approval processes. In the **\($ N\_663 Approval User Setup $\)** window, you also set amount limits for specific types of requests and define substitute approvers to whom approval requests are delegated when the original approver is absent.  
  
> [!NOTE]  
>  Approval users, both approval requesters and approvers, must first be set up as workflow users in the **\($ N\_1531 Workflow User Group $\)** window. For more information, see [How to: Set Up Workflow Users](../../BusinessFunctionality/Workflow/how-to-set-up-workflow-users.md).  
  
 When you have set up approval users, you can use the setup to create workflow responses for approval workflows. For more information, see step 9 in [How to: Create Workflows](../../BusinessFunctionality/Workflow/how-to-create-workflows.md).  
  
> [!NOTE]  
>  To define that an approval request is not approved until multiple approvers in an approval chain have approved it, set up approvers in a hierarchy. For approver type **Approver**, set approvers up in the **\($ N\_663 Approval User Setup $\)** window. For approver type, **Workflow User Group**, set approvers up in the **\($ N\_1533 Workflow User Groups $\)** window and define the hierarchy by assigning incremental numbers to each approver in the **\($ T\_1541\_3 Sequence No. $\)** field. For more information, see this topic and [How to: Set Up Workflow Users](../../BusinessFunctionality/Workflow/how-to-set-up-workflow-users.md).  
>   
>  To define that an approval request is not approved until multiple equal approvers have approved it, regardless of a hirarchy, set up a flat workflow user group. For approver type, **Workflow User Group**, set up approvers in the **\($ N\_1533 Workflow User Groups $\)** window and assign the same number to each approver in the **\($ T\_1541\_3 Sequence No. $\)** field. For more information, see [How to: Set Up Workflow Users](../../BusinessFunctionality/Workflow/how-to-set-up-workflow-users.md).  
  
### To set up an approval user  
  
1.  In the **Search** box, enter **Approval User Setup**, and then choose the related link.  
  
2.  Create a new line in the **\($ N\_663 Approval User Setup $\)** window, and then fill the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_91\_1 User ID $\)**|Select the user ID of the user who is involved in the approval process.|  
    |**\($ T\_91\_10 Salespers.\/Purch. Code $\)**|Specify the salesperson or purchaser code that applies to the user in the **\($ T\_91\_10 Salespers.\/Purch. Code $\)** field.<br /><br /> You typically fill the **\($ T\_91\_10 Salespers.\/Purch. Code $\)** field if the salesperson or purchaser who is responsible for the customer or vendor is also the person who must approve the sales or purchase request in question.|  
    |**\($ T\_91\_11 Approver ID $\)**|Select the user ID of the user who must approve requests made by the user in the **\($ T\_91\_1 User ID $\)** field.|  
    |**\($ T\_91\_12 Sales Amount Approval Limit $\)**|Specify the maximum sales amount in LCY that the user in the **\($ T\_91\_1 User ID $\)** field can approve.|  
    |**\($ T\_91\_14 Unlimited Sales Approval $\)**|Specify that the user in the **\($ T\_91\_1 User ID $\)** field can approve all sales requests regardless of their amount.<br /><br /> If you select this check box, then you cannot fill the **\($ T\_91\_12 Sales Amount Approval Limit $\)** field.|  
    |**\($ T\_91\_13 Purchase Amount Approval Limit $\)**|Specify the maximum purchase amount in LCY that the user in the **\($ T\_91\_1 User ID $\)** field can approve.|  
    |**\($ T\_91\_15 Unlimited Purchase Approval $\)**|Specify that the user in the **\($ T\_91\_1 User ID $\)** field can approve all purchase requests regardless of their amount.<br /><br /> If you select this check box, then you cannot fill the **\($ T\_91\_12 Sales Amount Approval Limit $\)** field.|  
    |**\($ T\_91\_19 Request Amount Approval Limit $\)**|Specify the maximum amount in LCY that the user in the **\($ T\_91\_1 User ID $\)** field can approve for purchase quotes.<br /><br /> To use this field, you must select the **Approver Chain** option in the **\($ T\_1523\_13 Approver Limit Type $\)** field in the **\($ N\_1521 Workflow Response $\)** window.|  
    |**\($ T\_91\_20 Unlimited Request Approval $\)**|Specify that the user in the **\($ T\_91\_1 User ID $\)** field can approve all purchase quotes regardless of their amount.<br /><br /> If you select this check box, then you cannot fill the **\($ T\_91\_19 Request Amount Approval Limit $\)** field.|  
    |**\($ T\_91\_16 Substitute $\)**|Select the user ID of the user who must approve requests made by the user in the **\($ T\_91\_1 User ID $\)** field if the user in the **\($ T\_91\_11 Approver ID $\)** is not available. **Note:**  The substitute can either be the user in the **\($ T\_91\_16 Substitute $\)** field, the direct approver, or the approval administrator, in that order of priority. For more information, see [How to: Delegate Requests for Approval](../../BusinessFunctionality/Workflow/how-to-delegate-requests-for-approval.md).|  
    |**\($ T\_91\_17 Email $\)**|Specify the email address of the user in the **\($ T\_91\_1 User ID $\)** field.|  
    |**\($ T\_91\_21 Approval Administrator $\)**|Specify the user who has rights to unblock approval workflows, for example, by delegating approval requests to new substitute approvers and deleting overdue approval requests.|  
  
    > [!NOTE]  
    >  The behavior of **\($ T\_1523\_13 Approver Limit Type $\)** field only applies to application areas where limits can be defined, namely sales and purchase approvals. Any other type of approval where limits do not apply will always behave as described for the **Direct Approver** option.  
  
3.  To test the approval user setup, on the **Actions** tab, in the **General** group, choose **Approval User Setup Test**. For more information, see [\($ R\_600 Approval User Setup Test $\)](../Topic/\($%20R_600%20Approval%20User%20Setup%20Test%20$\).md).  
  
4.  Repeat steps 2 and 3 for every user who you want to set up as an approval user.  
  
## See Also  
 [\($ T\_454\_19 Limit Type $\)](../Topic/\($%20T_454_19%20Limit%20Type%20$\).md)   
 [\($ R\_600 Approval User Setup Test $\)](../Topic/\($%20R_600%20Approval%20User%20Setup%20Test%20$\).md)   
 [How to: Set Up Workflow Users](../../BusinessFunctionality/Workflow/how-to-set-up-workflow-users.md)   
 [Setting Up Workflow Notifications](../../BusinessFunctionality/Workflow/setting-up-workflow-notifications.md)   
 [How to: Create Workflows](../../BusinessFunctionality/Workflow/how-to-create-workflows.md)   
 [Set Up Workflows](../../BusinessFunctionality/Workflow/set-up-workflows.md)   
 [Walkthrough: Setting Up and Using a Purchase Approval Workflow](../../BusinessFunctionality/Workflow/walkthrough-setting-up-and-using-a-purchase-approval-workflow.md)   
 [Workflow](../../BusinessFunctionality/Workflow/workflow.md)   
 [Business Functionality](../Topic/Business%20Functionality.md)