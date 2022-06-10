---
title: Record Special Sales Prices and Discounts
description: Describes how to define pricing and discount agreements for sales documents.
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: special price, alternate price, pricing
ms.date: 06/03/2022
ms.author: bholtorf

---

# Record Special Sales Prices and Discounts

> [!NOTE]
> 2020 release wave 2 introduced new, streamlined processes for setting up and managing prices and discounts. If you're a new customer using the latest version, you're using the new experience. If you're an existing customer, whether you are using the new experience depends on whether your administrator has enabled the **New sales pricing experience** feature update in **Feature Management**. For more information, see [Enabling Upcoming Features Ahead of Time](/dynamics365/business-central/dev-itpro/administration/feature-management).

[!INCLUDE[prod_short](includes/prod_short.md)] supports various pricing strategies, such as:

* One-price-fits-all models where an item is always sold at the same price.
* Special price agreements with specific customers, or groups of customers.
* Campaigns when a sale meets criteria for a special offer. For example, criteria might be when an order meets a minimum quantity, is before a certain date, or includes a certain type of item.  

To use a basic pricing model, you only need to specify a unit price when you set up an item or resource. That price will always be used on sales documents. For more advanced models, for example, when you want to offer special prices for a sales campaign, you can specify criteria on the **Sales Prices** page. You can offer special prices based on a combination of the following information:  

* Customer
* Item
* Unit of measure
* Minimum quantity
* Dates that define the period for which the prices are valid.

After you set up special prices, [!INCLUDE[prod_short](includes/prod_short.md)] can calculate best prices on sales and purchase documents, and on job and item journal lines. For more information, see [Best Price Calculation](sales-how-record-sales-price-discount-payment-agreements.md#best-price-calculation).

For sales discounts, you can set up two types:

| Discount Type | Description |
| --- | --- |
| **Sales Line Discount** |An amount inserted on sales lines if they contain a certain combination of customer, item, minimum quantity, unit of measure, or starting/ending date. This type works in the same way as for sales prices. |
| **Invoice Discount** |A discount percentage that is subtracted from the sales document total if the sum of all lines on the document exceeds a certain minimum. |

> [!TIP]  
> If an item should never be sold with a discount, leave the discount fields on the item page empty, and do not include the item in any line discount setups.

## To set up a sales price for a customer

These steps differ, depending on whether your administrator has turned on the **New sales pricing experience** feature update. If the feature update isn't turned on, follow the steps on the Current Experience tab. 

#### [Current Experience](#tab/current-experience/)

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.
2. Choose the customer, and then choose the **Prices** action.
3. Fill in the fields on the line as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] Fill a line for each combination that will grant a special sales price to the customer.

#### [New Experience](#tab/new-experience/)  

By default, the status of new price lists is Draft. Draft price lists aren't included in price calculations. When you're done adding lines and want to start using the prices, change the status to Active.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.
2. Choose the customer, and then choose the **Sales Price Lists** action. 
3. Choose **New** to create a new sales price list.
4. On the **General** and **Tax** FastTabs, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
5. To add items to the list, do one of the following steps:
   * To add many items, choose **Suggest Lines**, and then enter filter criteria to specify the types of items to add. Optionally, you can enter other settings for the items that are specific to the price list. You can change these settings later, if needed.
   * To copy items from another price list, choose **Copy Lines**, and then choose the price list to copy.
   * To add items manually, in the grid, in the **Product Type** field, choose the type of product that the price list is for. Depending on your selection, fill in the remaining fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
6. To start using the price list, in the **Status** field, choose **Active**.  

---

## Using Sales and Purchase Price Lists
> [!NOTE]
> Using price lists requires that your administrator has enabled the **New sales pricing experience** feature update in **Feature Management**. For more information, see [Enabling Upcoming Features Ahead of Time](/dynamics365/business-central/dev-itpro/administration/feature-management).

Most of the new sales pricing experience is similar to the current experience, but there are a few differences. Those differences are described in the following sections.

The **Applies-to Type** and **Applies-to No.** fields let you choose what a price list will apply to, such as customer or customer price group. Using **View Columns for**, you can show or hide columns relevant for setting prices, discounts, or prices and discounts.

### Converting Existing Prices When You Turn On the Pricing Feature Update
When you enable the **New sales pricing experience** feature update on the **Feature Management** page, the **Feature Data Update** guide opens. Use the **Use default prices** toggle as follows:

