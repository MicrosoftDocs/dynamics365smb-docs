---
title: Synchronize and fulfill sales orders
description: Set up and run import and processing of sales order from Shopify.
ms.date: 05/27/2022
ms.topic: article
ms.service: dynamics365-business-central
author: edupont04
ms.author: andreipa
ms.reviewer: solsen
---

# Synchronize and Fulfill Sales Orders

This article describes the necessary settings and steps that you must perform to synchronize and fulfill sales orders.

## Set import of orders on the Shopify Shop Card

A regular Shopify order can have extra amounts on top, such as shipping charges or, if enabled, tips. These amounts will be posted directly to G/L accounts. Choose the G/L account that should be used for specific transactions:

- **Shipping Cost Account**
- **Sold Gift Card Account**, for more information, see [Gift Card](synchronize-orders.md#gift-cards).
- **Tip account**  

Enable **Auto Create Orders**  to automatically create sales documents in [!INCLUDE[prod_short](../includes/prod_short.md)] once the Shopify order is imported.
The sales document in [!INCLUDE[prod_short](../includes/prod_short.md)] contains a link to the Shopify order. If you select the **Shopify Order No. on Doc. Line** field, then this information will be repeated in sales lines of type *Comment*.

In the **Tax area source** field, you can define priority on how to select tax area code or VAT business posting group based on address. This step is relevant for countries with sales tax, but can be used for VAT countries. For more information, see [Tax remarks](synchronize-orders.md#tax-remarks).

### Shipment method mapping

**Shipment method code** for sales documents imported from Shopify, can be filled in automatically. You need to configure **Shipment method mapping**.

1. Go to the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shop**, and choose the related link.
2. Select the Shop for which you want to define mapping to open **Shopify Shop Card** page.
3. Choose the **Shipment Method Mapping** action. The records for shipping methods defined in the [**Shipping**](https://www.shopify.com/admin/settings/payments) settings in your **Shopify admin** gets created automatically.
4. In the **Name** field, you can see name of shipping method from Shopify.
5. Enter the **Shipment Method Code** with the corresponding shipping method in [!INCLUDE[prod_short](../includes/prod_short.md)].

> [!NOTE]  
> If multiple shipping charges are associated with a sales order; only one will be selected as Shipping Method and assigned to sales document.

### Payment method mapping

To fill in the **Payment method code** for sales documents imported from Shopify automatically, you need to configure **Payment method mapping**.

1. Go to the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shop**, and choose the related link.
2. Select the Shop for which you want to define mapping to open **Shopify Shop Card** page.
3. Choose the **Payment Method Mapping** action.
4. In the **Gateway** and **Credit Card Company** fields, enter the name of payment method from Shopify. The record gets created automatically when you import shopify orders.
5. Enter the **Payment Method Code** with the corresponding payment method in [!INCLUDE[prod_short](../includes/prod_short.md)].
6. Set the **Priority** for cases when customer uses multiple means of payment. The payment method with the highest priority gets selected in the sales document. If both payment methods have the same priority, the payment method with the highest amount is used.

### Location mapping

To fill in the **Location Code** for sales documents imported from Shopify automatically, you need to configure **Shopify Shop Locations**.

1. Go to the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shop** and choose the related link.
2. Select the Shop for which you want to configure mapping of locations  to open **Shopify Shop Card** page.
3. Choose the **Locations** action to open **Shopify Shop Locations**.
4. Choose the **Get Shopify Locations** action to import all the locations defined in the Shopify. You can find them in the [**Locations**](https://www.shopify.com/admin/settings/locations) settings in your **Shopify admin**. Note that the location marked as *Default* will be used when importing unfulfilled Shopify orders.
5. Enter the **Default Location Code** with the corresponding location in [!INCLUDE[prod_short](../includes/prod_short.md)].

> [!NOTE]  
> You must configure location mapping if the **Location Mandatory** toggle is enabled in the **Inventory Setup** card, otherwise you won't be able to create sales document.

## Run order synchronization

The following procedure describes how to import and update the sales orders.

> [!NOTE]  
> Archived orders in Shopify can't be imported. Deactivate **Automatically archive the order** in the **Order Processing** section of the **Checkout** settings in your **Shopify admin** to make sure that all orders are imported to [!INCLUDE[prod_short](../includes/prod_short.md)]. If you need to import archived orders, use the **Unarchive Orders** action in the [Orders](https://www.shopify.com/admin/orders) page of Shopify Admin.

1. Go to the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shop**, and choose the related link.
2. Select the Shop for which you want to import orders to open **Shopify Shop Card** page.
3. Choose the **Orders** action.
4. Choose the **Sync Orders From Shopify** action.
5. Define filters on orders as necessary. For example, you can import fully paid orders or the ones with low risk level.
6. Choose the **OK** button.

Alternatively, you can search for **Sync Orders From Shopify** batch job.

You can schedule the task to be performed in an automated manner. For more information, see [Schedule recurring tasks](background.md#to-schedule-recurring-tasks).

## Review imported orders

Once the import is completed, you can explore the Shopify order and find all related information. For example, find the payment transactions, shipping costs, risk level, or fulfillments if the order was already fulfilled in Shopify. You can also see any order confirmation that has been sent to the customer by choosing the **Shopify Status Page** action.

> [!NOTE]  
> You can navigate to the **Shopify Orders** window directly and you'll see orders with *open* status from all shops. To review completed orders, you need to open **Shopify Orders** page from the specific **Shopify Shop Card** window.

## Create sales documents in Business Central

If the **Auto Create Orders** toggle is enabled on **Shopify Shop Card**, the [!INCLUDE[prod_short](../includes/prod_short.md)] tries to create a sales document once order is imported. If the process runs into issues, such as if a customer or product is missing, you'll need to fix the problem. Then you can try to create the sales order again.

### To create sales documents

1. Go to the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shop**, and choose the related link.
2. Select the Shop for which you want to synchronize orders to open **Shopify Shop Card** page.
3. Choose the **Orders** action.
4. Select the order for which you want to create a sales document and choose the **Create Sales Documents** action.
5. Choose **Yes**.

If the Shopify order requires fulfillment, the **Sales Order** will be created. For completely fulfilled Shopify orders, such as those orders that contain only a gift card or which are already handled in Shopify, the **Sales Invoice** gets created.

A sales document is now created and can be managed by using the standard [!INCLUDE[prod_short](../includes/prod_short.md)] functionalities.

### Manage missing customers

If your settings prevent creating a customer automatically and a proper existing customer can't be found, you'll assign a customer to Shopify order manually. There are a few options:

- You can assign the **Sell-to Customer No.** directly in the **Shopify Order** by choosing a customer from the list of existing customers.
- You can select a customer template code, create, and assign the customer via the **Create new customer** action in the **Shopify Order**.
- You can map existing customer to the related **Shopify Customer** in the **Shopify Customers** window and then choose the **Find Mapping** action in the **Shopify Order**.

### Tax remarks

While the imported Shopify order contains information about taxes, the taxes get recalculated when you create the sales document. That recalculatiob makes it important that the VAT/tax settings are correct in [!INCLUDE[prod_short](../includes/prod_short.md)].

- Multiple product tax/VAT rates. For example, some product categories are liable for reduced tax rates. Those items must exist in [!INCLUDE[prod_short](../includes/prod_short.md)] and be mapped to Shopify products. Otherwise, with automatic creation of missing items, the VAT product posting group will be used.

- Address-dependent tax rates. Use the **Tax area priority** field together with **Customer Templates** table to overwrite standard logic that fills in **Tax Area Code** in the sales document. The **Tax area priority** field specifies priority from where the function should take information about country/region and state/province. Then the corresponding record in the Shopify customer templates is found and **Tax Area Code**, **Tax Liable**, and **VAT Bus. Posting Group** is used when a sales document is created.
 
- Price including Tax. The **Prices including Tax**/**Prices including VAT** field in the created sales document doesn't depend on customer, but on **Customer Template** from the Shopify Shop Card or Customer template per country.

### Impact of edits of orders

|Edit|Impact|
|------|-----------|
|In Shopify, change fulfilment location | Original location will be synched to [!INCLUDE[prod_short](../includes/prod_short.md)]. |
|In Shopify, edit order and change quantity| Order header and supplementary tables will be updated in [!INCLUDE[prod_short](../includes/prod_short.md)], lines won't. |
|In Shopify, edit order and add new item | Order header will be updated, lines won't. |
|In [!INCLUDE[prod_short](../includes/prod_short.md)], change location to another location, mapped to Shopify Locations. Post shipment. | After synchronization of fulfilment, location will be updated in Shopify. |
|In [!INCLUDE[prod_short](../includes/prod_short.md)], change location to another location, not mapped to Shopify Locations. Post shipment. | Fulfilment won't be synchronized to Shopify. |
|In [!INCLUDE[prod_short](../includes/prod_short.md)], change decrease quantity. Post shipment. | Shopify order will be marked as partially fulfilled. |
|In [!INCLUDE[prod_short](../includes/prod_short.md)], add new item. Post shipment. | Shopify order will be marked as fulfilled. Lines won't be updated. |

## Synchronize shipments to Shopify

When a sales order that is created from a Shopify order, is shipped, you can synchronize the shipments to Shopify.

1. Go to the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sync Shipments to Shopify**, and choose the related link.
2. Define filters on shipments as necessary. For example, you can update shipment posted at specific date.
3. Choose the **OK** button.

The order in Shopify will be marked as fulfilled. The customer automatically receives a shipment notice email or text message (SMS). If a Shipping agent and a Tracking code are specified on the shipment, the tracking information is included in the email.

> [!NOTE]  
> Remember to run **Synchronize Orders from Shopify** to update fulfillment status of order in [!INCLUDE[prod_short](../includes/prod_short.md)]. The connector functionality also archives completely paid and fulfilled orders in both Shopify and in [!INCLUDE[prod_short](../includes/prod_short.md)] provided the conditions are met.

### Shipping agents and tracking URL

If the **Posted Sales Shipment** document contains **Shipping Agent Code** and/or **Package Tracking No.**, this information will be sent to Shopify and to end-customer in the shipping confirmation email.

Tracking company is populated based on the Shipping Agent record with the following priorities (from highest to lowest):

- **Shopify Tracking Company**
- **Name**
- **Code**

If the **Package Tracking URL** field is filled in for the Shipping agent record, then shipping confirmation will contain a tracking URL as well.

## Gift cards

In the Shopify shop you can sell gift cards, which can be later used to pay for real products.

When dealing with gift cards, it's important to enter a value in **Sold Gift Card Account** field in the **Shopify Shop Card** window. The sold gift card will be synchronized together with orders in line. An applied gift card will also be imported with the order, but now as a transaction. Notice that the gift card doesn't reduce the amount to invoice.

To review the issued and applied gift cards, choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Gift Cards**, and then choose the related link.

## Transactions

The payment transactions that took place at Shopify are synchronized together with the orders and can be viewed from the *Shopify Order*.

To review all transactions, choose the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Transactions**, and select the related link.

## Payouts

If your store has Shopify payments enabled, you'll receive payments through *Shopify Payouts* when a customer pays using Shopify payments and accelerated checkouts.

1. Go to the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shop**, and choose the related link.
2. Select the Shop for which you want to synchronize payouts to open **Shopify Shop Card** page.
3. Choose the **Sync Payouts** action.

To review all payouts, choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payouts**, and select the related link.

## See Also

[Get Started with the Connector for Shopify](get-started.md)  
