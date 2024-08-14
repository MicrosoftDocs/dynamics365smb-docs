---
title: Service commitments
description: You can use service commitments in subscription and recurring billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: 
ms.search.form: 
ms.date: 08/14/2024
ms.service: dynamics-365-business-central
---

# Service Commitments
Service Commitments represent obligations to customers and suppliers. They usually begin with the delivery of an item to the customer, include subsequent support, and govern billing arrangements. A Service Commitment can also be the subject of provision itself, e.g. in the case of a support service.

During the sales process, all relevant information about appropriately set up items is collected and stored in the form of a Service Object. The Service Object is created automatically when the item is delivered (posting of Sales Shipment).

Service Commitment Templates and Service Commitment Packages are available for mapping and setting up Service Commitments.
Service Commitments are grouped into Contracts (Customer and Vendor Contracts) for management and billing purposes.

Service Commitments include the details of the obligations that the supplier of a product assumes towards its customers, which in turn are covered by its supplier, if applicable.


## Warranty
When a product is sold, a warranty is required by law. This means that the supplier of a product guarantees that the products it supplies have the promised properties. The warranty is usually limited in time. <br />
The statutory warranty is usually supplemented by a Service Commitment, i.e. manufacturers grant the customer an extended warranty period from the date of purchase or even Service Commitments that go beyond what is legally indispensable, for example free on-site replacement of defective parts.

Since a Service Commitment represents the mapping of these commitments, it contains all relevant service agreements, such as prices, validity periods, cancellation periods, and the billing rhythm. In order for a Service Commitment to be billed (recurringly), it must be assigned to a contract. The Contract No. is then displayed in the Service Commitment.


## Use of Service Commitments
![](/img/srb/ProcessOverview.png)