* If you want to work with all prices on a single page, turn it on. Existing prices will be converted to one default price list for each of the following documents:

    * Sales
    * Purchases
    * Job sales
    * Job purchases 

    You can edit all prices for these areas on the **Prices Worksheet** page. The default prices lists will be set on the **Sales & Receivables Setup**, **Purchases & Payables Setup,** and **Jobs Setup** pages. 

> [!NOTE]
> If prices are set only on item or resource cards, default price lists will not be filled in with those prices during feature data update. However, you can open any of default price lists or the Price Worksheet page and use the **Suggest Lines** action to add the prices set on item or resource cards. 

* To use sales price lists, turn it off. Existing prices will be converted to a new price list for each combination of the following things: 

* Customer
* Customer group or campaign
* Starting and ending dates
* Currencies 

If you have many combinations, you'll have many price lists.

If you've already enabled the New Pricing Experience, you can create default price lists manually or specify an existing price list as the default. To set an existing price list as default, turn on the **Allow Updating Defaults** toggle on the price list. Then, on the **Sales & Receivables Setup**, **Purchase & Payables** or **Jobs Setup** pages, set the price list as the default.

### Editing Active Price Lists
To allow people to edit prices on active price lists for items, resources, customers, vendors, or other entities that use pricing, turn on the **Allow Editing Active Price** toggle on the **Sales & Receivables Setup** and **Purchase & Payables Setup** pages.   

When the **Allow Editing Active Price** toggle is turned off, to update prices in a price list you must change the status of the price list to **Draft**, make your change, and then reactivate the price list.

The **Prices Overview** page provides an overview of all prices across price lists. You can set filters to narrow down the list of prices you may want to modify or add to. After you modify prices, you must use the **Verify Lines** action to verify the prices against other price list lines. Verifying prices helps avoid duplicates and ambiguity during price calculation. 

> [!NOTE]
> When you edit a line in an active price list the status of the line becomes Draft, and the line will not be considered during price calculation until you use the **Verify lines** action. After you verify the price the line's status becomes Active and it will be considered in price calculations.

To add new prices, on the **Prices Overview** page, use the **Add New Lines** action. The **Prices Worksheet** page opens, and you can add price lines either by suggesting them based on criteria, copying them from other price lists, or manually entering them. Afterward, you can use the **Implement Price Change** action to compare the new prices with other price lists to avoid duplicates and ambiguity during price calculation.

## To copy sales prices
These steps differ, depending on whether your administrator has turned on the **New sales pricing experience** feature update. If the feature update isn't turned on, follow the steps on the Current Experience tab.

#### [Current Experience](#tab/current-experience/)  

If you want to copy sales prices, such as an individual customer's sales prices to use for a customer price group, you must run the **Suggest Sales Price on Wksh.** batch job on the **Sales Price Worksheet** page.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Price Worksheet**, and then choose the related link.  
2. Choose the **Suggest Sales Price on Wksh.** action.  
3. On the **Sales Prices** FastTab, fill in the **Sales Type** and **Sales Code** fields with the original sales prices you want to copy.  
4. In the top section of the request page, fill in the **Sales Type** and **Sales Code** fields with the type and name you want the sales prices copied to.  
5. If you want the batch job to create new prices, select the **Create New Prices** check box.  
6. Choose the **OK** button to fill in the lines on the **Sales Price Worksheet** page with the suggested new prices, indicating that they're valid for the selected sales type.  

   > [!NOTE]  
   > This batch job only creates suggestions and it does not implement the suggested changes. If you are satisfied with the suggestions and want to implement them, that is insert them on the **Sales Prices** page, choose the **Implement Price Changes** action on the **Sales Price Worksheet** page.

#### [New Experience](#tab/new-experience/)  
You can specify whether the new price list will use the settings from the header on the list you're copying, or the settings from the new list you're copying to. To use the settings from the price list you're copying prices to, turn on the **Use defaults from target** toggle.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Price Lists**, and then choose the related link. 
2. Choose the price list to copy, and then choose **Copy Lines**.
3. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

   > [!NOTE]
   > You can't have two items that have the same settings but different prices. If that happens, a message will display when you activate the price list. You can choose the price to use by opening the list and deleting the incorrect price.  
  
---

## To bulk update item prices
These steps differ, depending on whether your administrator has turned on the **New sales pricing experience** feature update. If the feature update isn't turned on, follow the steps on the Current Experience tab.

