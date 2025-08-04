---
title: Usage data supplier references
description: You can use references in usage based billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: 
ms.search.form: 
ms.date: 08/14/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Usage data supplier references

To process and bill usage data, [!INCLUDE [prod_short](../../includes/prod_short.md)] must find all additional data required for this purpose. This includes the [subscriptions](customers-subscriptions.md) that link to a [service commitment](service-commitments.md#service-commitment-packages), which is part of a vendor or customer contract.

> [!NOTE]
> You can only charge service commitments that are part of a vendor or customer contract.

The usage data usually only knows the subscription to which it's related. The service commitments, however, know to which contract they're assigned. The link is the subscriptions that connect to a service commitment.

For each subscription or its ID, a reference is created on the **Usage Data Supplier References** page. The unique number of the reference is entered on the service commitments. This path is how the usage data finds the related subscription, service commitments, service objects, and their items. The items are required for pricing, depending on the [method for pricing](service-commitments.md#service-commitment-packages), and in turn are included in [Imports and processing](../processing-usage-data/imports-processing.md). You can then use vendor and customer contracts to bill for usage data.

## References for subscriptions

To ensure that subscriptions are unique, each subscription or its ID has an entry in **Usage Data Supplier References** field on the **Usage Data Supplier References** page. This reference always belongs to the supplier that is used to import the usage data for a subscription. If the usage data supplier is set up to [automatically create subscriptions](customers-subscriptions.md#usage-data-subscriptions), the record is also created automatically. Otherwise, you must manually create the reference.

## References for products

Similar to subscriptions, you can also link supplier products to the item master data through a usage data supplier reference. You create the link in the item if the subscription's item exists in the master data (items).

To maintain the product reference, enter a link to a supplier product reference on an **Item Card** page in one of the following ways:

* By using the **Vendors** action.
* By using the lookup in the **Usage Data Supplier Reference Exists** field on the **Replenishment** FastTab.
* By using the **Item References** action.

The reference displays on the **Usage Data Supplier References** page as type **Product**.

> [!NOTE]
> For each item, you can enter a separate product reference per [Usage data suppliers](suppliers.md). [!INCLUDE [prod_short](../../includes/prod_short.md)] uses the reference to suggest the appropriate item as part of the [Extend contract](../processing-usage-data/extend-contract.md) functionality. If the product references aren't stored in the item master data, you can also select the corresponding item manually.

## References for customers

A list of customers for which usage data is imported and processed can be created automatically. However, this is optional. Each customer or their ID has an entry on the **Usage Data Supplier References** page. When you have [usage data customers](customers-subscriptions.md#usage-data-customers), the record is also created automatically. Otherwise, you must create the reference manually.

To maintain the customer reference, you can open the reference table by using the **Supplier Reference Entry No.** field on the **Usage Data Customers** page. A reference for a customer appears in the **Usage Data Supplier References** page as the **Customer** type.

## Related information

[Usage based billing customers and subscriptions](customers-subscriptions.md)  
[Extend contract](../processing-usage-data/extend-contract.md)  
[Extension of service commitments](service-commitments.md)  
