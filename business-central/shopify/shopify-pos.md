---
title: Working with Shopify POS
description: Special notes related to Shopify as a Sales Channel.
ms.date: 07/14/2025
ms.topic: article
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ms.search.form: 30100, 30167, 
author: brentholtorf
ms.author: andreipa
---

# Working with Shopify POS

Shopify POS (Point of Sale) lets you process transactions and accept payments in person. Shopify POS connects to Shopify back office as a sales channel to ensure that inventory, payments, and customer data fully synchronizes while you make sales from your retail store.

Shopify Connector imports orders created through Shopify POS in the same way as orders you create through other channels, such as Online store. However, there some nuances you might want to be aware of.

## Testing

To test Shopify POS on a trial or development store, use **Shopify payments** in test mode for credit card transactions. The test cards from **(for testing) Bogus Gateway** don't work. To learn more about testing, go to [Create and set up Shopify accounts](shopify-account.md).

## Order handling

Orders you create through POS are often immediately fulfilled by Shopify. It's important to check that the **Automatically archive the order** toggle is disabled in the **Order Processing** section of the [**General**](https://www.shopify.com/admin/settings/general) settings in your **Shopify admin** because you can't import orders that are archived in Shopify.

If you already fulfilled the Shopify order, when you choose the **Create sales document** action you create a **Sales Invoice**. Because a sales invoice doesn't reduce inventory levels, it might be a good idea to post such invoices as soon as you import them. Learn more at [To schedule recurring tasks](background.md#to-schedule-recurring-tasks).

## Customer

Shopify POS allows you to create orders without specifying a customer. Or, if the customer requested a receipt, you can create a simple customer record that only contains an email or phone number.

Shopify Connector requires that a Shopify customer has at least one address. Otherwise, it can't create the customer in [!INCLUDE [prod_short](../includes/prod_short.md)]. Neither **Auto Create Unknown Customer** toggle nor the **Create Customer** action can create a customer.

Because the **Sell-to Customer No.** and **Bill-to Customer No.** fields are mandatory for processing a Shopify order and creating a sales document, the following options are available:

- Create another Shopify Shop in [!INCLUDE [prod_short](../includes/prod_short.md)] and use it for POS orders only. Then, you can configure usage of the **Default Customer No.** for all orders. Learn more at [Different processing rules for orders](synchronize-orders.md#different-processing-rules-for-orders). If you have several POS locations, you might want to use different customers for them. Consider using Shopify Flow to assign tags to orders so you can distinguish between orders from different locations.

- Use extensibility to populate customer information. You can find a code example in [Extending Shopify](/dynamics365/business-central/dev-itpro/developer/devenv-extending-shopify#populate-fields-on-an-imported-shopify-order). You might need help from Microsoft partner.

## Related information

[Shopify Connector overview](shopify-connector-overview.md)  
[FAQ for the Shopify connector](shopify-faq.md)  
[Troubleshoot the Shopify Connector](troubleshoot.md)  
[Walkthrough: Setting Up and Using Shopify Connector](walkthrough-setting-up-and-using-shopify.md)  
