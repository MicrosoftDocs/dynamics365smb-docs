---
title: "How to: Create Delivery Reminders Manually"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "reminders, creating"
  - "delivery reminders, creating"
ms.assetid: df6254f1-6a38-425b-83a4-df5ae41a65ff
caps.latest.revision: 32
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "de-at"
  - "de-ch"
  - "de-de"
  - "fr-ch"
---
# How to: Create Delivery Reminders Manually
In FIX INCLUDE HERE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] -->, you can create delivery reminders when a purchase has not been delivered as expected. You can create a single delivery reminder manually, or you can generate delivery reminders for all overdue deliveries. For more information, see [How to: Generate Delivery Reminders](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/how-to-generate-delivery-reminders.md).  
  
> [!NOTE]  
>  To create delivery reminders, you must set up the delivery reminder properties. For more information, see [How to: Set Up Delivery Reminders](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/how-to-set-up-delivery-reminders.md).  
  
### To create a delivery reminder manually  
  
1.  In the **Search** box, enter **Delivery Reminder**, and then choose the related link.  
  
2.  In the **Delivery Reminder** window, on the **Home** tab, choose **New**.  
  
3.  In the **Delivery Reminder** window, on the **General** FastTab, fill in the fields as described in the following table.  
  
    |FIX INCLUDE HERE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)] -->|FIX INCLUDE HERE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)] -->|  
    |---------------------------------|---------------------------------------|  
    |**No.**|The unique identification number for the delivery reminder.|  
    |**Vendor No.**|The number of the vendor for whom you want to post the delivery reminder.<br /><br /> When you select the vendor number, the **Name**, **Address**, **Post Code\/City**, and **Contact** fields are filled in automatically.|  
    |**Posting Date**|The posting date for the delivery reminder. This date is copied to all of the delivery reminder ledger entries.|  
    |**Document Date**|The document date for the delivery reminder. This date is also used to calculate the due date for the delivery reminder. You can modify the posting date if required.|  
    |**Reminder Level**|The delivery reminder level. This value is based on the number of delivery reminders that have already been sent. For more information, see [How to: Set Up Delivery Reminder Terms, Levels, and Text](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/how-to-set-up-delivery-reminder-terms-levels-and-text.md).|  
    |**Reminder Terms Code**|Specify the delivery reminder terms code that is set up for the vendor.|  
    |**Due Date**|The due date for the delivery reminder.|  
  
4.  On the **Actions** tab, in the **Functions** group, choose **Suggest Reminder Lines**.  
  
     If there are overdue deliveries from the specified vendor, these are added to the deliver reminder.  
  
5.  Choose the **OK** button.  
  
     The delivery reminder is created. You can now issue and print the delivery reminder.  
  
## See Also  
 [Delivery Reminders](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/delivery-reminders.md)   
 [How to: Generate Delivery Reminders](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/how-to-generate-delivery-reminders.md)   
 [How to: Set Up Delivery Reminders](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/how-to-set-up-delivery-reminders.md)   
 [How to: Set Up Delivery Reminder Terms, Levels, and Text](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/how-to-set-up-delivery-reminder-terms-levels-and-text.md)   
 [How to: Assign Delivery Reminder Codes to Vendors](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/how-to-assign-delivery-reminder-codes-to-vendors.md)   
 [How to: Issue Delivery Reminders](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/how-to-issue-delivery-reminders.md)   
 [How to: Print Test Reports for Delivery Reminders](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/how-to-print-test-reports-for-delivery-reminders.md)