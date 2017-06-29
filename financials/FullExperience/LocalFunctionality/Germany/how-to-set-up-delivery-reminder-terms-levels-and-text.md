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
# How to: Set Up Delivery Reminder Terms, Levels, and Text
To create delivery reminders, you must set up the following:  
  
-   Delivery reminder terms  
  
-   Delivery reminder levels  
  
-   Delivery reminder text messages  
  
 Each delivery reminder term has two or more delivery reminder levels, and for each delivery reminder level, you can specify text that will be part of the delivery reminder.  
  
 For more information, see [Delivery Reminders](../delivery-reminders.md).  
  
### To set up delivery reminder terms  
  
1.  In the **Search** box, enter **Delivery Reminder Terms**, and then choose the related link.  
  
2.  On the **Home** tab, choose **New**.  
  
3.  Fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Code**|The code for the delivery reminder term. You can enter a maximum of 10 alphanumeric characters.|  
    |**Description**|The description for the delivery reminder term. You can enter a maximum of 30 alphanumeric characters.|  
    |**Max. No. of Delivery Reminders**|The maximum number of delivery reminders that can be created for an order.<br /><br /> **NOTE:** This is the maximum number across all reminder levels for this reminder term. For example, if you have set up three levels, and you set **Max. No. of Delivery Reminders** to 5, the first reminder is created at level 1, the second at level 2, and the last three at level 3.|  
  
4.  Choose the **OK** button.  
  
### To add delivery reminder levels to a delivery reminder term  
  
1.  In the **Delivery Reminder Terms** window, select the delivery reminder term for which you want to set up levels, and then, on the **Actions** tab, choose **Levels**.  
  
2.  On the **Home** tab, choose **New**.  
  
3.  Fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**No.**|The delivery reminder level number. This field is filled in automatically.|  
    |**Due Date Calculation**|The formula for the due date calculation for the delivery reminder. You can enter a combination of numbers from 0 to 9999, and date codes \(D for day, WD for weekday, W for week, M for month, Q for quarter, or Y for year\). The date codes denote the calculation for the delivery reminder due date. You can enter a maximum of 20 characters for the due date calculation formula.|  
  
     For more information, see Delivery Reminder Level.  
  
4.  Choose the **OK** button.  
  
 For each delivery reminder level, you can define text messages that are added to the delivery reminder. You can define beginning text that is added before the description of the overdue purchase order, and ending text that is added after the description of the overdue purchase order.  
  
 The following procedure describes how to set up beginning text messages, but the same steps apply for setting up ending text messages.  
  
### To set up delivery reminder text messages  
  
1.  In the **Delivery Reminder Levels** window, select a level, and then, on the **Navigate** tab, in the **Level** group, choose **Beginning Text**.  
  
2.  On the **Home** tab, choose **New**.  
  
3.  In the **Description** field, enter the beginning text message for the delivery reminder.  
  
     For more information, see Delivery Reminder Text.  
  
4.  Choose the **OK** button.  
  
## See Also  
 [Delivery Reminders](../delivery-reminders.md)   
 [How to: Set Up Delivery Reminders](../how-to-set-up-delivery-reminders.md)   
 [How to: Assign Delivery Reminder Codes to Vendors](../how-to-assign-delivery-reminder-codes-to-vendors.md)   
 [How to: Create Delivery Reminders Manually](../how-to-create-delivery-reminders-manually.md)   
 [How to: Issue Delivery Reminders](../how-to-issue-delivery-reminders.md)   
 Delivery Reminder Term   
 Delivery Reminder Level   
 Delivery Reminder Text