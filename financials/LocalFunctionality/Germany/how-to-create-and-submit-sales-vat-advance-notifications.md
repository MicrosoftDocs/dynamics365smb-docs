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
# How to: Create and Submit Sales VAT Advance Notifications
In ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/navnow_md.md)]-->, you can submit the sales VAT advance notification file electronically to the ELSTER portal. You can transmit the sales VAT advance notification file to the tax authorities after you have verified the calculated tax amount and the base amount.  
  
### To create an XML document for sales VAT advance notification  
  
1.  In the **Search** box, enter **Sales Vat Advanced Notification List**, and then choose the related link.  
  
2.  In the **Sales Vat Advanced Notification List** window, on the **Actions** tab, choose **New**.  
  
3.  In the **Sales VAT Adv. Notif. Card** window, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---
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

---------------------------------|---------------------------------------|  
    |**Contact for Tax Office**|The contact person for the tax office in your organization.|  
    |**Contact Phone No.**|The contact person's telephone number.|  
    |**Contact E-Mail**|The contact person's email address.|  
  
5.  On the **Actions** tab, in the **Functions** group, choose **Create XML-File**.  
  
6.  In the **Create Sales VAT Adv. Notif.** batch job, on the **Options** FastTab, in the **XML-File** field, select **Create** or **Create and Show**.  
  
7.  Choose the **OK** button.  
  
### To submit an XML document for sales VAT advance notification  
  
1.  In the **Sales VAT Advance Notification List** window, select the document that you want to submit to ELSTER.  
  
2.  On the **Actions** tab, in the **Functions** group, choose **Transmit XML-File**.  
  
     The XML file is transmitted to ELSTER.  
  
## See Also  
 [Electronic Submission of Sales VAT Advance Notifications to ELSTER](../electronic-submission-of-sales-vat-advance-notifications-to-elster.md)   
 [How to: Set Up Sales VAT Advance Notifications for ELSTER](../how-to-set-up-sales-vat-advance-notifications-for-elster.md)   
 VAT Statement   
 Sales VAT Adv. Notif. Card   
 Sales VAT Advance Notification   
 Create XML-File VAT Adv. Notif.