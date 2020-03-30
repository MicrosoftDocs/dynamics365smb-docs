---
    title: Setting Up and Using a Purchase Approval Workflow | Microsoft Docs
    description: You can automate the process of approving new or changed records, such as documents, journal lines, and customer cards, by creating workflows with steps for the approvals in question. Before you create approval workflows, you must set up an approver and substitute approver for each approval user. You can also set approvers’ amount limits to define which sales and purchase records they are qualified to approve. Approval requests and other notifications can be sent as email or internal note. For each approval user setup, you can also set up when they receive notifications.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Walkthrough: Setting Up and Using a Purchase Approval Workflow
You can automate the process of approving new or changed records, such as documents, journal lines, and customer cards, by creating workflows with steps for the approvals in question. Before you create approval workflows, you must set up an approver and substitute approver for each approval user. You can also set approvers’ amount limits to define which sales and purchase records they are qualified to approve. Approval requests and other notifications can be sent as email or internal note. For each approval user setup, you can also set up when they receive notifications.

> [!NOTE]
> In addition to the Workflow functionality within [!INCLUDE[d365fin](includes/d365fin_md.md)], you can integrate to Microsoft Flow to define workflows for events in [!INCLUDE[d365fin](includes/d365fin_md.md)]. Note that although they are two separate workflow systems, any Flow template that you create with Microsoft Flow is added to the list of workflow templates within [!INCLUDE[d365fin](includes/d365fin_md.md)]. For more information, see [Using Business Central in an Automated Workflow](across-how-use-financials-data-source-flow.md).   

 You can set up and use workflows that connect business-process tasks performed by different users. System tasks, such as automatic posting, can be included as steps in workflows, preceded or followed by user tasks. Requesting and granting approval to create new records are typical workflow steps. For more information, see [Workflow](across-workflow.md).  

## About This Walkthrough  
This walkthrough illustrates the following tasks:  

-   Setting up approval users.  
-   Setting up notifications for approval users.  
-   Modifying and enabling an approval workflow.  
-   Requesting approval of a purchase order, as Alicia.  
-   Receiving a notification and then approving the request, as Sean.  

## Story  
Sean is a super user at CRONUS. He creates two approval users. One is Alicia who represents a purchasing agent. The other is himself representing Alicia’s approver. Sean then gives himself unlimited purchase approval rights and specifies that he will receive notifications by internal note as soon as a relevant event occurs. Last, Sean creates the required approval workflow as a copy of the existing Purchase Order Approval Workflow workflow template, leaves all existing event conditions and response options unchanged, and then enables the workflow.  

To test the approval workflow, Sean first signs in to [!INCLUDE[d365fin](includes/d365fin_md.md)] as Alicia, and then requests approval of a purchase order. Sean then signs in as himself, sees the note on his Role Center, follows the link to the approval request for the purchase order, and approves the request.  

## Setting Up Sample Data
Before you can set up approval users and their notification method, you must make sure that two users exist in [!INCLUDE[d365fin](includes/d365fin_md.md)]: One user will represent Alicia. The other user, yourself, will represent Sean. For more information, see [Create Users According to Licenses](ui-how-users-permissions.md).

### Setting Up Approval Users  
When signed in as yourself, set Alicia up as an approval user whose approver is yourself. Set up your approval rights and specify how and when you are notified of approval requests.  

#### To set up yourself and Alicia as approval users  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Approval User Setup**, and then choose the related link.  
2.  On the **Approval User Setup** page, choose the **New** action.  

    > [!NOTE]  
    >  You must set up an approver before you can set up users who require that approver's approval. Therefore, you must set up yourself before you set up Alicia.  

3.  Set up the two approval users by filling the fields as described in the following table.  

    |User ID|Approver ID|Unlimited Purchase Approval|  
    |-------------|-----------------|---------------------------------|  
    |YOU||Selected|  
    |ALICIA|YOU||  

