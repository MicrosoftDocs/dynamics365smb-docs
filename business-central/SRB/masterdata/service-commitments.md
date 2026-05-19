---
title: Subscription packages and subscription lines
description: You can use subscription lines in subscription billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: 
ms.search.form: 8059,
ms.date: 02/06/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Subscription packages and subscription lines

Subscription lines represent obligations to customers and suppliers. They usually begin with the delivery of an item to the customer, include subsequent support, and govern billing arrangements. A subscription line can also be the subject of provisioning itself, for example, for a support service.

During the sales process, all relevant information about items is collected and stored in the form of a subscription. The subscription is created automatically when the item is delivered (posting of sales shipment).

Subscription line templates and subscription line packages are available for mapping and setting up subscription lines. Subscription lines are grouped into contracts (customer and vendor subscription contracts) for management and billing purposes.

Subscription lines include the details of the obligations that the supplier of a product assumes towards its customers, which in turn are covered by its supplier, if applicable.

The following image shows the use of subscription lines.

:::image type="content" source="../../media/sb-flow.png" alt-text="Screenshot that shows the flow for subscription lines.":::

## Subscription packages​

Subscription lines are grouped into subscription packages. You can use then **Assigned Items** action to assign them to items. At the time of delivery, the variable parameters (such as price calculations and durations) are converted into absolute values and attached as subscription lines to the sold item (subscription).

A subscription package corresponds to the unit that you offer and sell to a customer. You can store both the service liabilities to the customer and the service receivables to the supplier.

> [!TIP]
> To simplify the creation of a subscription package, you can use the **Copy Subscription Package** action an existing subscription package, and then change it for the new purpose.

## Subscription package​ line templates​

You can create subscription line templates to simplify the process of creating subscription packages and the details on their lines. The following section explains the interrelationships of the fields.

## Overview of subscription package​ and subscription package​ line fields

