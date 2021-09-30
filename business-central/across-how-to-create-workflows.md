---
    title: Create workflows to connect tasks
    description: You can create workflows that connect business-process tasks performed by different users, and include System tasks, like automatic posting, as workflow steps.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 06/30/2021
    ms.author: edupont

---
# Create Workflows to Connect Business-Process Tasks

You can create workflows that connect business-process tasks performed by different users. System tasks, such as automatic posting, can be included as steps in workflows, preceded or followed by user tasks. Requesting and granting approval to create new records are typical workflow steps.  

On the **Workflow** page, you create a workflow by listing the involved steps on the lines. Each step consists of a workflow event moderated by event conditions and a workflow response with response options. You define workflow steps by filling fields on workflow lines from fixed lists of event and response values representing scenarios that are supported by the application code.  

When you create workflows, you can copy the steps from existing workflows or from workflow templates. Workflow templates represent non-editable workflows that exist in the generic version of [!INCLUDE[prod_short](includes/prod_short.md)]. The code for workflow templates that are added by Microsoft are prefixed with "MS-", such as in "MS-PIW". For more information, see [Create Workflows from Workflow Templates](across-how-to-create-workflows-from-workflow-templates.md).  

If your business scenario requires workflow events or responses that are not supported, a Microsoft partner must implement them by creating an extension that implements the relevant workflow event.  

> [!NOTE]  
> All notifications about workflow steps are sent through a job queue. Make sure that the job queue reflects your business needs. For more information, see [Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md).  

:::image type="content" source="media/Workflows/workflow-example.png" alt-text="Illustration of a workflow example.":::

The workflow is divided into three sections:

1) **When Event**
    This is where the trigger is selected.
    Examples of trigger could be:
    - A master data record is changed
    - A journal line is created
    - an Incoming document is created or released
    - Approval of a document is requested

2) **On Condition of**
    The **conditions** are related to the event and opens for creating filters for when the event is triggered
3) **Then Response**
    The **Responses** responds to what the next step in the work are.

For both types of events, the events are system-defined. New events must be added through the development of an extension.

## To create a workflow

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Workflows**, and then choose the related link.  
2. Choose the **New** action. The **Workflow** page opens.  
3. In the **Code** field, enter a maximum of 20 characters to identify the workflow.  
4. To create the workflow from a workflow template, on the **Workflows** page, choose the **Create Workflow from Template** action. For more information, see [Create Workflows from Workflow Templates](across-how-to-create-workflows-from-workflow-templates.md).  
5. In the **Description** field, describe the workflow.  
6. In the **Category** field, specify which category the workflow belongs to.  
7. In the **When Event** field, specify the event that must occur to start the workflow step.  

    When you choose the field, the **Workflow Events** page opens where you select from all the workflow events that exist.  
8. In the **Condition** field, specify one or more conditions that must be met before the event in the **When Event** field can occur.  

    When you choose the field, the **Event Conditions** page opens where you choose from a list of filter fields that are relevant as conditions for the event in question. You can add new filter fields that you want to use as event conditions. You set event condition filters just as you set filters on report request pages.  

    If the workflow event is the change of a specific field on a record, then the **Event Conditions** page opens with options to select the field and the type of change.  

    1. To specify a field change for the event, on the **Event Conditions** page, in the **Field** field, select the field that changes.  
    2. In the **Operator** field, select either **Decreased**, **Increased**, or **Changed**.  
9. In the **Then Response** field, specify the response that will follow when the workflow event occurs.  

     When you choose the field, the **Workflow Responses** page opens where you select from all workflow responses that exist and set response options for the selected response.  
