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

The price and discount agreements that apply when you sell to customers or buy from vendors must be defined so that the agreed rules and values are applied to sales and purchase documents.

When you have recorded special prices and line discounts for sales and purchases, [!INCLUDE[d365fin](includes/d365fin_md.md)] ensures that your profit on item trade is always optimal by automatically calculating the best price on sales and purchase documents, and on job and item journal lines. For more information, see [Best Price Calculation](sales-how-record-sales-price-discount-payment-agreements.md#best-price-calculation).

Concerning prices, you can have a special sales price inserted on sales lines if a certain combination of customer, item, minimum quantity, unit of measure, and starting and ending dates exists.

Concerning discounts, you can set up and use two types of sales discounts:

| Discount Type | Description |
| --- | --- |
| **Sales Line Discount** |An amount discount that is inserted on sales lines if a certain combination of customer, item, minimum quantity, unit of measure, or starting/ending date exists. This works in the same way as for sales prices. |
| **Invoice Discount** |A discount percentage that is subtracted from the sales document total if the sum of all lines on the document exceeds a certain minimum. |

Because sales prices and sales line discounts are based on a combination of item and customer, you can also perform this configuration from the item page of the item where the rules and values apply.

> [!TIP]  
> If an item should never be sold with a discount, leave the discount fields on the item page empty, and do not include the item in any line discount setups.

The **Applies-to Type** and **Applies-to No.** fields let you choose what this price list will apply to, such as customer or customer price group. Using **View Columns for, you can show or hide columns relevant for setting prices, discounts or prices and discounts.

You can set up Price List lines manually or you can use, for example, the Suggest Lines action to create new prices for selected items, item discount groups, resources, and other product types. If you choose Suggest Lines, the Price Lines - Create New page allows you to set filters to select products for which you want to create new price list lines. You can also specify whether to consider a Minimum quantity when calculating prices, the adjustment factor to apply for new price list lines, and the rounding method to apply for prices. The Copy Lines action allows you to copy existing price list lines between price lists.

By default, the status of new price lists is Draft. When you're done adding lines and want the price calculation engine to include it, you can change the status to Active.

To review price lists and prices that apply for specific customers or vendors, on the Customer page, choose Sales Price Lists or, on the Vendor page, choose Purchase Price Lists. You can view price list lines set in various price lists by choosing Sales Prices or Purchase Prices from the Item and Resource pages.