* In addition to the unique **Code** and **Description**, you can specify a **Price Group** in the header to use when pricing subscription lines. To learn more, go to [Price group in sales subscription lines and subscriptions​](#price-group-in-sales-subscription-lines-and-subscriptions).
* **Partner** specifies whether to create a customer or vendor subscription line later. Accordingly, the subscription lines can then be called into customer or vendor subscription contracts and invoiced through purchase or sales invoices.
* **Template** indicates whether the line was created based on a subscription package​ line template. Specifying a subscription package​ line template is optional. You can also manually enter the line.
* **Description** specifies the description of the subscription package​ line.
* To learn more about the **Invoicing** field, go to [Types of subscription package lines​](#types-of-subscription-package-lines).
* To learn more about the **Invoicing Item No.** field, go to [Revenue recognition](#revenue-recognition).
* To learn more about the **Calculation Base Amount Type** field, go to [Pricing and calculation types](#pricing-and-calculation-types).
* **Calculation Base Amount %** is the percentage of the calculation base amount that is used in the sales process to price the subscription lines.
* **Calculation Base Period** specifies the period to which the service amount relates. For example, enter **1M** if the amount refers to one month, or **12M** if the amount refers to one year.
* **Billing Rhythm** defines how often to bill subscription lines.
* The dateformula in the **Subscription Line Start Formula** field specifies the time offset at which a subscription line becomes valid.
* **Initial Term** specifies the minimum term of the subscription lines. If the initial term is entered in the sales process and no **Subsequent Term** is entered, the service end date is automatically set to the end of the initial term.
* The dateformula in the **Subsequent Term** field specifies the duration of the automatic extension after the initial term. If the field is blank in the sales process, and either the **Initial Term** or the **Notice Period** is set at the same time, the service end date is automatically set to the expiration date of the initial term or the notice period.
* The dateformula in the **Notice Period** field specifies the lead time before a subscription line can be canceled. A 12 month initial term with a three month notice period means that the due date for termination is reached after nine months.
* **Discount** is used to control whether the subscription line is used for discounts during periodic billing.
* **Price Binding Period** defines the period in which the price won't change after the subscription line is created. When the subscription line is created, the **Next Price Update** date is calculated from the **Subscription Line Start Date** and the **Price Fixing Period**. You might need to personalize the page to display the field.

> [!TIP]
> To simplify the creation of subscription items, you can store subscription packages in item templates. If an item is created using a template that includes subscription packages, the packages automatically transfer to the new item.

## Dimensions​

If a subscription package contains lines with both **Partner=Customer** and **Partner=Vendor**, the dimensions of the customer subscription contract line transfer to the corresponding vendor contract line. The transfer is important when you analyze data. For example, the subscription package code is identical in data on both customer and vendor sides.

## Price group in sales subscription lines and subscriptions​

Before you can calculate the prices for the subscription lines in the sales document, you must find the appropriate subscription packages, including any price group assigned. The following conditions apply:

* If the price group isn't set in the document, only subscription packages without the price group are used.
* If the subscription package is set in the document, only subscription packages with the same price group apply. If no subscription packages match the price group, subscription packages without price group are also considered. Subscription packages that are set as default for the item apply directly. Others are display-only.
* If a subscription package without a price group isn't found, all subscription packages are considered. The default package for the item applies directly. Others are display-only.
* If no subscription package is found, no sales subscription lines are created.

The determination of subscription lines when manually creating a subscription is done in the same way as the creation and calculation of sales subscription lines. However, if you change the end user (customer) in the subscription, the subscription lines must be recalculated if the price group of the new end user (customer) and the subscription differ. The user receives a corresponding query. If they confirm, the subscription lines are deleted and recreated based on the above criteria. Otherwise, the end user (customer) resets to the original value.

> [!NOTE]
> You can only change the subscription lines in the subscription if none of the lines are linked to a customer or vendor subscription contract.

## Types of subscription package lines​

* Contract

   You invoice subscription package​ lines for subscriptions where the **Invoicing via** field contains **Subscription Contract** in a defined cycle. Optionally, you can specify terms and notice periods.

* Sales

  Subscription package​ lines for subscriptions where the **Invoicing via** field contains **Sales** aren't invoiced. The subscription and subscription line serve as information only (for example, for the warranty period or the after-sale to a warranty).

> [!NOTE]
> Only subscription lines whose corresponding package line is set to **Subscription Contract** in the **Invoicing via** field can be assigned to a customer or vendor contract, and thus billed on a recurring basis through that contract.

## Pricing and calculation types​

Three types of reference values are used to price subscription lines via the **Calculation Base Type** field:

* Item Price
* Document Price
* Document Price And Discount

To learn more, go to [Price determination of Subscription Lines](../sales/price-calculation.md).

## Revenue recognition

If you sell a typical subscription and invoice it on a recurring basis, the revenue should normally be realized based on the posting groups of the subscription item. You can create a simple subscription package for this (see [example below](#example-subscription-item-simple-monthly-subscription)), in which the **Invoicing Item No.** field simply remains empty. However, if the revenue is to be realized differently from the posting groups of the subscription item, you can set an [invoicing item](../masterdata/items.md) in the field mentioned. If specified, this is used in the invoice line and also for the deferrals. For subscription items, the field is a optional: if an invoicing item is specified here, it will be used. If no invoicing item is specified, the posting groups of the subscription item itself are used.

For scenarios in which the item itself is sold as a one-off, but a part is to be billed on a recurring basis (i.e., **Sales with Subscription** is selected in the **Subscription Option** field on the item card), an invoicing item must necessarily be specified, as the item sold once cannot be used for billing recurringly. An example of such a subscription package can be found [below](#example-sales-with-subscription).

The lookup of the **Invoicing Item No.** field shows only invoicing items.

Depending on the configuration of the posting groups in General Posting Setup, revenues can post to different revenue accounts for each subscription line to bill.

## Example: Subscription Item (simple, monthly subscription)

The get started with a simple, monthly subscription you'll need a subscription item (**Subscription Item** is selected in the **Subscription Option** field on the item card) and a subscription package with just one line. The following example shows such a setup which runs monthly.

| Partner | Template | Description | Invoicing via | Invoicing Item No. | Calculation Base Type | Calculation Base % | Billing Base Period | Billing Rhythm | Subscription Line Start Formula | Initial Term | Subsequent Term | Notice Period|
|--|--|--|--|--|--|--|--|--|--|--|--|--|
|Customer|SUBSCRIPTION-1M|Subscription (monthly)|Subscription Contract||Item Price|100|1M|1M|||||

You can find such an example as part of the Contoso demo data (item "SB1100").

## Example: Sales with Subscription

For the scenario where an item is sold as a one-off but with a recurring part you'll need an item **Sales with Subscription** selected in the **Subscription Option** field on the item card and a subscription package at least one line. The following example shows such a setup where the price for the recurring part is calculated with 10% from the document line for the whole year.

| Partner | Template | Description | Invoicing via | Invoicing Item No. | Calculation Base Type | Calculation Base % | Billing Base Period | Billing Rhythm | Subscription Line Start Formula | Initial Term | Subsequent Term | Notice Period|
|--|--|--|--|--|--|--|--|--|--|--|--|--|
|Customer|SUBSCRIPTION-12M|Subscription (annually)|Subscription Contract|SB1104|Document Price|10|12M|12M|||||

You can find such an example as part of the Contoso demo data (items "SB1103" with invoicing item "SB1104").

## Example: Warranty as a subscription line​

Depending on the product being sold, a warranty may be required by law. This requirement means that the supplier of a product guarantees that the products it supplies have the promised properties. The warranty is often limited in time.

You can supplement the statutory warranty with extra warranties or services that you can create as subscription lines. For example, manufacturers might grant the customer an extended warranty period from the date of purchase or even subscription lines that go beyond what is legally required. For example, free on-site replacement of defective parts.

A subscription line can represent the mapping of these commitments. It contains all relevant service agreements, such as prices (usually zero), validity periods, cancellation periods, and the billing rhythm. Just like other subscription lines, the subscription line must be assigned to a contract to be billed (on a recurring basis until it expires). The contract number then displays in the subscription line.

The following example shows a warranty set up as a subscription line. The warranty is free of charge and runs for 12 months.

| Partner | Template | Description | Invoicing via | Invoicing Item No. | Calculation Base Type | Calculation Base % | Billing Base Period | Billing Rhythm | Subscription Line Start Formula | Initial Term | Subsequent Term | Notice Period|
|--|--|--|--|--|--|--|--|--|--|--|--|--|
|Customer|GUARANTEE|Warranty|Sales||Item Price|0|12M|12M|||||
|Supplier|GUARANTEE|Warranty|Sales||Item Price|0|12M|12M|||||

The subscription package contains both a customer and a vendor line, so the customer can make claims within the specified period. However, this information is also covered by subscription lines towards the supplier. For example, if the vendor provided a warranty for the items.

## Related information

[More examples](../examples.md)
[Sales process](../sales/sales-service-commitments.md)
