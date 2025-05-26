---
title: Sales with service commitments
description: You can use sales with service commitments in subscription billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: 
ms.search.form: 
ms.date: 08/14/2024
ms.service: dynamics-365-business-central
---

# Sales with service commitments

Create a sales quote or sales order with service commitments to record your monetary agreements with the customer. Service commitments are printed on the documents and can be delivered from the order to be billed on a recurring basis.

## Assign service commitments

[Service commitments in subscription billing](../masterdata/service-commitments.md) describe the monetary content of agreements with customers and vendors, as well as ending dates.

If an item is used in a sales document that has one or more service commitment packages defined in the master data, the services from the service commitments marked as **Standard** are automatically created for the sales transaction. All service commitments from the corresponding service commitment packages are transferred to the sales item in the document. The service commitments can then be accessed and viewed or edited via the lookup in the **Services** field in the sales document line. To learn more, go to [View, Edit and Delete service commitments](#view-edit-and-delete-service-commitments).

All service commitments not marked as **Standard** can be assigned in the **Assign Service Commitments** dialog. The dialog opens automatically when an item is entered in the sales document if an optional service commitment package (not marked as **Standard**) is stored on the item. Because standard service commitment packages are always accepted, only optional service commitment packages display.
If you open the dialog by using the **Add Service Commitment** action on a line, all available service commitment packages for the item in the current sales item display.

By selecting the service commitment package and confirming with **OK**, the service commitments of the service commitment package transfer to the selected sales item. You can't select individual lines of a service commitment package. To learn more about price calculation of the sales service commitments, go to [Price determination of Service Commitments](price-calculation.md#price-determination-of-service-commitments).

Service commitments can be used in sales quotes, sales orders, and blanket sales orders.

## Print service commitments

Customer service commitments are automatically printed below the respective sales item. For each service commitment, the description, the discount %, and the sales price are printed. The formatting from the corresponding sales item regarding **Print Line** is taken into account (as the only formatting) when printing service commitments.

The amounts of service commitments and service commitment items aren't used to calculate the line and total amounts. The total amounts of service commitments are calculated depending on the billing rhythm and print below the sales items. For each billing rhythm used in the sales document, the recurring total amount is output (if it's greater than 0). The output of the total amounts is sorted by the duration of the billing rhythm. The total of the sales service commitment that was created for a contract renewal is printed separately and labeled with **Contract Renewal**. To learn more, go to [Contract renewal](../working-with-contracts/contract-renewal.md).

## View, edit and delete service commitments

You can check whether service commitments are entered for the sales item in the **Service Commitments** field on a line in the sales document. You can select the field to view, edit, or delete the service commitments.

## Shipping service commitments

When you ship an item on an order, a service object is automatically created if **Sales with Service Commitments** or **Service Commitment Item** are selected in the **Service Commitment Option** field on the item. To learn more, go to [Service commitments for items](../masterdata/items.md). The sales service commitments for the sales item automatically transfer as service commitments. A new service object is created for each shipment. Delivered service commitment items automatically display as invoiced, because the service commitments are invoiced only through contracts.

> [!NOTE]
> In sales orders, the behavior of service commitment items differs significantly from that of *normal* items in [!INCLUDE [prod_short](../../includes/prod_short.md)]. During an audit, the differences should be noted and explained to the auditor.

If service commitment items were shipped in a sales order, they automatically display as invoiced. By clicking on the **Invoiced Quantity** field, the lookup won't find a posted sales invoice. To avoid invoices with amount equals to 0 and to be able to delete the sales order, a sales invoice isn't created when you ship service commitments items.

Service commitment items also display as invoiced in posted sales shipments, although there isn't a corresponding posted sales invoice and both the item and value ledger entry show the **Quantity invoiced** as **0**.

The item and value ledger entries for the service commitment items from sales orders are created with **Sale Amount** and **Cost Amount** equal to **0**. The item and value ledger entries for the service commitment items from sales orders are created without an **Invoiced Quantity**.

When invoiced by a contract, item and value ledger entries are created with the **Invoiced Quantity** and **Sales Amount**.

The item and its description, as well as the customer and the delivery address, transfer to the service object. The quantity on the service object corresponds to the quantity in the shipment. All values from the service commitments in the order transfer to the service commitments in the service object. The **Shipment Date** corresponds to the **Provision Start Date** in the service object.

A **Agreed Serv. Comm. Start Date** can be entered in the sales service commitment for a sales item. If a **Agreed Serv. Comm. Start Date** is maintained in the sales service commitment, it's used as the **Service Start Date** and **Next Billing Date** in the service. If the field is blank, the **Service Start Date** and **Next Billing Date** are determined from the **Shipment Date** and **Service Commitment Start Formula** (the field is on the service commitment package line).

Here's an example. If delivery is on the 15th of a month, and the **Service Commitment Start Formula** defines the first of the following month as the service start date, the first of the following month is used. If the **Service Commitment Start Formula** field is empty, the delivery date is used.

> [!TIP]
> **-CM+1M** calculates the first day of the following month. To learn more about formulas, go to [Work with Calendar Dates and Times](../../ui-enter-date-ranges.md).

The **Cancellation Period** fields calculate based on the **Service Start Date**. The **Cancellation possible until** field specifies the date on which a service commitment can be cancelled in due time. The caculation is as follows:

* **Service Start Date** + **Initial Term** - **Notice Period**.

The **Term until** field indicates the next potential end date of a service commitment upon regular termination. It's calculation is **Service Start Date** plus **Notice Period**. If you use an **Initial Term**, it corresponds to **Service Start Date** plus **Initial Term**.

> [!IMPORTANT]
> The service commitment isn't automatically ended when the **Term until** date is reached.

If there is an agreed end date for a service commitment, specify an **Initial Term** date and leave the **Subsequent Term** empty. This way, upon delivery, the **Service End Date** is automatically determined based on the **Service Start Date**.

To learn more about service objects and service commitments, go to [Managing contracts, service objects, and services commitments](../working-with-contracts/contracts-services-mgmt.md).

## Inventory picks

When an item is delivered using an inventory pick, either the posting date or the shipment date are used to calculate the service start date. The **Service Start Date for Inventory Pick** field on the Service & Contract Setup page determines which of the two options comes into play. To learn more, go to .

## Calculate orders

You can't charge service commitments through a sales order. Although the item is billed once via the sales order, the service commitments aren't billed via the sales order, but through a contract.

Service commitment items can't be billed at all. Service commitment items can be rentals, support, and so on, that are offered and sold. They're automatically set to invoiced on delivery. Invoicing is also done on a recurring basis through a contract.

## Archive documents

Depending on the setting in **Sales & Receivables Setup**, sales quotes are automatically archived when converted to a sales order or sales orders are automatically archived when deleted (fast tab *Archive*). Sales quotes and orders can also be archived manually using the **Archive Document** action. The sales service commitments belonging to the lines are also archived.

## Related information

[Service commitments](../masterdata/service-commitments.md)  
