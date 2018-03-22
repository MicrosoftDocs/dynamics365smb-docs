---
title: Set Up Special Sales Prices and Discounts for Customers | Microsoft Docs
description: Describes how to define the alternate pricing and discount agreements that you want to apply to sales documents when selling to different customers.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: special price, alternate price, pricing
ms.date: 03/16/2018
ms.author: sgroespe

---
# Record Special Sales Prices and Discounts
The different price and discount agreements that apply when selling to different customers must be defined so that the agreed rules and values are applied to sales documents that you create for the customers.

When you have recorded special prices and line discounts for sales and purchases, [!INCLUDE[d365fin](includes/d365fin_md.md)] ensures that your profit on item trade is always optimal by automatically calculating the best price on sales and purchase documents and on job and item journal lines. For more information, see "Best Price Calculation" section.

Concerning prices, you can have a special sales price inserted on sales lines if a certain combination of customer, item, minimum quantity, unit of measure, or starting/ending date exists.

Concerning discounts, you can set up and use two types of sales discounts:

| Discount Type | Description |
| --- | --- |
| **Sales Line Discount** |An amount discount that is inserted on sales lines if a certain combination of customer, item, minimum quantity, unit of measure, or starting/ending date exists. This works in the same way as for sales prices. |
| **Invoice Discount** |A percentage discount that is subtracted from the document total if the value amount of all lines on a sales document exceeds a certain minimum. |

Because sales prices and sales line discounts are based on a combination of item and customer, you can also perform this configuration from the item card of the item where the rules and values apply.

> [!NOTE]  
> If you do not want an item to ever be sold at a discounted price, simply leave discount fields on the item card empty, and do not include the item in any line discount setup.

## To set up a sales price for a customer
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Customers**, and then choose the related link.
2. Open the relevant customer card, and then choose the **Prices** action.

    The **Sales Type** field is prefilled with **Customer**, and the **Sales Code** field is prefilled with the customer number.
3. Fill in the fields on the line as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] Fill a line for each combination that will grant a special sales price to the customer.

## To set up a sales line discount for a customer
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Customers**, and then choose the related link.
2. Open the relevant customer card, and then choose the **Line Discounts** action.

    The **Sales Type** field is prefilled with **Customer**, and the **Sales Code** field is prefilled with the customer number.
3. Fill in the fields on the line as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] Fill a line for each combination that will grant a sales line discount to the customer.

## To set up an invoice discount for a customer
When you have decided which customers are eligible for invoice discounts, enter the invoice discount code on the customer cards and set up the terms for each code.

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Customers**, and then choose the related link.
2. Open the customer card for a customer that will be eligible for invoice discounts.
3. In the **Invoice Disc. Code** field, select a code for the relevant invoice discount terms to use to calculate invoice discounts for the customer.

> [!NOTE]  
>   Invoice discount codes are represented by existing customer cards. This enables you to quickly assign invoice discount terms to customers by picking the name of another customer who will have the same terms.

Proceed to set up new the sales invoice discount terms.

1. In the **Customer Card** window, choose the **Invoice Discounts** action. The **Cust. Invoice Discounts** window opens.
2. In the **Currency Code** field, enter the code for a currency that the invoice discount terms on the line applies to. Leave the field blank to set up invoice discount terms in USD.
3. In the **Minimum Amount** field, enter the minimum amount that an invoice must have to be eligible for the discount.
4. In the **Discount %** field, enter the invoice discount as a percentage of the invoice amount.
5. Repeat steps 5 through 7 for each currency that the customer will receive a different invoice discount for.

The invoice discount is now set up and assigned to the customer in question. When you select the customer code in the **Invoice Disc. Code** field on other customer cards, the same invoice discount is assigned to those customers.

## To work with sales invoice discounts and service charges
When you use invoice discounts, the size of the invoice amount determines the size of the discount that is granted.  

In the **Cust. Invoice Discounts** window, you can also add a service charge to invoices over a certain amount.  

Before you can use invoice discounts with sales, you must enter certain information in the program. You must decide:  

- which customers will be granted this type of discount.  
- which discount percentages you will use.  

