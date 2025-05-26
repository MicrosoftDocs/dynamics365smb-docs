---
title: Service commitments in subscription billing
description: You can use service commitments in subscription billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: 
ms.search.form: 
ms.date: 08/14/2024
ms.service: dynamics-365-business-central
---

# Service commitments in subscription billing

Service commitments represent obligations to customers and suppliers. They usually begin with the delivery of an item to the customer, include subsequent support, and govern billing arrangements. A service commitment can also be the subject of provision itself, for example, in the case of a support service.

During the sales process, all relevant information about appropriately set up items is collected and stored in the form of a service object. The service object is created automatically when the item is delivered (posting of sales shipment).

Service commitment templates and service commitment packages are available for mapping and setting up service commitments. Service commitments are grouped into contracts (customer and vendor contracts) for management and billing purposes.

Service commitments include the details of the obligations that the supplier of a product assumes towards its customers, which in turn are covered by its supplier, if applicable.

The following image shows the use of service commitments.

:::image type="content" source="../../media/srb use of service commitments.png" alt-text="Use of service commitments.":::

## Service commitment templates​

You can create service commitment templates to simplify the process of creating service commitment packages and the details on their lines. The following section explains the interrelationships of the fields.

## Service commitment packages​

Service commitments are grouped into service commitment packages. You can use then **Assigned Items** action to assign them to items. At the time of delivery, the variable parameters (such as price calculations and durations) are converted into absolute values and attached as service commitments to the sold item (service object).

A service commitment package corresponds to the unit that's offered and sold to the customer. Both the service liabilities to the customer and the service receivables towards the own suppliers can be stored.

> [!TIP]
> To simplify the creation of a service commitment package, you can use the **Copy Service Commitment Package** action to an existing service commitment package, and then change it for the new purpose.

## Overview of service commitment package​ fields

