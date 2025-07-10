---
title: Working with Shopify POS
description: Special notes related to Shopify as a Sales Channel.
ms.date: 01/27/2025
ms.topic: shopify-pos
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ms.search.form: 30100, 30167, 
author: brentholtorf
ms.author: andreipa
---

# Working with Shopify POS

Shopify POS (Point of Sale) is a system used to process transactions and accept payments in person. Shopify POS connects to Shopify back office as sales channel ensuring that inventory, payments, and customer data are fully synced as you make sales from your retail store.

Shopify Connector imports orders created via Shopify POS the same way as orders created via other channels, like Online store. However there some nuances you might want to be aware.

## Testing 

To test Shopify POS on a trial or development store, use *Shopify payments* in test mode for credit card transactions. The test cards from *(for testing) Bogus Gateway* will not work. For more information about testing see, [Create and Set up Shopify Accounts](hopify-account.md)

## Order handling

It is common, that orders created via POS are immidiatelly fulfilled by Shopify. It is important to check that the **Automatically archive the order** is disabled in the **Order Processing** section of the [**General**](https://www.shopify.com/admin/settings/general) settings in your **Shopify admin** as you can't import orders that are archived in Shopify. 

If Shopify Order is already fulfilled, when you choose **Create sales document** action a **Sales Invoice** gets created.  As **Sales Invoice** doesn't reduce inventory level, it might be a good idea to post such invoices as soon as they are imported, for more information, see [To schedule recurring tasks](background#to-schedule-recurring-tasks)

## Customer

Shopify POS allows you to create orders without customer or, if customer requested receipt, simple customer record that only contains email or phone number. 

Shopify Connector requires Shopify customer to have at least one address, otherwise it will not be able to create missing customer in [!INCLUDE [prod_short](../includes/prod_short.md)]. Neither **Auto Create Unknown Customer** toggle nor the **Create Customer** action will be able to create customer. 
As **Sell-to Customer No.** and **Bill-to Customer No.** fields are mandatory for processing Shopify Order and creation of sales document, you have following options available: 

- Create another Shopify Shop in [!INCLUDE [prod_short](../includes/prod_short.md)] and use it for POS orders only. Then you can configure usage of the **Default Customer No.** for all orders. For more information, see [Different processing rules for orders](synchronize-orders.md#different-processing-rules-for-orders). If you have several POS locations you might want to use different customers for them. Consider using Shopify Flow to assign tags to orders to distinguish orders from different locations.

- Use extensibility to populate customer information. You can find code example here [Extending Shopify](/dynamics365/business-central/dev-itpro/developer/devenv-extending-shopify#populate-fields-on-an-imported-shopify-order). You might need help from Microsoft Partner for that.


## Related information

[Get Started with the Connector for Shopify](get-started.md)  
