---
title: Sales with service commitments
description: You can use sales with service commitments in subscription and recurring billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: 
ms.search.form: 
ms.date: 08/14/2024
ms.service: dynamics-365-business-central
---

# Sales process

Create a Sales Quote or Sales Order (hereafter *Sales Document*) with Service Commitments to record your monetary agreements with the customer. Service Commitments are printed on the documents and can be delivered from the order to be billed on a recurring basis.


## Assign Service Commitments
[Service Commitments](/docs/srb/masterdata/service-commitments.md) describe the monetary content of agreements with customers and vendors, as well as termination dates.

If an item is used in a sales document that has one or more Service Commitments Packages defined in the master data, the services from the Service Commitments marked as **Standard**=*Yes* are automatically created for the sales transaction. All Service Commitments from the corresponding Service Commitment Packages are transferred to the sales item in the document. The Service Commitments can then be accessed and viewed or edited via the lookup in the **Services** field in the sales document line ([see below](#view-edit-and-delete-service-commitments)).

All Service Commitments not marked as **Standard**=*Yes* can be assigned in the **Assign Service Commitments** selection window. The window opens automatically when an item is entered in the sales document if an optional Service Commitment Package (**Standard**=*No*) is stored on the item. Since Standard Service Commitment Packages are always accepted, only optional Service Commitment Packages are displayed.
If the selection window is opened using the **Add Service Commitment** line function, all available Service Commitment Packages for the item in the current sales item are displayed.

By selecting the Service Commitment Package and confirming with *OK*, the Service Commitments of the Service Commitment Package are transferred to the selected sales item. It is not possible to select individual parts of a Service Commitment Package (Service Commitment Package Lines). The price calculation of the Sales Service Commitments is described [here](/docs/srb/sales/price-calculation.md).

:::info Service Commitments in Sales Documents
Service Commitments can be used in Sales Quotes, Sales Orders and Blanket Sales Orders.
:::


## Print Service Commitments
Customer Service Commitments are automatically printed below the respective sales item. For each Service Commitments the description, the discount % and the sales price will be printed. The formatting from the corresponding sales item regarding **Print Line** is taken into account (as the only formatting) when printing Service Commitments.

The amounts of Service Commitments and Service Commitment Items are not taken into account when calculating the line and total amounts. The total amounts of Service Commitments are calculated depending on the billing rhythm and are printed cumulatively below the sales items. For each billing rhythm used in the sales document, the recurring total amount is output (if it is greater than 0). The output of the total amounts is sorted by the duration of the billing rhythm. The total of the Sales Service Commitment, which have been created for a **Contract Renewal** is printed separately and labeled [Contract Renewal](/docs/srb/working-with-contracts/contract-renewal.md).


## View, Edit and Delete Service Commitments
Whether Service Commitments have been entered for the sales item can be seen in the **Service Commitments** field in the respective sales document line. By clicking on the field, the Service Commitments can be viewed, edited and deleted.


## Shipping Service Commitments
When an order item is shipped, a **Service Object** is automatically created if the delivered item is marked as **Service Commitment Option**=*Sales with Service Commitments* or **Service Commitment Option**=*Service Commitment Item* ([Item Master data](/docs/srb/masterdata/items.md)). The Sales Service Commitments belonging to the sales item are automatically transferred as Service Commitments. A new **Service Object** is created for each shipment. Delivered *Service Commitment Items* are automatically displayed as invoiced, because respective Service Commitments are invoiced exclusively via contracts.
:::caution Important for auditors
In Sales Orders, the behavior of Service Commitment Items differs significantly from that of *normal* items from the Business Central Standard. During an audit, the differences should be noted and explained to the auditor.

If Service Commitment Items have been shipped in a Sales Order, they are automatically displayed as being invoiced. By clicking on the **Invoiced Quantity**, the lookup will not find a Posted Sales Invoice. No Sales Invoice is created when Service Commitments Items are shipped in order to avoid invoices with amount equals to 0 and to be able to deleted the Sales Order. 

Service Commitment Items are also displayed as invoiced in Posted Sales Shipments, although there is no corresponding Posted Sales Invoice and both the Item and Value Ledger entry show the **Quantity invoiced** to be 0.

The Item and Value Ledger entries for the Service Commitment Items from Sales Orders are created with **Sale Amount** and **Cost Amount** equal to 0. The Item and Value Ledger entries for the Service Commitment Items from Sales Orders are created without an **Invoiced Quantity**.

When invoiced by contract, the Item and Value Ledger entries are created with the **Invoiced Quantity** and **Sales Amount**.
:::

The item and its description, as well as the customer and the delivery address are transferred to the **Service Object**. The quantity in the **Service Object** corresponds to the quantity in the shipment. All values from the Service Commitments in the order are transferred to the Service Commitments in the **Service Object**.
The **Shipment Date** corresponds to the **Provision Start Date** in the **Service Object**.

A **Agreed Serv. Comm. Start Date** can be entered in the Sales Service Commitment for a sales item. If a **Agreed Serv. Comm. Start Date** is maintained in the Sales Service Commitment, it will be used as the **Service Start Date** and **Next Billing Date** in the Service.
If the field is blank, the **Service Start Date** and **Next Billing Date** will be determined from the Shipment Date and **Service Commitment Start Formula** (field only shown in the Service Commitment Package Line).
Example: If delivery is on the 15th of a month and the **Service Commitment Start Formula** defines the first of the following month as the Service Start Date, the first of the following month is used. If the **Service Commitment Start Formula** is empty, the delivery date is used.

:::tip Tip
-CM+1M calculates the first day of the following month (see <a href="https://learn.microsoft.com/en-us/dynamics365/business-central/ui-enter-date-ranges" title="Date and Time Specifications">Date and Time Specifications</a> documentation from Microsoft).
:::

Based on the **Service Start Date**, the **Cancellation Period** fields are calculated. The **Cancellation possible until** specifies the date on which a Service Commitments can be cancelled in due time. It corresponds to the **Service Start Date** plus the **Initial Term** minus the **Notice Period**. The **Term until** indicates the next potential end date of a Service Commitments upon regular termination. It is equal to the **Service Start Date** plus the **Notice Period**. If an **Initial Term** is maintained, it corresponds to the **Service Start Date** plus the **Initial Term**.

:::caution Attention
The Service Commitment is not automatically terminated when the **Term until** is reached.

If there is an agreed end of Service Commitment, the **Initial Term** must be maintained and the **Subsequent Term** must be empty. This way, upon delivery, the **Service End Date** is automatically determined based on the **Service Start Date**.
:::

For more information on **Service Object** and Service Commitments, see [Managing Contracts and Services](/docs/srb/working-with-contracts/contracts-services-mgmt.md).


## Bundle with Services Commitments
Multiple quote and order lines can be combined into a [Bundle](/docs/ebs/bundles.md). A bundle is like a single product that consists of several components. For example, a bundle can be used to combine a transfer fee and the ancillary costs (maintenance) into one bundle product.


## Inventory Picks
When an item is delivered via Inventory Pick, either the Posting Date or the Shipment Date is used to calculate the Service Start Date. The **Service Start Date for Inventory Pick** field in the **[Service & Contract Setup](/docs/srb/setup/general.md#inventory-picks)** page determines which of the two options comes into play.


## Calculate orders
Service Commitments cannot be charged (not even once) via a sales order. Although the item is billed once via the sales order, the Service Commitments are not billed via the sales order, but recurringly via a contract.

Service Commitment Items cannot be billed at all. Service Commitment Items can be rentals, support, etc. that are offered and sold. They are automatically set to invoiced on delivery. Invoicing is also done recurrently via a contract.


## Archive documents
Depending on the setting in **Sales & Receivables Setup**, sales quotes are automatically archived when converted to a sales order or sales orders are automatically archived when deleted (fast tab *Archive*). Sales quotes and orders can also be archived manually using the **Archive Document** action. In doing so, the Sales Service Commitments belonging to the lines are also archived.