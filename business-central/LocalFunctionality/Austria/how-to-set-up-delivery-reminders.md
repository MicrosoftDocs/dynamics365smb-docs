---
    title: How to Set Up Delivery Reminders
    description: In Business Central, you can use purchase delivery reminders to remind vendors about overdue deliveries.
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
# Set Up Delivery Reminders
In [!INCLUDE[d365fin](../../includes/d365fin_md.md)], you can use purchase delivery reminders to remind vendors about overdue deliveries. To create delivery reminders for vendors, you must set up base data for delivery reminder creation and number series for the delivery reminders on the **Purchases & Payables Setup** page.  

## To set up delivery reminders  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Purchases & Payables Setup**, and then choose the related link.  
2.  In the **Default Del. Rem. Date Field** field, specify one of the options described in the following table.  

    |Option|Description|  
    |----------------------------------|---------------------------------------|  
    |**Requested Receipt Date**|Specifies that the date value in the **Requested Receipt Date** field on the purchase order line will be used as the default date for creating delivery reminders.|  
    |**Promised Receipt Date**|Specifies that the date value in the **Promised Receipt Date** field on the purchase order line will be used as the default date for creating delivery reminders.|  
    |**Expected Receipt Date**|Specifies that the date value in the **Expected Receipt Date** field on the purchase order line will be used as the default date for creating delivery reminders.|  

3.   Fill in additional fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Delivery Reminder Nos.**|The number series code for delivery reminders.|  
    |**Issued Delivery Reminder Nos.**|The number series code for issued delivery reminders.|  

4.  Choose the **OK** button.  

## See Also  
 [Delivery Reminders](delivery-reminders.md)   
 [Set Up Delivery Reminder Terms, Levels, and Text](how-to-set-up-delivery-reminder-terms-levels-and-text.md)   
 [Assign Delivery Reminder Codes to Vendors](how-to-assign-delivery-reminder-codes-to-vendors.md)   
 [Create Delivery Reminders Manually](how-to-create-delivery-reminders-manually.md)
