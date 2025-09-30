---
title: Record special sales prices and discounts
description: Describes how to define pricing and discount agreements for sales documents.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 05/29/2024
ms.custom: bap-template
ms.search.keywords: special price, alternate price, pricing
ms.search.form: 7022, 7024
ms.service: dynamics-365-business-central
---

# Record special sales prices and discounts

> [!NOTE]
> 2020 release wave 2 introduced new, streamlined processes for setting up and managing prices and discounts. If you're a new customer using the latest version, you're using the new experience. If you're an existing customer, whether you're using the new experience depends on whether your administrator enabled the **New sales pricing experience** feature update in **Feature Management**. Learn more at [Enabling Upcoming Features Ahead of Time](/dynamics365/business-central/dev-itpro/administration/feature-management) in the administration content.

[!INCLUDE[prod_short](includes/prod_short.md)] supports various pricing strategies, such as:

* One-price-fits-all models where an item is always sold at the same price.
* Special price agreements with specific customers, or groups of customers.
* Campaigns when a sale meets the criteria for a special offer. For example, you might have the following criteria for an order:

  * It meets a minimum quantity
  * It's before a certain date
  * It includes a certain type of item  

To use a basic pricing model, you only need to specify a unit price when you set up an item or resource. That price is always used for the item on sales documents. For more advanced models, for example, when you want to offer special prices for a sales campaign, you can specify criteria on the **Sales Prices** page. You can offer special prices based on a combination of the following information:  

* Customer
* Item
* Unit of measure
* Minimum quantity
* Dates that define the period for which the prices are valid.

After you set up special prices, [!INCLUDE[prod_short](includes/prod_short.md)] can calculate best prices on sales and purchase documents, and on lines on projects and item journals. Learn more at [Best Price Calculation](sales-how-record-sales-price-discount-payment-agreements.md#best-price-calculation).

For sales discounts, you can set up two types:

| Discount Type | Description |
| --- | --- |
| **Sales Line Discount** |Add an amount on sales lines that have a specific combination of information. For example, customer, item, minimum quantity, unit of measure, or starting and ending date. This type works in the same way as for sales prices. |
| **Invoice Discount** |A discount percentage that is subtracted from the sales document total if the sum of all lines on the document exceeds a certain minimum. |

> [!TIP]  
> If an item should never be sold with a discount, leave the discount fields on the item page empty, and don't include the item in any line discount setups.

## To set up a sales price for a customer

These steps differ, depending on whether your administrator turned on the **New sales pricing experience** feature update. If the feature update isn't turned on, follow the steps on the Current Experience tab. 

#### [Current experience](#tab/current-experience/)

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.
2. Choose the customer, and then choose the **Prices** action.
3. Fill in the fields on the line as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] Fill a line for each combination that grants a special sales price to the customer.

#### [New experience](#tab/new-experience/)  

By default, the status of new price lists is **Draft**. Draft price lists aren't included in price calculations. When you're done adding lines and want to start using the prices, change the status to **Active**.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.
2. Choose the customer, and then choose the **Sales Price Lists** action. 
3. Choose **New** to create a new sales price list.
4. On the **General** and **Tax** FastTabs, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
5. To add items to the list, do one of the following steps:
   * To add many items, choose **Suggest Lines**, and then enter filter criteria to specify the types of items to add. Optionally, you can enter other settings for the items that are specific to the price list. You can change these settings later if needed.
   * To copy items from another price list, choose **Copy Lines**, and then choose the price list to copy.
   * To add items manually, in the grid, in the **Product Type** field, choose the type of product that the price list is for. Depending on your selection, fill in the remaining fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
6. To start using the price list, in the **Status** field, choose **Active**.  

---

## Using sales and purchase price lists

> [!NOTE]
> Using price lists requires that your administrator enabled the **New sales pricing experience** feature update in **Feature Management**. Learn more at [Enabling Upcoming Features Ahead of Time](/dynamics365/business-central/dev-itpro/administration/feature-management) in the administration content.

Most of the new sales pricing experience is similar to the current experience, but there are a few differences. Those differences are described in the following sections.

