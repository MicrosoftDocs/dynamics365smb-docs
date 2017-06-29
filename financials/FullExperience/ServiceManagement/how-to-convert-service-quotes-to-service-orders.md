---
title: "How to: Convert Service Quotes to Service Orders"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "quotes, converting to service orders"
ms.assetid: 123e7b37-5557-4505-9c1f-00306753f6a5
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
# How to: Convert Service Quotes to Service Orders
When a customer has accepted a service quote, you convert it to a service order.  
  
 You must have already created the service quote.  
  
### To convert a service quote to a service order  
  
1.  In the **Search** box, enter **Service Contract Quotes**, and then choose the related link.  
  
2.  Select the relevant service quote that you want to convert to a service order.  
  
3.  On the **Actions** tab, in the **General** group, choose **Make Order**.  
  
 The quote is converted to an order. It is deleted from the window and a new service order is set up with the same description as the service quote. The response date and time are recalculated for the service order and the status is set to **Pending**. The repair status of the service items in the order are changed to **Initial**.  
  
 ADD INCLUDE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)]--> searches for allocation entries for all the service items in the service quote that have the status **Active**. If it finds such allocation entries, their allocation status is updated to **Reallocation Needed**. When you reallocate the service items in the service order, the status of the allocation entries registered for the quote are updated to **Finished**.  
  
## See Also  
 [How to: Create Service Quotes](../Service/how-to-create-service-quotes.md)