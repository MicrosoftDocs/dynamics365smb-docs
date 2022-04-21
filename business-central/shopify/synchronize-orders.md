---
title: Synchronize and fulfill sales orders
description: Setup and execute import and processing of sales order from Shopify.
ms.date: 03/21/2022
ms.topic: article
ms.service: dynamics365-business-central
author: edupont04
ms.author: andreipa
manager: 
---

# Synchronize and fulfill sales orders

## Settings related to import of orders on the Shopify Shop Card
Besides normal item, your Shopify order can have extra amounts on top, such as shipping charges or, if enabled, tips. These amounts will be posted directly to G/L Accounts. Choose G/L Account that should be used for specific transactions:
- **Shipping Cost Account**
- **Sold Gift Card Account**, for more information, see [Gift Card](synchronize-orders.md#gift-cards)
- **Tip account**  

Enable **Auto Create Orders**  to automatically create sales documents in [!INCLUDE[prod_short](../includes/prod_short.md)] once Shopify order is imported.
Sales document in [!INCLUDE[prod_short](../includes/prod_short.md)] contains link to Shopify order. If you enable **Shopify Order No. on Doc. Line** then this information will be repeated in sales line of type Comment.

With the **Tax area source** field you can define priority on how to select tax area code or VAT Business Posting Group based on address. This is relevant for countries with sales tax, but can be also used for VAT countries. For more information, see [Tax remarks](synchronize-orders.md#tax-remarks).
 
### Shipment method mapping
If you want automatically fill in **Shipment method code** for sales documents imported from Shopify, you need to configure **Shipment method mapping**.

1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shop**, and then choose the related link.
2. Select the Shop for which you want to define mapping to open **Shopify Shop Card** page.
3. Choose the **Shipment Method Mapping** action. 
4. Fill in the **Name** field with name of shipping method from Shopify. You can find them in the [**Shipping**](https://www.shopify.com/admin/settings/payments) settings in your **Shopify admin**. The record also created automatically when you import shopify orders.
5. Fill in the **Code** with the corresponding shipping method in [!INCLUDE[prod_short](../includes/prod_short.md)].

> [!NOTE]
> If multiple shipping charges are assosiated with Sales Order - only one will be selected as Shipping Method and assigned to sales document.

### Payment method mapping
If you want automatically fill in **Payment method code** for sales documents imported from Shopify, you need to configure **Payment method mapping**.

1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shop**, and then choose the related link.
2. Select the Shop for which you want to define mapping to open **Shopify Shop Card** page.
3. Choose the **Payment Method Mapping** action. 
4. Fill in the **Gateway** and **Credit Card Company** fields with name of payment method from Shopify. The record also created automatically when you import shopify orders.
5. Fill in the **Payment Method** with the corresponding payment method in [!INCLUDE[prod_short](../includes/prod_short.md)].
6. Fill in the **Priority** field for cases when customer uses multiple means of payment. The payment method with the highest priority will be selected in the sales document. If both payment methods have the same priority, the payment method with the highest amount will be used.

## Execute Order Synchronization

Following procedure describes how to perform import and update of sales orders.

> [!NOTE]
> Archived orders in Shopify can not be imported. Disable **Automatically archive the order** in the **Order Processing** section of the **Checkout** settings in your **Shopify admin** to make sure that all orders are imported to [!INCLUDE[prod_short](../includes/prod_short.md)]. If you need to import archived order, use **Unarchive Orders** action in the [Orders](https://www.shopify.com/admin/orders) page of Shopify Admin.

1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shop**, and then choose the related link.
2. Select the Shop for which you want to import orders to open **Shopify Shop Card** page.
3. Choose the **Orders** action. 
4. Choose **Sync Orders From Shopify**
5. Define filters on orders as necessary. For example you can import fully paid orders or with low risk level.
6. Click ok.

Alternatively you can search for **Sync Orders From Shopify** batch job.

Once import completed, you can explore Shopofy Order and find all related information, such as payment transactions, shipping costs, fulfillments, risk level. You can also see order confirmation send to the customer by choosing **Shopify Status Page** action.

> [!NOTE]
> You can navigate to the **Shopify Orders** window directly, in this case you will see orders from all shops, but only open. To review completed orders you need to open **Shopify Orders** page from the specific **Shopify Shop Card** window.


## Create Sales Document in [!INCLUDE[prod_short](../includes/prod_short.md)] 

If **Auto Create Orders** toggle is enabled on **Shopify Shop Card** system will try to create sales document once order is imported. However if system encounters any issues, for example if customer or product is missing you will need to fix the problem and try create sales order again.

### To create sales document:
1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shop**, and then choose the related link.
2. Select the Shop for which you want to synchronize items to open **Shopify Shop Card** page.
3. Choose the **Orders** action. 
4. Select order for which you want to create sales document and choose the **Create Sales Documents** action
5. Click Yes.

If Shopify Order requires fulfillment system will create **Sales Order**, for fulfilled Shopify orders, for example ones that contain only gift card, system will create **Sales Invoice**.

A sales document is now created and can be handled by using the standard [!INCLUDE[prod_short](../includes/prod_short.md)] functionalities.

### Dealing with missing customer

If your settings prevent system to create customer automatically and it could not find proper existing customer you assign customer to Shopify Order manually. There are following options:

- You can assign **Sell-to Customer No.** directly in the **Shopify Order** by choosing from list of existing customers.
- You can select a Customer template code and create and assign the customer via the **Create new customer** action in the **Shopify Order**. 
- You can map existing customer to the related **Shopify Customer** in the **Shopify Customers** window and then choose the **Find Mapping** action in the **Shopify Order**. 

### Tax remarks
While imported Shopify Order contains information about taxes, when you create sales document the taxes will be recalculated. That's why it is important that VAT/Tax settings are correct in [!INCLUDE[prod_short](../includes/prod_short.md)].

* Multiple product tax/VAT rates. For example some product categories are liable for reduced tax rate. Those items must exist in [!INCLUDE[prod_short](../includes/prod_short.md)] and be mapped to Shopify Products. Otherwise with automatic creation of missing items the VAT Product Posting Group will be used.

* Address dependent tax rates. Use the **Tax area source** field together with **Customer Templates** table to overwrite standard logic that fills in **Tax Area Code** in the sales document. The **Tax area source** field specifies priority of where system should take information about Country/Region and Country/Province. Then system finds corresponding record in the Shopify Customer Templates and uses **Tax Area Code**, **Tax Liable**, **VAT Bus. Posting Group** in creates sales document.


## Synchronize Shipments to Shopify

When a sales order that is created from a Shopify Order, is shipped, you can synchronize the shipments to Shopify.

1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sync Shipments to Shopify**, and then choose the related link.
2. Define filters on shipments as necessary. For example you can update shipment posted at specific date.
3. Click ok.

Order in Shopify will be marked as fulfilled. The customer will automatically receive a shipment notice email or sms.
If a Shipping Agent and a Tracking Code are specified on the shipment, the tracking information will be included in the email.

> [!NOTE]
> Remember to execute **Synchronize Orders from Shopify** to update Fulfilment status of order in [!INCLUDE[prod_short](../includes/prod_short.md)], but also archives completelly paid and fulfilled orders in both Shopify and in [!INCLUDE[prod_short](../includes/prod_short.md)]


### Shipping agents and tracking URL
If the **Posted Sales Shipment** document contains **Shipping Agent Code** and/or **Package Tracking No.** this information will be sent to Shopify and to end-customer in the shipping confirmation email.

Tracking company will be populated based on Shipping Agent record in following priorities (from highest to lowest):
* **Shopify Tracking Company**
* **Name**
* **Code**

If the **Package Tracking URL** field is filled in for Shipping Agent record, then shipping confirmation will contain Tracking URL as well.

## Gift Cards
In the Shopify Shop you can sell gift cards, which can be later used to pay for real products.

When dealing with gift cards, it is important to fill in **Sold Gift Card Account** in the **Shopify Shop Card** window. The sold gift card will be synchronized together with orders as line.
Applied gift card will be also imported with order, but now as transaction. Notice that gift card doesn't reduce amount to invoice.

To review issued and applied gift cards choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Gift Cards**, and then choose the related link.

## Transactions
The payments transactions that took place in Shopify are synchronized together with the orders and can be viewed from the Shopify Order.

To review all transactions choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Transactions**, and then choose the related link.

## Payouts

If your store has Shopify Payments enabled, then you receive payments through Shopify Payouts when a customer pays using Shopify Payments and accelerated checkouts.

1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shop**, and then choose the related link.
2. Select the Shop for which you want to synchronize payouts to open **Shopify Shop Card** page.
3. Choose the **Sync Payouts** action. 

To review all payouts choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payouts**, and then choose the related link.

