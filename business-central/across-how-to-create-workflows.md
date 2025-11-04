---
title: Create approval workflows to connect tasks
description: Learn how to create workflows that connect tasks performed by different people in business processes.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: v-soumramani
ms.topic: how-to
ms.date: 10/15/2025
ms.search.keywords: workflows, create workflow, connect tasks, business process
ms.custom: bap-template
ms.service: dynamics-365-business-central
---

# Create workflows to connect tasks in business processes

You can create workflows that connect tasks that different people do in business processes. You can include system tasks, such as automatic posting, as steps in workflows that user tasks precede or follow. Requesting and granting approval to create new records are typical workflow steps.  

On the **Workflow** page, create a workflow by listing the steps on the lines. Each step consists of a trigger and a response:

* An event that specifies the conditions that start the workflow.
* A workflow response that defines what the workflow does.

[!INCLUDE[workflow](includes/workflow.md)]

When you create workflows, you can copy the steps from existing workflows or from workflow templates. Workflow templates are noneditable workflows that [!INCLUDE[prod_short](includes/prod_short.md)] provides. The identifiers for workflow templates are prefixed with "MS-". For example, "MS-PIW." Learn more at [Create Workflows from Workflow Templates](across-how-to-create-workflows-from-workflow-templates.md).  

> [!NOTE]  
> All notifications about workflow steps are sent through a job queue. Make sure the job queue reflects your business needs. Learn more at [Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md).  

:::image type="content" source="media/Workflows/workflow-example.png" alt-text="Illustration of a workflow example.":::

A workflow is divided into three sections:

1. **When Event**  
   This is where you select the trigger.  

   Examples of a trigger:

   * A master data record is changed
   * A journal line is created
   * An incoming document is created or released
   * Approval of a document is requested
2. **On Condition**  
   Conditions are related to the event and allow you to create filters to specify how the workflow continues.
3. **Then Response**  
   Responses specify the next steps in the workflow.

The options for events and responses are system-defined. To add new options, you must develop an extension.

## To create a workflow

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Workflows**, then choose the related link.  
2. Choose the **New** action. The **Workflow** page opens.  
3. In the **Code** field, enter a maximum of 20 characters to identify the workflow.  
4. To create the workflow from a workflow template, on the **Workflows** page, choose the **New Workflow from Template** action. Learn more at [Create Workflows from Workflow Templates](across-how-to-create-workflows-from-workflow-templates.md).  
5. In the **Description** field, describe the workflow.  
6. In the **Category** field, specify which category the workflow belongs to.  
7. In the **When Event** field, specify the event that must occur to start the workflow step.  

   When you choose the field, the **Workflow Events** page lists all available workflow events.  
8. In the **On Condition** field, specify one or more conditions that must be met before the event in the **When Event** field can occur.  

   When you choose the field, the **Event Conditions** page lists filter fields that can be conditions for the event. You can add new filter fields if you want.  

   If the workflow event is the change of a specific field on a record, use the **Event Conditions** page to select the field and the type of change.  

   1. To specify a field change for the event, on the **Event Conditions** page, in the **Field** field, select the field that changes.  
   2. In the **Operator** field, select either **Decreased**, **Increased**, or **Changed**.  
9. In the **Then Response** field, specify the response when the workflow event occurs.  

   When you choose the field, the **Workflow Responses** page lists all available workflow responses and response options.  
