---
title: "How to: Send Electronic Documents"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: 36a86b8f-4073-448b-94b1-fb3d96b26e0a
caps.latest.revision: 10
ms.author: "sgroespe"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
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
# How to: Send Electronic Documents
The generic version of FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[dyn_nav](../ApplicationDesign/includes/dyn_nav_md.md)] --> --> --> supports sending electronic invoices and credit memos in the PEPPOL format, which is supported by the largest document exchange service providers. A document exchange service provider dispatches electronic documents between trading partners. To provide support for other electronic document formats, you use the Data Exchange Framework. For more information, see [How to: Set Up Data Exchange Definitions](../BusinessFunctionality/DataExchange/how-to-set-up-data-exchange-definitions.md).  
  
 In the generic version of [!INCLUDE[dyn_nav](../ApplicationDesign/includes/dyn_nav_md.md)], a document exchange service is preconfigured and ready to be set up for your company. For more information, see [How to: Set Up a Document Exchange Service](../BusinessFunctionality/DataExchange/how-to-set-up-a-document-exchange-service.md).  
  
 To send a sales invoice as an electronic PEPPOL document, you select the **Electronic Document** option in the **Post and Send** dialog box from where you can also set up the customer’s default document sending profile. First, you must set up various master data, such as company information, customers, items, and units of measure. These are used to identify the business partners and items when converting data in fields in [!INCLUDE[dyn_nav](../ApplicationDesign/includes/dyn_nav_md.md)] to elements in the outgoing document file. The data conversion and export of the PEPPOL sales invoice are performed by dedicated codeunits and XMLports, represented by the **PEPPOL** electronic document format. For more information, see [How to: Set Up Electronic Document Sending and Receiving](../BusinessFunctionality/DataExchange/how-to-set-up-electronic-document-sending-and-receiving.md).  
  
### To send an electronic sales invoice  
  
1.  In the **Search** box, enter **Sales Invoices**, and then choose the related link.  
  
2.  Create a new sales invoice. For more information, see [Invoice Sales Activities](../Finance/invoice-sales-activities.md).  
  
3.  When the sales invoice is ready to be invoiced, on the **Actions** tab, in the **Posting** group, choose **Post and Send**.  
  
     If the customer’s default sending profile is **Electronic Document**, then it will be shown in the **Post and Send Confirmation** dialog box and you just have to choose the **Yes** button to post and send the invoice electronically in the selected format. For more information, see [How to: Set Up Document Sending Profiles](../Sales/how-to-set-up-document-sending-profiles.md).  
  
4.  In the **Post and Send Confirmation** dialog box, choose the AssistEdit button to the right of the **Send Document to** field.  
  
5.  In the **Send Document to** dialog box, in the **Electronic Document** field, choose **Through Dolcument Exchange Service**.  
  
6.  In the **Format** field, choose **PEPPOL**.  
  
7.  Choose the **OK** button. The **Post and Send Confirmation** dialog box appears. **Electronic Document \(PEPPOL\)** is added to the **Send Document to** field.  
  
8.  Choose the **Yes** button.  
  
     The sales invoice is posted and sent to the customer as an electronic document in the PEPPOL format.  
  
    > [!NOTE]  
    >  You can also send a posted sales invoice as an electronic document. The procedure is the same as described in this topic for non\-posted sales documents. In the **Posted Sales Invoice** window, on the **Actions** tab, in the **General** group, choose **Activity Log** to view the status of the electronic document. For more information, see **Activity Log**.  
  
## See Also  
 [Invoice Sales Activities](../Finance/invoice-sales-activities.md)   
 Activity Log   
 [How to: Set Up Document Sending Profiles](../Sales/how-to-set-up-document-sending-profiles.md)   
 [How to: Set Up Electronic Document Sending and Receiving](../BusinessFunctionality/DataExchange/how-to-set-up-electronic-document-sending-and-receiving.md)   
 [How to: Set Up a Document Exchange Service](../BusinessFunctionality/DataExchange/how-to-set-up-a-document-exchange-service.md)   
 [How to: Set Up Data Exchange Definitions](../BusinessFunctionality/DataExchange/how-to-set-up-data-exchange-definitions.md)   
 [Data Exchange](../BusinessFunctionality/DataExchange/data-exchange.md)   
 [Business Functionality](../Topic/Business%20Functionality.md)