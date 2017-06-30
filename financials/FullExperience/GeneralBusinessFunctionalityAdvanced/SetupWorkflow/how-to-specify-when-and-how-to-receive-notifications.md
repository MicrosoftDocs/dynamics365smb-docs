---
    title: Insert topic title| Microsoft Docs
    description: Insert description
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
# How to: Specify When and How to Receive Notifications
When you set up users in approval workflows, you must specify in the **Notification Setup** and **Notification Schedule** windows how and when each user receives notifications about approval workflow steps. Individual users can also change their notification setup by choosing the **Change Notification Settings** button on any notification.  
  
 Before you can set up an approval user’s notification preferences, you must set the user up as an approval user. For more information, [How to: Set Up Approval Users](../how-to-set-up-approval-users.md).  
  
 You define the layout and content of notifications by setting up notification templates. For more information, see [How to: Manage Notification Templates](../how-to-manage-notification-templates.md).  
  
 Many approval workflow steps are about notifying users that an event has occurred that they must act on. For example, on one workflow step, the event can be that User 1 requests approval of a new record. The related response is that a notification is sent to User 2, the approver. On the next workflow step, the event can be that User 2 approves the record. The related response is that a notification is sent to User 3 to start a process with the approved record. For workflow steps that are about approval, each notification is tied to an approval entry. For more information, see [Workflow](../workflow.md).  
  
### Specify when and how users receive notifications  
  
1.  In the **Search** box, enter **Approval User Setup**, and then choose the related link.  
  
2.  Select the line for the user that you want to set up notification preferences for, and then, on the **Home** tab, in the **Process** group, choose **Notification Setup**.  
  
3.  In the **Notification Setup** window, fill the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Notification Type**|Specify what type of event the notification is about.<br /><br /> Select one of the following options:<br /><br /> -   **New Record** specifies that the notification is about a new record, such as a document, that the user must act on.<br />-   **Approval** specifies that the notification is about one or more approval requests.<br />-   **Overdue** specifies that the notification is to remind users that they are late in acting on an event.|  
    |**Notification Template Code**|Specify the code of the notification template that is used to create notifications for the user.|  
    |**Unaggregated Notifications**|Specify if the user receives one notification for each event or aggregated notifications.<br /><br /> If the **Unaggregated Notifications** check box is not selected, then the user receives notifications that aggregate information about events that occur within the same recurrence pattern in the notification schedule.|  
  
     You have now specified how the user receives notifications. Proceed to specify when the user receives notifications.  
  
4.  On the **Home** tab, in the **Process** group, choose **Notification Schedule**.  
  
5.  In the **Notification Schedule** window, fill the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Recurrence**|Specify the recurrence pattern in which the user receives notifications.|  
    |**Time**|Specify what time of the day the user receives notifications when the value in the **Recurrence** field is different from **Instantly**.|  
    |**Daily Frequency**|Specify on which type of days the user receives notifications when the value in the **Recurrence** field is **Daily**.<br /><br /> Select **Weekday** to receive notifications every work day of the week. Select **Daily** to receive notifications every day of the week, including weekends.|  
    |**Monday** through **Sunday**|Specify on which days the user receives notifications when the value in the **Recurrence** field is **Weekly**.|  
    |**Date of Month**|Specify if the user receives notifications on the first, last, or a specific date of the month.|  
    |**Monthly Notification Date**|Specify the date of the month on which the user receives notifications when the value in the **Date of Month** field is **Custom**.|  
  
### Change when and how you receive notifications  
  
1.  On one of the notifications that you have received, either as email or note, choose the **Change Notification Settings** button.  
  
2.  In the **Notification Setup** window, change your notification preferences as described in the previous procedure.  
  
## See Also  
 Notification Setup   
 Notification Schedule   
 Notification Templates   
 [How to: Set Up Approval Users](../how-to-set-up-approval-users.md)   
 [How to: Manage Notification Templates](../how-to-manage-notification-templates.md)   
 [Setting Up Workflow Notifications](../setting-up-workflow-notifications.md)   
 Workflow   
 [Set Up Workflows](../set-up-workflows.md)   
 [Use Workflows](../use-workflows.md)