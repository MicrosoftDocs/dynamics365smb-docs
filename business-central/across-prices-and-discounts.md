---
title: Set Up Prices and Discounts | Microsoft Docs
description: Describes how to define standard and special price and discount agreements for sales and purchases.
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: special price, alternate price, pricing
ms.date: 10/01/2020
ms.author: bholtorf

---
# Set Up Prices and Discounts
> [!NOTE]
> In 2020 release wave 2 we released streamlined processes for setting up and managing prices and discounts. If you're a new customer using that version, you're using the new experience. If you're an existing customer, whether you are using the new experience depends on whether your administrator has enabled the **New sales pricing experience** feature update in **Feature Management**. For more information, see [Enabling Upcoming Features Ahead of Time](/dynamics365/business-central/dev-itpro/administration/feature-management.md).

Price and discount strategies for the purchase and sale of items and services are fundamental tools for successful businesses. In [!INCLUDE[d365fin](includes/d365fin_md.md)], after you set up the items and services your company buys and sells, you can define what you pay or charge for them by setting up price lists. Price lists are flexible and let you specify the business partner or activity that they apply to. For example, you can set up one price list that applies to all vendors and customers, or offer special prices or discounts for each business partner, perhaps based on a minimum quantity on purchase or sales orders, or a certain combination of customer, item, minimum quantity, unit of measure, or perios of time. The prices and discounts you define are automatically applied to purchase and sales documents. 

## Setting Up Prices and Discounts
Before you create price lists, you must define your pricing and discount strategies on the **Sales & Receivables Setup** and **Purchase & Payables Setup** pages.

You can set up and use two types of discounts:

| Discount Type | Description |
| --- | --- |
| **Line Discount** |A discount amount that is given for lines on sales and purchase documents. Typically, line discounts are based on a combination of customer, item, minimum quantity, unit of measure, or period of time that you define for sales and purchases on the **Sales & Receivables Setup** and **Purchase & Payables Setup** pages.|
| **Invoice Discount** |A discount percentage that is subtracted from sales and purchase document total if the sum of all lines on the document exceeds a certain minimum. |

Because sales prices and sales line discounts are based on a combination of item and customer, you can also perform this configuration from the item page of the item where the rules and values apply.

> [!TIP]  
> If an item should never be sold with a discount, leave the discount fields on the item page empty, and do not include the item in any line discount setups.

## Set Up a Price List 
You can set up price lists by adding items and services manually for each line, or you can use the **Suggest Lines** action to create new prices for selected items, item discount groups, resources, and other product types. If you choose **Suggest Lines**, on the **Price Lines - Create New** page you can use filters to select the items or services to include on the price list. You can also specify whether to consider a minimum quantity when calculating prices, the adjustment factor to apply for new price list lines, and the rounding method to apply for prices. 

By default, the status of new price lists is **Draft**. When you're ready to start using the list, you can change the status to **Active**.

To review price lists and prices that apply for specific customers or vendors, on the **Customer** or **Vendor** pages, choose either **Sales Price Lists** or **Purchase Price Lists** action. For items and resources, you can view price list lines by choosing **Sales Prices** or **Purchase Prices** on the **Item** and **Resource** pages.

## Copy a Price List
The **Copy Lines** action allows you to copy existing price list lines between price lists.

## Calculating the Best Price
When you have recorded special prices and line discounts for sales and purchases, [!INCLUDE[d365fin](includes/d365fin_md.md)] ensures that your profit on item trade is always optimal by automatically calculating the best price on sales and purchase documents, and on job and item journal lines. For more information, see [Best Price Calculation](sales-how-record-sales-price-discount-payment-agreements.md#best-price-calculation).

## See Also