### Setting Up Notifications  
In this walkthrough, the user is notified by internal note about requests to approve. Approval notification can also be by email. For more information, see [Specify When and How to Receive Notifications](across-how-to-specify-when-and-how-to-receive-notifications.md).

#### To set up how and when you are notified  
1.  On the **Approval User Setup** page, select the line for yourself, and then choose the **Notification Setup** action.  
2.  On the **Notification Setup** page, in the **Notification Type** field, choose **Approval**.  
3.  In the **Notification Method** field, choose **Note**.  
6.  On the **Notification Setup** page, choose the **Notification Schedule** action.  
7.  On the **Notification Schedule** page, in the **Recurrence** field, select **Instantly**.  

## Creating the Approval Workflow  
 Create the purchase order approval workflow by copying the steps from the Purchase Order Approval Workflow workflow template. Leave the existing workflow steps unchanged, and then enable the workflow.  

### To create and enable a purchase order approval workflow  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Workflows**, and then choose the related link.  
2.  On the **Workflows** page, choose the **New Workflow from Template** action.  
3.  On the **Workflow Templates** page, select the workflow template named Purchase Order Approval Workflow, and then choose the **OK** button.  

    The **Workflow** page opens for a new workflow containing all the information of the selected template. The value in the **Code** field is extended with “-01” to indicate that this is the first workflow that is created from the Purchase Order Approval Workflow workflow template.  
5.  On the header of the **Workflow** page, select the **Enabled** check box.  

## Using the Approval Workflow  
Use the new Purchase Order Approval Workflow workflow by first signing in to [!INCLUDE[d365fin](includes/d365fin_md.md)] as Alicia to request approval of a purchase order. Then sign in as yourself, view the note on the Role Center, follow the link to the approval request, and then approve the request.  

### To request approval of a purchase order, as Alicia  
1. Sign in as Alicia.
2.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders**, and then choose the related link.  
3.  Select the line for open purchase order 106001, and then choose the **Edit** action.  
4.  On the **Purchase Order** page, choose the **Send Approval Request** action.  

Notice that the value in the **Status** field has changed to **Pending Approval**.  

### To approve the purchase order, as Sean  
1. Sign in as Sean.
2. On the Role Center, in the **Self Service** area, choose the **Requests to Approve** tile.
3. On the **Requests to Approve** page, select the line about the purchase order by Alicia, and then choose the **Approve** action.  

The value in the **Status** field on Alicia’s purchase order changes to **Released**.  

You have now set up and tested a simple approval workflow based on the first two steps of the Purchase Order Approval Workflow workflow. You can easily extend this workflow to automatically post Alicia’s purchase order when Sean approves it. To do this, you must enable the Purchase Invoice Workflow workflow, in which the response to a released purchase invoice is to post it. First you must change the event condition on the first workflow step from (purchase) **Invoice** to **Order**.  

The generic version of [!INCLUDE[d365fin](includes/d365fin_md.md)] includes a number of workflow templates for scenarios that are supported by the application code. Most of these are for approval workflows.  

You define variations of workflows by filling fields on workflow lines from fixed lists of event and response values representing scenarios that are supported by the application code. For more information, see [Create Workflows](across-how-to-create-workflows.md).  

If a business scenario requires a workflow event or response that is not supported, a Microsoft partner must implement them by customizing the application code. For more information, see [Walkthrough: Implementing New Workflow Events and Responses](/dynamics-nav/Walkthrough--Implementing-New-Workflow-Events-and-Responses) in the developer and IT-pro help.  

## See Also  
[Set Up Approval Users](across-how-to-set-up-approval-users.md)   
[Setting Up Workflow Notifications](across-setting-up-workflow-notifications.md)   
[Create Workflows](across-how-to-create-workflows.md)   
[Use Approval Workflows](across-how-use-approval-workflows.md)   
[Workflow](across-workflow.md)  
[Using Business Central in an Automated Workflow](across-how-use-financials-data-source-flow.md)
