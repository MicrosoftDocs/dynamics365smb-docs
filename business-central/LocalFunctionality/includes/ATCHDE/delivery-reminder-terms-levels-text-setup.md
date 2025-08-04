---
author: brentholtorf
ms.topic: include
ms.date: 03/05/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

To create delivery reminders, you must set up the following prerequisites:

- Delivery reminder terms  
- Delivery reminder levels  
- Delivery reminder text messages  

Each delivery reminder term has two or more delivery reminder levels, and for each delivery reminder level, you can specify text that is part of the delivery reminder.  

## Set up delivery reminder terms  

1. Choose the ![Tell Me feature](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Delivery Reminder Terms**, and then choose the related link.  
1. Choose the **New** action.  
1. Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Code**|The code for the delivery reminder term. You can enter a maximum of 10 alphanumeric characters.|  
    |**Description**|The description for the delivery reminder term. You can enter a maximum of 30 alphanumeric characters.|  
    |**Max. No. of Delivery Reminders**|The maximum number of delivery reminders that can be created for an order.<br><br/> **NOTE:** This is the maximum number across all reminder levels for this reminder term. For example, if you set up three levels, and you set **Max. No. of Delivery Reminders** to 5, the first reminder is created at level 1, the second at level 2, and the last three at level 3.|  

1. Choose the **OK** button.  

## Add delivery reminder levels to a delivery reminder term  

1. On the **Delivery Reminder Terms** page, select the delivery reminder term for which you want to set up levels, and then choose the **Levels** action.  
1. Choose the **New** action.  
1. Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**No.**|The delivery reminder level number. This field is filled in automatically.|  
    |**Due Date Calculation**|The formula for the due date calculation for the delivery reminder. You can enter a combination of numbers from 0 to 9,999, and date codes (D for day, WD for weekday, W for week, M for month, Q for quarter, or Y for year). The date codes denote the calculation for the delivery reminder due date. You can enter a maximum of 20 characters for the due date calculation formula.|  

1. Choose the **OK** button.  

For each delivery reminder level, you can define text messages that are added to the delivery reminder. You can define beginning text that is added before the description of the overdue purchase order, and ending text that is added after the description of the overdue purchase order.  

The following procedure describes how to set up beginning text messages, but the same steps apply for setting up ending text messages.  

## Set up delivery reminder text messages  

1. On the **Delivery Reminder Levels** page, select a level, and then choose the **Beginning Text** action.  
1. Choose the **New** action.  
1. In the **Description** field, enter the beginning text message for the delivery reminder.  
1. Choose the **OK** button.  
