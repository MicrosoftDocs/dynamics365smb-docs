---
title: References
hide_title: true
sidebar_label: References
slug: /ubb/masterdata/references
---

# Usage data supplier references
In order for usage data to be processed and billed at all, the system must find all additional data required for this purpose. First of all, this includes the [Subscription](/docs/ubb/masterdata/customers-subscriptions.md), which in turn is linked to a [Service Commitment](/docs/ubb/masterdata/service-commitments.md#service-commitment-packages), which is part of a Vendor or Customer Contract.

:::info
Only Service Commitments that are part of a Vendor or Customer Contract can be charged.
:::

The usage data usually only *knows* the subscription to which it is related. The Service Commitments, on the other hand, *know* to which contract they are assigned. The link is the Subscriptions, whose connection to a Service Commitment must be known to the system. <br/>
In detail, this is implemented in such a way that for each Subscription or its ID, an entry is created in **Usage Data Supplier References**. The unique number of this entry is entered in the Service Commitments. Via this path, the usage data finds the related Subscription, the Service Commitments, the Service Objects and their items. The items are required for pricing, depending on the [method for pricing](/docs/ubb/masterdata/service-commitments.md#service-commitment-packages), and in turn go into the [Usage Data Billing](/docs/ubb/processing-usage-data/imports-processing.md). Vendor and Customer Contracts are then used to bill for usage data.


## References for subscriptions
To ensure the uniqueness of subscriptions, each subscription or its ID has an entry in **Usage Data Supplier References**. This reference always belongs to the supplier that is used to import the usage data for a subscription. In case of [automatic creation of a subscription](/docs/ubb/masterdata/customers-subscriptions.md#usage-data-subscriptions) the record is also created automatically. Otherwise, the reference must be created manually. <br/>
To maintain the subscription reference, the reference table can be called either via the field **Supplier Reference Entry No.** (may have to be shown if needed) in the [Usage Data Subscriptions](/docs/ubb/masterdata/customers-subscriptions.md#usage-data-subscriptions) or via the menu or search (*Alt+Q*). A reference for a subscription appears in the **Usage Data Supplier References** page as a type of *Subscription*.


## References for products
Similar to subscriptions, supplier products can also be linked to the Item master data in DYCE via a unique supplier reference. In the future, this can be done, for example, by importing a supplier price list. However, the link can also be made manually directly in the Item if the subscription's item already exist in the master data (Items). <br/>
In order to maintain the product reference, a link to a (also manually) entered supplier product reference is created in the relevant Item card via the **Item Vendor Catalog** (call via *Related / Purchases / Vendors* or via the lookup in the **Usage Data Supplier Reference Exists** field in the *Replenishment* fast tab) or via the **Item References** (call via *Related / Item*). This appears in the **Usage Data Supplier References** page as type *Product*.

:::info Extend Contract
For each item, a separate product reference can be entered per **[Usage Data Supplier](/docs/ubb/masterdata/suppliers.md)**. This is primarily used to allow the system to suggest the appropriate item as part of the **[Extend Contract](/docs/ubb/processing-usage-data/extend-contract.md)** functionality. If the product references are not stored in the item master data, the corresponding item can also be selected manually.
:::


## References for customers
To support clarity, a list of customers for which usage data is imported and processed can be created automatically. However, this is optional. Each customer or its ID then also has an entry in **Usage Data Supplier References**. When [automatically creating a customer](/docs/ubb/masterdata/customers-subscriptions.md#usage-data-customers), the record is also created automatically. Otherwise, the reference must be created manually. <br/>
To maintain the customer reference, the reference table can be called either via the field **Supplier Reference Entry No.** (may have to be shown if needed) in the [Usage Data Customers](/docs/ubb/masterdata/customers-subscriptions.md#usage-data-customers) or via the menu or search (*Alt+Q*). A reference for a customer appears in the **Usage Data Supplier References** page as type *Customer*.