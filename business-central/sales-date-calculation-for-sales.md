---
    title: Date Calculation for Sales | Microsoft Docs
    description: The program automatically calculates the date on which you must order an item to have it in inventory on a certain date. This is the date on which you can expect items ordered on a particular date to be available for picking.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 09/06/2017
    ms.author: sgroespe

---
# Date Calculation for Sales
[!INCLUDE[d365fin](includes/d365fin_md.md)] automatically calculates the earliest possible date that an item on a sales order line can be shipped.

If the customer has requested a specific delivery date, then the date on which the items must be available to pick to meet that delivery date is calculated.

If the customer does not request a specific delivery date, then the date on which the items can be delivered is calculated, starting from the date on which the items are available for picking.

## Calculating a Requested Delivery Date
If you specify a requested delivery date on the sales order line, then that date is used as the starting point for the following calculations.

- requested delivery date - shipping time = planned shipment date
- planned shipment date - outbound whse. handling time = shipment date

If the items are available to pick on the shipment date, then the sales process can continue.

If the items are not available to be picked on the shipment date, then a stock-out warning is displayed.

## Calculating the Earliest Possible Delivery Date
If you do not specify a requested delivery date on the sales order line, or if the requested delivery date cannot be met, then the earliest date on which that the items are available is calculated. That date is then entered in the Shipment Date field on the line, and the date on which you plan to ship the items as well as the date on which they will be delivered to the customer are calculated using the following formulas.

- shipment date + outbound whse. handling time = planned shipment date
- planned shipment date + shipping time = planned delivery date


## See Also  
 [Date Calculation for Purchases](purchasing-date-calculation-for-purchases.md)   
 [Calculate Order Promising Dates](sales-how-to-calculate-order-promising-dates.md)  
 [Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
