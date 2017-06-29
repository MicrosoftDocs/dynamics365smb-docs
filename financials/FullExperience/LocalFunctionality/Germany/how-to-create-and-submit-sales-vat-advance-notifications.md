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
In FIX INCLUDE HERE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] -->, you can submit the sales VAT advance notification file electronically to the ELSTER portal. You can transmit the sales VAT advance notification file to the tax authorities after you have verified the calculated tax amount and the base amount.  
  
### To create an XML document for sales VAT advance notification  
  
1.  In the **Search** box, enter **Sales Vat Advanced Notification List**, and then choose the related link.  
  
2.  In the **Sales Vat Advanced Notification List** window, on the **Actions** tab, choose **New**.  
  
3.  In the **Sales VAT Adv. Notif. Card** window, fill in the fields as described in the following table.  
  
    |FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)] --> -->|FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)] --> -->|  
    |---------------------------------|---------------------------------------|  
    |**Description**|Specify a description of the sales VAT advance notification.|  
    |**XSL\-Filename**|Specify the path to the style sheet, such as C:\/Program Files\/ElsterFormular\/Stylesheet\/UStVAT.xsl.|  
    |**Starting Date**|Specify the start date for the sales VAT advance notification period.|  
    |**Period**|Specify if this is the monthly or quarterly sales VAT advance notification.|  
    |**Additional Information**|Optionally, specify additional information that you want to submit to the tax authorities.|  
    |**Documents Submitted Separately**|Select to submit additional documents to the tax authorities together with the VAT statement.|  
    |**Incl. VAT Entries \(Closing\)**|Specify the VAT entry type to calculate the tax amounts and the base amounts.|  
    |**Incl. VAT Entries \(Period\)**|Specify the VAT entry period type to calculate the tax amounts and the base amounts.|  
    |**Corrected Notification**|Select to indicate that this is a corrected notification.|  
    |**Offset Amount of Refund**|Select to include a refund with the payment charge on the sales VAT advance notification.|  
    |**Cancel Order for Direct Debit**|Select to cancel the standing order for direct debit for the sales VAT advance notification.|  
  
    > [!NOTE]  
    >  The **XML\-File Creation Date** field and the **Statement Name** field are populated automatically when the XML file is created. The **Transmission successful** field is also automatically populated. These fields cannot be modified.  
  
4.  On the **Communication** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Contact for Tax Office**|The contact person for the tax office in your organization.|  
    |**Contact Phone No.**|The contact person's telephone number.|  
    |**Contact E\-Mail**|The contact person's email address.|  
  
5.  On the **Actions** tab, in the **Functions** group, choose **Create XML\-File**.  
  
6.  In the **Create Sales VAT Adv. Notif.** batch job, on the **Options** FastTab, in the **XML\-File** field, select **Create** or **Create and Show**.  
  
7.  Choose the **OK** button.  
  
### To submit an XML document for sales VAT advance notification  
  
1.  In the **Sales VAT Advance Notification List** window, select the document that you want to submit to ELSTER.  
  
2.  On the **Actions** tab, in the **Functions** group, choose **Transmit XML\-File**.  
  
     The XML file is transmitted to ELSTER.  
  
## See Also  
 [Electronic Submission of Sales VAT Advance Notifications to ELSTER](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/electronic-submission-of-sales-vat-advance-notifications-to-elster.md)   
 [How to: Set Up Sales VAT Advance Notifications for ELSTER](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/how-to-set-up-sales-vat-advance-notifications-for-elster.md)   
 VAT Statement   
 Sales VAT Adv. Notif. Card   
 Sales VAT Advance Notification   
 Create XML\-File VAT Adv. Notif.