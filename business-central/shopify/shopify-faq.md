---
title: FAQ for technical details
description: Implementation details related to the Shopify connector.
ms.date: 05/27/2022
ms.topic: article
ms.service: dynamics365-business-central
author: AndreiPanko
ms.author: andreipa
---

# FAQ for Technical Details

This article answers frequently asked questions about the Shopify connector.

## What is Shopify? 

Shopify is a subscription-based software that allows anyone to set up an online store and sell their products. The Shopify platform offers online retailers a suite of services including payments, marketing, shipping, and customer engagement tools. 

## What is the Microsoft Dynamics 365 Business Central Shopify connector? 

With the Shopify connector, businesses can link their Shopify store (or stores) with [!INCLUDE[prod_short](../includes/prod_short.md)] to maximize business productivity. Using the Shopify connector, they can manage and view insights from their business and their Shopify online store as one unit. 

The Shopify connector includes the following capabilities:

- Support for more than one Shopify shop.
  - Each shop has its own setup, including a collection of products, locations used to calculate inventory, and price lists.  
- Bi-directional synchronization of items or products.
  - The connector will sync images, item variants, barcodes, vendor item numbers, extended texts, and tags.  
  - Export item attributes to Shopify.  
  - Use selected customer price groups and discounts to define prices exported to Shopify.  
  - Decide whether items can be created automatically or only allow updates to existing products.  
- Synchronization of inventory levels.
  - Choose some or all of the available locations in [!INCLUDE [prod_short](../includes/prod_short.md)].  
  - Update inventory levels on multiple locations in Shopify.  
- Bi-directional synchronization of customers.
  - Smart-map customers by phone and email.  
  - Use country-specific templates when creating customers, which helps ensure that tax settings are correct.  
- Import of orders from Shopify.
  - During the import, you can automatically create customers in [!INCLUDE [prod_short](../includes/prod_short.md)] or decide to manage the customers in Shopify.  
  - Include orders created in other channels, such as Shopify POS or Amazon.  
  - Shipping costs, gift cards, tips, shipping and payment methods, transactions, and risk of fraud.  
  - Receive payout information from Shopify Payments.  
- Track fulfillment information.
  - Optionally, choose to transfer item tracking information from [!INCLUDE [prod_short](../includes/prod_short.md)] to Shopify.  

## Why did Microsoft and Shopify form this partnership? 

[!INCLUDE[prod_short](../includes/prod_long.md)] is teaming up with Shopify to help our customers create a better shopping experience. While Shopify provides merchants with an easy-to-use commerce solution, [!INCLUDE[prod_short](../includes/prod_short.md)] offers comprehensive business management across finance, sales, service, and operations teams within a single application. Seamless connection between the two systems synchronizes orders, stock, and customer information so merchants can fulfill orders faster and better serve customers.

## What Microsoft products is the Shopify connector available for?

This feature is available only for [!INCLUDE[prod_short](../includes/prod_short.md)] online, starting with version 20.1. It isn't available for on-premises deployments. The app with the connector is pre-installed for new environments. Organizations with existing environments can download and install the app from AppSource. The organization must have both a Business Central license and a Shopify license to use the connector. Learn more about supported countries, languages, and editions of [!INCLUDE[prod_short](../includes/prod_short.md)] at [Shopify Connector on the AppSource](https://go.microsoft.com/fwlink/?linkid=2196238).

The Shopify connector doesn't work for [Embed App](/dynamics365/business-central/dev-itpro/deployment/embed-app-overview), where the client URL has the format: `https://[application name].bc.dynamics.com`. 

## What support is offered for the Shopify connector?

The Shopify connector is covered by the current support model. Learn more at [Technical Support](/dynamics365/business-central/dev-itpro/administration//manage-technical-support) (in English only). 

Get help with Shopify by starting with [General Shopify Help Center](https://help.shopify.com/) or [24/7 Support for your store as a Shopify merchant](https://help.shopify.com/questions#/).

## Is the Shopify connector extensible?

Currently, this app is non-extensible with plans to make it extensible at some point (as yet undetermined) in the future.

## Is the Shopify connector open for contribution

Yes, this extension is open for contribution by the community. You can find the [source code](https://github.com/microsoft/ALAppExtensions/tree/main/Apps/W1/Shopify) in the Microsoft AL application add-ons repository.




## See Also

[Get Started with the Connector for Shopify](get-started.md)  
