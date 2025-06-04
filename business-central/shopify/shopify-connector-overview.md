---
title: Shopify Connector Overview
description: Learn to use Shopify Connector to synchronize orders, stock, and customer information to fulfill orders faster, and better serve customers.
author: andreipanko
ms.author: andreipa
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords:
ms.date: 01/24/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# What is Shopify?

Shopify is a subscription-based application that allows you to set up an online store and sell products. The Shopify platform offers online retailers a suite of services for payments, marketing, shipping, and customer engagement.

## What is the Microsoft Dynamics 365 Business Central Shopify Connector?

With the Shopify Connector, businesses can link their Shopify stores with [!INCLUDE[prod_short](../includes/prod_short.md)] to maximize business productivity. Using the Shopify Connector, you can access and manage insights from your business and your Shopify online store as one unit.

### Capabilities

- Support for more than one Shopify shop.
  - Each shop has its own setup, including a collection of products and locations used to calculate inventory and price lists.  
- Bidirectional synchronization of items or products.
  - The connector synchronizes images, item variants, bar codes, vendor item numbers, extended and marketing texts, translations, tags, and metafields.  
  - Export item attributes to Shopify.
  - Activate sales channels which you want to use when you sync products from [!INCLUDE [prod_short](../includes/prod_short.md)] to Shopify.
  - Use selected customer price groups and discounts to define prices exported to Shopify.
  - Define prices and discounts for product catalogs linked to B2B companies.
  - Decide whether items can be created automatically or only allow updates to existing products.
- Synchronize inventory levels.
  - Choose some or all of the available locations in [!INCLUDE [prod_short](../includes/prod_short.md)].  
  - Update inventory levels on multiple locations in Shopify.  
- Bidirectional synchronization of customers and companies.
  - Smart-map customers by phone and email.
  - Use specific country/region templates when creating customers, which helps ensure that tax settings are correct.
  - Smart-map B2B companies by tax or registration numbers.
- Import orders from Shopify
  - Include orders created in various sales channels, such as online stores, **Shopify POS**, or **B2B**.
  - Shipping costs, gift cards, tips, shipping and payment methods, payment terms and transactions, PO number, risk of fraud, return, refund, or cancellation information.
  - During import, you can automatically create customers in [!INCLUDE [prod_short](../includes/prod_short.md)] or decide to manage the customers in Shopify.  
  - Receive payout information from Shopify Payments.
- Track fulfillment information.
  - Optionally, choose to transfer item tracking information from [!INCLUDE [prod_short](../includes/prod_short.md)] to Shopify.
- Export posted sales invoices
  - Buyers can sign in to Shopify and access all their invoices, regardless of which app they were created in.
- Integrate easily.
  - Enable automatic synchronization of products, inventory, orders, fulfillments, and more.
  - Rich logging capabilities that helps with troubleshooting if ever needed.

## Why did Microsoft and Shopify form this partnership?

[!INCLUDE[prod_short](../includes/prod_long.md)] teamed up with Shopify to help our customers create a better shopping experience. While Shopify provides merchants with an easy-to-use commerce solution, [!INCLUDE[prod_short](../includes/prod_short.md)] offers comprehensive business management across finance, sales, service, and operations teams. Use the seamless connection between the applications to synchronize orders, stock, and customer information to fulfill orders faster, and better serve customers.

## Set up and run synchronization

The following table describes a sequence of tasks related to setting up and running synchronizations, with links to the articles that describe them.

|**To**|**See**|  
|------------|-------------|  
| Connect [!INCLUDE [prod_short](../includes/prod_short.md)] to the Shopify online store.| [Get started with the Shopify connector](get-started.md)|
| Set up and run synchronizations of items between Shopify and [!INCLUDE [prod_short](../includes/prod_short.md)]. | [Synchronize items with Shopify](synchronize-items.md)|
| Send inventory levels to Shopify.|[Synchronize inventory with Shopify](synchronize-items.md#sync-inventory-to-shopify)|
| Send main and undiscounted prices to Shopify. |[Synchronize prices with Shopify](synchronize-items.md#sync-prices-with-shopify)|
| Learn how various settings in Shopify affect the storefront prices and taxes that display to customers.| [Set up taxes for the Shopify connection](setup-taxes.md)|
| Import customers and companies from or export to Shopify.| [Synchronize customers and companies with Shopify](synchronize-customers.md)|
| Set up and run import and processing of sales orders from Shopify.| [Synchronize and fulfill sales orders with Shopify](synchronize-orders.md)|
| Set up and run import of transactions and payouts from Shopify.| [Synchronize transactions and payouts](transactions-and-payouts.md)|
| Configure synchronization of data between [!INCLUDE [prod_short](../includes/prod_short.md)] and Shopify in the background.| [Automate Shopify synchronization using job queue](background.md)|

## Demonstration and testing

The following table contains links the articles that help you to try, demonstrate, and explore the Shopify Connector.

|**To**|**See**|  
|------------|-------------|  
| Create and set up a Shopify account for testing.| [Create and set up a Shopify account](shopify-account.md)|
| Try various integration scenarios for demonstrating workflows between Shopify and [!INCLUDE [prod_short](../includes/prod_short.md)].| [Walkthrough: Set up and use the Shopify connector](walkthrough-setting-up-and-using-shopify.md)|
| Review different approaches for testing. | [Testing strategies](get-started.md#testing-strategies)|

## Support and troubleshooting

Find information related to support and troubleshooting.

|**To**|**See**|  
|------------|-------------|  
| Learn what to do if something goes wrong when you synchronize data between Shopify and [!INCLUDE [prod_short](../includes/prod_short.md)].| [Troubleshoot the Shopify connector](troubleshoot.md)|
| Learn implementation details related to the Shopify Connector.| [FAQ for the Shopify connector](shopify-faq.md)|
| Check support options for Shopify Connector| [Support for the Shopify Connector](shopify-support.md)|

## [!INCLUDE[prod_short](../includes/free_trial_md.md)]  

[!INCLUDE[footer-include](../includes/footer-banner.md)]

## Related information

[Get started with the Shopify Connector](get-started.md)  
[Walkthrough: Set up and use the Shopify Connector](walkthrough-setting-up-and-using-shopify.md)
