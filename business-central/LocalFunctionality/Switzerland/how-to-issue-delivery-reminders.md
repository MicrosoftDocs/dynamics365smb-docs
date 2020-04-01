---
    title: How to Issue Delivery Reminders
    description: After you have created delivery reminders, you must issue and print them so that you can send reminders to vendors. Before you issue the delivery reminders, you can print a test report.

    services: project-madeira 
    documentationcenter: ''
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
# Issue Delivery Reminders
After you have created delivery reminders, you must issue and print them so that you can send reminders to vendors. Before you issue the delivery reminders, you can print a test report. For more information, see [Print Test Reports for Delivery Reminders](how-to-print-test-reports-for-delivery-reminders.md).  

When you issue the delivery reminders, delivery reminder ledger entries are created. You can view the created ledger entries on the **Deliv. Reminder Ledger Entries** page.  

## To issue delivery reminders  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Delivery Reminder**, and then choose the related link.  
2.  On the **Delivery Reminder** page, select the delivery reminder that you want to issue, and then choose the **Edit** action.  
3.  Choose the **Issue** action.  
4.  On the **Issue Delivery Reminder** page, on the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Print**|Select to print the delivery reminders when they are issued.|  
    |**Replace Posting Date**|Select to replace the existing posting date for the delivery reminder.|  
    |**Posting Date**|The posting date for the delivery reminder.<br /><br /> This posting date is used for all delivery reminders if you have selected the **Replace Posting Date** check box. If the **Replace Posting Date** check box is cleared, this date will be used for only those delivery reminders for which a posting date is not available.|  

5.  Optionally, on the **Delivery Reminder Header** FastTab, select the appropriate filters.  

    > [!NOTE]  
    >  You can remove filters and issue all delivery reminders at the same time.  

6.  Choose the **OK** button.  

You can view the issued reminders on the **Issued Delivery Reminder** page. Optionally, you can now print a delivery reminder.  

## To view delivery reminder ledger entries  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Purchase Orders**, and then choose the related link.  
2.  Select the purchase order for which you want to view the reminder status, and then choose the **Edit** action.  
3.  Choose the **Deliv. Reminder Ledger Entries** action.  

In the Deliv. Reminder Ledger Entries page, you can view the delivery reminder ledger entries for the selected purchase order.  

## See Also  
 [Delivery Reminders](delivery-reminders.md)   
 [Generate Delivery Reminders](how-to-generate-delivery-reminders.md)   
 [Create Delivery Reminders Manually](how-to-create-delivery-reminders-manually.md)
