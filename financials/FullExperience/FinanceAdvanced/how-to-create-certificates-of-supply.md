---
title: "How to: Create Certificates of Supply"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "certificates of supply, creating"
ms.assetid: bb5516f4-e0a8-4ada-b1fd-e61362fcf261
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-nz"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# How to: Create Certificates of Supply
When you sell goods to a customer in another EU country\/region, you can print a certificate of supply. If the shipment uses a combination of VAT business posting group and VAT product posting group that have been set up to require a certificate of supply in the **VAT Posting Setup** window, the certificate will be automatically set up for you in the **Certificates of Supply** window, with its status set to **Required**.  
  
 Alternatively, you can manually update the status of a certificate of supply in the **Certificates of Supply** window from **Not Applicable** to **Required**. You can also manually change the status from **Required** to **Not Applicable** as needed.  
  
### To enable the creation of a certificate of supply in VAT posting  
  
1.  In the **Search** box, enter **VAT Posting Setup**, and then choose the related link.  
  
2.  In the **VAT Posting Setup** window, choose the relevant line, and then on the **Home** tab, in the **Manage** group, choose **Edit**.  
  
3.  In the **VAT Posting Setup Card** window, select the **Certificate of Supply Required** check box.  
  
     For example, VAT posting setup for trade with customers and vendors in other EU countries\/regions that is VAT\-liable must require a certificate of supply.  
  
### To manually create a certificate of supply  
  
1.  Open a posted sales shipment document.  
  
2.  On the **Home** tab, in the **Shipment** group, choose **Certificate of Supply Details**.  
  
     If the VAT Posting Group setup does not have the **Certificate of Supply Required** check box selected, then a record is created and the field is set to **Not Applicable**. A certificate is created.  
  
3.  Verify that the certificate has been created. In the **Search** box, enter **Certificates of Supply** and choose the related link.  
  
     The **Certificates of Supply** window opens, which provides a list of all available certificates that have a status of **Required**, **Received**, or **Not Received**.  
  
4.  On the **Home** tab, in the **Process** group, choose **Print Certificate of Supply**.  
  
     You can preview or print the document. When you choose **Print Certificate of Supply** and print the document, the **Printed** check box is automatically selected. In addition, if not already specified, the status of the certificate is updated to **Required**.  
  
## See Also  
 [How to: Process Certificates of Supply](../Finance/how-to-process-certificates-of-supply.md)   
 [Certificates of Supply](../Finance/certificates-of-supply.md)