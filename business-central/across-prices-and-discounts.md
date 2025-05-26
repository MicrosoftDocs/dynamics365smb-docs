---
title: Set up prices and discounts
description: Describes how to define standard and special price and discount agreements for sales and purchases.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: price, pricing, discount, discounting, rebate, sale, purchase, invoice
ms.search.form: 459, 460, 7001, 7011, 7015, 7016, 7017, 7018
ms.date: 03/27/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Set up prices and discounts

> [!NOTE]
> In 2020 release wave 2, we released streamlined processes for setting up and managing prices and discounts. If you're a new customer using that version, you're using the new experience. If you're an existing customer, whether you're using the new experience depends on whether your admin enabled the **New sales pricing experience** feature update on the **Feature Management** page. To learn more, go to [Enabling Upcoming Features Ahead of Time](/dynamics365/business-central/dev-itpro/administration/feature-management).

Price and discount strategies for the purchase and sale of items and services are fundamental tools for successful businesses. After you set up the items and services your company buys and sells, you can define what you pay or charge for them. When you select the item or service on sales and purchase documents, [!INCLUDE [prod_short](includes/prod_short.md)] adds the amounts.

## Setting up prices and discounts

Before you create price lists, you must define your pricing and discount strategies on the **Sales & Receivables Setup** and **Purchase & Payables Setup** pages.

You can set up and use two types of discounts:

| Discount Type | Description |
| --- | --- |
| **Line Discount** |A discount amount that is given for lines on sales and purchase documents. Typically, line discounts are based on a combination of customer, item, minimum quantity, unit of measure, or period of time that you define for sales and purchases on the **Sales & Receivables Setup** and **Purchase & Payables Setup** pages.|
| **Invoice Discount** |A discount percentage that is subtracted from sales and purchase document total if the sum of all lines on the document exceeds a certain minimum. |

Because sales prices and sales line discounts are based on a combination of item and customer, you can also set them up on the items to which the rules and values apply.

> [!TIP]  
> If an item should never be sold with a discount, leave the discount fields on the item empty, and don't include the item in any line discount setups.

## About price lists

Price lists are flexible and let you specify the business partner or activity that they apply to. For example, you can set up one price list that applies to all vendors and customers, or offer special prices or discounts for each business partner. Special prices or discounts are often based on a minimum quantity on purchase or sales orders, periods of time, or a certain combination of customer, item, minimum quantity, and unit of measure. The prices and discounts you define automatically apply to purchase and sales documents.

## Set up prices

These steps differ, depending on whether your admin turned on the **New sales pricing experience** feature update.

### [Current Experience](#tab/current-experience)  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.
2. Choose the customer, and then choose the **Prices** action.
3. Fill in the fields on the line as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] Fill a line for each combination that grants a special sales price to the customer.

### [New Experience](#tab/new-experience)  

You can add items and services manually for each line, or you can use the **Suggest Lines** action to create new prices for selected items, item discount groups, resources, and other product types. If you choose **Suggest Lines**, on the **Price Lines - Create New** page you can use filters to select the items or services to include on the price list. You can also specify whether to consider other factors, such as:

* A minimum quantity when calculating prices.
* The adjustment factor to apply for new price list lines.
* The rounding method to apply for prices.

[!INCLUDE [edit-in-excel-price-list](includes/edit-in-excel-price-list.md)]

By default, the status of new price lists is **Draft**. When you're ready to start using the list, you can change the status to **Active**.

To review price lists and prices that apply for specific customers or vendors, on the **Customer** or **Vendor** pages, choose either **Sales Price Lists** or **Purchase Price Lists** action. For items and resources, you can view price list lines by choosing **Sales Prices** or **Purchase Prices** on the **Item** and **Resource** pages.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.
2. Choose the customer, and then choose the **Sales Price Lists** action.
3. Choose **New** to create a new sales price list.
4. On the **General** and **Tax** FastTabs, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
5. Add items to the list in one of the following ways:
   * To add many items, choose **Suggest Lines**, and then enter filter criteria to specify the types of items to add. Optionally, you can enter settings for the items that are specific to the price list. You can change the settings later, if needed.
   * To copy items from another price list, choose **Copy Lines**, and then choose the price list to copy.
   * To add items manually, in the **Product Type** field, choose the type of product that the price list is for. Depending on your selection, fill in the remaining fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