The **Applies-to Type** and **Applies-to No.** fields let you choose what a price list applies to, such as customer or customer price group. Using **View Columns for**, you can show or hide columns relevant for setting prices, discounts, or prices and discounts.

### Converting existing prices when you turn on the pricing feature update

When you enable the **New sales pricing experience** feature update on the **Feature Management** page, the **Feature Data Update** guide opens. Use the **Use default prices** toggle as follows:

* If you want to work with all prices on a single page, turn it on. Existing prices convert to one default price list for each of the following documents:

  * Sales
  * Purchases
  * Job sales
  * Job purchases

  You can edit all prices for these areas on the **Prices Worksheet** page. You set the default price lists on the **Sales & Receivables Setup**, **Purchases & Payables Setup,** and **Projects Setup** pages.

> [!NOTE]
> If prices are set only on item or resource cards, default price lists aren't updated with those prices during the data update. However, you can open any of the default price lists or the **Price Worksheet** page and use the **Suggest Lines** action to add the prices set on item or resource cards.

* To use sales price lists, turn it off. Existing prices convert to a new price list for each combination of the following things:

  * Customer
  * Customer group or campaign
  * Starting and ending dates
  * Currencies

If you have many combinations, you get many price lists.

If you already enabled the New Pricing Experience, you can create default price lists manually or specify an existing price list as the default. To set an existing price list as default, turn on the **Allow Updating Defaults** toggle on the price list. Then, on the **Sales & Receivables Setup**, **Purchase & Payables**, or **Projects Setup** pages, set the price list as the default.

### Editing active price lists

To allow people to edit prices on active price lists for items, resources, customers, vendors, or other entities that use pricing, turn on the **Allow Editing Active Price** toggle on the **Sales & Receivables Setup** and **Purchase & Payables Setup** pages.

When the **Allow Editing Active Price** toggle is turned off, to update prices in a price list you must change the status of the price list to **Draft**, make your change, and then reactivate the price list.

The **Prices Overview** page provides an overview of all prices across price lists. You can set filters to narrow down the list of prices you might want to modify or add to. After you modify prices, you must use the **Verify Lines** action to verify the prices against other price list lines. Verifying prices helps avoid duplicates and ambiguity during price calculation.

> [!NOTE]
> When you edit a line in an active price list the status of the line becomes **Draft**, and the line isn't considered during price calculation until you use the **Verify Lines** action. After you verify the price, the status of the line becomes **Active** and it is considered in price calculations.

To add new prices, on the **Prices Overview** page, use the **Add New Lines** action. The **Prices Worksheet** page opens, and you can add price lines either by suggesting them based on criteria, copying them from other price lists, or manually entering them. Afterward, you can use the **Implement Price Change** action to compare the new prices with other price lists to avoid duplicates and ambiguity during price calculation.

#### Create sales price lines based on the unit price

1. On the **Prices Worksheet** page, choose the **Suggest Lines** action.
2. On the **Price Lines - Create new** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. On the **Product filter** field, define filters for the selected **Product Type**.
4. Choose the **Defaults** field to specify settings such as:
   * Which entities the price list is assigned to.
   * Dates when the price is valid.
   * The currency code.
   * The amount type filter that defines the columns shown on the price list lines.
5. Choose **OK**. New lines are added to the **Price Worksheet** page with the selected settings and the unit prices from the item cards.
6. Edit the created lines with the new unit prices or discounts. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

#### Create sales price lines based on existing price lists

1. On the **Prices Worksheet** page, choose the **Copy Lines** action.
2. On the **Price Lines - Copy existing** page, select an existing price list on the **From Price List** field.
3. On the **Price Line filter** field, define filters for the products on the selected price list.
4. Choose the **Defaults** field to specify settings such as:
   * Which entities the price list is assigned to.
   * Dates when the price is valid.
   * The currency code.
   * The amount type filter that defines the columns shown on the price list lines.