10. On the **Options for the Selected Response** FastTab, specify options for the workflow response, by selecting values in the different fields that appear, as follows:  

    1. To specify options for a workflow response that involves sending a notification, fill the fields as described in the following table.  

        |Field|Description|  
        |-----|-----------|  
        |**Notify Sender**|Specify if the approval requestor is notified instead of the approval request recipient. If you select the check box, the **Recipient User ID** field is disabled because the requestor of the approval, the sender, will be notified instead. The name of the workflow response changes accordingly, to **Create Notification for &lt;Sender&gt;**. If the check box is not selected, the name of the workflow response is **Create Notification for &lt;User&gt;**.
        |**Recipient User ID**|Specify the user who the notification must be sent to. **Note**: This option is only available for workflow responses with a placeholder for a specific user. For workflow responses without placeholders for users, the notification recipient is typically defined by the approval user setup.|  
        |**Notification Entry Type**|Specifies if the workflow notification is triggered by a record change, an approval request, or a passed due data.|
        |**Link Target Page**|Specify another page that the link in the notification opens instead of the default page. Note that the page must have the same source table as the record involved.|
        |**Custom Link**|Specify the URL of a link that is added to the notification in addition to the link to page.|  

    2. To specify options for a workflow response that involves creating an approval request, fill the fields as described in the following table.  

        |Field|Description|  
        |-----|-----------|  
        |**Due Date Formula**|Specify in how many days the approval request must be resolved from the date when it was sent.|
        |**Delegate After**|Specify if and when an approval request will automatically be delegated to the relevant substitute. You can select to automatically delegate one, two, or five days after the date when the approval was requested.|
        |**Approver Type**|Specify who the approver is, according to the setup of approval users and workflow users. When the field is set to **Salesperson/Purchaser**, that setting specifies that the user who is set up in the **Salespers./Purch. Code** field on the **Approval User Setup** page determines the approver. Approval request entries are then created according to the value in the **Approver Limit Type** field. For more information, see [Set Up Approval Users](across-how-to-set-up-workflow-users.md).|
        |**Show Confirmation Message**|Specify if a confirmation message is shown to users after they request an approval.|
        |**Approver Limit Type**|Specify how approvers' approval limits affect when approval request entries are created for them. A qualified approver is an approver whose approval limit is above the value on the request being made.The following options exist: <ol><li>**Approver Chain** specifies that approval request entries are created for all the requester's approvers up to and including the first qualified approver</li><li>**Direct Approver** specifies that an approval request entry is only created for the requester's immediate approver, regardless of the approver's approval limit.</li><li>**First Qualified Approver** specifies that an approval request entry is only created for the requester's first qualified approver.</li></ol>|
    3. To specify options for a workflow response that involves creating journal lines, fill the fields as described in the following table.  

        |Field|Description|  
        |-----|-----------|  
        |**General Journal Template Name**|Specify the name of the general journal template that the specified journal lines are created in.|  
        |**General Journal Batch Name**|Specify the name of the general journal batch that the specified journal lines are created in.|  

11. Choose the **Increase Indent** and **Decrease Indent** buttons to indent the event name in the **When** field to define the step's position in the workflow.  

    1. Indicate that the step is the next in the workflow sequence by indenting the event name under the event name of the previous step.  
    2. Indicate that the step is one of more alternative steps that may start depending on its condition by placing the event name at the same indentation as the other alternative steps. Order such optional steps according to priority by placing the most important step first.  

    > [!NOTE]  
    >  You can only change the indent of a step that does not have a subsequent step.  

12. Repeat steps 7 through 11 to add more workflow steps, either before or after the step that you have just created.  
13. Select the **Enabled** check box to specify that the workflow will start as soon as the event on the first step of type **Entry Point** occurs. For more information, see [Using Workflows](across-use-workflows.md).  

> [!NOTE]  
> Do not enable a workflow until you are sure that the workflow is completed and that the involved workflow steps can start.  

> [!TIP]  
> To see relations between tables that are used in workflows, Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, and then enter **Workflow – Table Relations**.  

## Example of creating a new workflow using existing events

In the following example a new workflow is made to approve changes to the name of en existing vendor:

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Workflows**, and then choose the related link.  
2. Choose the **New** action. The **Workflow** page opens.
3. In the workflow section, fill in the fields as described in the following table.

    |Field  |Value  |
    |---------|---------|
    |**Code**|**VENDAPN-01**|
    |**Description**|**Vendor Name Change Approval** |
    |**Category**|**PURCH**|

