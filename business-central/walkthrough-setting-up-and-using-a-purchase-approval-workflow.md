---
    title: Setting Up and Using a Purchase Approval Workflow | Microsoft Docs
    description: You can automate the process of approving new or changed records, such as documents, journal lines, and customer cards, by creating workflows with steps for the approvals in question. Before you create approval workflows, you must set up an approver and substitute approver for each approval user. You can also set approvers’ amount limits to define which sales and purchase records they are qualified to approve. Approval requests and other notifications can be sent as email or internal note. For each approval user setup, you can also set up when they receive notifications.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# Walkthrough: Setting Up and Using a Purchase Approval Workflow
You can automate the process of approving new or changed records, such as documents, journal lines, and customer cards, by creating workflows with steps for the approvals in question. Before you create approval workflows, you must set up an approver and substitute approver for each approval user. You can also set approvers’ amount limits to define which sales and purchase records they are qualified to approve. Approval requests and other notifications can be sent as email or internal note. For each approval user setup, you can also set up when they receive notifications.  

 You can set up and use workflows that connect business-process tasks performed by different users. System tasks, such as automatic posting, can be included as steps in workflows, preceded or followed by user tasks. Requesting and granting approval to create new records are typical workflow steps. For more information, see [Workflow](across-workflow.md).  

## About This Walkthrough  
This walkthrough illustrates the following tasks:  

-   Setting up approval users (incl. setting up a user in Windows and in [!INCLUDE[d365fin](includes/d365fin_md.md)]).  
-   Setting up notifications for approval users.  
-   Modifying and enabling an approval workflow.  
-   Starting the job queue that dispatches notifications.  
-   Requesting approval of a purchase order, as Alicia.  
-   Receiving a notification and then approving the request, as Sean.  

## Prerequisites  
To complete this walkthrough, you will need the CRONUS International Ltd. demonstration company.

## Story  
Sean is a super user at CRONUS on his own computer.  

He creates two approval users. One is Alicia who represents a purchasing agent. The other is himself representing Alicia’s approver. Sean then gives himself unlimited purchase approval rights and specifies that he will receive notifications by internal note as soon as a relevant event occurs. Last, Sean creates the required approval workflow as a copy of the existing Purchase Order Approval Workflow workflow template, leaves all existing event conditions and response options unchanged, and then enables the workflow.  

To test the approval workflow, Sean first logs into [!INCLUDE[d365fin](includes/d365fin_md.md)] as Alicia, and then requests approval of a purchase order. Sean then logs in as himself, sees the note on his Role Center, follows the link to the approval request for the purchase order, and approves the request.  

## Setting Up the Sample Data  
You must create a new user on the local computer and in [!INCLUDE[d365fin](includes/d365fin_md.md)] representing Alicia who you will later select as an approval user. Your own user account will represent Sean.  

### To add Alicia as a user on the local computer  

1.  Choose **Start**, in the **Search programs and files** box, enter **Edit local users and groups**, and then choose the related link.  
2.  Open the **Users** folder.  
3.  On the **Actions** tab, choose **New User**.  
4.  In the **User Name** field, enter Alicia.  
5.  In the **Password** and **Confirm Password** fields, enter a valid password.  
6.  Deselect the **User must change password at next logon** check box.  
7.  Close the **Local Users and Groups** window.  

### To add Alicia as a user in [!INCLUDE[d365fin](includes/d365fin_md.md)]  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Users**, and then choose the related link.  
2.  In the **Windows Users** window, on the **Home** tab, in the **New** group, choose **New**.  
3.  In the **User Card** window, in the **User Name** field, enter Alicia.  
4.  In the **Windows User Name** field, choose the AssistEdit button.  
5.  In the **Select User or Group**, window, in the **Enter the object name to select** field, enter Alicia, and then choose the **Check Names** button.  
6.  When [COMPUTER NAME]ALICIA appears in the field, choose the **OK** button.  
7.  On the **User Permission Sets** FastTab, in the **Permission Set** field, select **SUPER**.  
8.  In the **Company** field, select **CRONUS International Ltd.**  
9. Choose the **OK** button.  

## Setting Up Approval Users  
Using the Windows user that you have just created, set Alicia up as an approval user whose approver is yourself. Set up your approval rights and specify how and when you are notified of approval requests.  

### To set up yourself and Alicia as approval users  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Approval User Setup**, and then choose the related link.  
2.  In the **Approval User Setup** window, on the **Home** tab, in the **New** group, choose **New**.  

    > [!NOTE]  
    >  You must set up an approver before you can set up users who require that approver's approval. Therefore, you must set up yourself before you set up Alicia.  

3.  Set up the two approval users by filling the fields as described in the following table.  

    |User ID|Approver ID|Unlimited Purchase Approval|  
    |-------------|-----------------|---------------------------------|  
    |[COMPUTER NAME][YOU]||Selected|  
    |[COMPUTER NAME]ALICIA|[COMPUTER NAME][YOU]||  

## Setting Up Notifications  
Specify how and when you are notified of approval requests.  

