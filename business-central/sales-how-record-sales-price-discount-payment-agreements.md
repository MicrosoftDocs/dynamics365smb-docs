---
title: Set Up Sales Prices and Discounts for Customers | Microsoft Docs
description: Describes how to set up and apply pricing and discount agreements for sales documents.
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: special price, alternate price, pricing
ms.search.form: 1345, 7002, 7007, 7015, 7016, 7023
ms.date: 04/01/2021
ms.author: bholtorf

---
# Record Sales Prices and Discounts
> [!NOTE]
> In 2020 release wave 2 we released streamlined processes for setting up and managing prices and discounts. If you're a new customer using that version, you're using the new experience. If you're an existing customer, whether you are using the new experience depends on whether your administrator has enabled the **New sales pricing experience** feature update in **Feature Management**. For more information, see [Enabling Upcoming Features Ahead of Time](/dynamics365/business-central/dev-itpro/administration/feature-management).

[!INCLUDE[prod_short](includes/prod_short.md)] supports various pricing strategies, ranging from one-price-fits-all models where an item is always sold at the same price, to special price agreements with specific customers, groups of customers, or special offers when you're running a sales campaign. For example, you might offer a special price on a sales order under the following conditions:

* When it's for a minimum quantity
* It's for a certain type of item  
* If it's created during a specific period of time

To use a basic pricing model, you only need to specify a unit price for an item or resource. That price will always be used on sales documents. For more advanced models, for example, when you are running a sales campaign and want to offer special prices, you can specify criteria for that on the **Sales Prices** page. You can offer special prices based on combinations of the following: 

* Customer
* Item
* Unit of measure
* Minimum quantity
* Date ranges that define when the prices are valid

Additionally, after you set up special prices, [!INCLUDE[prod_short](includes/prod_short.md)] can automatically calculate the best price on sales and purchase documents and on job and item journal lines. For more information, see [Best Price Calculation](sales-how-record-sales-price-discount-payment-agreements.md#best-price-calculation).  

For sales discounts, you can set up and use the following types:

| Discount Type | Description |
| --- | --- |
| **Sales Line Discount** |An amount that is used on sales lines if a certain combination of customer, item, minimum quantity, unit of measure, or starting and ending dates exists. These combinations work in the same way as for sales prices. |
| **Invoice Discount** |A discount percentage that is subtracted from the sales document total if the sum of all lines on the document exceeds a certain minimum. |

> [!TIP]  
> If an item should never be sold with a discount, leave the discount fields on the item page empty, and do not include the item in any line discount setups.

## To set up a sales price for a customer

These steps differ, depending on whether your administrator has turned on the **New sales pricing experience** feature update. If the feature update is not turned on, follow the steps on the Current Experience tab. 

## [Current Experience](#tab/current-experience)

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.
2. Choose the customer, and then choose the **Prices** action.
3. Fill in the fields on the line as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] Fill a line for each combination that will grant a special sales price to the customer.

## [New Experience](#tab/new-experience)  
By default, the status of new price lists is Draft. Draft price lists are not included in price calculations. When you're done adding lines and want to start using the prices, change the status to Active.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.
2. Choose the customer, and then choose the **Sales Price Lists** action. 
3. Choose **New** to create a new sales price list.
4. On the **General** and **Tax** FastTabs, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
5. You can add items to the list in the following ways:
   * To add many items, choose **Suggest Lines**, and then enter filter criteria to specify the types of items to add. Optionally, you can enter other settings for the items. These settings are specific to the price list. You can change them later, if needed.
   * To copy items from another price list, choose **Copy Lines**, and then choose the price list to copy.
   * To add items manually, in the **Product Type** field on a line, choose the type of product that the price list is for. Depending on your selection, fill in the remaining fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
6. To start using the price list, in the **Status** field, choose **Active**.  

---

## Using Sales and Purchase Price Lists
> [!NOTE]
> Using price lists requires that your administrator has enabled the **New sales pricing experience** feature update in **Feature Management**. For more information, see [Enabling Upcoming Features Ahead of Time](/dynamics365/business-central/dev-itpro/administration/feature-management).

