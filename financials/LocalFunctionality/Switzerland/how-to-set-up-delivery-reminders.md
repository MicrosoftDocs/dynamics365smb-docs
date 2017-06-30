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
# How to: Set Up Delivery Reminders
In [!INCLUDE[d365fin](../../includes/d365fin_md.md)], you can use purchase delivery reminders to remind vendors about overdue deliveries. To create delivery reminders for vendors, you must set up base data for delivery reminder creation and number series for the delivery reminders in the **Purchases & Payables Setup** window.  
  
### To set up delivery reminders  
  
1.  In the **Search** box, enter **\($ N\_460 Purchases & Payables Setup $\)**, and then choose the related link.  
  
2.  On the **General** FastTab, in the **Default Del. Rem. Date Field** field, specify one of the following options as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tableoption](../../includes/bp_tabledescription_md.md)]-->|  
    |----------------------------------|---------------------------------------|  
    |**Requested Receipt Date**|To specify that the date value in the **Requested Receipt Date** field on the purchase order line will be used as the default date for creating delivery reminders.|  
    |**Promised Receipt Date**|To specify that the date value in the **Promised Receipt Date** field on the purchase order line will be used as the default date for creating delivery reminders.|  
    |**Expected Receipt Date**|To specify that the date value in the **Expected Receipt Date** field on the purchase order line will be used as the default date for creating delivery reminders.|  
  
3.  On the **Numbering** FastTab, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Delivery Reminder Nos.**|The number series code for delivery reminders.|  
    |**Issued Delivery Reminder Nos.**|The number series code for issued delivery reminders.|  
  
4.  Choose the **OK** button.  
  
## See Also  
 [\($ N\_460 Purchases & Payables Setup $\)](../-$-n_460-purchases-payables-setup-$-.md)   
 [Delivery Reminders](../delivery-reminders.md)   
 [How to: Set Up Delivery Reminder Terms, Levels, and Text](../how-to-set-up-delivery-reminder-terms-levels-and-text.md)   
 [How to: Assign Delivery Reminder Codes to Vendors](../how-to-assign-delivery-reminder-codes-to-vendors.md)   
 [How to: Create Delivery Reminders Manually](../how-to-create-delivery-reminders-manually.md)