5. Fill in the other fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
6. Choose **OK**. New lines are added to the **Price Worksheet** page with the selected settings.
7. Edit the created lines with the new unit prices or discounts. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## To copy sales prices

These steps differ, depending on whether your administrator turned on the **New sales pricing experience** feature update. If the feature update isn't turned on, follow the steps on the Current Experience tab.

#### [Current experience](#tab/current-experience/)  

If you want to copy sales prices, such as an individual customer's sales prices to use for a customer price group, you must run the **Suggest Sales Price on Wksh.** batch job on the **Sales Price Worksheet** page.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Price Worksheet**, and then choose the related link.  
2. Choose the **Suggest Sales Price on Wksh.** action.  
3. On the **Sales Prices** FastTab, fill in the **Sales Type** and **Sales Code** fields with the original sales prices you want to copy.  
4. In the top section of the request page, fill in the **Sales Type** and **Sales Code** fields with the type and name you want the sales prices copied to.  
5. If you want the batch job to create new prices, select the **Create New Prices** checkbox.  
6. Choose the **OK** button to fill in the lines on the **Sales Price Worksheet** page with the suggested new prices, indicating that they're valid for the selected sales type.  

   > [!NOTE]  
   > This batch job only creates suggestions and it doesn't implement the suggested changes. If you're satisfied with the suggestions and want to implement them, that is insert them on the **Sales Prices** page, choose the **Implement Price Changes** action on the **Sales Price Worksheet** page.

#### [New experience](#tab/new-experience/)  

You can specify the settings that the price list uses:

* Use the settings from the header on the list you're copying.
* Use the settings from the list you're copying to. To use the settings from the price list you're copying prices to, turn on the **Use defaults from target** toggle.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Price Lists**, and then choose the related link.
2. Choose the price list to copy, and then choose **Copy Lines**.
3. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

   > [!NOTE]
   > You can't have two items that have the same settings but different prices. If that happens, a message displays when you activate the price list. You can choose the price to use by opening the list and deleting the incorrect price.  
  
---

## Bulk update item prices

These steps differ, depending on whether your administrator turned on the **New sales pricing experience** feature update. If the feature update isn't turned on, follow the steps on the Current Experience tab.

#### [Current experience](#tab/current-experience/)

To bulk update item prices, such as increase all prices by a percentage, you can fill in the Sales Price Worksheet page by using the following batch jobs:

* **Suggest Sales Price on Wksh.** suggests changes in one of two ways:

  * By applying an adjustment factor to existing sales prices.
  * By copying existing sales price agreements to other customers, customer price groups, or sales campaigns.

* **Suggest Item Price on Wksh.** suggests changes in one of two ways:

  * By applying an adjustment factor to existing unit prices on item cards.
  * By suggesting prices for new combinations of currency, units of measure, and so on.

  This batch job doesn't change the unit prices on items.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Price Worksheet**, and then choose the related link.  
2. Choose the **Suggest Item Price on Wksh.** action.  
3. On the **Item** FastTab, fill in the **No.** or **Inventory Posting Group** or other fields with the original item prices you want to update.  
4. In the top section of the request page, fill in the **Sales Type** and **Sales Code** with the type and name you want the sales prices copied to.
5. If you want the batch job to automatically adjust suggested item prices, enter the adjustment in the **Adjustment Factor** field. For example, you would enter 1.15 in **Adjustment Factor** for a 15% increase in item price.  
6. If you want the batch job to create new prices, turn on the **Create New Prices** toggle.  
7. Choose the **OK** button to fill in the lines on the **Sales Price Worksheet** page with the suggested new prices.
8. To implement the suggestions, use the **Implement Price Changes** action. The batch job creates suggestions but doesn't implement them.

#### [New experience](#tab/new-experience/)

To update prices for multiple items, you must create a new price list, and then copy the lines from an existing price list. When you copy the lines you can use filters to specify what to copy, and you can specify an integer or decimal number in the **Adjustment Factor** field to increase or decrease prices. The price list must be in the **Draft** status. If needed, you can then deactivate the old price list.

