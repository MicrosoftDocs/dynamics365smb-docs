---
title: Calculate dates for purchases
description: Learn how to calculate purchase dates to optimize inventory planning and streamline procurement processes.
author: brentholtorf 
ms.topic: how-to
ms.devlang: al
ms.search.keywords: purchase order, purchase, date, receipt, delivery, lead time
ms.search.forms: 
ms.date: 10/03/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Calculate dates for purchases

If you want to have items in inventory on a certain date, [!INCLUDE[prod_short](includes/prod_short.md)] can automatically calculate the date on which you must order them.

The result is the date on which you can pick the items that you ordered.  

If you specify a requested receipt date on a purchase order line, the calculated order date is the date on which you must place the order. The date on which the items are available for picking displays in the **Expected Receipt Date** field.  

If you don't specify a requested receipt date, the date you expect to receive the items is based on order date on the line.

The receipt date is also the date when the items are available for picking.  

> [!TIP]
> By default, many of the date fields this article mentions are hidden on purchase order lines. If a field isn't available, you can add it by personalizing the page. Learn more in [Personalize Your Workspace](ui-personalization-user.md).

## Calculating with a requested receipt date

If there's a requested receipt date on the purchase order line, that date is the basis for the following calculations:  

- requested receipt date - lead time calculation = order date  
- requested receipt date + inbound whse. handling time + safety lead time = expected receipt date  

If you specify a requested receipt date on a purchase order line, that date is assigned to new lines as you create them. You can change or remove the date on the lines.  

> [!NOTE]
> If your process is based on backward calculation, for example, if you use the requested receipt date to get the order date, we recommend that you use date formulas that have fixed durations, such as "5D" for five days or "1W" for one week. Date formulas without fixed durations, such as "CW" for current week or CM for current month, can result in incorrect date calculations. Learn more in [Work with Calendar Dates and Times](ui-enter-date-ranges.md) for information about date formulas.

## Calculating without a requested receipt date

If you enter a purchase order line without a requested receipt date, the **Order Date** field on the line shows the date in the **Order Date** field on the purchase order header. This date is either the date you entered or the work date. The dates are then calculated for the purchase order line, with the order date as the starting point, as follows:  

- order date + lead time calculation = planned receipt date  
- planned receipt date + inbound whse. handling time + safety lead time = expected receipt date  

If you change the order date on the line, [!INCLUDE[prod_short](includes/prod_short.md)] recalculates the other dates.  

## Default values for lead time calculation

[!INCLUDE[prod_short](includes/prod_short.md)] uses the date formula in the **Lead Time Calculation** field on the purchase order line to calculate the order and expected receipt dates.  

You can manually specify the date formula on lines. Otherwise, [!INCLUDE[prod_short](includes/prod_short.md)] uses the formulas that are defined on the following pages in this order of priority:

1. Item/Vendor Catalog
2. Item Card
3. Stockkeeping Unit Card
4. Vendor Card

## Related information

[Date Calculation for Sales](sales-date-calculation-for-sales.md)  
[Calculate Order Promising Dates](sales-how-to-calculate-order-promising-dates.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