If you invoice discounts to be calculated automatically, you can specify this in the **Sales & Receivables Setup** window.  

For each customer, you can specify whether you will grant invoice discounts if the requirement is satisfied (that is, if the invoice amount is large enough). You can define the terms of the invoice discount in local currency for domestic customers and in foreign currency for foreign customers.  

You link discount percentages to specific invoice amounts in **Cust. Invoice Discounts** windows. You can enter any number of percentages in each window. Each customer can have its own window, or you can link several customers to the same window.  

In addition to (or instead of) a discount percentage, you can link a service charge amount to a specific invoice amount.  

> [!TIP]  
>  Before you start entering this information in the program, it is a good idea to prepare an outline of the discount structure you want to use. This makes it easier to see which customers can be linked to the same invoice discount window. The fewer windows you have to set up, the faster you can enter the basic information.  

## Best Price Calculation
When you have recorded special prices and line discounts for sales and purchases, [!INCLUDE[d365fin](includes/d365fin_md.md)] ensures that your profit on item trade is always optimal by automatically calculating the best price on sales and purchase documents and on job and item journal lines.

The best price is the lowest permissible price with the highest permissible line discount on a given date. [!INCLUDE[d365fin](includes/d365fin_md.md)] automatically calculates this when it inserts the unit price and the line discount percentage for items on new document and journal lines.

> [!NOTE]  
>   The following describes how the best price is calculated for sales. The calculation is the same for purchases.

1. [!INCLUDE[d365fin](includes/d365fin_md.md)] checks the combination of the bill-to customer and the item and then calculates the applicable unit price and line discount percentage, using the following criteria:

    - Does the customer have a price/discount agreement, or does the customer belong to a group that does?
    - Is the item or the item discount group on the line included in any of these price/discount agreements?
    - Is the order date (or the posting date for the invoice and credit memo) within the starting and ending date of the price/discount agreement?
    - Is a unit of measure code specified? If so, [!INCLUDE[d365fin](includes/d365fin_md.md)] checks for prices/discounts with the same unit of measure code, and prices/discounts with no unit of measure code.

2. [!INCLUDE[d365fin](includes/d365fin_md.md)] checks if any price/discount agreements apply to information on the document or journal line, and then inserts the applicable unit price and line discount percentage, using the following criteria:

    - Is there a minimum quantity requirement in the price/discount agreement that is fulfilled?
    - Is there a currency requirement in the price/discount agreement that is fulfilled? If so, the lowest price and the highest line discount for that currency are inserted, even if local currency would provide a better price. If there is no price/discount agreement for the specified currency code, [!INCLUDE[d365fin](includes/d365fin_md.md)] inserts the lowest price and the highest line discount in your local currency.

If no special price can be calculated for the item on the line, then either the last direct cost or the unit price from the item card is inserted.

## To copy sales prices  
If you want to copy sales prices, such as an individual customer's sales prices to use for a customer price group, you must run the **Suggest Sales Price on Wksh.** batch job. You find the batch job in the **Sales Price Worksheet** window.    

1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Sales Price Worksheet**, and then choose the related link.  
2.  Choose the **Suggest Sales Price on Wksh.** action.  
3.  On the **Sales Prices** FastTab, fill in the **Sales Type** and **Sales Code** fields with the original sales prices you want to copy.  
4.  In the top section of the request window, fill in the **Sales Type** and **Sales Code** with the type and name you want the sales prices copied to.  
5.  If you want the batch job to create new prices, select the **Create New Prices** field.  
6.  Choose the **OK** button to fill in the lines on the **Sales Price Worksheet** window with the suggested new prices, indicating that they are valid for the selected **Sales Type**.  

> [!NOTE]  
>  This batch job only creates suggestions and it does not implement the suggested changes. If you are satisfied with the suggestions and want to implement them, that is insert them in the **Sales Prices** table, you can use the **Implement Price Changes** batch job, which is found on the **Actions** tab, in the **Functions** group, in the **Sales Price Worksheet** window.

## See Also
[Setting Up Sales](sales-setup-sales.md)  
[Sales](sales-manage-sales.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