## Service Commitment Templates
Service Commitment Templates can be created optionally. They are used to simplify the creation of Service Commitment Packages or their details (lines). The interrelationships of the fields are explained in the [Service Commitment Packages](#service-commitment-packages).


## Service Commitment Packages
Service Commitment Templates are grouped into Service Commitment Packages. These can then be firmly assigned directly to the items (via the call **Assigned Items**). At the time of delivery, the variable parameters (e.g. price calculations and durations) are converted into absolute values and attached as Service Commitments to the sold item (Service Object).

A Service Commitment Package corresponds to the unit that is offered and sold to the customer. In a Service Commitment Package, both the service liabilities to the customer and the service receivables towards the own suppliers can be stored. <br />
The example of the legal warranty shown below illustrates this, as here the customer can make claims within the specified period, but these are simultaneously covered by Service Commitments towards the supplier.

:::tip Copy Service Commitment Packages
To simplify the creation of a Service Commitment Package, an existing Service Commitment Package can be copied using the **Copy Service Commitment Package** action and then customized.
:::


### Overview of the fields in the Service Commitment Package
* In addition to the unique **Code** and **Description**, a **Price Group** can be stored. This allows a Price Group to be taken into account when pricing Service Commitments. For more details please see section [Price Group in Sales Service Commitments and Service Objects](#price-group-in-sales-service-commitments-and-service-objects).
* **Partner** specifies whether a customer or vendor Service Commitment is to be created later. Accordingly, the Services Commitments can then be called into Customer/Vendor Contracts and invoiced via Purchase or Sales Invoices.
* **Template** indicates whether the line was created based on a **Service Commitment Template**. Specifying a *Service Commitment Template* is optional - the line can also be entered manually.
* **Description** specifies the description of the Service Commitment that will be created in further processing.
* For explanation of **Invoicing via** see [Types of Service Commitments](#types-of-service-commitments).
* For explanation of **Invoicing via Item No.** see [Control of revenue accounts](#control-of-revenue-accounts).
* For explanation of **Calculation Base Amount Type** see [Pricing and calculation types](#pricing-and-calculation-types).
* **Calculation Base Amount %** is the percentage of the **Calculation Base Amount** that is used in the sales process to price the Service Commitments.
* **Calculation Base Period** specifies the period to which the Service Amount should subsequently relate. For example, enter 1M if the amount refers to one month or 12M if the amount refers to one year.
* **Billing Rhythm** defines the frequency at which the Service Commitments should be billed later.
* The Dateformula in the **Service Commitment Start Formula** field specifies the time offset at which a Service Commitment becomes valid.
* **Initial Term** specifies the minimum term of the subsequent Service Commitments. If the Initial Term is populated in the sales process and no **Subsequent Term** is entered, the **Service End Date** is automatically set to the end of the Initial Term.
* The Dateformula in the **Subsequent Term** field specifies the duration of the automatic extension after the Initial Term. If the field is blank in the sales process and either the Initial Term or the Notice Period is set at the same time, the Service End Date is automatically set to the expiration date of the Initial Term or the Notice Period.
* The Dateformula in the **Notice Period** field specifies the lead time before a Service Commitments can be cancelled at a later date. A 12 month Initial Term with a 3 month notice period means that the due date for termination is reached after 9 months.
* **Discount** is used to control whether the Service Commitment is used for discounts during periodic billing.
* The **Price Binding Period** defines the period, in which the price will not be changed after the Service Commitment has been created. When the Service Commitment is created, the **Next Price Update** date is calculated from the **Service Start Date** and the **Price Fixing Period**. The field can be displayed using personalization.

### Example
Partner|Template|Description|Invoicing via|Invoicing via Item No.|Calculation Base Type|Calculation Base %|Calculation Base Period|Calculation Base Rhythm|Service Commitment Start Formula|Initial Term|Subsequent Term|Cancellation Period
|--:|--:|--:|--:|--:|--:|--:|--:|--:|--:|--:|--:|--:|
Customer|Guarantee|Warranty|Sale||Item Price|0|12M||12M||
Supplier|Guarantee|Warranty|Sale||Item Price|0|12M||12M||

:::tip Service Commitment Packages in Item Templates
To simplify the creation of items with Service Commitments, Service Commitment Packages can already be stored in the Item Templates. If an item is created using a template that includes Service Commitment Packages, these are automatically transferred to the new item. This is particularly useful if several items are created as [batch processing](/docs/pli/price-list.md#creating-and-updating-catalog-items) via **DYCE Price List Import**.
:::


### Dimensions
If a Service Commitment Package contains lines with both Partner=*Customer* and Partner=*Vendor*, the [dimensions](/docs/srb/setup/general.md#dimensions) of the later [Customer Contract Line](/docs/srb/working-with-contracts/customer-contracts.md) are passed to the corresponding [Vendor Contract Line](/docs/srb/working-with-contracts/vendor-contracts.md). The decisive factor here is that the service package code is identical. This is primarily for evaluation purposes.


### Price Group in Sales Service Commitments and Service Objects
Before the prices for the Service Commitments in the sales document can be calculated, the appropriate Service Commitment Package(s) must be determined - also on the basis of the price group, among other things. <br/>
The following applies:
* If the Service Commitment Package is not set in the document, only Service Commitment Packages *without* the price group are used.
* If the Service Commitment Package is set in the document, *only* Service Commitment Packages with the same price group will be applied. If *no* Service Commitment Packages matching the price group are found, Service Commitment Packages *without* price group will also be considered. Service Commitment Packages that are set as default (**Default**=*YES*) for the item will be applied directly. Others will only be displayed.
* If no Service Commitment Package *without* Price Group is found either, *all* Service Commitment Packages will be considered. Those that are set as the default package (**Default**=*YES*) for the item will be applied directly. Others are only displayed.
* If no Service Commitment Package is found at all, no Sales Service Commitments will be created.

The determination of Service Commitments when manually creating a Service Object is done in the same way as the creation and calculation of Sales Service Commitments. However, if the End User (Customer) in the Service Object is changed, the Service Commitments must be recalculated if the price group of the new End User (Customer) differs from the one in the Service Object. The user receives a corresponding query. If this is confirmed, the Service Commitments are deleted and recreated based on the above criteria. Otherwise, the End User (Customer) will be reset to the original value.

:::note Note
It is only possible to change the Service Commitments in the Service Object if none of the services are linked to a Customer Contract or Vendor Contracts.
:::


## Types of Service Commitments
* **Contract** <br />.
    A Service Commitment whose Default in the **Invoicing via** field is set to *Contract* will be brought to Invoicing via a defined cycle. Optionally, terms and notice periods can be stored for this.
* **Sales** <br />
    A Service Commitment, whose default in the field **Invoicing via** is set to *Sales*, will not be invoiced. The Service Object and Service Commitment does only serve as information (e.g. for the warranty period or the after-sale to a warranty).

:::info
Only Services Commitments whose template is set to *Contract* in **Invoicing via** can be assigned to an Customer or Vendor Contract and thus billed recurrently via that contract.
:::


## Pricing and calculation types
Three types of reference values (*Item Price*, *Document Price* and *Document Price And Discount*) are used to price Service Commitments via the **Calculation Base Type** field. The details are explained [here](/docs/srb/sales/price-calculation.md).


## Control of revenue accounts
Services that are (optionally) co-sold with an item (see [Sales with Services](/docs/srb/masterdata/items.md) in the **Service Commitment Option** field in the Item card) are usually handled by an *Invoicing Item*. Depending on the configuration of the posting groups in Financial Accounting, revenues can thus be posted to different revenue accounts for each Service Commitment to be billed. The lookup of the field **Invoicing via Item No.** is restricted to Invoicing Items.<br />
Services that are themselves the subject of provisioning (e.g., a support service) can also themselves contain the posting groups for revenue control (see [Service Commitment Item](/docs/srb/masterdata/items.md) in the **Service Commitment Option** field in the Item card). In this case, the **Invoicing via Item No.** field can also be left blank.