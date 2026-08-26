---
title: Synchronize prices with Shopify
description: Set up and manage price synchronization between Business Central and Shopify, including B2B pricing, market-specific pricing, and how tax settings affect exported prices.
ms.date: 07/17/2026
ms.topic: how-to
ms.search.form: 30126, 30127, 30159, 30174
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Synchronize Prices with Shopify

This article explains how to configure price synchronization between [!INCLUDE[prod_short](../includes/prod_short.md)] and Shopify, and how various tax settings in Shopify affect storefront prices. It covers domestic and international pricing scenarios, B2B catalogs, and market-specific pricing.

For information about how taxes are handled on imported Shopify orders, go to [Taxes in imported Shopify orders](synchronize-orders.md#taxes-in-imported-shopify-orders).

> [!NOTE]
> The tax-related sections in this article aren't intended to be a comprehensive taxation guide. Contact your local tax authority or a tax professional for advice. The article assumes that you're liable to pay taxes when you sell goods locally or internationally.

## Price synchronization overview

The Shopify Connector allows you to sync product pricing to your Shopify store. 

It can send both the main selling price (shown as **Price** in Shopify) and the original, non-discounted price (displayed as **Compare at Price**) to the Shopify Product (Shopify Variant) pages.

If you use Markets in Shopify, which can represent different countries/regions, B2B companies, or POS locations - you can link product catalogs to these markets and sync market-specific prices through the connector. Learn more at [Synchronize market-specific prices with Shopify](#synchronize-market-specific-prices-with-shopify).

For Shopify PLUS merchants, there is an additional option to connect catalogs to company locations, making it easier to manage B2B pricing scenarios. Learn more at [Synchronize market-specific prices with Shopify](#synchronize-market-specific-prices-with-shopify).

## Sync prices to the Shopify products page

The following table describes the settings you can use to manage the process of defining and exporting prices.

|Field|Description|
|------|-----------|
|**Customer Price Group**|Determine the price for an item in Shopify. The sales price of this customer price group is taken. If no group is specified, the price on the item card is used.|
|**Customer Discount Group**|Determine the discount to use when calculating the price of an item in Shopify. Discounted prices are stored in the **Price** field and the full price is stored in the **Compare at Price** field.|
|**Allow Line Disc.**|Specifies whether you allow a line discount when calculating prices for Shopify. This setting applies only for prices on the item. Prices for the customer price group have their own toggle on lines.|
|**Prices including VAT**|Specifies whether price calculations for Shopify include VAT. Learn more at [Pricing and taxes](#pricing-and-taxes).|
|**VAT Business Posting Group**|Only needed if you want to include taxes into price. Here you can specify which VAT business posting group is used to calculate prices with taxes in Shopify. Use your group for domestic customers. Learn more at [Pricing and taxes](#pricing-and-taxes).|
|**Currency Code**|Enter a currency code only if your online shop uses a different currency than the local currency (LCY). The specified currency must have exchange rates configured. If your online shop uses the same currency as [!INCLUDE[prod_short](../includes/prod_short.md)], leave the field empty.|

To export prices for synchronized items do following:

1. Go to the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Products**, and choose the related link.
2. Choose the **Sync Prices to Shopify** action.

> [!NOTE]
> There are a few things to note about price calculations and synchronization.
>
> * When it determines a price, [!INCLUDE[prod_short](../includes/prod_short.md)] uses the "lowest price" logic. However, the lowest price logic ignores the unit price defined on the item card if a price is defined in the price group. This is true even if the unit price from the item card price is lower.
> * To calculate prices, the connector creates a temporary sales quote for the item with a quantity of 1, and uses standard price calculation logic. Only prices and discounts that are applicable for quantity 1 are used. You can't export different prices or discounts based on quantity.
> * The connector sends a request to update prices in Shopify if the price in [!INCLUDE[prod_short](../includes/prod_short.md)] changed. For example, if you synchronized products and prices and then changed a price in Shopify, choosing the **Sync Prices to Shopify** action doesn't affect the price in the Shopify because the new price calculated by the connector is the same as the price stored in the Shopify Variant from the previous sync. 
> * If there are 100 or more prices to be updated, the connector executes update asynchronously. You can check the status of the synchronization in the **Shopify Bulk Operations** page.
> * If you run the sync in the foreground and items are skipped (for example, because they're blocked or sales-blocked), a notification appears. Choose **View Skipped Records** to see the details. If you run the price sync from the job queue, the task completes successfully even when items are skipped. The job queue doesn't show a warning. To verify whether items were skipped, open the **Shopify Skipped Records** page and check for recent entries.

## Price synchronization for B2B

[!INCLUDE [shopify-preview](../includes/shopify-preview.md)]

If you use Shopify B2B, you can configure the Connector to synchronize prices for Shopify Catalogs linked to B2B customers.

### Synchronize B2B catalogs from the Shopify

1. Select the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify B2B Catalogs**, and select the related link.
2. Select **Get Catalogs**.

You can only access catalogs linked to B2B companies. To learn more, go to [B2B Companies](synchronize-customers.md#b2b-companies). Note that catalogs in [!INCLUDE[prod_short](../includes/prod_short.md)] don't contain information about products. You manage catalog content in Shopify Admin.

### Sync prices for B2B Catalog

1. Select the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify B2B Catalogs**, and select the related link.
2. Select the entry for which to define and export prices, and then fill in the fields as necessary.

   You can use two strategies. One is the default strategy, where you can use settings similar to the ones for synchronizing the **Price** and **Compare at Price** fields for Shopify products (Shopify variant). The following table describes settings for the default strategy.

   |Field|Description|
   |------|-----------|
   |**Customer Price Group**|Determine the price for an item in Shopify. The sales price of this customer price group is taken. If no group is specified, the price on the item card is used.|
   |**Customer Discount Group**|Determine the discount to use when calculating the price of an item in Shopify. Discounted prices are stored in the **Price** field and the full price is stored in the **Compare at Price** field. |
   |**Allow Line Disc.**|Specifies whether you allow a line discount when calculating prices for Shopify. This setting applies only for prices on the item. Prices for the customer price group have their own toggle on lines.|
   |**Prices including VAT**|Specifies whether price calculations for Shopify include VAT. Learn more at [Pricing and taxes](#pricing-and-taxes).|
   |**VAT Business Posting Group**|Only needed if you want to include taxes into price. Here you can specify which VAT business posting group is used to calculate prices with taxes in Shopify. Use your group for domestic customers. Learn more at [Pricing and taxes](#pricing-and-taxes).|
   
   The second strategy is to use the **Customer No.** field. In this case, the connector uses the customer to calculate the price. It ignores other values defined in the Shopify Catalog entry, and uses the **Customer Price Group**, **Customer Discount Group**, and **Allow Line Discount** fields from the customer card. Use personalization to add the **Customer No.** field to the **Shopify Catalog** page.

4. After you enter the settings, turn on the **Sync Prices** toggle and choose **Sync Prices** action to start synchronizing catalog prices.

## Synchronize market-specific prices with Shopify

If you use Markets in Shopify, you can set up the connector to sync prices for Shopify catalogs that link to those markets.

### Synchronize market catalogs from the Shopify

1. Select the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Market Catalogs**, and select the related link.
2. Select **Get Catalogs**.

A market can represent a region, POS location, or company location (B2B).

### Sync prices for market catalogs

1. Select the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Market Catalogs**, and select the related link.
2. On the **Shopify Market Catalogs** page, select the entry where you want to define and export prices. Fill in the fields as needed. The following table describes the fields.

   |Field|Description|
   |------|-----------|
   |**Customer Price Group**|Determine the price for an item in Shopify. The sales price of this customer price group is taken. If no group is specified, the price on the item card is used.|
   |**Customer Discount Group**|Determine the discount to use when calculating the price of an item in Shopify. Discounted prices are stored in the **Price** field and the full price is stored in the **Compare at Price** field. |
   |**Allow Line Disc.**|Specifies whether you allow a line discount when calculating prices for Shopify. This setting applies only for prices on the item. Prices for the customer price group have their own toggle on lines.|
   |**Prices including VAT**|Specifies whether price calculations for Shopify include VAT. Learn more at [Pricing and taxes](#pricing-and-taxes).|
   |**VAT Business Posting Group**|Only needed if you want to include taxes into price. Here you can specify which VAT business posting group is used to calculate prices with taxes in Shopify. Use your group for domestic customers. Learn more at [Pricing and taxes](#pricing-and-taxes).|
   |**Currency Code**|Specifies the currency code for the catalog. The specified currency must have exchange rates configured. If catalog uses the same currency as [!INCLUDE[prod_short](../includes/prod_short.md)], the field will be empty.|

3. Enter the settings, turn on the **Sync Prices** toggle, and then select **Sync Prices** to synchronize catalog prices.

## Pricing and taxes

This section describes how various tax settings in Shopify affect the storefront prices that display to customers, and how to configure [!INCLUDE[prod_short](../includes/prod_short.md)] to support those settings.

### Domestic pricing

After you configure your Shopify to collect taxes in your domestic country or region, you can decide how to display prices on your storefront.

You specify whether to include tax in prices by turning on or off the **Include sales tax in product price and shipping rate** toggle in the [**Taxes and Duties**](https://www.shopify.com/admin/settings/taxes) settings in your **Shopify admin**.

The toggle is typically enabled for the following countries/regions:

* Australia
* Austria
* Belgium
* Czech Republic
* Denmark
* Finland
* France
* Germany
* Iceland
* Italy
* Netherlands
* New Zealand
* Norway
* Spain
* Sweden
* Switzerland
* United Kingdom

In markets such as these, a price of 100 EUR defined on the product card already contains value-added tax (VAT). The price, including VAT, is displayed to the customer in the storefront and at checkout.  

In the USA and Canada, customers don't expect prices to include taxes because the final tax depends on where products ship to. Tax is added at checkout, so the **Include sales tax in product price and shipping rate** toggle is usually turned off. In this case, a price of $100 defined on the product card is the price without tax. At checkout, taxes are added to the price.

To support the scenario where **Include sales tax in product price and shipping rate** is selected, in [!INCLUDE[prod_short](../includes/prod_short.md)], fill in the following fields on the **Shopify Shop Card** page:  

1. Turn on the **Prices including VAT** toggle.  
2. In the **VAT Business Posting Group** field, specify the posting group you use for domestic customers.

Now, define item prices in the **Item Card** or **Sales Price List** fields, with or without tax. When exporting prices to Shopify, [!INCLUDE [prod_short](../includes/prod_short.md)] includes domestic taxes in the calculated price and shows that price for the product in Shopify.

> [!NOTE]
> These settings affect the export of prices. When you import orders from Shopify, the information about whether prices include tax comes directly from Shopify based on the market and tax display configuration for the customer's region.

### International pricing

This section covers settings for scenarios where you're required to collect taxes when selling to another country/region, such as other countries/regions in the EU.

Currently, the Shopify connector only lets you export one price. Shopify automatically applies local taxes, currencies, and rounding. The **Include sales tax in product price and shipping rate** toggle results in the actions described in the following subsections.

#### All prices include tax is selected

|-|Domestic sales|Foreign country/region where you're collecting taxes|Foreign country/region where you're not collecting taxes|
|------------------------|--------|--------|--------|
|Price displayed in the storefront|1200|1200|1200|
|Tax rate percentage|20|25|0|
|Price at checkout|1200|1200|1200|

The price for the customer stays intact, regardless of their location, but your margin is affected due to differing tax rates per country/region.

#### All prices include tax is not selected

|-|Domestic sales|Foreign country/region where you're collecting taxes|Foreign country/region where you're not collecting taxes|
|------------------------|--------|--------|--------|
|Price displayed in the storefront|1000|1000|1000|
|Tax rate percentage|20|25|0|
|Price at checkout|1200|1250|1000|

Shopify adds local taxes to the price defined on the product card based on where goods are shipped to.

### Dynamic tax-inclusive pricing

Countries/regions have different requirements for including tax in prices. If you want prices to automatically include tax, you can turn on [Dynamic tax-inclusive pricing](https://help.shopify.com/en/manual/markets/pricing/dynamic-tax-inclusive-pricing) in Shopify.

In your **Shopify admin**, go to [**Markets**](https://www.shopify.com/admin/settings/markets), choose the market that you want to customize, and then select the **(+)** icon next to **Tax and duties**. In the **Tax display** field, choose **Dynamic tax display**.

> [!NOTE]
> This setting doesn't affect prices in domestic markets, which is controlled by the **Include sales tax in product price and shipping rate** toggle.

#### All prices include tax is selected

|-|Domestic sales|Foreign country/region where tax is included in price|Foreign country/region where tax is excluded|
|------------------------|---------------|---------------|--------|
|Price displayed in the storefront|1200|1250|1000|
|Tax rate percentage|20|25|10|
|Price at checkout|1200|1250|1100|

The price for each customer changes, depending on their location.

#### All prices include tax is not selected

|-|Domestic sales|Foreign country/region where tax is included in price|Foreign country/region, where tax is excluded|
|------------------------|--------|--------|--------|
|Price displayed in the storefront|1000|1250|1000|
|Tax rate percentage|20|25|10|
|Price at checkout|1200|1250|1100|

> [!NOTE]
> The **Include sales tax in product price and shipping rate** toggle doesn't change how prices display to international customers.

### EU customer pricing

Different EU countries/regions have different local tax rates. However, if you're located in the EU and sell to other EU countries/regions, you can use your local tax rate in some cases.  

In your **Shopify admin**, check the **Collect VAT** checkbox in the **European Union** section of the [**Taxes and Duties**](https://www.shopify.com/admin/settings/taxes) settings.

|Collect VAT|VAT rate|
|-|-|
|Micro-business exemption|Use your domestic tax rate for all sales inside the EU|
|One-stop shop or specific country/region registration|Use the VAT rate of your customer's country/region|

#### Collect VAT set to one-stop shop registration

In the following example, the **Include sales tax in product price and shipping rate** toggle is turned on. The price on the product card is set to *1200*.

|-|Domestic sales|Foreign country/region|
|------------------------|--------|--------|
|Price displayed in the storefront|1200|1250|
|Tax rate percentage|20|25|
|Price at checkout|1200|1250|

Shopify uses the tax rate in the foreign country/region when it calculates final prices.

#### Collect VAT set to micro-business exemption

In the following example, the **Include sales tax in product price and shipping rate** toggle is turned on. The price on the product card is set to *1200*.

|-|Domestic sales|Foreign country/region with local tax rate of 25 percent.|
|------------------------|--------|--------|
|Price displayed in the storefront|1200|1200|
|Tax rate percentage|20|20|
|Price at checkout|1200|1200|

Shopify uses the domestic tax rate and ignores the tax rate in the foreign country/region when it calculates final prices.

## Related information

[Synchronize items with Shopify](synchronize-items.md)  
[Synchronize inventory with Shopify](synchronize-inventory.md)  
[Synchronize and fulfill sales orders with Shopify](synchronize-orders.md)  
[Shopify Connector overview](shopify-connector-overview.md)  
[FAQ for the Shopify connector](shopify-faq.md)  
[Troubleshoot the Shopify Connector](troubleshoot.md)  
[Walkthrough: Setting Up and Using Shopify Connector](walkthrough-setting-up-and-using-shopify.md)  
