---
title: Bundles
description: You can use bundles in subscription and recurring billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: 
ms.search.form: 
ms.date: 08/14/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Bundles and formatting

Bundles can be used in **Sales Quotes**, **Sales Orders** (from here on called *sales documents*) and in **Customer Contracts**. This is an aggregation of individual components into a standalone product. In addition, formatting can be used to control what content and how that content is output on print documents. Bundles and formatting are part of the app **[DYCE Easy Bundle Seller](/docs/ht/welcome.md)**, which comes with **DYCE Subscription & Recurring Billing**. <br/>
Bundles can be predefined based on [master data](/docs/ebs/bundles.md#master-data-for-bundles) or created [individually (on-the-fly)](/docs/ebs/bundles.md#creating-a-custom-bundle).


## Using bundles in the Customer Contract
The functionality and handling of [bundles](/docs/ebs/bundles.md) and [Formatting](/docs/ebs/formatting.md) are explained in detail in the corresponding parts of the DYCE documentation. Therefore, this section only covers the specifics regarding Customer Contracts.


### Creating individual bundles
The procedure to create a bundle in a Customer Contract follows the same method as described [here](/docs/ebs/bundles.md) for sales documents. The exception is that in **Customer Contracts** the quantity of components cannot be changed. In addition, the page for editing a bundle can be accessed using the **Edit Bundle** function in the line menu (*Contract Line* in Customer Contracts).


### Prices and discounts in the bundle
Unlike sales documents, Customer Contracts do not allow you to edit the price, discount, and amount in the bundle.

:::caution Attention
In Customer Contract, contract lines with different **Next Billing Date** and **Billing Rhythm** can be combined into one bundle. Therefore, the price calculation in the bundle does not include these factors. Thus, the bundle is not suitable for combining contract lines with different **Next Billing Date** and **Billing Rhythm**.
:::


### Bundle and Service Commitments
Items with Service Commitments and Service Commitment Items can be assigned as components to a bundle. The price calculation in the bundle does not change. All components are included in the bundle price calculation regardless of the Service Commitment Option. The prices of Service Commitments are not included in the bundles price calculation.

:::caution Attention
If the bundle consists of mixed Service Commitment Items and other items, the Service Commitment Items are not automatically counted as billed upon shipment. When the bundle is invoiced, the Service Commitment Items are included in the invoice with price 0.
:::


### Dimensions in bundles
In sales documents, dimensions can be stored directly on the bundle. In **Customer Contracts**, no dimensions can be stored on the bundle.
The behavior of dimensions for bundles can be controlled for sales documents in the **[Sales & Receivables Setup](/docs/ebs/setup.md)** page in the **Dimensions** fast tab using the **Dimension Priority Bundle** field.

:::caution Attention
In the Customer Contract, dimensions can only be stored on the components and not the bundle itself.
:::


### Shipping a bundle
Based on the **Service Commitment Option** of the component, a bundle greatly affects how a sales order can be shipped.
* **Sales without Service Commitments** <br />
Item shipment behaves identically with and without a bundle.
* **Sales with Service Commitments** <br />
As components in a bundle, shipment is possible only in the correct quantity ratio. The quantity ratio refers to all components with Service Commitment Option *Sales with Service Commitment* and *Service Commitment Item*. These components must be shipped in a way that they make up whole bundles. <br />
For example, if a third-party license and a proprietary license are combined as a bundle, the two licenses must be delivered in a ratio that results in a whole bundle. If exactly one third party license is sold for each own license, one third party license must be shipped at the same time for each own license. In the order, **Qty. to ship** is predefined accordingly.
* **Service Commitment Item** <br />
A component with the Service Commitment Option *Service Commitment Item* behaves like the Service Commitment Option *Sales with Service Commitments*. It is important to note that **Qty. Invoiced** is not automatically set on delivery unless the bundle consists solely of Service Commitment Items.

The bundle is saved when the shipment is posted so that it can be transferred to the Customer Contract. When transferring a Service Commitment from the bundle to a Customer Contract, the bundle is automatically created and all components are transferred.

:::info
The quantity of components can not be changed, once a component has been shipped. The quantity of the bundle can still be adjusted after shipment. The **Bundle Qty. Shipped** and **Bundle Qty. Invoiced** are displayed in the bundle.
:::


### Invoicing bundles in Sales documents
In the sales order, the bundle is treated as an independent product during billing. It can only be billed when it has been shipped before. Components in a bundle cannot be billed independently. I.e. only as many bundles can be invoiced as whole bundles were shipped. If a bundle consists of two components and only one is delivered, it is not a complete bundle and therefore cannot be invoiced. If both components are delivered, the bundle can be invoiced. Accordingly, **Qty. to invoice** is set in the components so that bundles are always invoiced as a whole.

If a bundle consists of **Service Commitment Items** only, it does not need to be invoiced. On shipment, the components are automatically entered as invoiced.

:::info
If a component is to be explicitly invoiced individually, the bundle can be dissolved at any time. To dissolve the bundle, either the bundle line must be deleted or the indicator *Bundle* must be removed. <br/>
The bundle cannot be reassembled after release. New sales lines must be created for the quantities not yet delivered and a new bundle must be created. <br/>
If a bundle was released that had a Service Commitment Item as a component, that Service Commitment Item is not billed. If the order is billed, **Qty. invoiced** is set in the Service Commitment Item, but no invoice is created because the invoice amount would be 0.
:::


### Invoicing bundles in Customer Contracts
In Customer Contracts, the bundle is treated as a subtotal. Price, discount and amount from the bundle are calculated in the contract and transferred to the invoice during billing. In the invoice, the bundle is calculated again. <br/>
The bundle is created as a text line in the invoice. Below the components are created. The entry from the **Service Object Description** in the contract is copied to the description of the document line. Below the bundle line, the **Billing Period** of the bundle is output as a text line. The billing period of the bundle corresponds to the earliest to latest billing period of the components. The billing period of the individual components is not created as a text line.

:::caution Attention
If two contract lines are to be assigned to a bundle, the **Next Billing Date** and the **Billing Rhythm** must be the same. <br/>
The bundle amount refers to the complete **Billing Rhythm**. If a different period is selected during billing, the amount from the bundle will be recalculated in the invoice.
:::


## Formatting
Formatting can be used to control which contents and how these contents are output on print documents. This control allows, among other things, the printing of headings and hiding of components. For more information on formatting, please refer to [this](/docs/ebs/formatting.md) part of the DYCE documentation.