#### [Current Experience](#tab/current-experience/)

To bulk update item prices, such as increase all prices by a percentage, you can fill in the Sales Price Worksheet page by using the following batch jobs:

* **Suggest Sales Price on Wksh.** suggests changes in one of two ways. Either by applying an adjustment factor to existing sales prices, or by copying existing sales price agreements to other customers, customer price groups, or sales campaigns.
* **Suggest Item Price on Wksh.** suggests changes in one of two ways. Either by applying an adjustment factor to existing unit prices on item cards, or by suggesting prices for new combinations of currency, units of measure, and so on. The unit prices on items aren't changed by this batch job.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Price Worksheet**, and then choose the related link.  
2. Choose the **Suggest Item Price on Wksh.** action.  
3. On the **Item** FastTab, fill in the **No.** or **Inventory Posting Group** or other fields with the original item prices you want to update.  
4. In the top section of the request page, fill in the **Sales Type** and **Sales Code** with the type and name you want the sales prices copied to.
5. If you want the batch job to automatically adjust suggested item prices, enter the adjustment in **Adjustment Factor** field. For example, you would enter 1.15 in **Adjustment Factor** for 15% increase in item price.  
6. If you want the batch job to create new prices, turn on the **Create New Prices** toggle.  
7. Choose the **OK** button to fill in the lines on the **Sales Price Worksheet** page with the suggested new prices.
8. To implement the suggestions, use the **Implement Price Changes** action. The batch job creates suggestions but doesn't implement them. 

#### [New Experience](#tab/new-experience/)

To update prices for multiple items, you must create a new price list, and then copy the lines from an existing price list. When you copy the lines you can use filters to specify what to copy, and you can specify an integer or decimal number in the **Adjustment Factor** field to increase or decrease prices. The price list must be in the **Draft** status. If needed, you can then deactivate the old price list.

> [!NOTE]
> You can't have two lines that have the same settings but different prices. If that happens, a message will display when you activate a price list. You can choose the price to use by opening the list and deleting the incorrect price.  

---

## Best Price Calculation

After you record special prices and line discounts for sales and purchases, [!INCLUDE[prod_short](includes/prod_short.md)] calculates the best price on sales and purchase documents, and on job and item journal lines.

The best price is the lowest price with the highest line discount allowed on a given date. [!INCLUDE[prod_short](includes/prod_short.md)] calculates best prices when it adds unit prices and the line discount percentages on document and journal lines.

> [!NOTE]  
> The following describes how the best price is calculated for sales. For purchases, the calculation is similar but is based on the available parameters. For example, item discount groups are not supported for purchasing.

1. [!INCLUDE[prod_short](includes/prod_short.md)] checks the combination of the bill-to customer and the item and then calculates the applicable unit price and line discount percentage, using the following criteria:

    * Does the customer have a price/discount agreement, or does the customer belong to a group that does?
    * Is the item or the item discount group on the line included in any of these price/discount agreements?
    * Is the order date (or the posting date for the invoice and credit memo) within the starting and ending date of the price/discount agreement?
    * Is a unit of measure code specified? If so, [!INCLUDE[prod_short](includes/prod_short.md)] checks for prices/discounts with the same unit of measure code, and prices/discounts with no unit of measure code.

2. [!INCLUDE[prod_short](includes/prod_short.md)] checks whether any price/discount agreements apply to information on the document or journal line. It then inserts the applicable unit price and line discount percentage using the following criteria:

    * Is there a minimum quantity requirement in the price/discount agreement that is fulfilled?
    * Is there a currency requirement in the price/discount agreement that is fulfilled? If so, the lowest price and the highest line discount for that currency are inserted, even if local currency would provide a better price. If there's no price/discount agreement for the specified currency code, [!INCLUDE[prod_short](includes/prod_short.md)] inserts the lowest price and the highest line discount in your local currency.

If no special price can be calculated for the item on the line, then either the last direct cost or the unit price from the item card is inserted.

## Sales Invoice Discounts and Service Charges

When you use invoice discounts, the total amount on the invoice determines the size of the discount that is granted. On the **Cust. Invoice Discounts** page, you can also add a service charge to invoices over a certain amount.  

Before you can use invoice discounts with sales, you must specify certain information. You must make the following decisions:  

* Which customers will be granted this type of discount?  
* Which discount percentages you'll use?  

If you want invoice discounts to be calculated automatically, on the **Sales & Receivables Setup** page, turn on the **Calc Inv. Discount** toggle.  