The **Applies-to Type** and **Applies-to No.** fields let you choose what a price list will apply to, such as customer or customer price group. Use the **View Columns for** field to show columns that are relevant only for prices, discounts, or prices and discounts.

### Converting Existing Prices When You Turn On the Pricing Feature Update
When you enable the **New sales pricing experience** feature update on the **Feature Management** page, the **Feature Data Update** guide opens. Use the **Use default prices** toggle as follows:

* If you want to work with all prices on a single page, turn it on. Existing prices are converted to one default price list for each of the following:

    * Sales
    * Purchases
    * Job sales
    * Job purchases 

    Afterward, you can edit all prices for these areas on the **Prices Worksheet** page. The default price lists are set on the **Sales & Receivables Setup**, **Purchases & Payables Setup**, and **Jobs Setup** pages. 

    > [!NOTE]
    > If prices are set only on item or resource cards, default price lists will not be filled in with those prices during data update. However, you can open any of default price lists or the Price Worksheet page and use the **Suggest Lines** action to add the prices set on item or resource cards. 

* To use sales price lists, turn it off. Existing prices will be converted to a new price list for each combination of customer, customer group, or campaign, and the starting and ending dates and currencies. If you have many combinations, you will have many price lists.

If you have already enabled the New Pricing Experience, you can create default price lists manually or specify an existing price list as the default. To set an existing price list as default, turn on the **Allow Updating Defaults** toggle on the price list. Then, on the **Sales & Receivables Setup**, **Purchase & Payables** or **Jobs Setup** pages, set the price list as the default.

## Editing Active Price Lists
To allow people to edit prices on active price lists for items, resources, customers, vendors, or other entities that use pricing, turn on the **Allow Editing Active Price** toggle on the **Sales & Receivables Setup** and **Purchase & Payables Setup** pages. 

When the **Allow Editing Active Price** toggle is turned off, to update prices in a price list you must change the status of the price list to **Draft**, make your change, and then reactivate the price list.

The **Prices Overview** page provides an overview of all prices across price lists. You can set filters to narrow down the list. After you change prices, you must use the **Verify Lines** action to verify the prices against other price list lines. For example, verifying the prices helps avoid duplicate or conflicting prices. 

> [!NOTE]
> When you edit a line in an active price list the status of the line becomes Draft, and the line will not be included in price calculations until you use the **Verify lines** action. After you verify the price, the line's status becomes Active and it will be used in price calculations.

To add new prices, on the **Prices Overview** page, use the **Add New Lines** action. The **Prices Worksheet** page opens, where you add price lines in the following ways:

* By suggesting them based on criteria
* Copying them from other price lists
* Manually entering them. 

Afterward, you can use the **Implement Price Change** action to compare the new prices with other price lists to avoid duplicates.

## To copy sales prices
These steps differ, depending on whether your administrator has turned on the **New sales pricing experience** feature update. If the feature update is not turned on, follow the steps on the Current Experience tab.

## [Current Experience](#tab/current-experience)  

If you want to copy sales prices, such as an individual customer's sales prices to use for a customer price group, you must run the **Suggest Sales Price on Wksh.** batch job on the **Sales Price Worksheet** page.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Price Worksheet**, and then choose the related link.  
2. Choose the **Suggest Sales Price on Wksh.** action.  
3. On the **Sales Prices** FastTab, fill in the **Sales Type** and **Sales Code** fields with the original sales prices you want to copy.  
4. In the top section of the request page, fill in the **Sales Type** and **Sales Code** fields with the type and name you want the sales prices copied to.  
5. If you want the batch job to create new prices, select the **Create New Prices** check box.  
6. Choose the **OK** button to fill in the lines on the **Sales Price Worksheet** page with the suggested new prices, indicating that they are valid for the selected sales type.  

   > [!NOTE]  
   > This batch job only creates suggestions and it does not implement the suggested changes. If you are satisfied with the suggestions and want to implement them, that is insert them on the **Sales Prices** page, choose the **Implement Price Changes** action on the **Sales Price Worksheet** page.

## [New Experience](#tab/new-experience)  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Price Lists**, and then choose the related link. 
2. Choose the price list to copy, and then choose **Copy Lines**.
3. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

   > [!NOTE]
   > You cannot have two lines that have the same settings but different prices. If that happens, a message will display when you activate a price list. You can choose the price to use by opening the list and deleting the incorrect price.  
  