10. On the **Options for the Selected Response** FastTab, specify options for the workflow response by selecting values in the different fields that appear, as follows:  

    1. To specify options for a workflow response that involves sending a notification, fill the fields as described in the following table.  

       > [!NOTE]
       > These fields vary, depending on the response you chose.

       |Field|Description|
       |-----|-----------|
       |**Notify Sender**|Specify whether to notify the approval requestor instead of the approval request recipient. If you select the checkbox, the **Recipient User ID** field is disabled because the requestor of the approval, the sender, is notified instead. The name of the workflow response changes accordingly, to **Create Notification for &lt;Sender&gt;**. If the checkbox isn't selected, the name of the workflow response is **Create Notification for &lt;User&gt;**.|
       |**Recipient User ID**|Specify the user the notification must be sent to. **Note**: This option is only available for workflow responses with a placeholder for a specific user. For workflow responses without placeholders for users, the notification recipient is typically defined by the **Approval User Setup**.|
       |**Notification Entry Type**|Specify a trigger for the workflow notification. The trigger can be a record change, an approval request, or passed due date.|
       |**Link Target Page**|Specify the page that the link in the notification opens. The page must have the same source table as the record involved.|
       |**Custom Link**|Specify the URL of a link included in the notification in addition to the link to the page.|

    2. To specify options for a workflow response that involves creating an approval request, fill the fields as described in the following table.  

       |Field|Description|  
       |-----|-----------|  
       |**Due Date Formula**|Specify the number of days the approver has to resolve the request. The period starts when the request is sent.|
       |**Delegate After**|Specify if and when an approval request is automatically delegated to the substitute. You can select to automatically delegate one, two, or five days after the date when the approval was requested.|
       |**Approver Type**|Specify who the approver is, according to the setup of approval users and workflow users. When the field is set to **Salesperson/Purchaser**, the user specified in the **Salespers./Purch. Code** field on the **Approval User Setup** page determines the approver. Approval request entries are then created according to the value in the **Approver Limit Type** field. Learn more at [Set Up Approval Users](across-how-to-set-up-workflow-users.md).|
       |**Show Confirmation Message**|Specify whether to show a confirmation message after a user requests an approval.|
       |**Approver Limit Type**|Specify the effect of limits for approvers. An approver's approval limit must be above the value on the request. The following options exist: <ol><li>**Approver Chain** specifies that approval request entries are created for all the requester's approvers up to and including the first qualified approver</li><li>**Direct Approver** specifies that an approval request entry is only created for the requester's immediate approver, regardless of the approver's approval limit.</li><li>**First Qualified Approver** specifies that an approval request entry is only created for the requester's first approver.</li><li>**Specific Approver** specifies that you notify the user chosen in the **Approver ID** field.</li></ol>|

    3. To specify options for a workflow response that involves creating journal lines, fill in the fields as described in the following table.  

       |Field|Description|  
       |-----|-----------|  
       |**General Journal Template Name**|Specify the name of the general journal template that the specified journal lines are created in.|  
       |**General Journal Batch Name**|Specify the name of the general journal batch that the specified journal lines are created in.|  

11. Choose the **Increase Indent** and **Decrease Indent** buttons to indent the event name in the **When** field to define the step's position in the workflow.  

    1. To indicate that it's the next step, indent the event under the name of the previous step.  
    2. Indicate the step is one of several alternative steps that might start, depending on its condition, by indenting the event name to match the other alternative steps. Order such optional steps according to priority by placing the most important step first.  

    > [!NOTE]  
    > You can only change the indent of a step that doesn't have a subsequent step.  

12. Repeat steps 7 through 11 to add more workflow steps, either before or after the step you created.  
13. Turn on the **Enabled** toggle to specify that the workflow starts when the event on the first step of type **Entry Point** occurs. Learn more at [Use Workflows](across-use-workflows.md).  

> [!NOTE]  
> Don't enable a workflow until you're sure it's ready.  
> [!TIP]  
> To explore the relations between the tables used in workflows, [!INCLUDE[open-search](includes/open-search-lowercase.md)], then enter **Workflow – Table Relations**.  

## Example of creating a new workflow using existing events

The following example creates a workflow to approve a change to the name of a vendor:

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Workflows**, then choose the related link.  
2. Choose the **New** action. The **Workflow** page opens.
3. In the workflow section, fill in the fields as described in the following table.

   |Field  |Value  |
   |---------|---------|
   |**Code**|**VENDAPN-01**|
   |**Description**|**Vendor Name Change Approval** |
   |**Category**|**PURCH**|

