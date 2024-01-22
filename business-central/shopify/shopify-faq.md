---
title: FAQ for technical details
description: Implementation details related to the Shopify connector.
ms.date: 03/27/2023
ms.topic: article
ms.service: dynamics365-business-central
author: brentholtorf
ms.author: bholtorf
---

# FAQ for Technical Details

This article answers frequently asked questions about the Shopify connector.

## What is Shopify?

Shopify is a subscription-based application that allows anyone to set up an online store and sell products. The Shopify platform offers online retailers a suite of services for payments, marketing, shipping, and customer engagement.

## What is the Microsoft Dynamics 365 Business Central Shopify connector?

With the Shopify connector, businesses can link their Shopify store (or stores) with [!INCLUDE[prod_short](../includes/prod_short.md)] to maximize business productivity. Using the Shopify connector, they can access and manage insights from their business and their Shopify online store as one unit.

### Capabilities

- Support for more than one Shopify shop
  - Each shop has its own setup, including a collection of products and locations used to calculate inventory and price lists.  
- Bi-directional synchronization of items or products
  - The connector synchronizes images, item variants, bar codes, vendor item numbers, extended texts, and tags.  
  - Export item attributes to Shopify.  
  - Use selected customer price groups and discounts to define prices exported to Shopify.  
  - Decide whether items can be created automatically or only allow updates to existing products.  
- Synchronization of inventory levels
  - Choose some or all of the available locations in [!INCLUDE [prod_short](../includes/prod_short.md)].  
  - Update inventory levels on multiple locations in Shopify.  
- Bi-directional synchronization of customers
  - Smart-map customers by phone and email.  
  - Use specific country/region templates when creating customers, which helps ensure that tax settings are correct.  
- Import orders from Shopify
  - Include orders created in various sales channels, such as Online store or **Shopify POS**.
  - Shipping costs, gift cards, tips, shipping and payment methods, transactions, and risk of fraud.  
  - During import, you can automatically create customers in [!INCLUDE [prod_short](../includes/prod_short.md)] or decide to manage the customers in Shopify.  
  - Receive payout information from Shopify Payments.
- Track fulfillment information
  - Optionally, choose to transfer item tracking information from [!INCLUDE [prod_short](../includes/prod_short.md)] to Shopify.  

## Why did Microsoft and Shopify form this partnership?

[!INCLUDE[prod_short](../includes/prod_long.md)] is teaming up with Shopify to help our customers create a better shopping experience. While Shopify provides merchants with an easy-to-use commerce solution, [!INCLUDE[prod_short](../includes/prod_short.md)] offers comprehensive business management across finance, sales, service, and operations teams. Use the seamless connection between the applications to synchronize orders, stock, and customer information to fulfill orders faster, and better serve customers.

## Which Microsoft products are the Shopify connector available for?

This feature is available only for [!INCLUDE[prod_short](../includes/prod_short.md)] online, starting with version 20.1. It isn't available for on-premises deployments. The connector is pre-installed for new environments. Organizations with existing environments can download and install the connector from AppSource. The organization must have both a [!INCLUDE [prod_short](../includes/prod_short.md)] license and a Shopify license to use the connector. To learn more about supported countries/regions, languages, and editions of [!INCLUDE[prod_short](../includes/prod_short.md)], go to [Shopify Connector on the AppSource](https://go.microsoft.com/fwlink/?linkid=2196238).

The Shopify connector doesn't work for [Embed App](/dynamics365/business-central/dev-itpro/deployment/embed-app-overview), where the client URL has the `https://[application name].bc.dynamics.com` format.

## What support is offered for the Shopify connector?

### [!INCLUDE[prod_short](../includes/prod_short.md)]

The Shopify connector is covered by the current support model. Learn more at [Technical Support](/dynamics365/business-central/dev-itpro/administration//manage-technical-support) (in English only).

Get help from a consultant who knows the Shopify connector for [!INCLUDE[prod_short](../includes/prod_short.md)], to meet your unique business-specific requirements. Search in [Consultancy Services](https://aka.ms/BCShopifyConsultant).

### Shopify

Get help with Shopify from the [General Shopify Help Center](https://help.shopify.com/), or from [24/7 Support for your store as a Shopify merchant](https://help.shopify.com/questions#/).

You can also explore [Experts Marketplace](https://experts.shopify.com/) to find the right experts who offer services for Shopify merchants.

## Currently unsupported features, however, we're tracking them and may consider adding them

- B2B features, including companies, company price lists, and payment terms
  - The extended support of B2B will become available in 2024 Wave 1. For more informaiton, see [Connect Business Central with Shopify B2B](/dynamics365/release-plan/2023wave2/smb/dynamics365-business-central/connect-business-central-shopify-b2b)
- Markets
  - Multiple translations of master data. You can choose one language that will be used for product information export.
  - Prices per country/region. One price list is available for the selected currency. Shopify handles the conversion to other currencies.
- Draft orders

## Is the Shopify connector extensible?

Yes, the Shopify connector is extensible. Check GitHub to access the [list of extensibility points](https://github.com/microsoft/ALAppExtensions/tree/main/Apps/W1/Shopify) and explore some [examples](https://github.com/microsoft/ALAppExtensions/blob/main/Apps/W1/Shopify/extensibility_examples.md).

## Is the Shopify connector open for contribution

Yes, this extension is open for contributions from our community. You can find the [source code](https://github.com/microsoft/ALAppExtensions/tree/main/Apps/W1/Shopify) in the Microsoft AL application add-ons repository.

## Building your version of Shopify Connector

Accordingly to Shopify, if you want to build and publish listing on Shopify market place a connector app, that have the primary purpose of transferring or sharing merchant data to a third party ([!INCLUDE [prod_short](../includes/prod_short.md)]), you will be required to have written consent from Shopify, as part of this process you will be required to get consent from Microsoft in the "End Recipient Data Acknowledgement Form", we need to ask you to handle the matter with Shopify as Microsoft cannot sign 3rd party agreements.

### What to do:
Check Shopify requirements, as you still might be able to have unlisted app.

Alternatively, the Shopify Connector for Business Central constantly gets new features and new customers. If you discovered specific gap, please either consider submitting a product suggestion (https://aka.ms/bcideas) or code contribution to Business Central. For requirements that might not be relevant for majority of customers, that cannot be easily addressed by the current extensibility model, please reach out and discuss the use case with the Business Central Development team. We should be able to find a feasible solution.


## See Also

[Get Started with the Connector for Shopify](get-started.md)  