---

## To bulk update item prices
These steps differ, depending on whether your administrator has turned on the **New sales pricing experience** feature update. If the feature update is not turned on, follow the steps on the Current Experience tab.

### [Current Experience](#tab/current-experience)

If you want to bulk update item prices, such as increase all item prices by some percentage, you can fill in the **Sales Price Worksheet** by using the following batch jobs:

* **Suggest Item Price on Wksh.** suggests changes by applying an adjustment factor to existing sales prices, or by copying existing sales price agreements to other customer, customer price groups, or sales campaigns.
* **Suggest Item Price on Wksh.** suggests changes by applying an adjustment factor to existing unit prices on item cards, or by suggesting prices for new combinations of currency, units of measure, and so on. The unit prices on items are not changed.    

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Price Worksheet**, and then choose the related link.  
2. Choose the **Suggest Item Price on Wksh.** action.  
3. On the **Item** FastTab, fill in the **No.** or **Inventory Posting Group** or other fields with the original item prices you want to update.  
4. In the top section of the request page, fill in the **Sales Type** and **Sales Code** with the type and name you want the sales prices copied to.
5. If you want the batch job to automatically adjust suggested item prices, enter the adjustment in **Adjustment Factor** field. For example, you would enter **1.15** in the **Adjustment Factor** for a **15%** increase in the item price.  
6. If you want the batch job to create new prices, turn on the **Create New Prices** toggle.  
7. Choose **OK** to fill in the lines on the **Sales Price Worksheet** page with the suggested new prices.
8. To implement the suggestions, use the **Implement Price Changes** action. The batch job creates suggestions but does not implement them.

## [New Experience](#tab/new-experience)

To update prices for multiple items, you must create a new price list, and then copy the lines from an existing price list. When you copy the lines you can use filters to specify what to copy, and you can specify an integer or decimal number in the **Adjustment Factor** field to increase or decrease prices. The price list must be in the **Draft** status. If needed, you can then deactivate the old price list.

> [!NOTE]
> You cannot have two lines that have the same settings but different prices. If that happens, a message will display when you activate a price list. You can choose the price to use by opening the list and deleting the incorrect price.  

---

## Sales Invoice Discounts and Service Charges
When you use invoice discounts, the total amount on the invoice determines the size of the discount that is granted. On the **Cust. Invoice Discounts** page, you can also add a service charge to invoices over a certain amount.  

If you want invoice discounts to be calculated automatically, on the **Sales & Receivables Setup** page, turn on the **Calc Inv. Discount** toggle.  

For each customer, you can specify whether you will offer invoice discounts if the criteria are met. For example, if the invoice amount is large enough. You can define the terms of the invoice discount in local currency for domestic customers and in foreign currency for foreign customers.  

You link discount percentages to specific invoice amounts in the **Cust. Invoice Discounts** page for each customer. You can enter any number of percentages. Each customer can have their own page, or you can link several customers to the same page.  

In addition to, or instead of, a discount percentage, you can link a service charge amount to a specific invoice amount.  

For training in discounts in sales, see [Set up discounts for your customers](/learn/modules/customer-discounts-dynamics-365-business-central/index) at Microsoft Learn.  

### Calculating Invoice Discounts on Sales

[!INCLUDE [sales-invoice-discounts](includes/sales-invoice-discounts.md)]

## To set up a sales line discount for a customer
These steps differ, depending on whether your administrator has turned on the **New sales pricing experience** feature update. If the feature update is not turned on, follow the steps on the Current Experience tab.

## [Current Experience](#tab/current-experience)  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.
2. Open the relevant customer card, and then choose the **Line Discounts** action.
3. Fill in the fields on the line as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] Fill a line for each combination that will grant a sales line discount to the customer.