> [!NOTE]
> You can't have two lines that have the same settings but different prices. If that happens, a message displays when you activate a price list. You can choose the price to use by opening the list and deleting the incorrect price.  

> [!TIP]
> Another way to do bulk changes is to use the Edit in Excel action. If you use Excel, there are some specific steps to follow. To learn more, go to [Add or edit lines on price lists using Edit in Excel](#add-or-edit-lines-on-price-lists-using-edit-in-excel).

---

## Best price calculation

After you record special prices and line discounts for sales and purchases, [!INCLUDE[prod_short](includes/prod_short.md)] calculates the best price on the following documents and journals:

* Sales and purchase documents
* Project and item journal lines

The best price is the lowest price with the highest line discount allowed on a given date. [!INCLUDE[prod_short](includes/prod_short.md)] calculates best prices when it adds unit prices and the line discount percentages on document and journal lines.

> [!NOTE]  
> The following steps describe how [!INCLUDE [prod_short](includes/prod_short.md)] calculates the best price for sales. For purchases, the calculation is similar but is based on the available parameters. For example, item discount groups aren't supported for purchasing.

1. [!INCLUDE[prod_short](includes/prod_short.md)] checks the combination of the bill-to customer and the item and then calculates the applicable unit price and line discount percentage, using the following criteria:

    * Does the customer have a price/discount agreement, or does the customer belong to a group that does?
    * Is the item or the item discount group on the line included in any of these price/discount agreements?
    * Is the date within the starting and ending date of the price/discount agreement? For invoices and credit memos, this date is the date in the **Posting Date** field on the document header. For all other documents, it's the date in the **Order Date** field on their headers.
    * Is a unit of measure code specified? If so, [!INCLUDE[prod_short](includes/prod_short.md)] checks for prices/discounts with the same unit of measure code, and prices/discounts with no unit of measure code.

2. [!INCLUDE[prod_short](includes/prod_short.md)] checks whether any price/discount agreements apply to information on the document or journal line. It then inserts the applicable unit price and line discount percentage using the following criteria:

    * Is there a minimum quantity requirement in the price/discount agreement that is fulfilled?
    * Is there a currency requirement in the price/discount agreement that is fulfilled? If so, the lowest price and the highest line discount for that currency are inserted, even if local currency would provide a better price. If there's no price/discount agreement for the specified currency code, [!INCLUDE[prod_short](includes/prod_short.md)] inserts the lowest price and the highest line discount in your local currency.

If no special price can be calculated for the item on the line, then either the last direct cost or the unit price from the item card is inserted.

## Sales invoice discounts and service charges

When you use invoice discounts, the total amount on the invoice determines the size of the discount that you grant. On the **Cust. Invoice Discounts** page, you can also add a service charge to invoices over a certain amount.  

Before you can use invoice discounts with sales, you must specify certain information. You must make the following decisions:  

* Which customers get this type of discount?  
* Which discount percentages do you use?  

If you want invoice discounts to be calculated automatically, on the **Sales & Receivables Setup** page, turn on the **Calc Inv. Discount** toggle.  

You can specify whether you grant invoice discounts when an invoice meets certain criteria for each customer. For example, when the invoice amount is large enough. Invoice discounts can be in local currency for domestic customers, or in foreign currency for foreign customers.  

You link discount percentages to specific invoice amounts on the **Cust. Invoice Discounts** page for each customer. You can enter any number of percentages. Each customer can have their own page, or you can link several customers to the same page.  

In addition to, or instead of, a discount percentage, you can link a service charge amount to a specific invoice amount.  

> [!TIP]  
> Before you enter this information, it's a good idea to prepare an outline of the discount structure that you want to use. The structure makes it easier to determine which customers can be linked to the same invoice discount page. The fewer pages you have to set up, the faster you can enter the basic information.

For training in discounts in sales, see [Set up discounts for your customers](/training/modules/customer-discounts-dynamics-365-business-central/index).

### Calculating invoice discounts on sales

[!INCLUDE [sales-invoice-discounts](includes/sales-invoice-discounts.md)]

## To set up a sales line discount for a customer

These steps differ, depending on whether your administrator turned on the **New sales pricing experience** feature update. If the feature update isn't turned on, follow the steps on the Current Experience tab.

#### [Current experience](#tab/current-experience/)  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.
2. Open the relevant customer card, and then choose the **Line Discounts** action.
3. Fill in the fields on the line as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] Fill a line for each combination that grants a sales line discount to the customer.

