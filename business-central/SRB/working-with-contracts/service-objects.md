---
title: Service Objects
hide_title: true
sidebar_label: Service Objects
slug: /srb/working-with-contracts/service-objects
---

# Service Objects
Service Objects represent a history of products sold to a customer. They contain all information related to the delivered item, such as <br/>.
* master data (Item No., Description).
* Details of the sale (customer, delivery recipient, invoice recipient)
* Quantity, date of provision and date of next settlement
* All Service Commitments (sales and Service Commitments including prices, terms and cancellation periods).

A Service Object can be created automatically from a Sales order using the [Shipment](/docs/srb/sales/sales-service-commitments.md) (see **[Service Commitment Option](/docs/srb/masterdata/items.md)** field on the Item card for prerequisites). When a Service Object is created on shipment, the information regarding the End User and the Invoice Recipient is taken from the order and the delivery. This also includes the **Your Reference** field, which is transferred to the **Customer Reference** field. <br/>
Alternatively, a Service Object can also be entered manually by creating a new record (action **New** in the **Service Objects** page) and filling in the fields on each fast tabs. This may be necessary, for example, in the case of a manual transfer of equipment or licenses.
The Service Object with the associated Contract Commitments forms the basis for the Customer and Vendor Contracts and their periodic [Recurring Billing](/docs/srb/recurring-billing.md).

:::info Service Objects in master data
Service Objects are visible in the fact box area at the Customer, Vendor and Contact. A click on the respective cue opens the corresponding overview.
:::

The following information is required to manually create a Service Object:
1. **No.** can be filled via a number series.
2. **Item No.** is used to define the device/software/license/user/... that will be billed recurrently. Only items with the **Service Commitment Option** *Sales with Service Commitments* or *Service Commitment Item* can be selected. 
3. The **Description** is automatically taken from the item and can be edited.
4. In the **Quantity** any positive, integer value can be entered. It specifies the number of devices/licenses whose Service Commitments are to be billed recurrently.
5. The **End User** fast tab contains information (contact and customer information) about which customer has purchased the item and the Service Commitments. When creating a Service Object manually, the customer must be entered here.
6. The **Shipping and Billing** fast tab contains information about the (original) shipment of the product and whether a different invoice recipient paid for the item. The contact details of the delivery recipient from the sales order are automatically used. The Ship-to party can be changed if required (even subsequently), in the same way as for sales documents. The other delivery recipient fields are automatically updated after modification.

As additional information, the **Customer Reference**, the **Version**, the **Provision Start Date** and the **Provision End Date** can be maintained, whereby the **Provision Start Date** is automatically entered when the Service Object is created via the delivery from a Sales Order.

:::note Customer Reference in the Contract invoice
If a Customer Reference is stored on a Service Object, this information will automatically appear below the corresponding invoice line.
:::


## Service Object with Serial Number
When serial number tracked items are delivered with Service Commitments, one Service Object is automatically created for each serial number. The serial number is determined from the item tracking lines for the Sales Order line and transferred to the Service Object in the **Serial No.** field. The field on the Service Object is editable. The quantity in a serial number tracked Service Object must always be 1 and cannot be changed. In order to store a serial number for a Service Object, an item tracking must be set for the item. Changes can be tracked using the **[Archived Service Commitments](/docs/srb/working-with-contracts/so-service-commitments.md#log-changes-to-services-commitments)**.

:::note Serial number in Contract invoices
If a serial number is stored on a Service Object, this information will appear depending on the [Invoice Details](/docs/srb/setup/general.md#invoice-details) set in the setup.
:::


## Service Object Attributes
With the help of attributes, items can be described in detail using any number of criteria. The same is possible for Service Objects. Two fact boxes are available for this purpose - both in the card and in the overview. The fact box **Item Attributes** shows the attributes that are stored for the item of the Service Object. In addition, the characteristics specific to a concrete Service Object can be stored and displayed via the **Service Object Attributes** fact box. To maintain the specific characteristics of a Service Object, open the **Service Object Attribute Values** page either via the dropdown menu of the fact box or via the **Attributes** action. In addition, it is possible to define a feature as **Primary** here. <br/>
The primary attribute is displayed in the Service Object card in the *General* fast tab (*Show more*). Here, the description of the primary attribute is used dynamically as the field name. It is possible to output the primary attribute of a Service Object when billing the related Service Commitments in the Contract invoice. The configuration required for this can be done [here](/docs/srb/setup/general.md#invoice-details). <br/>
For the description of the attributes, translations can be stored analogous to the standard of Business Central. For more information on attributes, please refer to <a href="https://learn.microsoft.com/en-us/dynamics365/business-central/inventory-how-work-item-attributes" title="Work with item attributes">this part</a> of the Microsoft documentation.


## Entering Service Commitments in a Service Object
An item is required to create Service Commitments, since Service Commitments themselves cannot be created manually. An item must therefore be entered in the Service Object in order to create Service Commitments. The **Assign Service Commitments** function can be used to view the **Service Commitment Packages** with the item's Service Commitments. The function opens the selection window of the same name. Here, **Service and Calculation Start Date** can be entered and Service Commitment Packages can be selected. Only Service Commitment Packages that have not yet been created as Service Commitments for the Service Object appear in the selection. For all selected Service Packages, the related Service Commitments are created in the Service Object and displayed in the **Services** fast tab. The prices from the item card are used as a basis for the price calculation. If an End User is subsequently entered, the prices in the Service Commitments are updated with the customer-specific prices on demand, if necessary. If the End User is assigned before the Service Commitments are created, the customer-specific prices are used directly.

:::info
A Service Object can only be deleted if all related Service Commitments are deleted. The Service Commitments are therefore - if possible - also deleted when the Service Object is deleted.
:::


## Quantity change
For Service Objects whose items are not configured for item tracking (lot or serial number obligation), the quantity can be changed directly in the Service Object. This will result in a recalculation of the Service Amounts in the associated Service Commitments and contract lines.
It is not possible to change the quantity for Service Objects whose items are configured for item tracking (lot or serial number obligation). Service Objects with lot number tracking retain the quantity from the delivery (or that of the initial entry). Service Objects with serial number tracking can only be created with quantity=*1*. 