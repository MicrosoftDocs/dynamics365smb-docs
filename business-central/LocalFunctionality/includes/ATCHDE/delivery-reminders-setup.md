---
author: brentholtorf
ms.topic: include
ms.date: 03/05/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

In [!INCLUDE[prod_short](../../../includes/prod_short.md)], you can use purchase delivery reminders to remind vendors about overdue deliveries. To create delivery reminders for vendors, you must set up base data for delivery reminder creation and number series for the delivery reminders on the **Purchases & Payables Setup** page.

## Set up delivery reminders  

1. Choose the ![Tell Me feature](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchases & Payables Setup**, and then choose the related link.  
1. In the **Default Del. Rem. Date Field** field, specify one of the options described in the following table.  

    |Option|Description|  
    |----------------------------------|---------------------------------------|  
    |**Requested Receipt Date**|Specifies the date value in the **Requested Receipt Date** field on the purchase order as the default date for creating delivery reminders.|  
    |**Promised Receipt Date**|Specifies the date value in the **Promised Receipt Date** field on the purchase order line as the default date for creating delivery reminders.|  
    |**Expected Receipt Date**|Specifies the date value in the **Expected Receipt Date** field on the purchase order line as the default date for creating delivery reminders.|  

1. Fill in additional fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Delivery Reminder Nos.**|The number series code for delivery reminders.|  
    |**Issued Delivery Reminder Nos.**|The number series code for issued delivery reminders.|  

1. Choose the **OK** button.  