* In addition to the unique **Code** and **Description**, you can specify a **Price Group** to use when pricing service commitments. To learn more, go to [Price group in sales service commitments and service objects​](#price-group-in-sales-service-commitments-and-service-objects).
* **Partner** specifies whether to create a customer or vendor service commitment later. Accordingly, the service commitments can then be called into customer or vendor contracts and invoiced through purchase or sales invoices.
* **Template** indicates whether the line was created based on a service commitment template. Specifying a service commitment template is optional. You cal also manually enter the line.
* **Description** specifies the description of the service commitment.
* To learn more about the **Invoicing** field, go to [Types of Service Commitments](#types-of-service-commitments).
* To learn more about the **Invoicing via Item No.** field, go to [Control revenue accounts​ via invoicing items](#control-revenue-accounts-via-invoicing-items).
* To learn more about the **Calculation Base Amount Type** field, go to [Pricing and calculation types](#pricing-and-calculation-types).
* **Calculation Base Amount %** is the percentage of the calculation base amount that is used in the sales process to price the service commitments.
* **Calculation Base Period** specifies the period to which the service amount should subsequently relate. For example, enter **1M** if the amount refers to one month, or **12M** if the amount refers to one year.
* **Billing Rhythm** defines how often to bill service commitments.
* The Dateformula in the **Service Commitment Start Formula** field specifies the time offset at which a service commitment becomes valid.
* **Initial Term** specifies the minimum term of the service commitments. If the initial term is entered in the sales process and no **Subsequent Term** is entered, the service end date is automatically set to the end of the initial term.
* The Dateformula in the **Subsequent Term** field specifies the duration of the automatic extension after the initial term. If the field is blank in the sales process, and either the **Initial Term** or the **Notice Period** is set at the same time, the service end date is automatically set to the expiration date of the initial term or the notice period.
* The Dateformula in the **Notice Period** field specifies the lead time before a service commitment can be cancelled. A 12 month initial term with a three month notice period means that the due date for termination is reached after nine months.
* **Discount** is used to control whether the service commitment is used for discounts during periodic billing.
* **Price Binding Period** defines the period in which the price won't change after the service commitment is created. When the service commitment is created, the **Next Price Update** date is calculated from the **Service Start Date** and the **Price Fixing Period**. You might need to personalize the page to display the field.

> [!TIP]
> To simplify the creation of items with service commitments, you can store service commitment packages in item templates. If an item is created using a template that includes service commitment packages, the packages automatically transfer to the new item.

## Dimensions​

If a service commitment package contains lines with both **Partner=Customer** and **Partner=Vendor**, the dimensions of the later customer contract line pass to the corresponding vendor contract line. This is important when you analyze data, for example, the service package code is identical in data on both customer and vendor sides.

## Price group in sales service commitments and service objects​

Before the prices for the service commitment s in the sales document can be calculated for the selected line item, the appropriate service commitment package(s) must be determined, including any price group assigned. The following applies:

* If the price group isn't set in the document, only service commitment packages without the price group are used.
* If the service commitment package is set in the document, only service commitment packages with the same price group apply. If no service commitment packages match the price group, service commitment packages without price group are also considered. Service commitment packages that are set as default for the item apply directly. Others are display-only.
* If a service commitment package without a price group isn't found, all service commitment packages are considered. The default package for the item applies directly. Others are display-only.
* If no service commitment package is found, no sales service commitments are created.

The determination of service commitments when manually creating a service object is done in the same way as the creation and calculation of sales service commitments. However, if you change the end user (customer) in the service object, the service commitments must be recalculated if the price group of the new end user (customer) and the service object differ. The user receives a corresponding query. If they confirm, the service commitments are deleted and recreated based on the above criteria. Otherwise, the end user (customer) resets to the original value.

> [!NOTE]
> You can only change the service commitments in the service object if none of the services are linked to a customer contract or vendor contract.

## Types of service commitments​

* Contract

   A service commitment for a service object where the **Invoicing via** field is set to **Contract** will be brought to invoicing in a defined cycle. Optionally, you can specify terms and notice periods.

* Sales

  A service commitment for a service object where **Invoicing via** is set to **Sales** won't be invoiced. The service object and service commitment serve as information only (for example, for the warranty period or the after-sale to a warranty).

> [!NOTE]
> Only service commitments whose template is set to **Contract** in the **Invoicing via** field can be assigned to a customer or vendor contract, and thus billed on a recurring basis through that contract.

## Pricing and calculation types​

Three types of reference values are used to price service commitments via the **Calculation Base Type** field:

* Item Price
* Document Price
* Document Price And Discount)  

To learn more, go to [Price determination of Service Commitments](../sales/price-calculation.md).

## Control revenue accounts​ via invoicing items

Services that you sell along with an item are usually handled by an invoicing item. Depending on the configuration of the posting groups in financial accounting, revenues can post to different revenue accounts for each service commitment to bill. The lookup of the **Invoicing via Item No.** field shows only invoicing items.

Services that are themselves the subject of provisioning (such as a support service) can also contain the posting groups for revenue control. In this case, the **Invoicing via Item No.** field is left blank.

## Example: Warranty as a service commitment​

When a product is sold, a warranty is required by law. This means that the supplier of a product guarantees that the products it supplies have the promised properties. The warranty is usually limited in time.

The statutory warranty can be supplemented by additional warranties or services that you can create as service commitments. For example, manufacturers might grant the customer an extended warranty period from the date of purchase or even service commitments that go beyond what is legally required. For example, free on-site replacement of defective parts.

A service commitment can represent the mapping of these commitments. It contains all relevant service agreements, such as prices (usually zero), validity periods, cancellation periods, and the billing rhythm. Just like other service commitments, the service commitment must be assigned to a contract to be billed (on a recurring basis until it expires). The contract number then displays in the service commitment.

The following example shows a warranty set up as a service commitment. The warranty is free of charge and runs for 12 months.

| Partner | Template | Description | Invoicing via | Invoicing via Item No. | Calculation Base Type | Calculation Base % | Calculation Base Period | Calculation Base Rhythm | Service Commitment Start Formula | Initial Term | Subsequent Term |Cancellation Period|
|--|--|--|--|--|--|--|--|--|--|--|--|--|
|Customer|Guarantee|Warranty|Sale||Item Price|0|12M||12M|
|Supplier|Guarantee|Warranty|Sale||Item Price|0|12M||12M|

The service commitment package contains both a customer and a vendor line, so the customer can make claims within the specified period, but these are also covered by service commitments towards the supplier (for example, the vendor has provided warranty for the items sold).

## Related information

[Sales process](../sales/sales-service-commitments.md)  
