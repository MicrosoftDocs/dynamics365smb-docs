---
title: Setting up Taxes
description: How to set up taxes in Shopify and Business Central.
ms.date: 05/27/2022
ms.topic: article
ms.service: dynamics365-business-central
author: AndreiPanko
ms.author: andreipa
---

# Setting up Taxes

In this guide we'll investigate how various setting on Shopify impact storefront prices and taxes displayed to the customer and how to configure [!INCLUDE[prod_short](../includes/prod_short.md)] to support setting on Shopify. This guide is not intended to be a comprehensive taxation guide. To learn more, contact your local tax authority or a tax professional.
In following guide we assume that you are liable to pay taxes when selling goods locally or internationally.

## Selling in domestic market 

Once you configured your Shopify to collect taxes in your domestic country/region, you can decide how you want to display prices at the storefront. 
You can control this behavior by enabling or deactivating the **All prices include tax** of the [**Taxes and duties**](https://www.shopify.com/admin/settings/taxes) settings in your **Shopify admin**.

It is common to have this toggle enabled for such countries as Australia, Austria, Belgium, Czech Republic, Denmark, Finland, France, Germany, Iceland, Italy, Netherlands, New Zealand, Norway, Spain, Sweden, Switzerland, United Kingdom. In this case, the price 100 EUR defined in the Product card already contains tax (VAT) and same price is displayed to user at storefront and at checkout.
While in USA or Canada customers expect to see prices without taxes, and taxes added at check-out, hence the All prices include tax toggle is usually disabled. Then 100 USD defined in the Product card represents price without card and at checkout stage taxes will be added on top.

To support scenario when **All prices includes tax** is enabled on [!INCLUDE[prod_short](../includes/prod_short.md)] side you need to:
Fill in the **Customer Template Code** field in **Shopify Shop Card** page with the template that has following fields defined:
1. **General Business Posting Group** that is used for domestic customers.
2. **VAT Business Posting Group** that is used for domestic customers.
3. **Prices Including VAT** is set to *Yes*.

Now you can define prices in the **Item Card** or **Sales Price List**. You can define prices with or without tax. When exporting prices to Shopify, system will calculate price to include domestic tax and use this price in the Product card in Shopify.

>[Note!]
>If you configured Shopify Connector to create customers automatically, you may need more fields in your template, for example **Customer Posting Group**. If you used default customer for imported orders, make sure this customer has same fields populated. You still need to fill in **Customer Template Code** as specified above, because the **Prices including Tax**/**Prices including VAT** field in the created sales document doesn't depend on the customer, but on the **Customer Template** from the Shopify Shop Card or Customer template per country.

## Selling internationally

In this paragraph we'll explore settings for scenarios, when you are required to collect taxes when selling to another country. For example, you are selling to other countries inside EU.

Currently the **Shopify Connector** extension supports export of one price only. Shopify automatically applies local taxes, currencies, roundings. The **All prices includes tax** toggle will have following effect.

### All prices includes tax is enabled

||Domestic sales|Foreign country where you collecting taxes|Foreign country where you don't collect taxes|
|------------------------|--------|--------|--------|
|Price displayed in the storefront|1200|1200|1200|
|Tax rate %|20|25|0|
|Price at checkout|1200|1200|1200|

Price for customer stays intact, regardless of their location, but your margin is affected because of different tax rates in countries.

### All prices includes tax is disabled

||Domestic sales|Foreign country where you collecting taxes|Foreign country where you don't collect taxes|
|------------------------|--------|--------|--------|
|Price displayed in the storefront|1000|1000|1000|
|Tax rate %|20|25|0|
|Price at checkout|1200|1250|1000|

Shopify adds local taxes on top of price defined in the Product card based on where goods will be shipped to.

## Dynamic tax-inclusive pricing

Because different countries have different requirements on whether tax should be included into price or not, there is a possibility to enable [Dynamic tax-inclusive pricing](https://help.shopify.com/en/manual/markets/pricing/dynamic-tax-inclusive-pricing) 

You can do it by enabling the **Include or exclude tax based on your customer's country** in the **Other Markets - Preferences** section of the [**Markets**](https://www.shopify.com/admin/settings/markets) settings in your **Shopify admin**.

>[Note!]
>This setting doeesn't affect the representation of prices in domestic market, which is controlled by the all prices includes tax toggle.

### All prices includes tax is enabled

||Domestic sales|Foreign country, where tax included into price|Foreign country, where tax excluded|
|------------------------|--------|--------|--------|
|Price displayed in the storefront|1200|1250|1000|
|Tax rate %|20|25|10|
|Price at checkout|1200|1250|1100|

Price for customer will change depending on their location.

### All prices includes tax is disabled

||Domestic sales|Foreign country, where tax included into price|Foreign country, where tax excluded|
|------------------------|--------|--------|--------|
|Price displayed in the storefront|1000|1250|1000|
|Tax rate %|20|25|10|
|Price at checkout|1200|1250|1100|

Notice that **All prices includes tax** toggle doesn't change how prices are displayed to international customers.

## Selling in EU

Different EU countries have different tax local tax rates. However if you located in EU and sell to other EU countries, you can use local tax rate in some cases.

The **Collect VAT** in the **European Union** section of the [**Taxes and duties**](https://www.shopify.com/admin/settings/taxes) settings in your **Shopify admin**.

|Collect VAT|VAT rate|
|-|-|
|Micro-business exemption|Your domestic rate will be used for all sales for customers inside EU|
|One-Stop Shop registration or Country-specific registration|the VAT rate of your customer's country|


### Collect VAT set to One-Stop Shop registration		
In example below the All prices includes tax toggle is enabled. Price in Product card is set to 1200.	
		
||Domestic sales|Foreign country with local tax rate 25|
|------------------------|--------|--------|
|Price displayed in the storefront|1200|1250|
|Tax rate %|20|25|
|Price at checkout|1200|1250|		
		
### Collect VAT set to  Micro-business exemption			
In example below the All prices includes tax toggle is enabled. Price in Product card is set to 1200.	
		
||Domestic sales|Foreign country with local tax rate 25|
|------------------------|--------|--------|
|Price displayed in the storefront|1200|1200|
|Tax rate %|20|20|
|Price at checkout|1200|1200|		    
    
Shopify ignores tax rate in the foreign country when calculating final prices and uses domestic tax rate.

## Importing shopify orders sold internationally

If you are collecting taxes from multiple countries, you most probably need to define country specific setting in [!INCLUDE[prod_short](../includes/prod_short.md)]. This is required because when sales document gets created in [!INCLUDE[prod_short](../includes/prod_short.md)], system calculates taxes instead of reusing ones imported from Shopify.

Country/region specific settings should be done in the **Shopify Customer Template** window.

There you can define **Default Customer No.** or **Customer Template No.**. In both cases make sure that selected customer/template has following fields defined:
1. **General Business Posting Group** that is used for foreign customers.
2. **VAT Business Posting Group** that is used for foreign customers.
3. **Prices Including VAT** is aligned with setting on the Shopify side:
* Set *Yes* if **All prices includes tax** is enabled and **Include or exclude tax based on your customer's country** is disabled.
* Set *No* if **All prices includes tax** is disabled and **Include or exclude tax based on your customer's country** is disabled.
* Set *Yes* if **Include or exclude tax based on your customer's country** is enabled and country/region is listed in the [Tax-inclusive countries](https://help.shopify.com/en/manual/markets/pricing/dynamic-tax-inclusive-pricing#tax-inclusive-versus-tax-exclusive-countries-and-regions).
* Set *No* if **Include or exclude tax based on your customer's country** is enabled and country/region is not listed in [Tax-inclusive countries](https://help.shopify.com/en/manual/markets/pricing/dynamic-tax-inclusive-pricing#tax-inclusive-versus-tax-exclusive-countries-and-regions).

>[Note] **Prices Including VAT** is coming from tempalte, not from the specific customer. That's why it is important to have customer template defined.

## Other tax remarks

### Tax remarks

While the imported Shopify order contains information about taxes, the taxes get recalculated when you create the sales document. That recalculation makes it important that the VAT/tax settings are correct in [!INCLUDE[prod_short](../includes/prod_short.md)].

- Multiple product tax/VAT rates. For example, some product categories are liable for reduced tax rates. Those items must exist in [!INCLUDE[prod_short](../includes/prod_short.md)] and be mapped to Shopify products. Otherwise, with automatic creation of missing items, the VAT product posting group will be used.

- Address-dependent tax rates. Use the **Tax area priority** field together with **Customer Templates** table to overwrite standard logic that fills in the **Tax Area Code** in the sales document. The **Tax area priority** field specifies the priority from where the function should take the information about the country/region and state/province. Then the corresponding record in the Shopify customer templates is found and the **Tax Area Code**, **Tax Liable**, and **VAT Bus. Posting Group** is used when a sales document is created.


## See Also

[Get Started with the Connector for Shopify](get-started.md)  