4. To create the first workflow step, do the following.

   1. In the **When Event** field, specify *A vendor record is changed*.  
   2. In the **On Condition** field, choose the word **Always**. Then, on the **Event Conditions** page, choose the **Add a condition for when a field value changes** link, then select the **Name** field. The result of this step is that the condition reads as *Name is Changed*.  
   3. In the **Then Response** field, choose the **Select Response** link. Then, on the **Workflow Responses** page, in the **Select Response** field, choose the **Revert the value of the \<Field\> field on the record and save the change** response. Then, in the **Options for the Selected Response** section, specify the **Name** field.  
   4. Choose the **Add More Responses** link, then add an entry for the **Create an approval request for the record using approver type <%1> and <%2>** response.  
   5. In the **Options for the Selected Response** section for the new response, change the **Approver type** field to **Workflow User Group**. Then, in the **Workflow User Group** field, specify the user group. Learn more at [Set Up Approval Users](across-how-to-set-up-approval-users.md).  
   6. Add a third response, **Send approval request for the record and create a notification**.  
   7. Add a fourth response, **Show message "%1"**. Then, in the **Options for the Selected Response** section, in the **Message** field, specify **An approval request has been sent**.  
   8. Choose **OK** to return to the workflow step.  

5. In the next line, add a new workflow step for the **An approval request is approved** event.

   1. In the **When Event** field, specify **An approval request is approved**.  
   2. Choose the line menu, then choose **Increase Indent**.  
   3. In the **On Condition** field, choose **Always**. Then, in the **Pending Approvals** field, specify **0**. The condition reads as **Pending Approvals:0** to indicate that the request doesn't require more approvers.  
   4. In the **Then Response** field, choose the **Select Response** link. Then, on the **Workflow Responses** page, in the **Select Response** field, choose the **Send approval request for the record and create a notification** response.  
   5. Choose **OK**.  
6. In the next line, add a second workflow step for the **An approval request is approved** event.  

   1. In the **When Event** field, specify **An approval request is approved**.
   2. In the **On Condition** field, choose **Always**. Then, in the **Pending Approvals** field, specify **>0**. The condition reads as **Pending Approvals:>0** to indicate that this isn't the last approver.  
   3. In the **Then Response** field, choose the **Select Response** link. Then, on the **Workflow Responses** page, in the **Select Response** field, choose the **Send approval request for the record and create a notification** response.  
   4. Choose **OK**.  
7. In the next line, add a workflow step for the **An approval request is delegated** event.  

   1. In the **When Event** field, specify **An approval request is delegated**.  
   2. In the **On Condition** field, leave the value as **Always**.  
   3. In the **Then Response** field, choose the **Select Response** link. Then, on the **Workflow Responses** page, in the **Select Response** field, choose the **Send approval request for the record and create a notification** response.  
   4. Choose **OK**.  
8. In the next line, add a second workflow step for the **An approval request is rejected** event.  

   1. In the **When Event** field, specify **An approval request is rejected**.  
   2. In the **On Condition** field,  leave the value as **Always**.  
   3. In the **Then Response** field, choose the **Select Response** link. Then, on the **Workflow Responses** page, in the **Select Response** field, choose the **Discard the new values** response.  
   4. Choose the **Add More Responses** link, then add an entry for the **Reject the approval request for the record and create a notification** response
   5. Choose **OK**.  
9. To enable the workflow, turn on the **Enabled** toggle.  

The following illustration provides an overview of the result of this procedure.  

:::image type="content" source="media/Workflows/workflow-example-2.png" alt-text="Illustration of the Vendor Name Approval workflow.":::

Next, test the workflow by opening an existing vendor card and changing their name. Verify that an approval request is sent after changing the vendor name.

## Related information

[Create Workflows from Workflow Templates](across-how-to-create-workflows-from-workflow-templates.md)  
[Set Up Approval Users](across-how-to-set-up-approval-users.md)  
[Set Up Approval Workflow Notifications](across-setting-up-workflow-notifications.md)  
[View Archived Workflow Step Instances](across-how-to-view-archived-workflow-step-instances.md)  
[Delete Approval Workflows](across-how-to-delete-workflows.md)  
[Walkthrough: Setting Up and Using a Purchase Approval Workflow](walkthrough-setting-up-and-using-a-purchase-approval-workflow.md)  
[Set Up Approval Workflows](across-set-up-workflows.md)  
[Use Approval Workflows](across-use-workflows.md)  
[Workflow](across-workflow.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