6. To start using the price list, in the **Status** field, choose **Active**.  

---

## To set up a sales line discount for a customer

These steps differ, depending on whether your administrator turned on the **New sales pricing experience** feature update.

### [Current Experience](#tab/current-experience/)  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.
2. Open the relevant customer card, and then choose the **Line Discounts** action.
3. Fill in the fields on the line as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] Fill a line for each combination that grants a sales line discount to the customer.

> [!Note]
>
> To set up prices or line discounts for all customers, a customer price group, or a campaign, you must open the pages from an item card. Alternatively, for sales prices, use the **Sales Price Worksheet** page. To learn more, go to [To bulk update item prices](sales-how-record-sales-price-discount-payment-agreements.md#to-bulk-update-item-prices).  

### [New Experience](#tab/new-experience/)  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.
2. Choose the customer, and then choose the **Sales Price Lists** action.
3. Open the price list for which to specify the line discount.
4. Turn on the **Allow Line Disc.** toggle.
5. Create a new line, or choose an existing line, and then fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
6. In the **Defines** field, choose either **Price & Discount**, or just **Discount**. 
7. In the **Line Discount %** field, specify the discount percentage.

   > [!TIP]
   > If you're editing an existing line, you can filter the lines by choosing the appropriate option in the **View Columns for** field.

---

## Work with invoice discounts and service charges

When you use invoice discounts, the size of the invoice amount determines the size of the discount that is granted. On the **Invoice Discounts** page, you can also add a service charge to invoices over a certain amount.

Before you can use invoice discounts with sales, you must enter certain information in application. You must decide which customers you want to grant this type of discount, and the discount percentages.  

If you want [!INCLUDE [prod_short](includes/prod_short.md)] to automatically calculate invoice discounts, turn on the **Calc. Inv. Discount** toggle on the **Sales & Receivables Setup** page.  

For each customer, you can specify whether you grant invoice discounts if the requirement is satisfied (that is, if the invoice amount is large enough). You can define the terms of the invoice discount in local currency for domestic customers and in foreign currency for foreign customers.  

You link discount percentages to specific invoice amounts on the **Invoice Discounts** page. You can enter as many percentages as you need. Each customer can have their own page, or you can link several customers to the same page.  

In addition to (or instead of) a discount percentage, you can link a service charge amount to a specific invoice amount.  

> [!TIP]  
> Before you start entering this information, it's a good idea to prepare your discount structure beforehand, so it's easier to see which customers to link to the same invoice discount page. For more information about discounts in sales, see [Set up discounts for your customers](/training/modules/customer-discounts-dynamics-365-business-central/index).

### To set up an invoice discount for a customer

After you decide which customers are eligible for invoice discounts, enter the invoice discount code on the customer cards and set up the terms for each code.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.
2. Open the customer page for a customer that's eligible for invoice discounts.
3. In the **Invoice Disc. Code** field, select a customer for which you specified the invoice discount terms to use to calculate invoice discounts.

> [!NOTE]  
> Invoice discount codes are the discount term settings for a customer, which can save you time. You can quickly assign invoice discount terms to customers by reusing the settings from another customer.

Proceed to set up new the sales invoice discount terms.

1. On the **Customers** page, choose the **Invoice Discounts** action. The **Cust. Invoice Discounts** page opens.
2. In the **Currency Code** field, enter the code for a currency that the invoice discount terms on the line applies to. Leave the field blank to set up invoice discount terms in USD.
3. In the **Minimum Amount** field, enter the minimum amount that an invoice must have to be eligible for the discount.
4. In the **Discount %** field, enter the invoice discount as a percentage of the invoice amount.
5. Repeat steps 2 through 4 for each currency that the customer uses.

The invoice discount is now set up and assigned to the customer. When you select the customer code in the **Invoice Disc. Code** field on other customer cards, the same invoice discount is assigned to those customers.

## To copy sales prices

These steps differ, depending on whether your admin turned on the **New sales pricing experience** feature update.

### [Current Experience](#tab/current-experience/)

To copy sales prices, such as an individual customer's sales prices, to use for a customer price group, you must run the **Suggest Sales Price on Wksh.** batch job on the **Sales Price Worksheet** page.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Price Worksheet**, and then choose the related link.  
2. Choose the **Suggest Sales Price on Wksh.** action.  
3. On the **Sales Prices** FastTab, fill in the **Sales Type** and **Sales Code** fields with the original sales prices you want to copy.  
4. In the top section of the request page, fill in the **Sales Type** and **Sales Code** fields with the type and name you want the sales prices copied to.  
5. If you want the batch job to create new prices, select the **Create New Prices** check box.  
6. Choose the **OK** button to fill in the lines on the **Sales Price Worksheet** page with the suggested new prices, indicating that they're valid for the selected sales type.  

   > [!NOTE]  
   > This batch job only creates suggestions and it doesn't implement the suggested changes. If you're satisfied with the suggestions and want to implement them, that is insert them on the **Sales Prices** page, choose the **Implement Price Changes** action on the **Sales Price Worksheet** page.

### [New Experience](#tab/new-experience/)

The status of the price list must be **Draft**.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Price Lists**, and then choose the related link. 
2. Choose the price list to copy, and then choose **Copy Lines**.
3. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

   > [!NOTE]
   > You can't have two lines that have the same settings but different prices. If that happens, a message displays when you activate a price list. You can choose the price to use by opening the list and deleting the incorrect price.  
  
---

## To bulk update item prices

These steps differ, depending on whether your administrator turned on the **New sales pricing experience** feature update.

### [Current Experience](#tab/current-experience/)

If you want to bulk update item prices, such as increase all item prices by some percentage, you must run the **Suggest Item Price on Wksh.** batch job. You can find a link to the batch job on the **Sales Price Worksheet** page.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Price Worksheet**, and then choose the related link.  
2. Choose the **Suggest Item Price on Wksh.** action.  
3. On the **Item** FastTab, fill in the **No.** or **Inventory Posting Group** or other fields with the original item prices you want to update.  
4. In the top section of the request page, fill in the **Sales Type** and **Sales Code** with the type and name you want the sales prices copied to.
5. If you want the batch job to automatically adjust suggested item prices, enter adjustment in **Adjustment Factor** field. For example, you would enter 1.15 in **Adjustment Factor** for 15% increase in item price.  
6. If you want the batch job to create new prices, select the **Create New Prices** field.  
7. Choose the **OK** button to fill in the lines on the **Sales Price Worksheet** page with the suggested new prices, indicating that they're valid for the selected **Item**.  

> [!NOTE]
> This batch job only creates suggestions and it doesn't implement the suggested changes. If you're satisfied with the suggestions and want to implement them, that is insert them in the **Sales Prices** table, you can use the **Implement Price Changes** batch job, which is found on the **Actions** tab, in the **Functions** group, on the **Sales Price Worksheet** page.

### [New Experience](#tab/new-experience/)

To update prices for multiple items, you must create a new price list, and then copy the lines from an existing price list. When you copy the lines you can use filters to specify what to copy, and you can specify an integer or decimal number in the **Adjustment Factor** field to increase or decrease prices. The price list must be in the **Draft** status. If needed, you can then deactivate the old price list.

> [!NOTE]
> You can't have two lines that have the same settings but different prices. If that happens, a message displays when you activate a price list. You can choose the price to use by opening the list and deleting the incorrect price.  

[!INCLUDE [edit-in-excel-price-list](includes/edit-in-excel-price-list.md)]

---

## Calculating the best price

When you record special prices and line discounts for sales and purchases, [!INCLUDE[d365fin](includes/d365fin_md.md)] optimizes your profit. It automatically calculates the best price on sales and purchase documents, and on job and item journal lines. To learn more, go to [Best Price Calculation](sales-how-record-sales-price-discount-payment-agreements.md#best-price-calculation).

## Related information

[Setting Up Sales](sales-setup-sales.md)  
[Sales](sales-manage-sales.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
