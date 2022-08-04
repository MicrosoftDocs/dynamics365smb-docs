---
title: Set up taxes for Shopify connection
description: How to set up taxes in Shopify and Business Central.
ms.date: 05/27/2022
ms.topic: article
ms.service: dynamics365-business-central
author: AndreiPanko
ms.author: andreipa
---

# Set Up Taxes for the Shopify Connection

In this article, we'll investigate how various settings in Shopify impact the storefront prices and taxes that are displayed to the customer. We'll also look at how to configure [!INCLUDE[prod_short](../includes/prod_short.md)] to support the settings in Shopify. This article is not intended to be a comprehensive taxation guide. To learn more, contact your local tax authority or a tax professional.  

The article assumes that you are liable to pay taxes when selling goods locally or internationally.

## If you sell domestically 

Once you configure your Shopify to collect taxes in your domestic country or region, you can decide how you want to display prices on your storefront. 
You control this by enabling or disabling the **all prices include tax** toggle in the [**Taxes and duties**](https://www.shopify.com/admin/settings/taxes) settings in your **Shopify admin**.

It is common to have this toggle enabled for such countries as Australia, Austria, Belgium, the Czech Republic, Denmark, Finland, France, Germany, Iceland, Italy, the Netherlands, New Zealand, Norway, Spain, Sweden, Switzerland, and the United Kingdom. In markets such as these, the price *100 EUR* defined in the product card already contains value-added tax (VAT) and that same price is displayed to the customer at storefront and at checkout.  

In the USA and Canada, customers expect to see product prices without taxes, which are added at checkout. So the **all prices include tax** field is usually not selected. In this case, the price *$100* defined in the product card represents the price without tax. At the checkout stage, taxes will be added on top of the price to tally the checkout total.

To support the scenario where **all prices include tax** is selected on the [!INCLUDE[prod_short](../includes/prod_short.md)] side, fill in the **customer template code** field in the **Shopify shop card** page to access the template with following fields defined:  
<!--I changed that last part of the sentence above because it didn't track logically. Just wanted to let you know in case I introduced an inaccuracy.-->

1. **General business posting group**, used for domestic customers.  
2. **VAT business posting group**, used for domestic customers.  
3. **Prices including VAT** set to *yes*.  

Now define item prices in the **item card** or **sales price list** field, with or without tax. When exporting prices to Shopify, the system calculates the price to include domestic taxes then shows that price in the product card in Shopify.

> [!NOTE]
> If you configured the Shopify connector to create customers automatically, you may need more fields in your template, such as **customer posting group**. If you use the default customer for imported orders, make sure the customer has the same fields populated. You still need to fill in the **customer template code** as specified above, because the **prices including tax**/**prices including VAT** field in the created sales document doesn't depend on the customer, but on the **customer template** from the Shopify shop card or customer template per country.

## If you sell internationally

In this section, we'll explore settings for scenarios where you're required to collect taxes when selling to another country, such as other countries in the EU. 

Currently, the **Shopify connector** extension supports export of one price only. Shopify automatically applies local taxes, currencies, and rounding. The **all prices include tax** toggle results in the actions described in the following subsections.

### *All prices include tax* is selected

||Domestic sales|Foreign country where you're collecting taxes|Foreign country where you're not collecting taxes|
|------------------------|--------|--------|--------|
|Price displayed in the storefront|1200|1200|1200|
|Tax rate percentage|20|25|0|
|Price at checkout|1200|1200|1200|

Price for customer stays intact, regardless of their location, but your margin is affected due to tax rates differing per country.

### *All prices include tax* is not selected

||Domestic sales|Foreign country where you're collecting taxes|Foreign country where you're not collecting taxes|
|------------------------|--------|--------|--------|
|Price displayed in the storefront|1000|1000|1000|
|Tax rate percentage|20|25|0|
|Price at checkout|1200|1250|1000|

Shopify adds local taxes on top of the price defined on the product card based on where goods are shipped to.

## Dynamic tax-inclusive pricing

Because different countries have different requirements depending on if you're including tax in the shown price or not, you can switch on [dynamic tax-inclusive pricing](https://help.shopify.com/en/manual/markets/pricing/dynamic-tax-inclusive-pricing) in Shopify. This automates the tax inclusion function. 
<!--I added the last sentence to complete the thought. I hope that's okay.-->

Select **include or exclude tax based on your customer's country** in the **other markets - preferences** section of the [**markets**](https://www.shopify.com/admin/settings/markets) settings in your **Shopify admin**.  

> [!NOTE]
> This setting doesn't affect the representation of prices in domestic markets, which is controlled by the **all prices include tax** toggle.

### *All prices include tax* is selected

||Domestic sales|Foreign country where tax is included in price|Foreign country where tax is excluded|
|------------------------|--------|--------|--------|
|Price displayed in the storefront|1200|1250|1000|
|Tax rate percentage|20|25|10|
|Price at checkout|1200|1250|1100|

The price for each customer changes depending on their location.

### *All prices include tax* is not selected

||Domestic sales|Foreign country where tax is included in price|Foreign country, where tax is excluded|
|------------------------|--------|--------|--------|
|Price displayed in the storefront|1000|1250|1000|
|Tax rate percentage|20|25|10|
|Price at checkout|1200|1250|1100|

> [!NOTE]
> The **all prices include tax** toggle doesn't change how prices are displayed to international customers.

## If you sell to EU customers

Different EU countries have different local tax rates. However, if you're located in the EU and sell to other EU countries, you can use your local tax rate in some cases.  

Check the **collect VAT** box in the **European Union** section of the [**taxes and duties**](https://www.shopify.com/admin/settings/taxes) settings in your **Shopify admin**.

|Collect VAT|VAT rate|
|-|-|
|Micro-business exemption|Use your domestic tax rate for all sales inside the EU|
|One-stop shop or country-specific registration|Use the VAT rate of your customer's country|


### Collect VAT set to one-stop shop registration

In the following example, the **all prices include tax** toggle is enabled. The price on the product card is set to *1200*.	
		
|-|Domestic sales|Foreign country|
|------------------------|--------|--------|
|Price displayed in the storefront|1200|1250|
|Tax rate percentage|20|25|
|Price at checkout|1200|1250|		
		
### Collect VAT set to micro-business exemption

In the following example, the **all prices include tax** toggle is enabled. THe price on the product card is set to *1200*.	
		
|-|Domestic sales|Foreign country with local tax rate of 25 percent.|
|------------------------|--------|--------|
|Price displayed in the storefront|1200|1200|
|Tax rate percentage|20|20|
|Price at checkout|1200|1200|		    
    
Shopify ignores the tax rate in the foreign country when calculating final prices and uses the domestic tax rate.

## Importing Shopify orders sold to international customers

If you are collecting taxes from multiple countries, you most likely need to define a country-specific setting in [!INCLUDE[prod_short](../includes/prod_short.md)]. This is required because when a sales document gets created in [!INCLUDE[prod_short](../includes/prod_short.md)], the system calculates taxes instead of reusing ones imported from Shopify.

Country/region-specific settings are chosen in the **Shopify customer template** window.
<!--Should this be "window" or "page"? I haven't been seeing "window" is use elsewhere, but I don't know what the interface looks like for this action.--> There you can define **default customer no.** or **customer template no.**. In either case make sure the selected customer or template has the following fields defined:

1. **General business posting group** (used for foreign customers).
2. **VAT business posting group** (used for foreign customers).
3. **Prices including VAT** (aligned with setting on the Shopify side):
* Choose *Yes* if **All prices include tax** is enabled and **Include or exclude tax based on your customer's country** is disabled.
* Choose *No* if **All prices include tax** is disabled and **Include or exclude tax based on your customer's country** is disabled.
* Choose *Yes* if **Include or exclude tax based on your customer's country** is enabled and the country or region is listed in the [Tax-inclusive countries](https://help.shopify.com/en/manual/markets/pricing/dynamic-tax-inclusive-pricing#tax-inclusive-versus-tax-exclusive-countries-and-regions).
* Choose *No* if **Include or exclude tax based on your customer's country** is enabled and country/region is not listed in [Tax-inclusive countries](https://help.shopify.com/en/manual/markets/pricing/dynamic-tax-inclusive-pricing#tax-inclusive-versus-tax-exclusive-countries-and-regions).
<!--I changed "Set" to "Choose" since "Set" really isn't an instruction we use. if they're toggling, we then would say "Toggle" as in "Toggle *No* if...."-->
> 
[!Note]
> The setting of the **prices including VAT** field comes from the template, not from the specific customer. That's why it's important to have the customer template defined.

## Other tax remarks

While the imported Shopify order contains information about taxes, the taxes get recalculated when you create the sales document. That recalculation means it's important the VAT/tax settings are correct in [!INCLUDE[prod_short](../includes/prod_short.md)].

- Multiple product tax or VAT rates. For example, some product categories are eligible for reduced tax rates. You can use the [tax override](https://help.shopify.com/en/manual/taxes/tax-overrides#create-a-manual-collection-for-products-that-need-a-tax-override) feature in Shopify. When items are imported and created in [!INCLUDE[prod_short](../includes/prod_short.md)], they use the tax setup as filled in on the item template code in the Shopify shop. Before importing orders with such items, you need to update the VAT product posting group.  

- Address-dependent tax rates. Use the **tax area priority** field together with **customer templates** table to overwrite standard logic that fills in the **tax area code** in the sales document. The **tax area priority** field specifies the priority regarding where the function should take the information about the country or region and state or province. Then the corresponding record in the Shopify customer templates is identified, and the **tax area code**, **tax liable**, and **VAT bus. posting group** are used when a sales document is created.  

## See Also

[Get Started with the Connector for Shopify](get-started.md)  