> [!Note]
> When you open the **Sales Prices** and **Sales Line Discounts** pages from a specific customer, the **Sales Type Filter** and **Sales Code Filter** fields are set for the customer and cannot be changed or removed.
>
> To set up prices or line discounts for all customers, a customer price group, or a campaign, you must open the pages from an item card. Alternatively, for sales prices, use the **Sales Price Worksheet** page. For more information, see [To bulk update item prices](sales-how-record-sales-price-discount-payment-agreements.md#to-bulk-update-item-prices).  

## [New Experience](#tab/new-experience)  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.
2. Choose the customer, and then choose the **Sales Price Lists** action.
3. Open the price list for which to specify the line discount.
4. Create a new line, or choose an existing line, and then fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
5. In the **Defines** field, choose either **Price & Discount**, or just **Discount**. 
6. In the **Line Discount %** field, specify the discount percentage.

   > [!TIP]
   > You can filter the lines by choosing the appropriate option in the **View Columns for** field.   
  
   > [!NOTE]
   > Invoice discount codes are represented by existing customer cards. Using customer names as codes enables you to quickly assign invoice discount terms to customers by picking the name of another customer who will have the same terms. To set up customer-specific invoice discount terms, set the **Invoice Disc. Code** field to the customer's customer code, and then proceed to the next step.

---

## To set up an invoice discount for a customer
When you have decided which customers are eligible for invoice discounts, enter the invoice discount code on the customer cards and set up the terms for each code.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.
2. Open the customer page for a customer that will be eligible for invoice discounts.
3. In the **Invoice Disc. Code** field, select a code for the relevant invoice discount terms to use to calculate invoice discounts for the customer. 

> [!NOTE]  
> Invoice discount codes are represented by existing customer cards. Using customer names as codes lets you to quickly assign invoice discount terms to customers by picking the name of another customer who will have the same terms.

Now set up the sales invoice discount terms.

1. On the **Customers** page, choose the **Invoice Discounts** action. The **Cust. Invoice Discounts** page opens.
2. In the **Currency Code** field, enter the code for a currency that the invoice discount terms on the line applies to. Leave the field blank to set up invoice discount terms in USD.
3. In the **Minimum Amount** field, enter the minimum amount that an invoice must have to be eligible for the discount.
4. In the **Discount %** field, enter the invoice discount as a percentage of the invoice amount.
5. Repeat steps 5 through 7 for each currency that the customer will receive a different invoice discount for.

## Best Price Calculation
When you have recorded special prices and line discounts for sales and purchases, [!INCLUDE[d365fin](includes/d365fin_md.md)] ensures that your profit on item trade is always optimal by automatically calculating the best price on sales and purchase documents and on job and item journal lines.

The best price is the lowest permissible price with the highest permissible line discount on a given date. [!INCLUDE[d365fin](includes/d365fin_md.md)] automatically calculates this when it inserts the unit price and the line discount percentage for items on new document and journal lines.

> [!NOTE]  
> The following describes how the best price is calculated for sales. The calculation is the same for purchases.

1. [!INCLUDE[d365fin](includes/d365fin_md.md)] checks the combination of the bill-to customer and the item and then calculates the applicable unit price and line discount percentage, using the following criteria:

    - Does the customer have a price/discount agreement, or does the customer belong to a group that does?
    - Is the item or the item discount group on the line included in any of these price/discount agreements?
    - Is the order date (or the posting date for the invoice and credit memo) within the starting and ending date of the price/discount agreement?
    - Is a unit of measure code specified? If so, [!INCLUDE[d365fin](includes/d365fin_md.md)] checks for prices/discounts with the same unit of measure code, and prices/discounts with no unit of measure code.

2. [!INCLUDE[d365fin](includes/d365fin_md.md)] checks whether any price/discount agreements apply to information on the document or journal line, and then inserts the applicable unit price and line discount percentage using the following criteria:

    - Is there a minimum quantity requirement in the price/discount agreement that is fulfilled?
    - Is there a currency requirement in the price/discount agreement that is fulfilled? If so, the lowest price and the highest line discount for that currency are inserted, even if local currency would provide a better price. If there is no price/discount agreement for the specified currency code, [!INCLUDE[d365fin](includes/d365fin_md.md)] inserts the lowest price and the highest line discount in your local currency.

If no special price can be calculated for the item on the line, then either the last direct cost or the unit price from the item card is inserted.

## See Related Training at [Microsoft Learn](/learn/modules/manage-sales-prices-dynamics-365-business-central/index)

## See Also

[Setting Up Sales](sales-setup-sales.md)  
[Sales](sales-manage-sales.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]