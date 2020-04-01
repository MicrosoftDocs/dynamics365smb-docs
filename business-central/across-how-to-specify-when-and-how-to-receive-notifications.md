---
    title: How to Specify When and How to Receive Notifications | Microsoft Docs
    description: When you set up users in approval workflows, you must specify in the Notification Setup and Notification Schedule pages how and when each user receives notifications about approval workflow steps. Individual users can also change their notification setup by choosing the Change Notification Settings button on any notification.
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
# Specify When and How to Receive Notifications
When you set up users in approval workflows, you must specify in the **Notification Setup** and **Notification Schedule** pages how and when each user receives notifications about approval workflow steps. Individual users can also change their notification setup by choosing the **Change Notification Settings** button on any notification.  

> [!NOTE]
> Notifications are delivered according to notification settings for the receiver, not the sender. That's an important distinction because it means that when someone requests an approval as part of a workflow their request is not necessarily sent immediately. Instead, it will be delivered according to the approvers's notification settings. 

 Before you can set up an approval user’s notification preferences, you must set the user up as an approval user. For more information, [Set Up Approval Users](across-how-to-set-up-approval-users.md).  

 You can define the layout of email notifications by customizing Report 1320, Notification Email. For more information, see [Create and Modify Custom Report Layouts](ui-how-create-custom-report-layout.md).  

 Many approval workflow steps are about notifying users that an event has occurred that they must act on. For example, on one workflow step, the event can be that User 1 requests approval of a new record. The related response is that a notification is sent to User 2, the approver. On the next workflow step, the event can be that User 2 approves the record. The related response is that a notification is sent to User 3 to start a process with the approved record. For workflow steps that are about approval, each notification is tied to an approval entry. For more information, see [Workflow](across-workflow.md).  

## Specify when and how users receive notifications  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Approval User Setup**, and then choose the related link.  
2.  Select the line for the user that you want to set up notification preferences for, and then choose the **Notification Setup** action.  
3.  On the **Notification Setup** page, fill the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Notification Type**|Specify what type of event the notification is about.<br /><br /> Select one of the following options:<br /><br /> -   **New Record** specifies that the notification is about a new record, such as a document, that the user must act on.<br />-   **Approval** specifies that the notification is about one or more approval requests.<br />-   **Overdue** specifies that the notification is to remind users that they are late in acting on an event.|  
    |**Notification Method**|Specify if the notification is an email or an internal note.|

    You can define the layout of email notifications by customizing Report 1320, Notification Email. For more information, see [Create and Modify Custom Report Layouts](ui-how-create-custom-report-layout.md).

    You have now specified how the user receives notifications. Proceed to specify when the user receives notifications.  

4.  Choose the **Notification Schedule** action.  
5.  On the **Notification Schedule** page, fill the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Recurrence**|Specify the recurrence pattern in which the user receives notifications.|  
    |**Time**|Specify what time of the day the user receives notifications when the value in the **Recurrence** field is different from **Instantly**.|  
    |**Daily Frequency**|Specify on which type of days the user receives notifications when the value in the **Recurrence** field is **Daily**.<br /><br /> Select **Weekday** to receive notifications every work day of the week. Select **Daily** to receive notifications every day of the week, including weekends.|  
    |**Monday** through **Sunday**|Specify on which days the user receives notifications when the value in the **Recurrence** field is **Weekly**.|  
    |**Date of Month**|Specify if the user receives notifications on the first, last, or a specific date of the month.|  
    |**Monthly Notification Date**|Specify the date of the month on which the user receives notifications when the value in the **Date of Month** field is **Custom**.|  

## Change when and how you receive notifications  
1.  On one of the notifications that you have received, either as email or note, choose the **Change Notification Settings** button.  
2.  On the **Notification Setup** page, change your notification preferences as described in the previous procedure.  

## See Also  
 [Set Up Approval Users](across-how-to-set-up-approval-users.md)   
 [Create and Modify Custom Report Layouts](ui-how-create-custom-report-layout.md)   
 [Setting Up Workflow Notifications](across-setting-up-workflow-notifications.md)   
 [Setting Up Workflows](across-set-up-workflows.md)   
 [Using Workflows](across-use-workflows.md)
