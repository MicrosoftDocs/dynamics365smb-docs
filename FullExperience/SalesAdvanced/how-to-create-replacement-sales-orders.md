---
title: "How to: Create Replacement Sales Orders"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "returns, sales"
  - "sales returns, creating"
ms.assetid: 98e56237-cd78-41b9-b140-2e674d22df23
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
# How to: Create Replacement Sales Orders
You may decide to compensate a customer for an item that you have sold them by replacing the item. You can make a replacement with the same item or a different item. This situation could occur if you mistakenly shipped the wrong item to the customer, for example.  
  
 At this point, you have shipped the original item to the customer.  
  
### To create a replacement sales order from a sales return order  
  
1.  In the **Search** box, enter **Sales Return Orders**, and then choose the related link.  
  
2.  Create a sales return order for the customer. On the **Home** tab, in the **New** group, choose **New**.  
  
3.  Enter a line for the returned item.  
  
4.  On the next line, make a negative entry for the replacement item by inserting a negative amount in the **Quantity** field.  
  
5.  On the **Actions** tab, in the **Functions** group, choose **Move Negative Lines**.   
    The **Move Negative Sales Lines** batch job request window opens.  
  
6.  When you run this batch job, the negative line for the replacement item is deleted from the sales return order and inserted itto a new **Sales Order** window.  
  
## See Also  
 [Sales Return Order](../Topic/\($%20N_6630%20Sales%20Return%20Order%20$\).md)   
 [How to: Create Sales Return Orders](../Sales/how-to-create-sales-return-orders.md)   
 [Manage Sales Returns](../Sales/manage-sales-returns.md)