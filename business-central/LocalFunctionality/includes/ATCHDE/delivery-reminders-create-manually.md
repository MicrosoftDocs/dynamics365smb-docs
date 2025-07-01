---
author: brentholtorf
ms.topic: include
ms.date: 03/05/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

In [!INCLUDE[prod_short](../../../includes/prod_short.md)], you can create delivery reminders when a purchase isn't delivered as expected. You can create a single delivery reminder manually, or you can generate delivery reminders for all overdue deliveries.

> [!NOTE]
> To create delivery reminders, you must set up the delivery reminder terms, levels, and texts.

## Create a delivery reminder manually  

1. Choose the ![Tell Me feature](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Delivery Reminder**, and then choose the related link.  
1. Choose the **New** action.  
1. On the **Delivery Reminder** page, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**No.**|The unique identification number for the delivery reminder.|  
    |**Vendor No.**|The number of the vendor for whom you want to post the delivery reminder.<br><br/> When you select the vendor number, the **Name**, **Address**, **Post Code/City**, and **Contact** fields are filled in automatically.|  
    |**Posting Date**|The posting date for the delivery reminder. This date is copied to all of the delivery reminder ledger entries.|  
    |**Document Date**|The document date for the delivery reminder. This date is also used to calculate the due date for the delivery reminder. You can modify the posting date if necessary.|  
    |**Reminder Level**|The delivery reminder level. This value is based on the number of delivery reminders sent.|  
    |**Reminder Terms Code**|Specify the delivery reminder terms code that is set up for the vendor.|  
    |**Due Date**|The due date for the delivery reminder.|  

1. Choose the **Suggest Reminder Lines** action.  

   If there are overdue deliveries from the specified vendor, these are added to the delivery reminder.  

1. Choose the **OK** button.  

   The delivery reminder is created. You can now issue and print the delivery reminder.  
