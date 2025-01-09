---
title: FAQ for technical details
description: Implementation details related to the Shopify connector.
ms.date: 05/01/2024
ms.topic: article
ms.service: dynamics-365-business-central
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf

---

# FAQ for technical details

This article answers frequently asked questions about the Shopify Connector.

## What is Shopify?

Shopify is a subscription-based application that allows anyone to set up an online store and sell products. The Shopify platform offers online retailers a suite of services for payments, marketing, shipping, and customer engagement.

## What is the Microsoft Dynamics 365 Business Central Shopify Connector?

With the Shopify Connector, businesses can link their Shopify stores with [!INCLUDE[prod_short](../includes/prod_short.md)] to maximize business productivity. Using the Shopify Connector, they can access and manage insights from their business and their Shopify online store as one unit.

### Capabilities

- Support for more than one Shopify shop
  - Each shop has its own setup, including a collection of products and locations used to calculate inventory and price lists.  
- Bidirectional synchronization of items or products
  - The connector synchronizes images, item variants, bar codes, vendor item numbers, extended and marketing texts, tags and metafields.  
  - Export item attributes to Shopify.  
  - Use selected customer price groups and discounts to define prices exported to Shopify.
  - Define prices and discounts for product catalogs linked to B2B companies.
  - Decide whether items can be created automatically or only allow updates to existing products.
- Synchronization of inventory levels
  - Choose some or all of the available locations in [!INCLUDE [prod_short](../includes/prod_short.md)].  
  - Update inventory levels on multiple locations in Shopify.  
- Bidirectional synchronization of customers and companies
  - Smart-map customers by phone and email.  
  - Use specific country/region templates when creating customers, which helps ensure that tax settings are correct.  
- Import orders from Shopify
  - Include orders created in various sales channels, such as online store, **Shopify POS** or **B2B**.
  - Shipping costs, gift cards, tips, shipping and payment methods, transactions, and risk of fraud, return, refund or cancelation information.
  - During import, you can automatically create customers in [!INCLUDE [prod_short](../includes/prod_short.md)] or decide to manage the customers in Shopify.  
  - Receive payout information from Shopify Payments.
- Track fulfillment information
  - Optionally, choose to transfer item tracking information from [!INCLUDE [prod_short](../includes/prod_short.md)] to Shopify.
- Headless integration
  - Enable automatic synchronization of products, inventory, orders, fulfillments, and more.

## Why did Microsoft and Shopify form this partnership?

[!INCLUDE[prod_short](../includes/prod_long.md)] teamed up with Shopify to help our customers create a better shopping experience. While Shopify provides merchants with an easy-to-use commerce solution, [!INCLUDE[prod_short](../includes/prod_short.md)] offers comprehensive business management across finance, sales, service, and operations teams. Use the seamless connection between the applications to synchronize orders, stock, and customer information to fulfill orders faster, and better serve customers.

## Which Microsoft products work with the Shopify Connector?

The connector is available only for [!INCLUDE[prod_short](../includes/prod_short.md)] online. The connector is preinstalled for new environments. Organizations with existing environments can download and install the connector from AppSource. The organization must have both a [!INCLUDE [prod_short](../includes/prod_short.md)] license and a Shopify license to use the connector. To learn more about supported countries/regions, languages, and editions of [!INCLUDE[prod_short](../includes/prod_short.md)], go to [Shopify Connector on the AppSource](https://go.microsoft.com/fwlink/?linkid=2196238).

It isn't available for on-premises deployments.

The Shopify connector doesn't work for [Embed App](/dynamics365/business-central/dev-itpro/deployment/embed-app-overview), where the client URL has the `https://[application name].bc.dynamics.com` format.

The Shopify connector doesn't work with other Dynamics 365 applications, like Dynamics 365 Sales or Dynamics 365 Supply Chain Management.

## What support is offered for the Shopify Connector?

### [!INCLUDE[prod_short](../includes/prod_short.md)]

The Shopify Connector is covered by the current support model. Learn more at [Technical Support](/dynamics365/business-central/dev-itpro/administration//manage-technical-support) (in English only).

Get help from a consultant who knows the Shopify Connector for [!INCLUDE[prod_short](../includes/prod_short.md)], to meet your unique, business-specific requirements. Search in [Consultancy Services](https://aka.ms/BCShopifyConsultant).

### Shopify

Get help with Shopify from the [General Shopify Help Center](https://help.shopify.com/), or from [24/7 Support for your store as a Shopify merchant](https://help.shopify.com/questions#/).

You can also explore [Experts Marketplace](https://experts.shopify.com/) to find the right experts who offer services for Shopify merchants.

## Currently unsupported features; however, we're tracking them and may consider adding them

- Markets
  - Prices per country/region. One price list is available for the selected currency. Shopify handles the conversion to other currencies.
- Draft orders

## Is the Shopify Connector extensible?

The Shopify Connector offers a few points of extensibility. We're keeping the number of points to a minimum so that we can follow the rapid development on the Shopify side without introducing breaking changes. However most important scenarios are covered. For more details and examples, see [Extend the Shopify Connector](/dynamics365/business-central/dev-itpro/developer/devenv-extending-shopify).
Instead of building every modification as extension, we suggest exploring if you can contribute code to the Shopify Connector through a co-development process.

## Is the Shopify Connector open for contribution?

This extension is open for contributions from our community. You can find the [source code](https://github.com/microsoft/ALAppExtensions/tree/main/Apps/W1/Shopify) in the Microsoft AL application add-ons repository.

## Building your version of the Shopify Connector

According to Shopify, if you want to build and publish a connector app on Shopify marketplace that has the primary purpose of transferring or sharing merchant data to a third party ([!INCLUDE [prod_short](../includes/prod_short.md)]), you must have written consent from Shopify. As part of this process, you must get consent from Microsoft in the "End Recipient Data Acknowledgement Form". We need to ask you to handle the matter with Shopify because Microsoft can't sign third-party agreements.

### What to do

Check the Shopify requirements because you still might be able to have an unlisted app.

Alternatively, the Shopify Connector for [!INCLUDE [prod_short](../includes/prod_short.md)] constantly gets new features and new customers. If you discover a specific gap, consider [submitting a product suggestion](https://aka.ms/bcideas) or a code contribution to [!INCLUDE [prod_short](../includes/prod_short.md)]. For requirements that might not be relevant for a majority of customers, and can't be easily addressed by the current extensibility model, please reach out to the [!INCLUDE [prod_short](../includes/prod_short.md)] development team to discuss the use case. We should be able to find a feasible solution.

## See Also

[Get Started with the Connector for Shopify](get-started.md)  