You can specify whether you'll grant invoice discounts when an invoice meets certain criteria for each customer. For example, when the invoice amount is large enough. Invoice discounts can be in local currency for domestic customers, or in foreign currency for foreign customers.  

You link discount percentages to specific invoice amounts on the **Cust. Invoice Discounts** page for each customer. You can enter any number of percentages. Each customer can have their own page, or you can link several customers to the same page.  

In addition to, or instead of, a discount percentage, you can link a service charge amount to a specific invoice amount.  

> [!TIP]  
> Before you enter this information, it is a good idea to prepare an outline of the discount structure that you want to use. This makes it easier to see which customers can be linked to the same invoice discount page. The fewer pages you have to set up, the faster you can enter the basic information.

For training in discounts in sales, see [Set up discounts for your customers](/learn/modules/customer-discounts-dynamics-365-business-central/index) at Microsoft Learn.  

### Calculating Invoice Discounts on Sales

[!INCLUDE [sales-invoice-discounts](includes/sales-invoice-discounts.md)]

## To set up a sales line discount for a customer
These steps differ, depending on whether your administrator has turned on the **New sales pricing experience** feature update. If the feature update isn't turned on, follow the steps on the Current Experience tab.

#### [Current Experience](#tab/current-experience/)  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.
2. Open the relevant customer card, and then choose the **Line Discounts** action.
3. Fill in the fields on the line as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] Fill a line for each combination that will grant a sales line discount to the customer.

> [!NOTE]
> When you open the **Sales Prices** and **Sales Line Discounts** pages from a specific customer, the **Sales Type Filter** and **Sales Code Filter** fields are set for the customer and can't be changed or removed.
>
> To set up prices or line discounts for all customers, a customer price group, or a campaign, you must open the pages from an item card. Alternatively, for sales prices, use the **Sales Price Worksheet** page. For more information, see [To bulk update item prices](sales-how-record-sales-price-discount-payment-agreements.md#to-bulk-update-item-prices).  

#### [New Experience](#tab/new-experience/)  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.
2. Choose the customer, and then choose the **Sales Price Lists** action.
3. Open the price list for which to specify the line discount.
4. Create a new line, or choose an existing line, and then fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
5. In the **Defines** field, choose either **Price & Discount**, or just **Discount**. 
6. In the **Line Discount %** field, specify the discount percentage.

    > [!TIP]
    > If you're editing an existing line, you can filter the lines by choosing the appropriate option in the **View Columns for** field.

    > [!NOTE]  
    > Invoice discount codes are represented by existing customer cards. This enables you to quickly assign invoice discount terms to customers by picking the name of another customer who will have the same terms. To set up customer-specific invoice discount terms, set the **Invoice Disc. Code** field to the customer's customer code, and then proceed to the next step.

---

## To set up an invoice discount for a customer
After you decide which customers are eligible for invoice discounts, enter the invoice discount code on the Customer Card pages. Then set up the terms for each code.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.
2. Open the customer page for a customer that will be eligible for invoice discounts.
3. In the **Invoice Disc. Code** field, select a code for the relevant invoice discount terms to use to calculate invoice discounts for the customer. <!--Looks like I can only choose customers in this list-->

> [!NOTE]  
> Invoice discount codes are represented by existing customer cards. This enables you to quickly assign invoice discount terms to customers by picking the name of another customer who will have the same terms.

Proceed to set up new the sales invoice discount terms.

1. On the **Customers** page, choose the **Invoice Discounts** action. The **Cust. Invoice Discounts** page opens.
2. In the **Currency Code** field, enter the code for a currency that the invoice discount terms on the line applies to. Leave the field blank to set up invoice discount terms in USD.
3. In the **Minimum Amount** field, enter the minimum amount that an invoice must have to be eligible for the discount.
4. In the **Discount %** field, enter the invoice discount as a percentage of the invoice amount.
5. Repeat steps 5 through 7 for each currency that the customer will receive a different invoice discount for.

## See Related Training at [Microsoft Learn](/learn/modules/manage-sales-prices-dynamics-365-business-central/index)

## See Also

[Setting Up Sales](sales-setup-sales.md)  
[Sales](sales-manage-sales.md)  
[Setting Up Customer Price Groups](sales-how-to-set-up-customer-price-groups.md)  
[Setting Up Customer Discount Groups](sales-how-to-set-up-customer-discount-groups.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]