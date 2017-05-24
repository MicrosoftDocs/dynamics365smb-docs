---
title: "How to: Set Up Delivery Reminder Terms, Levels, and Text"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "reminders, setting up"
  - "reminders, for delivery"
  - "delivery reminders, levels"
  - "delivery reminders, template text"
  - "delivery reminders, terms"
ms.assetid: ba8e22f6-e55d-47fb-990d-f86f2b394d25
caps.latest.revision: 38
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "de-at"
  - "de-ch"
  - "de-de"
  - "fr-ch"
---
# How to: Set Up Delivery Reminder Terms, Levels, and Text
To create delivery reminders, you must set up the following:  
  
-   Delivery reminder terms  
  
-   Delivery reminder levels  
  
-   Delivery reminder text messages  
  
 Each delivery reminder term has two or more delivery reminder levels, and for each delivery reminder level, you can specify text that will be part of the delivery reminder.  
  
 For more information, see [Delivery Reminders](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/delivery-reminders.md).  
  
### To set up delivery reminder terms  
  
1.  In the **Search** box, enter **Delivery Reminder Terms**, and then choose the related link.  
  
2.  On the **Home** tab, choose **New**.  
  
3.  Fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Code**|The code for the delivery reminder term. You can enter a maximum of 10 alphanumeric characters.|  
    |**Description**|The description for the delivery reminder term. You can enter a maximum of 30 alphanumeric characters.|  
    |**Max. No. of Delivery Reminders**|The maximum number of delivery reminders that can be created for an order.<br /><br /> **NOTE:** This is the maximum number across all reminder levels for this reminder term. For example, if you have set up three levels, and you set **Max. No. of Delivery Reminders** to 5, the first reminder is created at level 1, the second at level 2, and the last three at level 3.|  
  
4.  Choose the **OK** button.  
  
### To add delivery reminder levels to a delivery reminder term  
  
1.  In the **\($ N\_5005279 Delivery Reminder Terms $\)** window, select the delivery reminder term for which you want to set up levels, and then, on the **Actions** tab, choose **Levels**.  
  
2.  On the **Home** tab, choose **New**.  
  
3.  Fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**No.**|The delivery reminder level number. This field is filled in automatically.|  
    |**Due Date Calculation**|The formula for the due date calculation for the delivery reminder. You can enter a combination of numbers from 0 to 9999, and date codes \(D for day, WD for weekday, W for week, M for month, Q for quarter, or Y for year\). The date codes denote the calculation for the delivery reminder due date. You can enter a maximum of 20 characters for the due date calculation formula.|  
  
     For more information, see [\($ T\_5005277 Delivery Reminder Level $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/-$-t_5005277-delivery-reminder-level-$-.md).  
  
4.  Choose the **OK** button.  
  
 For each delivery reminder level, you can define text messages that are added to the delivery reminder. You can define beginning text that is added before the description of the overdue purchase order, and ending text that is added after the description of the overdue purchase order.  
  
 The following procedure describes how to set up beginning text messages, but the same steps apply for setting up ending text messages.  
  
### To set up delivery reminder text messages  
  
1.  In the **\($ N\_5005281 Delivery Reminder Levels $\)** window, select a level, and then, on the **Navigate** tab, in the **Level** group, choose **Beginning Text**.  
  
2.  On the **Home** tab, choose **New**.  
  
3.  In the **Description** field, enter the beginning text message for the delivery reminder.  
  
     For more information, see [\($ T\_5005278 Delivery Reminder Text $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/-$-t_5005278-delivery-reminder-text-$-.md).  
  
4.  Choose the **OK** button.  
  
## See Also  
 [Delivery Reminders](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/delivery-reminders.md)   
 [How to: Set Up Delivery Reminders](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/how-to-set-up-delivery-reminders.md)   
 [How to: Assign Delivery Reminder Codes to Vendors](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/how-to-assign-delivery-reminder-codes-to-vendors.md)   
 [How to: Create Delivery Reminders Manually](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/how-to-create-delivery-reminders-manually.md)   
 [How to: Issue Delivery Reminders](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/how-to-issue-delivery-reminders.md)   
 [\($ T\_5005276 Delivery Reminder Term $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/-$-t_5005276-delivery-reminder-term-$-.md)   
 [\($ T\_5005277 Delivery Reminder Level $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/-$-t_5005277-delivery-reminder-level-$-.md)   
 [\($ T\_5005278 Delivery Reminder Text $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/-$-t_5005278-delivery-reminder-text-$-.md)