---
    title: Insert topic title| Microsoft Docs
    description: Insert description
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

    ---
# Date Calculation for Sales
ADD INCLUDE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)]--> automatically calculates the earliest possible date that an item on a sales order line can be shipped.  
  
 If the customer has requested a specific delivery date, then the date on which the items must be available to pick to meet that delivery date is calculated.  
  
 If the customer does not request a specific delivery date, then the date on which the items can be delivered is calculated, starting from the date on which the items are available for picking.  
  
## Calculating a Requested Delivery Date  
 If you specify a requested delivery date on the sales order line, then that date is used as the starting point for the following calculations.  
  
 requested delivery date \- shipping time \= planned shipment date  
  
 planned shipment date \- outbound whse. handling time \= shipment date  
  
 If the items are available to pick on the shipment date, then the sales process can continue.  
  
 If the items are not available to be picked on the shipment date, then a stock\-out warning is displayed.  
  
## Calculating the Earliest Possible Delivery Date  
 If you do not specify a requested delivery date on the sales order line, or if the requested delivery date cannot be met, then the earliest date on which that the items are available is calculated. That date is then entered in the **Shipment Date** field on the line, and the date on which you plan to ship the items as well as the date on which they will be delivered to the customer are calculated using the following formulas.  
  
 shipment date \+ outbound whse. handling time \= planned shipment date  
  
 planned shipment date \+ shipping time \= planned delivery date  
  
## See Also  
 Requested Delivery Date   
 Shipment Date   
 [How to: Enter Outbound Warehouse Handling Time](../DesignAndEngineering/how-to-enter-outbound-warehouse-handling-time.md)   
 [How to: Set Up Shipping Agent Services](../Sales/how-to-set-up-shipping-agent-services.md)   
 [About Order Promising](../Sales/about-order-promising.md)   
 [How to: Calculate Order Promising Dates](../Sales/how-to-calculate-order-promising-dates.md)