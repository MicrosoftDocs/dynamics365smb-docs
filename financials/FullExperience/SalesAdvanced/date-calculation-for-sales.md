---
title: "Date Calculation for Sales"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "order promising, calculating for sales"
  - "sales, dates for shipping"
  - "dates, calculating"
ms.assetid: 74443939-d78e-4235-ab3f-9b91af3966cb
caps.latest.revision: 7
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
# Date Calculation for Sales
[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] automatically calculates the earliest possible date that an item on a sales order line can be shipped.  
  
 If the customer has requested a specific delivery date, then the date on which the items must be available to pick to meet that delivery date is calculated.  
  
 If the customer does not request a specific delivery date, then the date on which the items can be delivered is calculated, starting from the date on which the items are available for picking.  
  
## Calculating a Requested Delivery Date  
 If you specify a requested delivery date on the sales order line, then that date is used as the starting point for the following calculations.  
  
 requested delivery date \- shipping time \= planned shipment date  
  
 planned shipment date \- outbound whse. handling time \= shipment date  
  
 If the items are available to pick on the shipment date, then the sales process can continue.  
  
 If the items are not available to be picked on the shipment date, then a stock\-out warning is displayed.  
  
## Calculating the Earliest Possible Delivery Date  
 If you do not specify a requested delivery date on the sales order line, or if the requested delivery date cannot be met, then the earliest date on which that the items are available is calculated. That date is then entered in the **\($ T\_37\_10 Shipment Date $\)** field on the line, and the date on which you plan to ship the items as well as the date on which they will be delivered to the customer are calculated using the following formulas.  
  
 shipment date \+ outbound whse. handling time \= planned shipment date  
  
 planned shipment date \+ shipping time \= planned delivery date  
  
## See Also  
 [\($ T\_36\_5790 Requested Delivery Date $\)](../Topic/\($%20T_36_5790%20Requested%20Delivery%20Date%20$\).md)   
 [\($ T\_37\_10 Shipment Date $\)](../Topic/\($%20T_37_10%20Shipment%20Date%20$\).md)   
 [How to: Enter Outbound Warehouse Handling Time](../DesignAndEngineering/how-to-enter-outbound-warehouse-handling-time.md)   
 [How to: Set Up Shipping Agent Services](../Sales/how-to-set-up-shipping-agent-services.md)   
 [About Order Promising](../Sales/about-order-promising.md)   
 [How to: Calculate Order Promising Dates](../Sales/how-to-calculate-order-promising-dates.md)