4. To create the first workflow step, follow these steps.

    1. In the **When Event** field, specify *A vendor record is changed*.  
    2. In the **On Condition** field, choose the word **Always**, and then, in the **Event Conditions** page, choose the **Add a condition for when a field value changes** link, and then select the *Name* field.  

      The result of this step is that the condition reads as *Name is Changed*.  
    3. In the **Then Response** field, choose the **Select Response** link, and then, in the **Workflow Responses** page, in the **Select Response** field, choose the *Revert the value of the \<Field\> field on the record and save the change* response, and then, in the **Options for the Selected Response** section, specify the *Name* field.  
    4. Choose the **Add More Responses** link, and then add an entry for the *Create an approval request for the record using approver type <%1> and <%2>.* response.  
    5. In the **Options for the Selected Response** section for the new response, change the **Approver type** field to *Workflow User Group*, and then, in the **Workflow User Group** field, specify the relevant user group.  

    For more information, see [Set Up Approval Users](across-how-to-set-up-approval-users.md).  
    6. Add a third response, *Send approval request for the record and create a notification.*  
    7. Add a fourth response, *Show message "%1"*, and then, in the **Options for the Selected Response** section, in the Message field, specify **An approval request has been sent**.  
    8. Choose the OK button to return to the workflow step.  

5. In the next line, add a new workflow step for the *An approval request is approved.* event.  

    1. In the **When Event** field, specify *An approval request is approved*.  
    2. Choose the line menu, and then choose **Increase Indent**.  
    3. In the **On Condition** field, choose the word **Always**, and then, in the **Pending Approvals** field, specify *0*.  

      The result of this step is that the condition reads as *Pending Approvals:0* to indicate that this is the last approver.  
    4. In the **Then Response** field, choose the **Select Response** link, and then, in the **Workflow Responses** page, in the **Select Response** field, choose the *Send approval request for the record and create a notification* response.  
    5. Choose the OK button.  
6. In the next line, add a second workflow step for the *An approval request is approved* event.  

    1. In the **When Event** field, specify *An approval request is approved*.
    2. In the **On Condition** field, choose the word **Always**, and then, in the **Pending Approvals** field, specify *>0*.  

      The result of this step is that the condition reads as *Pending Approvals:>0* to indicate that this is *not* the last approver.  
    3. In the **Then Response** field, choose the **Select Response** link, and then, in the **Workflow Responses** page, in the **Select Response** field, choose the *Send approval request for the record and create a notification* response.  
    4. Choose the OK button.  
7. In the next line, add a workflow step for the *An approval request is rejected* event.  

    1. In the **When Event** field, specify *An approval request is rejected*.  
    2. In the **On Condition** field,  leave the value as *Always*.  
    3. In the **Then Response** field, choose the **Select Response** link, and then, in the **Workflow Responses** page, in the **Select Response** field, choose the *Discard the new values* response.  
    4. Choose the **Add More Responses** link, and then add an entry for the *Reject the approval request for the record and create a notification* response
    5. Choose the OK button.  
8. In the next line, add a second workflow step for the *An approval request is rejected* event.  

    1. In the **When Event** field, specify *An approval request is rejected*.  
    2. In the **On Condition** field,  leave the value as *Always*.  
    3. In the **Then Response** field, choose the **Select Response** link, and then, in the **Workflow Responses** page, in the **Select Response** field, choose the *Send approval request for the record and create a notification* response.  
    4. Choose the OK button.  
9. To enable the workflow, choose the **Enabled** field.  

The following illustrations provides an overview of the result of this procedure.  

:::image type="content" source="media/Workflows/workflow-example-2.png" alt-text="Illustration of the Vendor Name Approval workflow.":::

Next, you must and test the workflow by opening an existing vendor and change the name. Verify that an approval request is made on changing the vendor name.

## See Also

[Create Workflows from Workflow Templates](across-how-to-create-workflows-from-workflow-templates.md)  
[Set Up Approval Users](across-how-to-set-up-approval-users.md)  
[Setting Up Workflow Notifications](across-setting-up-workflow-notifications.md)  
[View Archived Workflow Step Instances](across-how-to-view-archived-workflow-step-instances.md)  
[Delete Workflows](across-how-to-delete-workflows.md)  
[Walkthrough: Setting Up and Using a Purchase Approval Workflow](walkthrough-setting-up-and-using-a-purchase-approval-workflow.md)  
[Setting Up Workflows](across-set-up-workflows.md)  
[Using Workflows](across-use-workflows.md)  
[Workflow](across-workflow.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
