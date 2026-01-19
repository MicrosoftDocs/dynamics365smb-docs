---
title: Set up taxes for Shopify connection
description: How to set up taxes in Shopify and Business Central.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.date: 07/14/2025
ms.topic: how-to
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Set up taxes for the Shopify connection

In this article, we'll investigate how various settings in Shopify affect the storefront prices and taxes that display to customers. We'll also cover how to configure [!INCLUDE[prod_short](../includes/prod_short.md)] to support the settings in Shopify. This article is not intended to be a comprehensive taxation guide. To learn more, contact your local tax authority or a tax professional.  

The article assumes that you are liable to pay taxes when you sell goods locally or internationally.

## Pricing if you sell domestically

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
> These settings affect the export of prices. When you import orders from Shopify, the information about whether prices include tax comes directly from Shopify, which is useful when selling to different markets using the **Include or exclude tax based on your customer's country** setting in Shopify Admin.

## Pricing if you sell internationally

This section explores settings for scenarios where you're required to collect taxes when selling to another country/region, such as other countries/regions in the EU.

Currently, the Shopify connector only lets you export one price. Shopify automatically applies local taxes, currencies, and rounding. The **Include sales tax in product price and shipping rate** toggle results in the actions described in the following subsections.

### All prices include tax is selected

|-|Domestic sales|Foreign country/region where you're collecting taxes|Foreign country/region where you're not collecting taxes|
|------------------------|--------|--------|--------|
|Price displayed in the storefront|1200|1200|1200|
|Tax rate percentage|20|25|0|
|Price at checkout|1200|1200|1200|

The price for the customer stays intact, regardless of their location, but your margin is affected due to differing tax rates per country/region.

### All prices include tax is not selected

|-|Domestic sales|Foreign country where you're collecting taxes|Foreign country where you're not collecting taxes|
|------------------------|--------|--------|--------|
|Price displayed in the storefront|1000|1000|1000|
|Tax rate percentage|20|25|0|
|Price at checkout|1200|1250|1000|

Shopify adds local taxes to the price defined on the product card based on where goods are shipped to.

## Dynamic tax-inclusive pricing

