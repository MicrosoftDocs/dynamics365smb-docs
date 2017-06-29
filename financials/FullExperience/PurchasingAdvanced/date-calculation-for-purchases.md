---
title: "Date Calculation for Purchases"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "requested delivery dates"
  - "requested receipt dates"
  - "order promising, calculating for purchases"
ms.assetid: c92e770c-52a1-4048-91c9-de55db1052c4
caps.latest.revision: 6
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
# Date Calculation for Purchases
ADD INCLUDE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)]--> automatically calculates the date on which you must order an item to have it in inventory on a certain date. This is the date on which you can expect items ordered on a particular date to be available for picking.  
  
 If you specify a requested receipt date on a purchase order header, then the calculated order date is the date on which the order must be placed to receive the items on the date that you requested. Then, the date on which the items are available for picking is calculated and entered in the **Expected Receipt Date** field.  
  
 If you do not specify a requested receipt date, then the order date on the line is used as the starting point for calculating the date on which you can expect to receive the items and the date on which the items are available for picking.  
  
## Calculating with a Requested Receipt Date  
 If there is a requested receipt date on the purchase order line, then that date is used as the starting point for the following calculations.  
  
 requested receipt date \- lead time calculation \= order date  
  
 requested receipt date \+ inbound whse. handling time \+ safety lead time \= expected receipt date  
  
 If you entered a requested receipt date on the purchase order header, then that date is copied to the corresponding field on all the lines. You can change this date on any of the lines, or you can remove the date on the line.  
  
## Calculating without a Requested Delivery Date  
 If you enter a purchase order line without a requested delivery date, then the **Order Date** field on the line is filled with the date in the **Order Date** field on the purchase order header. This is either the date that you entered or the work date. The following dates are then calculated for the purchase order line, with the order date as the starting point.  
  
 order date \+ lead time calculation \= planned receipt date  
  
 planned receipt date \+ inbound whse. handling time \+ safety lead time \= expected receipt date  
  
 If you change the order date on the line, such as when items are not available at your vendor until a later date, then the relevant dates on the line are automatically recalculated.  
  
 If you change the order date on the header, then that date is copied to the **Order Date** field on all the lines, and all the related date fields are then recalculated.  
  
## See Also  
 Expected Receipt Date   
 Order Date   
 [How to: Enter Inbound Warehouse Handling Time](../DesignAndEngineering/how-to-enter-inbound-warehouse-handling-time.md)   
 [Date Calculation for Sales](../Sales/date-calculation-for-sales.md)   
 [About Order Promising](../Sales/about-order-promising.md)