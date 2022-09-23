---
title: Set Up Approval Users
description: Before you can create workflows that involve approval steps, you must set up the workflow users involved in the approval processes on the Approval User Setup page.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.form: 663
ms.date: 09/08/2022
ms.author: edupont

---
# Set Up Approval Users

Before you can create workflows that involve approval steps, you must set up the workflow users who are involved in approval processes. On the **Approval User Setup** page, you also set amount limits for specific types of requests and define substitute approvers to whom approval requests are delegated when the original approver is absent.  

> [!NOTE]  
> Both approval requesters and approvers must first be set up as workflow users on the **Workflow User Group** page. Learn more at [Set Up Workflow Users](across-how-to-set-up-workflow-users.md).  

When you have set up approval users, you can create workflow responses for approval workflows. Learn more from step 9 at [Create Approval Workflows](across-how-to-create-workflows.md).  

> [!NOTE]  
> To define an approval request as not approved until multiple users have approved it, set approvers up in a hierarchy. For approver type **Approver**, set approvers up on the **Approval User Setup** page. For approver type **Workflow User Group**, set approvers up on the **Workflow User Groups** page and define the hierarchy by assigning incremental numbers to each approver in the **Sequence No.** field. Learn more below and at [Set Up Workflow Users](across-how-to-set-up-workflow-users.md).  

## To set up an approval user

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Approval User Setup**, then choose the related link.  
2. Create a new line on the **Approval User Setup** page, then fill the fields as described in the following table.  

   |Field|Description|
   |-----|-----------|
   |**User ID**|Select the user ID of the person involved in the approval process.|
   |**Salespers./Purch. Code**|Specify the salesperson or purchaser code that applies to the user.<br /><br /> You typically fill in the **Salespers./Purch. Code** field if the salesperson or purchaser responsible for the customer or vendor is also the person who must approve the sales or purchase request in question.|
   |**Approver ID**|Select the user ID of the person who must approve requests made by the person identified in the **User ID** field.|
   |**Sales Amount Approval Limit**|Specify the maximum sales amount in local currency (LCY) that the person identified in the **User ID** field can approve.|
   |**Unlimited Sales Approval**|Specify that the person identified in the **User ID** field can approve all sales requests regardless of the amount.<br /><br /> If you select this check box, you can't fill in the **Sales Amount Approval Limit** field.|
   |**Purchase Amount Approval Limit**|Specify the maximum purchase amount in LCY that the person identified in the **User ID** field can approve.|
   |**Unlimited Purchase Approval**|Specify that the person identified in the **User ID** field can approve all purchase requests regardless of the amount.<br /><br /> If you select this check box, you can't fill in the **Purchase Amount Approval Limit** field.|
   |**Request Amount Approval Limit**|Specify the maximum amount in LCY that the person identified in the **User ID** field can approve for purchase quotes.<br /><br /> To use this field, you must select the **Approver Chain** option in the **Approver Limit Type** field on the **Workflow Response** page.|
   |**Unlimited Request Approval**|Specify that the person identified in the **User ID** field can approve all purchase quotes regardless of the amount.<br /><br /> If you select this check box, you can't fill in the **Request Amount Approval Limit** field.|
   |**Substitute**|Select the user ID of the person who will approve requests made by the person identified in the **User ID** field, if the user in the **Approver ID** isn't available. <br /><br />**Note:**  The substitute can either be the user in the **Substitute** field, the direct approver, or the approval administrator, in that order of priority. Learn more at [Use Approval Workflows](across-how-use-approval-workflows.md).|
   |**Email**|Specify the email address of the person in the **User ID** field.|
   |**Approval Administrator**|Specify the user with rights to unblock approval workflow, such as by delegating approval requests to new substitute approvers or deleting overdue approval requests.|

   > [!NOTE]
   > Only one person can be the approval administrator.

3. To test the approval user setup, choose the **Approval User Setup Test** action.  
4. Repeat steps 2 and 3 for every person you want to set up as an approval user.  

## See related [Microsoft training](/training/modules/create-workflows/)

## See also

[Set Up Workflow Users](across-how-to-set-up-workflow-users.md)  
[Setting Up Workflow Notifications](across-setting-up-workflow-notifications.md)  
[Create Approval Workflows](across-how-to-create-workflows.md)  
[Setting Up Approval Workflows](across-set-up-workflows.md)  
[Walkthrough: Setting Up and Using a Purchase Approval Workflow](walkthrough-setting-up-and-using-a-purchase-approval-workflow.md)  
[Workflow](across-workflow.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
