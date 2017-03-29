---
title: 'How to: Record Special Sales Prices and Discounts| Microsoft Docs'
description: 'How to: Record Special Sales Prices and Discounts'
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: special price, alternate price, pricing
ms.date: 03/29/2017
ms.author: sgroespe

---
# How to: Record Special Sales Prices and Discounts
The different price and discount agreements that apply when selling to different customers must be defined so that the agreed rules and values are applied to sales documents that you create for the customers.

When you have recorded special prices and line discounts for sales and purchases, [!INCLUDE[d365fin](includes/d365fin_md.md)] ensures that your profit on item trade is always optimal by automatically calculating the best price on sales and purchase documents and on job and item journal lines. For more information, see [Advanced: Best Price Calculation](advanced-best-price-calculation.md).

Concerning prices, you can have a special sales price inserted on sales lines if a certain combination of customer, item, minimum quantity, unit of measure, or starting/ending date exists.

Concerning discounts, you can set up and use two types of sales discounts:

| Discount Type | Description |
| --- | --- |
| **Sales Line Discount** |An amount discount that is inserted on sales lines if a certain combination of customer, item, minimum quantity, unit of measure, or starting/ending date exists. This works in the same way as for sales prices. |
| **Invoice Discount** |A percentage discount that is subtracted from the document total if the value amount of all lines on a sales document exceeds a certain minimum. |

Because sales prices and sales line discounts are based on a combination of item and customer, you can also perform this configuration from the item card of the item where the rules and values apply.

## To set up a sales price for a customer
1. In the top right corner, choose the **Search for Page or Report** icon, enter **Customers**, and then choose the related link.
2. Open the relevant customer card, and then choose the **Prices** action.

    The **Sales Type** field is prefilled with **Customer**, and the **Sales Code** field is prefilled with the customer number.
3. Fill in the fields on the line as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] Fill a line for each combination that will grant a special sales price to the customer.

## To set up a sales line discount for a customer
1. In the top right corner, choose the **Search for Page or Report** icon, enter **Customers**, and then choose the related link.
2. Open the relevant customer card, and then choose the **Line Discounts** action.

    The **Sales Type** field is prefilled with **Customer**, and the **Sales Code** field is prefilled with the customer number.
3. Fill in the fields on the line as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] Fill a line for each combination that will grant a sales line discount to the customer.

## To set up an invoice discount for a customer
When you have decided which customers are eligible for invoice discounts, enter the invoice discount code on the customer cards and set up the terms for each code.

1. In the top right corner, choose the **Search for Page or Report** icon, enter **Customers**, and then choose the related link.
2. Open the customer card for a customer that will be eligible for invoice discounts.
3. In the **Invoice Disc. Code** field, select a code for the relevant invoice discount terms to use to calculate invoice discounts for the customer.

    **Note**: Invoice discount codes are represented by existing customer cards. This enables you to quickly assign invoice discount terms to customers by picking the name of another customer who will have the same terms.

    Proceed to set up new the sales invoice discount terms.
4. In the **Customer Card** window, choose the **Invoice Discounts** action. The **Cust. Invoice Discounts** window opens.
5. In the **Currency Code** field, enter the code for a currency that the invoice discount terms on the line applies to. Leave the field blank to set up invoice discount terms in USD.
6. In the **Minimum Amount** field, enter the minimum amount that an invoice must have to be eligible for the discount.
7. In the **Discount %** field, enter the invoice discount as a percentage of the invoice amount.
8. Repeat steps 5 through 7 for each currency that the customer will receive a different invoice discount for.

The invoice discount is now set up and assigned to the customer in question. When you select the customer code in the **Invoice Disc. Code** field on other customer cards, the same invoice discount is assigned to those customers.

## See Also
[Advanced: Best Price Calculation](advanced-best-price-calculation.md)  
[Setting Up Sales](sales-setup-sales.md)  
[Sales](sales-manage-sales.md)  
[Working With [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