### To set up how and when you are notified  
1.  In the **Approval User Setup** window, select the line for yourself, and then on the **Home** tab, in the **Process** group, choose **Notification Setup**.  
2.  In the **Notification Setup** window, in the **Notification Type** field, enter **Approval**.  
3.  Choose the **Notification Template Code** field, and then choose the **Advanced** button.  
4.  In the **Notification Templates** window, on the **Home** tab, in the **Manage** group, choose **Edit List**.  
5.  On the line for the APPROVAL template, in the **Notification Method** field, enter **Note**.  
6.  Choose the **OK** button.  
7.  In the **Notification Setup** window, on the **Home** tab, in the **Process** group, choose **Notification Schedule**.  
8.  In the **Notification Schedule** window, in the **Occurence** field, choose **Instantly**.  
9. Choose the **OK** button.  

## Creating the Approval Workflow  
 Create the purchase order approval workflow by copying the steps from the Purchase Order Approval Workflow workflow template. Leave the existing workflow steps unchanged, and then enable the workflow.  

### To create and enable a purchase order approval workflow  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Workflows**, and then choose the related link.  
2.  In the **Workflows** window, on the **Actions** tab, in the **General** group, choose **Create Workflow from Template**.  
3.  On the **Actions** tab, in the **General** group, choose **Create Workflow from Template**. The **Workflow Templates** window opens.  
4.  Select the workflow template named Purchase Order Approval Workflow, and then choose the **OK** button.  

    The **Workflow** window opens for a new workflow containing all the information of the selected template. The value in the **Code** field is extended with “-01” to indicate that this is the first workflow that is created from the Purchase Order Approval Workflow workflow template.  
5.  On the header of the **Workflow** window, select the **Enabled** check box.  

## Starting a Notification Job Queue  
Make sure that a job queue in your installation is set up to handle workflow notifications.  

### To start the NOTIFY job queue  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Job Queues**, and then choose the related link.  
2.  In the **Job Queues** window, select the line for the NOTIFY job queue, and then, on the **Home** tab, in the **Process** group, choose **Start Job Queue**.  

## Using the Approval Workflow  
Use the new Purchase Order Approval Workflow workflow by first logging into [!INCLUDE[d365fin](includes/d365fin_md.md)] as Alicia to request approval of a purchase order. Then log in as yourself, view the note on the Role Center, follow the link to the approval request, and then approve the request.  

To log into [!INCLUDE[d365fin](includes/d365fin_md.md)] as different users, you will use the **Run as different user** function.  

### To log into [!INCLUDE[d365fin](includes/d365fin_md.md)] as Alicia  

1.  For the [!INCLUDE[d365fin](includes/d365fin_md.md)] web client, on the browser launch button for the web page, press Shift + Right-Click, and then choose **Run as different user**.  

    For the [!INCLUDE[d365fin](includes/d365fin_md.md)] Windows client, on the launch button for the program, press Shift + Right-Click, and then choose **Run as different user**.  

2.  In the **Windows Security** window, enter [COMPUTER NAME]ALICIA and the required password.  

### To request approval of a purchase order, as Alicia  

1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Purchase Orders**, and then choose the related link.  
2.  Select the line for open purchase order 104001, and then on the **Home** tab, in the **Manage** group, choose **Edit**.  
3.  In the **Purchase Order** window, on the **Actions** tab, in the **Approval** group, choose **Send Approval Request**.  

    Notice that the value in the **Status** field has changed to **Pending Approval**.  

4.  Close [!INCLUDE[d365fin](includes/d365fin_md.md)].  

### To approve the purchase order, as Sean  

1.  Open [!INCLUDE[d365fin](includes/d365fin_md.md)] as you generally do. The program will open with you as the user.  
2.  On the Role Center, in the **My Notifications** window, look for a new note from Alicia.  

    > [!NOTE]  
    >  Although the notification recurrence is set to **Instantly**, the note will arrive approximately one minute after Alicia sent the approval request. This is due to the default recurrence frequency of the Job Queue feature.  

3.  When the note appears in the **My Notifications** window, choose the **Approval Entry: XX, XX** value in the **Page** field. The **Requests to Approve** window opens with Alicia’s request for the purchase order highlighted.  
4.  In the **Requests to Approve** window, on the **Home** tab, in the **Process** group, choose **Approve**.  

    The value in the **Status** field on Alicia’s purchase order changes to **Released**.  

You have now set up and tested a simple approval workflow based on the first two steps of the Purchase Order Approval Workflow workflow. You can easily extend this workflow to automatically post Alicia’s purchase order when Sean approves it. To do this, you must enable the Purchase Invoice Workflow workflow, in which the response to a released purchase invoice is to post it. First you must change the event condition on the first workflow step from (purchase) **Invoice** to **Order**.  

The generic version [!INCLUDE[d365fin](includes/d365fin_md.md)] includes a number of workflow templates for scenarios that are supported by the application code. Most of these are for approval workflows. For more information, see Workflow Templates.  

You define variations of workflows by filling fields on workflow lines from fixed lists of event and response values representing scenarios that are supported by the application code. For more information, see [Create Workflows](across-how-to-create-workflows.md).  

If a business scenario requires a workflow event or response that is not supported, a Microsoft partner must implement them by customizing the application code. For more information, see [Walkthrough: Implementing New Workflow Events and Responses](/dynamics-nav/Walkthrough--Implementing-New-Workflow-Events-and-Responses) in the developer and IT-pro help.  

## See Also  
[Set Up Approval Users](across-how-to-set-up-approval-users.md)   
[Setting Up Workflow Notifications](across-setting-up-workflow-notifications.md)   
[Create Workflows](across-how-to-create-workflows.md)   
[Use Approval Workflows](across-how-use-approval-workflows.md)   
[Workflow](across-workflow.md)