Countries/regions have different requirements for including tax in prices. If you want prices to automatically include tax, you can turn on [Dynamic tax-inclusive pricing](https://help.shopify.com/en/manual/markets/pricing/dynamic-tax-inclusive-pricing) in Shopify.

Depending on the implementation for the market you're in:

* In your **Shopify admin**, select **Include or exclude tax based on your customer's country** in the **Other Markets - Preferences** section of the [**Markets**](https://www.shopify.com/admin/settings/markets) settings.  

* If you use new markets, in your **Shopify admin**, go to [**Markets**], and choose the market that you want to customize. Choose the **(+)** icon next to **Tax and duties**. In the **Tax display** field, choose **Dynamic tax display**.  

> [!NOTE]
> This setting doesn't affect prices in domestic markets, which is controlled by the **Include sales tax in product price and shipping rate** toggle.

### All prices include tax is selected

|-|Domestic sales|Foreign country/region where tax is included in price|Foreign country/region where tax is excluded|
|------------------------|---------------|---------------|--------|
|Price displayed in the storefront|1200|1250|1000|
|Tax rate percentage|20|25|10|
|Price at checkout|1200|1250|1100|

The price for each customer changes, depending on their location.

### All prices include tax is not selected

|-|Domestic sales|Foreign country/region where tax is included in price|Foreign country/region, where tax is excluded|
|------------------------|--------|--------|--------|
|Price displayed in the storefront|1000|1250|1000|
|Tax rate percentage|20|25|10|
|Price at checkout|1200|1250|1100|

> [!NOTE]
> The **Include sales tax in product price and shipping rate** toggle doesn't change how prices display to international customers.

## Pricing if you sell to EU customers

Different EU countries/regions have different local tax rates. However, if you're located in the EU and sell to other EU countries/regions, you can use your local tax rate in some cases.  

In your **Shopify admin**, check the **Collect VAT** checkbox in the **European Union** section of the [**Taxes and Duties**](https://www.shopify.com/admin/settings/taxes) settings.

|Collect VAT|VAT rate|
|-|-|
|Micro-business exemption|Use your domestic tax rate for all sales inside the EU|
|One-stop shop or specific country/region registration|Use the VAT rate of your customer's country/region|

### Collect VAT set to one-stop shop registration

In the following example, the **Include sales tax in product price and shipping rate** toggle is turned on. The price on the product card is set to *1200*.

|-|Domestic sales|Foreign country/region|
|------------------------|--------|--------|
|Price displayed in the storefront|1200|1250|
|Tax rate percentage|20|25|
|Price at checkout|1200|1250|

Shopify uses the tax rate in the foreign country/region when it calculates final prices.

### Collect VAT set to micro-business exemption

In the following example, the **Include sales tax in product price and shipping rate** toggle is turned on. The price on the product card is set to *1200*.

|-|Domestic sales|Foreign country/region with local tax rate of 25 percent.|
|------------------------|--------|--------|
|Price displayed in the storefront|1200|1200|
|Tax rate percentage|20|20|
|Price at checkout|1200|1200|

Shopify uses the domestic tax rate and ignores the tax rate in the foreign country/region when it calculates final prices.

## Taxes in imported Shopify orders

Although the Shopify orders you import have tax information, the tax amounts recalculate when you create the sales document. The recalculation means it's important that your VAT or sales tax settings are correct in [!INCLUDE[prod_short](../includes/prod_short.md)].

You can review imported tax details in the **Tax Lines** page, which you can open from the **Shopify Order** page.

### Multiple product tax or VAT rates

Some product categories are eligible for reduced tax rates, such as pharmaceutical products or children's clothing and footwear. You can use the [tax override](https://help.shopify.com/en/manual/taxes/tax-overrides#create-a-manual-collection-for-products-that-need-a-tax-override) feature in Shopify to specify that. When you import those products and create items in [!INCLUDE[prod_short](../includes/prod_short.md)], they use the tax setup specified on the item template code in the Shopify shop. Before you import orders with such items, update the VAT product posting group.

### Address-dependent tax rates

If you're collecting taxes from multiple countries/regions, you must define a specific country/regional setting in [!INCLUDE[prod_short](../includes/prod_short.md)]. 

You specify country/region-specific settings on the **Shopify Customer Template** page. You can define the **Default Customer No.** or **Customer Template No.**. In either case, ensure the customer or template has the following fields filled in:

1. **General Business Posting Group** (used for foreign customers).
2. **VAT Business Posting Group** (used for foreign customers).

For merchants using the US or Canadian localizations:

3. **Tax Liable**
4. **Tax Area Code**

    Use the **Tax Area Priority** field together with the **Customer Setup by Country/Region** page to define how to fill in the **Tax Area Code** field on the sales document. The **Tax Area Priority** field specifies the priority regarding where to get the information about the country or region and state or province. If not selected, the **Tax Area Code** from customer is specified in the **Sell-to Customer No.** field of the Shopify order. If selected, the connector finds the relevant record based on the addresses in the Shopify order, and uses the **Tax Area Code** when creating the sales document.  

### Prices including VAT

The value of the **Prices including VAT** field comes directly from Shopify when you import orders and refunds. For local sales it is defined by **Include sales tax in product price and shipping rate** and for international sales 

> [!Important] 
> For merchants using the US or Canadian localizations, review the **Include sales tax in product price and shipping rate** in Shopify Admin. If enabled, you can't convert imported orders into sales documents because [!INCLUDE [prod_short](../includes/prod_short.md)] doesn't support backward sales tax calculation.
>
> If this field is selected and you don't charge taxes, you can manually turn off the **VAT (Tax) Included** field on the **Shopify Order** page and proceed.

### Channel Liable Taxes 

As of **January 1, 2025**, Shopify started to collect withholding taxes for all orders placed through the **Shop sales channel** that are shipped to or within the United States. Shopify remits these taxes through the Marketplace Facilitator Tax program in all US states for all US-registered sellers only.

To support this functionality, the Shopify Connector includes **Channel Liable Tax** tracking to help merchants properly handle tax reporting and avoid double taxation.

**Channel Liable Tax** occurs when the sales channel (marketplace, and in this case Shopify) is responsible for:

- Collecting sales tax from the customer.
- Remitting tax to the appropriate tax authorities.

The Shopify Connector tracks channel liable tax information at multiple levels:

1. The **Channel Liable** field in the **Shopify Order Tax Line** page, which indicates whether this specific tax line is liable to be collected and remitted by the sales channel.
2. The **Channel Liable Taxes** flow field in the **Shopify Order Header** page displays **Yes** if any associated tax line has the **Channel Liable** toggle turned on.
3. The **Channel Liable Taxes** field in the **Shopify Orders to Import** page, which is also used as request page when you import orders. It indicates whether the line on the order is channel liable.

> [!NOTE]
>
> For performance reason, the connector only checks the first tax line.

You can use the **Channel Liable Tax** information in the following ways:

1. Review imported orders. The **Channel Liable Taxes** field indicates whether the order contains any marketplace-collected taxes.
2. View tax line details. Choose the **Tax Lines** action on the **Shopify Order Card** page.
3. Filter orders during import. When you import orders from Shopify, you can filter by channel liable status.

#### Filter orders during import

This is useful for:
- Separating orders for different accounting treatments. 
- Identifying which orders to exclude from tax returns
- Reconciling with Shopify's tax reports

Learn more at [Different processing rules for orders](synchronize-orders.md#different-processing-rules-for-orders).

1. Open **Sync Orders from Shopify** report.
2. Apply filter: `Channel Liable Taxes = Yes` to see only orders with marketplace-collected taxes
3. Apply filter: `Channel Liable Taxes = No` to see orders where you're responsible for tax collection

## Related information

[Shopify Connector overview](shopify-connector-overview.md)  
[FAQ for the Shopify connector](shopify-faq.md)  
[Troubleshoot the Shopify Connector](troubleshoot.md)  
[Walkthrough: Setting Up and Using Shopify Connector](walkthrough-setting-up-and-using-shopify.md)  
