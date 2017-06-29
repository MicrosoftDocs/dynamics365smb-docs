---
title: "How to: Specify When and How to Receive Notifications"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: d7e02210-d8c1-4510-b747-205a7f9be867
caps.latest.revision: 4
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
# How to: Specify When and How to Receive Notifications
When you set up users in approval workflows, you must specify in the **\($ N\_1512 Notification Setup $\)** and **\($ N\_1513 Notification Schedule $\)** windows how and when each user receives notifications about approval workflow steps. Individual users can also change their notification setup by choosing the **Change Notification Settings** button on any notification.  
  
 Before you can set up an approval user’s notification preferences, you must set the user up as an approval user. For more information, [How to: Set Up Approval Users](../../BusinessFunctionality/Workflow/how-to-set-up-approval-users.md).  
  
 You define the layout and content of notifications by setting up notification templates. For more information, see [How to: Manage Notification Templates](../../BusinessFunctionality/Workflow/how-to-manage-notification-templates.md).  
  
 Many approval workflow steps are about notifying users that an event has occurred that they must act on. For example, on one workflow step, the event can be that User 1 requests approval of a new record. The related response is that a notification is sent to User 2, the approver. On the next workflow step, the event can be that User 2 approves the record. The related response is that a notification is sent to User 3 to start a process with the approved record. For workflow steps that are about approval, each notification is tied to an approval entry. For more information, see [Workflow](../../BusinessFunctionality/Workflow/workflow.md).  
  
### Specify when and how users receive notifications  
  
1.  In the **Search** box, enter **Approval User Setup**, and then choose the related link.  
  
2.  Select the line for the user that you want to set up notification preferences for, and then, on the **Home** tab, in the **Process** group, choose **Notification Setup**.  
  
3.  In the **\($ N\_1512 Notification Setup $\)** window, fill the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_1512\_2 Notification Type $\)**|Specify what type of event the notification is about.<br /><br /> Select one of the following options:<br /><br /> -   **New Record** specifies that the notification is about a new record, such as a document, that the user must act on.<br />-   **Approval** specifies that the notification is about one or more approval requests.<br />-   **Overdue** specifies that the notification is to remind users that they are late in acting on an event.|  
    |**\($ T\_1512\_3 Notification Template Code $\)**|Specify the code of the notification template that is used to create notifications for the user.|  
    |**\($ T\_1512\_4 Unaggregated Notifications $\)**|Specify if the user receives one notification for each event or aggregated notifications.<br /><br /> If the **\($ T\_1512\_4 Unaggregated Notifications $\)** check box is not selected, then the user receives notifications that aggregate information about events that occur within the same recurrence pattern in the notification schedule.|  
  
     You have now specified how the user receives notifications. Proceed to specify when the user receives notifications.  
  
4.  On the **Home** tab, in the **Process** group, choose **Notification Schedule**.  
  
5.  In the **\($ N\_1513 Notification Schedule $\)** window, fill the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_1513\_3 Recurrence $\)**|Specify the recurrence pattern in which the user receives notifications.|  
    |**\($ T\_1513\_4 Time $\)**|Specify what time of the day the user receives notifications when the value in the **\($ T\_1513\_3 Recurrence $\)** field is different from **Instantly**.|  
    |**\($ T\_1513\_5 Daily Frequency $\)**|Specify on which type of days the user receives notifications when the value in the **\($ T\_1513\_3 Recurrence $\)** field is **Daily**.<br /><br /> Select **Weekday** to receive notifications every work day of the week. Select **Daily** to receive notifications every day of the week, including weekends.|  
    |**\($ T\_1513\_6 Monday $\)** through **\($ T\_1513\_12 Sunday $\)**|Specify on which days the user receives notifications when the value in the **\($ T\_1513\_3 Recurrence $\)** field is **Weekly**.|  
    |**\($ T\_1513\_13 Date of Month $\)**|Specify if the user receives notifications on the first, last, or a specific date of the month.|  
    |**\($ T\_1513\_14 Monthly Notification Date $\)**|Specify the date of the month on which the user receives notifications when the value in the **\($ T\_1513\_13 Date of Month $\)** field is **Custom**.|  
  
### Change when and how you receive notifications  
  
1.  On one of the notifications that you have received, either as email or note, choose the **Change Notification Settings** button.  
  
2.  In the **\($ N\_1512 Notification Setup $\)** window, change your notification preferences as described in the previous procedure.  
  
## See Also  
 [\($ N\_1512 Notification Setup $\)](../Topic/\($%20N_1512%20Notification%20Setup%20$\).md)   
 [\($ N\_1513 Notification Schedule $\)](../Topic/\($%20N_1513%20Notification%20Schedule%20$\).md)   
 [\($ N\_1510 Notification Templates $\)](../Topic/\($%20N_1510%20Notification%20Templates%20$\).md)   
 [How to: Set Up Approval Users](../../BusinessFunctionality/Workflow/how-to-set-up-approval-users.md)   
 [How to: Manage Notification Templates](../../BusinessFunctionality/Workflow/how-to-manage-notification-templates.md)   
 [Setting Up Workflow Notifications](../../BusinessFunctionality/Workflow/setting-up-workflow-notifications.md)   
 [\($ N\_1501 Workflow $\)](../Topic/\($%20N_1501%20Workflow%20$\).md)   
 [Set Up Workflows](../../BusinessFunctionality/Workflow/set-up-workflows.md)   
 [Use Workflows](../../BusinessFunctionality/Workflow/use-workflows.md)