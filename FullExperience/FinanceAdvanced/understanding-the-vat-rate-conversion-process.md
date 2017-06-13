---
title: "Understanding the VAT Rate Conversion Process"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "VAT rate, understanding"
ms.assetid: 90865cd7-6a76-4722-a6fe-05774778c17a
caps.latest.revision: 5
ms.author: "sgroespe"
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
# Understanding the VAT Rate Conversion Process
This topic describes the VAT rate change conversion process.  
  
## Understanding the VAT Rate Conversion Process  
 The following list defines the capabilities of the VAT rate change tool:  
  
-   Performs VAT rate conversions for master data, journals, and orders in different ways. The selected master data and journals will be updated by the new general product posting group or VAT product post group. If an order has been fully or partially shipped, the shipped items will keep the current general product posting group or VAT product posting group. A new order line will be created for the unshipped items and updated to align current and new VAT or general product posting groups. In addition, item charge assignments, reservations, and item tracking information will be updated accordingly.  
  
-   Will not convert sales or purchase orders and invoices where shipments have been posted. These documents are posted using the current VAT rate.  
  
-   Will not convert documents that have posted prepayment invoices. For example, you have made or received prepayments on invoices that have not been completed before you use the VAT rate change tool. In this case, there will be a difference between the VAT that is due and the VAT that has been paid in the prepayments when the invoice is completed. The VAT rate change tool will skip these documents and you will have to manually update them.  
  
-   Will not convert drop shipments or special orders.  
  
-   Wil not convert sales or purchase orders with warehouse integration if they are partially shipped or received.  
  
-   Will not convert service contracts.  
  
## See Also  
 [How to: Perform VAT Rate Conversions](../Finance/how-to-perform-vat-rate-conversions.md)