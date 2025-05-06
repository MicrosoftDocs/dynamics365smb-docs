---
title: Service objects
description: You can use service objects in subscription and recurring billing.
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

# Service objects

Service objects represent a history of products sold to a customer. They contain all information related to the delivered item:

* Master data (item number and description).
* Details of the sale (customer, delivery recipient, invoice recipient)
* Quantity, date of provision, and date of next settlement
* All service commitments (sales and service commitments including prices, terms, and cancellation periods).

A service object can be created automatically from a sales order using the shipment. To learn more, go to [Sales process](../sales/sales-service-commitments.md) and [Service Commitments at Items](../masterdata/items.md). When you create a service object on a shipment, the information regarding the end user and the invoice recipient is taken from the order and the delivery. This also includes the **Your Reference** field, which is transferred to the **Customer Reference** field.

Alternatively, you can also enter a service object manually by creating a new record on the **Service Objects** page and filling in the fields on each FastTab. This may be necessary, for example, in the case of a manual transfer of equipment or licenses.

The service object with the associated contract commitments forms the basis for the customer and vendor contracts and their periodic recurring billing. To learn more, go to [Recurring billing](../recurring-billing.md).

> [!NOTE]
> Service objects display on the information pane on the customer, vendor, and contact. A click on the respective cue opens the corresponding overview.

To manually create a service object, the following information is required:

* **No.** can be filled in by a number series.
* **Item No.** defines the device, software, license, user, and so on, that will be billed recurrently. You can only select items with the **Service Commitment Option** set to **Sales with Service Commitments** or **Service Commitment Item**. 
* The **Description** comes from the item, but you can edit it.
* In the **Quantity** field, enter a positive integer to specify the number of devices/licenses whose service commitments you bill recurrently.
* The **End User** FastTab contains information (contact and customer information) about which customers purchased the item and the service commitments. When you create a service object manually, you must specify the customer.
* The **Shipping and Billing** FastTab contains information about the (original) shipment of the product, and whether a different invoice recipient paid for the item. The contact details of the delivery recipient from the sales order are used. You can change the ship-to party if needed in the same way as for sales documents. The other delivery recipient fields update automatically.

As additional information, you can maintain the **Customer Reference**, **Version**, **Provision Start Date**, and the **Provision End Date**, whereby the **Provision Start Date** is automatically entered when the service object is created via the delivery from a sales order.

> [!NOTE]
> If a service object has a customer reference, the reference appears below the corresponding invoice line.

## Service object with serial number

When serial number tracked items are delivered with service commitments, one service object is created for each serial number. The serial number is determined from the item tracking lines for the sales order line and transferred to the service object in the **Serial No.** field. The field on the service object is editable. The quantity in a serial number tracked service object must always be one, and you can't change it. To store a serial number for a service object, an item tracking must be set for the item. Changes can be tracked using archived service commitments. To learn more, go to [Log changes to service commitments](so-service-commitments.md#log-changes-to-service-commitments).

> [!NOTE]
> If service object stores a serial number, this information will appear depending on settings for invoice details. To learn more, go to [Invoice details](../setup/general.md#invoice-details).

## Service object attributes

Attributes let you describe items in detail using any number of criteria. The same is possible for service objects. Two FactBoxes are available for this purpose, both on the card and in the overview.

* The **Item Attributes** FactBox shows the attributes that are stored for the item of the service object.
* The **Service Object Attributes** FactBox shows the characteristics that are specific to a service object. To maintain the specific characteristics of a service object, open the **Service Object Attribute Values** page either via the dropdown menu of the FactBox or by using the **Attributes** action.

You can also define a feature as **Primary**. The primary attribute displays on the **Service Object Card** page on the **General** FastTab. You might need to choose **Show more**. Here, the description of the primary attribute is used as the field name. You can output the primary attribute of a service object when you bill the related service commitments in the contract invoice. To learn about the configuration this requires, go to [Invoice details](../setup/general.md#invoice-details).

For the description of the attributes, you can store translations in a similar way as the standard translations in [!INCLUDE [prod_short](../../includes/prod_short.md)]. To learn more about attributes, go to [Work with item attributes](../../inventory-how-work-item-attributes.md).

## Enter service commitments in a service object

Because you can't manually create service commitments themselves cannot be created manually, an item is required to create service commitments. You must specify an item for the service object. Use the **Assign Service Commitments** action to view the **Service Commitment Packages** with the item's service commitments. The action opens the selection page of the same name, where you can enter a **Service and Calculation Start Date** and select service commitment packages. Only service commitment packages that aren't created as service commitments for the service object are available.

For all selected service packages, the related service commitments are created in the service object and display on the **Services** FastTab. The prices from the item card are used as a basis for the price calculation. If an end user is entered, the prices in the service commitments are updated with the customer-specific prices on demand, if necessary. If the end user is assigned before the service commitments are created, the customer-specific prices are used directly.

> [!NOTE]
> You can delete a service object only if all related service commitments are deleted. If it's possible, the service commitments are also deleted when you delete the service object.

## Quantity change

For service objects whose items aren't configured for item tracking (lot or serial number mandatory), you can change the quantity directly on the service object. The result is a recalculation of the service amounts in the associated service commitments and contract lines.

You can't change the quantity for service objects whose items are configured for item tracking (lot or serial number mandatory). Service objects with lot number tracking retain the quantity from the delivery or the initial entry. You can only create service objects with serial number tracking with a quantity of **1**.

## Related information

[Managing contracts, service objects, and services commitments](contracts-services-mgmt.md)  
