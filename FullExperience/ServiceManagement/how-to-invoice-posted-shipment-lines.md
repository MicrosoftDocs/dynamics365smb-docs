---
title: "How to: Invoice Posted Shipment Lines"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "service posting, invoices"
  - "posting, service invoices"
  - "service invoices, posting shipment lines"
ms.assetid: 8e2bfe82-41ee-407c-bd08-14daf56766ec
caps.latest.revision: 6
ms.author: "edupont"
manager: "terryaus"
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
# How to: Invoice Posted Shipment Lines
You might need to create a service invoice for the service that has already been shipped, either from one or several service orders, but not yet invoiced or consumed. You can fill in the invoice lines automatically with the selected posted shipment lines for a specific customer.  
  
### To invoice posted shipment lines  
  
1.  In the **Search** box, enter **Service Invoices**, and then choose the related link.  
  
2.  On the **Home** tab, in the **New** group, choose **New**. Create a new service invoice.  
  
3.  Fill in the fields on the **General** FastTab.  
  
4.  Create invoice lines for services shipped but not invoiced. Alternatively, you can run the **Get Shipment Lines** function.  
  
    1.  Choose **Actions**![Action Menu icon](../DesignAndEngineering/media/actionmenuicon.png "actionMenuIcon"), choose **Functions**, and then choose **Get Shipment Lines**.  
  
    2.  In the **Get Service Shipment Lines** window, select the shipment lines that you want to invoice, and choose the **OK** button. The selected posted shipment lines are inserted into the invoice.  
  
5.  Post the service invoice.  
  
 The posted service invoice is created, as well as the corresponding ledger entries. Previously posted shipment documents are updated with the invoiced quantities and the relevant quantities on the service lines of the source orders.  
  
## See Also  
 [How to: Create Combined Invoices](../Service/how-to-create-combined-invoices.md)   
 [How to: Create Service Invoices Manually](../Service/how-to-create-service-invoices-manually.md)   
 [How to: Post Invoices from Service Orders](../Service/how-to-post-invoices-from-service-orders.md)   
 [How to: Undo Service Shipments](../Service/how-to-undo-service-shipments.md)