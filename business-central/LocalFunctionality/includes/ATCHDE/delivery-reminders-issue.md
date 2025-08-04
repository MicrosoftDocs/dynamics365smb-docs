---
author: brentholtorf
ms.topic: include
ms.date: 03/05/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

After you create delivery reminders, you must issue and print them so that you can send reminders to vendors. Before you issue the delivery reminders, you can print a test report.

When you issue the delivery reminders, delivery reminder ledger entries are created. You can view the created ledger entries on the **Deliv. Reminder Ledger Entries** page.  

## Issue delivery reminders  

1. Choose the ![Tell Me feature](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Delivery Reminder**, and then choose the related link.  
1. On the **Delivery Reminder** page, select the delivery reminder that you want to issue, and then choose the **Edit** action.  
1. Choose the **Issue** action.  
1. On the **Issue Delivery Reminder** page, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Print**|Select to print the delivery reminders when they're issued.|  
    |**Replace Posting Date**|Select to replace the existing posting date for the delivery reminder.|  
    |**Posting Date**|The posting date for the delivery reminder.<br><br/> This posting date is used for all delivery reminders if you select the **Replace Posting Date** checkbox. If the **Replace Posting Date** checkbox is cleared, this date is used for only those delivery reminders for which a posting date isn't available.|  

1. Optionally, on the **Delivery Reminder Header** FastTab, select the appropriate filters.  

    > [!NOTE]  
    > You can remove filters and issue all delivery reminders at the same time.  

1. Choose the **OK** button.  

You can view the issued reminders on the **Issued Delivery Reminder** page. Optionally, you can now print a delivery reminder.  

## View delivery reminder ledger entries  

1. Choose the ![Tell Me feature](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders**, and then choose the related link.  
1. Select the purchase order for which you want to view the reminder status, and then choose the **Edit** action.  
1. Choose the **Deliv. Reminder Ledger Entries** action.  

On the **Deliv. Reminder Ledger Entries** page, you can view the delivery reminder ledger entries for the selected purchase order.  
