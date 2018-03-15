---
    title: How to Create and Submit Sales VAT Advance Notifications
    description: In Business Central, you can submit the sales VAT advance notification file electronically to the ELSTER portal. You can transmit the sales VAT advance notification file to the tax authorities after you have verified the calculated tax amount and the base amount.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# Create and Submit Sales VAT Advance Notifications
In [!INCLUDE[d365fin](../../includes/d365fin_md.md)], you can submit the sales VAT advance notification file electronically to the ELSTER portal. You can transmit the sales VAT advance notification file to the tax authorities after you have verified the calculated tax amount and the base amount.  

## To create an XML document for sales VAT advance notification  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Sales Vat Advanced Notification List**, and then choose the related link.  
2.  In the **Sales Vat Advanced Notification List** window, choose the **New** action.  
3.  In the **Sales VAT Adv. Notif. Card** window, fill in the fields as described in the following table.  

    |Field|Description|  
    |------------------------------------|---------------------------------------|  
    |**Contact for Tax Office**|The contact person for the tax office in your organization.|  
    |**Contact Phone No.**|The contact person's telephone number.|  
    |**Contact E-Mail**|The contact person's email address.|  

5.  Choose the **Create XML-File** action.  
6.  In the **Create Sales VAT Adv. Notif.** batch job, on the **Options** FastTab, in the **XML-File** field, select the **Create** or the **Create and Show** option.  
7.  Choose the **OK** button.  

## To submit an XML document for sales VAT advance notification  

1.  In the **Sales VAT Advance Notification List** window, select the document that you want to submit to ELSTER.  
2.  Choose the **Transmit XML-File** action.  

The XML file is transmitted to ELSTER.  

## See Also  
 [Electronic Submission of Sales VAT Advance Notifications to ELSTER](electronic-submission-of-sales-vat-advance-notifications-to-elster.md)   
 [Set Up Sales VAT Advance Notifications for ELSTER](how-to-set-up-sales-vat-advance-notifications-for-elster.md)
