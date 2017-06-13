---
title: "How to: Set Up Delivery Reminders"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "reminders, setting up"
  - "delivery reminders, setting up"
  - "purchase documents, delivery reminders"
ms.assetid: 2a27f809-12e2-43f5-ae28-64c4aeaa80b3
caps.latest.revision: 34
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "de-at"
  - "de-ch"
  - "de-de"
  - "fr-ch"
---
# How to: Set Up Delivery Reminders
In [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)], you can use purchase delivery reminders to remind vendors about overdue deliveries. To create delivery reminders for vendors, you must set up base data for delivery reminder creation and number series for the delivery reminders in the **Purchases & Payables Setup** window.  
  
### To set up delivery reminders  
  
1.  In the **Search** box, enter **Purchases & Payables Setup**, and then choose the related link.  
  
2.  On the **General** FastTab, in the **Default Del. Rem. Date Field** field, specify one of the following options as described in the following table.  
  
    |[!INCLUDE[bp_tableoption](../../ApplicationDesign/includes/bp_tableoption_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |----------------------------------|---------------------------------------|  
    |**Requested Receipt Date**|To specify that the date value in the **Requested Receipt Date** field on the purchase order line will be used as the default date for creating delivery reminders.|  
    |**Promised Receipt Date**|To specify that the date value in the **Promised Receipt Date** field on the purchase order line will be used as the default date for creating delivery reminders.|  
    |**Expected Receipt Date**|To specify that the date value in the **Expected Receipt Date** field on the purchase order line will be used as the default date for creating delivery reminders.|  
  
3.  On the **Numbering** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Delivery Reminder Nos.**|The number series code for delivery reminders.|  
    |**Issued Delivery Reminder Nos.**|The number series code for issued delivery reminders.|  
  
4.  Choose the **OK** button.  
  
## See Also  
 [Purchases & Payables Setup](../../Purchasing/-$-n_460-purchases-payables-setup-$-.md)   
 [Delivery Reminders](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/delivery-reminders.md)   
 [How to: Set Up Delivery Reminder Terms, Levels, and Text](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/how-to-set-up-delivery-reminder-terms-levels-and-text.md)   
 [How to: Assign Delivery Reminder Codes to Vendors](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/how-to-assign-delivery-reminder-codes-to-vendors.md)   
 [How to: Create Delivery Reminders Manually](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/how-to-create-delivery-reminders-manually.md)