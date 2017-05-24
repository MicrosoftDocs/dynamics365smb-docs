---
title: "How to: Create and Submit Sales VAT Advance Notifications"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "sales VAT advance notifications, sending"
  - "ELSTER, sending advance notifications"
  - "VAT, sending advance notifications"
ms.assetid: d79c9984-730d-4fe2-ba1b-7e897e5c9289
caps.latest.revision: 29
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "de-de"
---
# How to: Create and Submit Sales VAT Advance Notifications
In [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)], you can submit the sales VAT advance notification file electronically to the ELSTER portal. You can transmit the sales VAT advance notification file to the tax authorities after you have verified the calculated tax amount and the base amount.  
  
### To create an XML document for sales VAT advance notification  
  
1.  In the **Search** box, enter **\($ N\_11017 Sales Vat Advanced Notification List $\)**, and then choose the related link.  
  
2.  In the **\($ N\_11017 Sales Vat Advanced Notification List $\)** window, on the **Actions** tab, choose **New**.  
  
3.  In the **\($ N\_11016 Sales VAT Adv. Notif. Card $\)** window, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_11011\_2 Description $\)**|Specify a description of the sales VAT advance notification.|  
    |**\($ T\_11011\_9 XSL\-Filename $\)**|Specify the path to the style sheet, such as C:\/Program Files\/ElsterFormular\/Stylesheet\/UStVAT.xsl.|  
    |**\($ T\_11011\_5 Starting Date $\)**|Specify the start date for the sales VAT advance notification period.|  
    |**\($ T\_11011\_6 Period $\)**|Specify if this is the monthly or quarterly sales VAT advance notification.|  
    |**\($ T\_11011\_24 Additional Information $\)**|Optionally, specify additional information that you want to submit to the tax authorities.|  
    |**\($ T\_11011\_30 Documents Submitted Separately $\)**|Select to submit additional documents to the tax authorities together with the VAT statement.|  
    |**\($ T\_11011\_13 Incl. VAT Entries \(Closing\) $\)**|Specify the VAT entry type to calculate the tax amounts and the base amounts.|  
    |**\($ T\_11011\_14 Incl. VAT Entries \(Period\) $\)**|Specify the VAT entry period type to calculate the tax amounts and the base amounts.|  
    |**\($ T\_11011\_15 Corrected Notification $\)**|Select to indicate that this is a corrected notification.|  
    |**\($ T\_11011\_16 Offset Amount of Refund $\)**|Select to include a refund with the payment charge on the sales VAT advance notification.|  
    |**\($ T\_11011\_17 Cancel Order for Direct Debit $\)**|Select to cancel the standing order for direct debit for the sales VAT advance notification.|  
  
    > [!NOTE]  
    >  The **\($ T\_11011\_7 XML\-File Creation Date $\)** field and the **\($ T\_11011\_12 Statement Name $\)** field are populated automatically when the XML file is created. The **\($ T\_11011\_18 Transmission successful $\)** field is also automatically populated. These fields cannot be modified.  
  
4.  On the **Communication** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_11011\_25 Contact for Tax Office $\)**|The contact person for the tax office in your organization.|  
    |**\($ T\_11011\_26 Contact Phone No. $\)**|The contact person's telephone number.|  
    |**\($ T\_11011\_27 Contact E\-Mail $\)**|The contact person's email address.|  
  
5.  On the **Actions** tab, in the **Functions** group, choose **Create XML\-File**.  
  
6.  In the **\($ B\_11016 Create Sales VAT Adv. Notif. $\)** batch job, on the **Options** FastTab, in the **XML\-File** field, select **Create** or **Create and Show**.  
  
7.  Choose the **OK** button.  
  
### To submit an XML document for sales VAT advance notification  
  
1.  In the **\($ N\_11017 Sales VAT Advance Notification List $\)** window, select the document that you want to submit to ELSTER.  
  
2.  On the **Actions** tab, in the **Functions** group, choose **Transmit XML\-File**.  
  
     The XML file is transmitted to ELSTER.  
  
## See Also  
 [Electronic Submission of Sales VAT Advance Notifications to ELSTER](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/electronic-submission-of-sales-vat-advance-notifications-to-elster.md)   
 [How to: Set Up Sales VAT Advance Notifications for ELSTER](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/how-to-set-up-sales-vat-advance-notifications-for-elster.md)   
 [\($ N\_317 VAT Statement $\)](assetId:///4f9b4cd2-b932-4191-8034-91d9d24b83c6)   
 [\($ N\_11016 Sales VAT Adv. Notif. Card $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/-$-n_11016-sales-vat-adv.-notif.-card-$-.md)   
 [\($ T\_11011 Sales VAT Advance Notification $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/-$-t_11011-sales-vat-advance-notification-$-.md)   
 [\($ B\_11016 Create XML\-File VAT Adv. Notif. $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/-$-b_11016-create-xml-file-vat-adv.-notif.-$-.md)