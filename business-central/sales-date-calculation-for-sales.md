---
title: Delivery date calculation for sales
description: The application automatically calculates the date on which you must order an item to have it in inventory on a certain date and available for picking.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords:
ms.date: 03/06/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Delivery date calculation for sales

[!INCLUDE[prod_short](includes/prod_short.md)] automatically calculates the earliest possible date that an item on a sales order line can be shipped.

* If the customer has requested a specific delivery date, then the date on which the items must be available to pick to meet that delivery date is calculated.
* If the customer doesn't request a specific delivery date, then the date on which the items can be delivered is calculated. The calculation starts from the date on which the items are available for picking.

## Calculating a requested delivery date

If you specify a requested delivery date on the sales order line, that date becomes the starting point for the following calculations.

- *requested delivery date - shipping time = planned shipment date*
- *planned shipment date - outbound whse. handling time = shipment date*

If the items are available to pick on the shipment date, then the sales process can continue. Otherwise, a stock-out warning is displayed.

> [!NOTE]
> If your process is based on backward calculation, for example, if you use the requested delivery date to get the planned shipment date, we recommend you use date formulas with fixed durations, such as "5D" for five days or "1W" for one week. Date formulas without fixed durations, such as "CW" for current week or CM for current month, can result in incorrect date calculations. Learn more about date formulas at [Work with Calendar Dates and Times](ui-enter-date-ranges.md).

## Calculating the earliest possible delivery date

If you don't specify a requested delivery date on the sales order line, or if the requested delivery date can't be met, then the earliest date on which the items are available is calculated. That date is then entered in the **Shipment Date** field on the line, and the date on which you plan to ship the items and the date on which they'll be delivered to the customer are calculated using the following formulas.

- *shipment date + outbound whse. handling time = planned shipment date*
- *planned shipment date + shipping time = planned delivery date*

## Related information

[Date Calculation for Purchases](purchasing-date-calculation-for-purchases.md)  
[Calculate Order Promising Dates](sales-how-to-calculate-order-promising-dates.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
