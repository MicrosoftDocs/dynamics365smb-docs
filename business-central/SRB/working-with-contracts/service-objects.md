---
title: Subscriptions
description: You can use subscriptions in subscription billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: 
ms.search.form: 8059, 8060_Primary, 
ms.date: 07/11/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Subscriptions

Subscriptions represent a history of products sold to a customer. They contain all information related to the delivered item:

* Master data, such as the item number and description.
* Details of the sale, such as the customer, delivery recipient, and invoice recipient.
* Quantity, date of provision, and date of next settlement
* All subscription lines, including sales and subscription lines with prices, terms, and cancellation periods.

A subscription can be created automatically from a sales order posting the shipment. To learn more, go to [Sales process](../sales/sales-service-commitments.md) and [Subscription lines for items](../masterdata/items.md). When you create a subscription on a shipment, the information regarding the end user and the invoice recipient is taken from the order and the delivery. This also includes the **Your Reference** field, which is transferred to the **Customer Reference** field.

Alternatively, you can also enter a subscription manually by creating a new record on the **Subscriptions** page and filling in the fields on each FastTab. This may be necessary, for example, in the case of a manual transfer of equipment or licenses.

The subscription with the associated lines forms the basis for the customer and vendor subscription contracts and their periodic recurring billing. To learn more, go to [Recurring billing](../recurring-billing.md).

> [!NOTE]
> Subscription attributes display on the information pane on the customer, vendor, and contact. A click on the respective cue opens the corresponding overview.

## Manually create a subscription

To manually create a subscription, follow these steps:

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Subscriptions**, and then choose the related link.
1. **No.** can be filled in by a number series.
1. In **Type** and **Source No.** fields, choose the item or the G/L account for the subscription. For example, the device, software, license, user, and so on, that you will bill recurrently. You can only select items with the **Subscription Option** set to **Sales with Subscription** or **Subscription Item**.
1. The content in the **Description** field comes from the item, but you can edit it.
1. In the **Quantity** field, specify the number of devices or licenses whose subscription lines you bill recurrently.
1. On the **End User** FastTab, enter information about the customer that purchased the item and the subscription lines.
1. The **Shipping and Billing** FastTab, enter information about the original shipment of the product, and whether a different invoice recipient paid for the item. Use the contact details of the delivery recipient from the sales order. You can change the ship-to party if needed in the same way as for sales documents. The other delivery recipient fields update automatically.

As additional information, on the **General** FastTab, you can fill in the **Customer Reference**, **Version**, **Provision Start Date**, and **Provision End Date** fields. The **Provision Start Date** is automatically entered when the subscription is created by receiving a sales order. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)]

> [!NOTE]
> If a subscription has a customer reference, the reference appears below the corresponding invoice line.

## Subscriptions with serial numbers

When serial number tracked items are delivered with subscription lines, one subscription is created for each serial number. The serial number is determined from the item tracking lines for the sales order line and transferred to the subscription in the **Serial No.** field. The field on the subscription is editable. The quantity in a serial number tracked subscription must always be one, and you can't change it. To store a serial number for a subscription, an item tracking must be set for the item. Changes can be tracked using archived subscription lines. To learn more, go to [Log changes to subscription lines](so-service-commitments.md#log-changes-to-subscription-lines).

> [!NOTE]
> If a subscription stores a serial number, this information will appear depending on settings for invoice details. To learn more, go to [Invoice details](../setup/general.md#invoice-details).

## Subscription attributes

On the **Subscription** page, the **Attributes** action lets you describe items in more detail. Two FactBoxes are available for this purpose, both on the card and in the overview.

* The **Item Attributes** FactBox shows the attributes that are specified for the item that's included in the subscription.
* The **Subscription Attributes** FactBox shows the characteristics that are specific to the subscription. To maintain the specific characteristics of a subscription, open the **Subscription Attribute Values** page either via the dropdown menu of the FactBox or by using the **Attributes** action.

You can also define an attribute as **Primary**. The primary attribute displays on the **Subscription** page on the **General** FastTab. You might need to choose **Show more**. Here, the description of the primary attribute is used as the field name. You can output the primary attribute of a subscription when you bill the related subscription lines in the contract invoice. To learn about the configuration this requires, go to [Invoice details](../setup/general.md#invoice-details).

For the description of the attributes, you can store translations in a similar way as the standard translations in [!INCLUDE [prod_short](../../includes/prod_short.md)]. To learn more about attributes, go to [Work with item attributes](../../inventory-how-work-item-attributes.md).

## Enter subscription lines in a subscription

If you create a subscription manually, you must specify an item. Use the **Assign Subscription Lines** action to view the subscription packages with the item's subscription lines. The action opens the selection page of the same name, where you can enter a **Service and Calculation Start Date** and select subscription packages. Only subscription packages that aren't created as subscription lines for the subscription are available.

For all selected service packages, the related subscription lines are created in the subscription and display on the **Subscription Lines** FastTab. The prices from the item card are used as a basis for the price calculation. If an end user is entered, the prices in the subscription lines are updated with the customer-specific prices on demand, if necessary. If the end user is assigned before the subscription lines are created, the customer-specific prices are used directly.

If you create a subscription manually based on a G/L account, you need to enter all details in the subscription lines manually since there's no way to apply subscription packages in this way.

> [!NOTE]
> You can delete a subscription only if all related subscription lines are deleted. If it's possible, the subscription lines are also deleted when you delete the subscription.

## Quantity change

For subscriptions whose items aren't configured for item tracking (lot or serial number mandatory), you can change the quantity directly on the subscription. The result is a recalculation of the amounts in the associated subscription lines and contract lines.

You can't change the quantity for subscriptions whose items are configured for item tracking (lot or serial number mandatory). Subscriptions with lot number tracking retain the quantity from the delivery or the initial entry. You can only create subscriptions with serial number tracking with a quantity of **1**.

## Related information

[Managing contracts, subscriptions, and subscription lines](contracts-services-mgmt.md)  