> [!NOTE]
> When you open the **Sales Prices** and **Sales Line Discounts** pages from a specific customer, the **Sales Type Filter** and **Sales Code Filter** fields are set for the customer and can't be changed or removed.
>
> To set up prices or line discounts for all customers, a customer price group, or a campaign, you must open the pages from an item card. Alternatively, for sales prices, use the **Sales Price Worksheet** page. Learn more at [To bulk update item prices](sales-how-record-sales-price-discount-payment-agreements.md#to-bulk-update-item-prices).  

#### [New experience](#tab/new-experience/)  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.
2. Choose the customer, and then choose the **Sales Price Lists** action.
3. Open the price list for which to specify the line discount.
4. Create a new line, or choose an existing line, and then fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
5. In the **Defines** field, choose either **Price & Discount**, or just **Discount**. 
6. In the **Line Discount %** field, specify the discount percentage.

    > [!TIP]
    > If you're editing an existing line, you can filter the lines by choosing the appropriate option in the **View Columns for** field.

    > [!NOTE]  
    > Invoice discount codes are represented by existing customer cards. This connection enables you to quickly assign invoice discount terms to customers by picking the name of another customer with the same terms. To set up customer-specific invoice discount terms, set the **Invoice Disc. Code** field to the customer's customer code, and then proceed to the next step.

---

## To set up an invoice discount for a customer

After you decide which customers are eligible for invoice discounts, enter the invoice discount code on the Customer Card pages. Then set up the terms for each code.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.
2. Open the customer page for a customer that's eligible for invoice discounts.
3. In the **Invoice Disc. Code** field, select a code for the relevant invoice discount terms to use to calculate invoice discounts for the customer.

> [!NOTE]  
> Invoice discount codes are represented by existing customer cards. This connection enables you to quickly assign invoice discount terms to customers by picking the name of another customer with the same terms.

Proceed to set up the new sales invoice discount terms.

1. On the **Customers** page, choose the **Invoice Discounts** action. The **Cust. Invoice Discounts** page opens.
2. In the **Currency Code** field, enter the code for a currency that the invoice discount terms on the line apply to. Leave the field blank to set up invoice discount terms in USD.
3. In the **Minimum Amount** field, enter the minimum amount that an invoice must have to be eligible for the discount.
4. In the **Discount %** field, enter the invoice discount as a percentage of the invoice amount.
5. Repeat steps 5 through 7 for each currency that you give the customer a different invoice discount for.

## Add or edit lines on price lists using Edit in Excel

The Edit in Excel action lets you use Excel to quickly edit and add lines, and then publish your changes back to [!INCLUDE [prod_short](includes/prod_short.md)]. For example, the action is useful when you want to make many changes. To learn more about the Edit in Excel action, go to [Edit in Excel](across-work-with-excel.md#edit-in-excel).

> [!NOTE]
> If you want to add lines to a price list, you must update the Excel spreadsheet as follows:
>
> 1. Choose the price list you want to update, and then use the **Edit in Excel** action to open it in Excel.
> 1. On the new lines for the new price information, fill in the **Line No.** and **Price List Code** fields only. Don't add any other information on the line.
> 1. In the **Microsoft Dynamics Office Add-in** pane, choose **Publish**. After the add-in successfully publishes the change, choose **Refresh**.
> 1. Fill in the remaining fields on the lines. When you're done, choose **Publish** again.

## Related information

[Setting Up Sales](sales-setup-sales.md)  
[Sales](sales-manage-sales.md)  
[Setting Up Customer Price Groups](sales-how-to-set-up-customer-price-groups.md)  
[Setting Up Customer Discount Groups](sales-how-to-set-up-customer-discount-groups.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
