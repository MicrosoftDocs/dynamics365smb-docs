---
title: Sales with subscription lines
description: You can use sales with subscription lines in subscription billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: 
ms.search.form: 
ms.date: 08/14/2024
ms.service: dynamics-365-business-central
---

# Sales with subscription lines

Create a sales quote or sales order with subscription lines to record your monetary agreements with the customer. Subscription lines are printed on the documents and can be delivered from the order to be billed on a recurring basis.

## Assign subscription lines

[Subscription lines in subscription billing](../masterdata/service-commitments.md) describe the monetary content of agreements with customers and vendors, as well as ending dates.

If an item is used in a sales document that has one or more subscription line packages defined in the master data, the services from the subscription lines marked as **Standard** are automatically created for the sales transaction. All subscription lines from the corresponding subscription line packages are transferred to the sales item in the document. The subscription lines can then be accessed and viewed or edited via the lookup in the **Services** field in the sales document line. To learn more, go to [View, Edit and Delete subscription lines](#view-edit-and-delete-subscription-lines).

All subscription lines not marked as **Standard** can be assigned in the **Assign Subscription Lines** dialog. The dialog opens automatically when an item is entered in the sales document if an optional subscription line package (not marked as **Standard**) is stored on the item. Because standard subscription line packages are always accepted, only optional subscription line packages display.
If you open the dialog by using the **Add Subscription Line** action on a line, all available subscription line packages for the item in the current sales item display.

By selecting the subscription line package and confirming with **OK**, the subscription lines of the subscription line package transfer to the selected sales item. You can't select individual lines of a subscription line package. To learn more about price calculation of the sales subscription lines, go to [Price determination of Subscription Lines](price-calculation.md#price-determination-of-subscription-lines).

Subscription lines can be used in sales quotes, sales orders, and blanket sales orders.

## Print subscription lines

Customer subscription lines are automatically printed below the respective sales item. For each subscription line, the description, the discount %, and the sales price are printed. The formatting from the corresponding sales item regarding **Print Line** is taken into account (as the only formatting) when printing subscription lines.

The amounts of subscription lines and subscription line items aren't used to calculate the line and total amounts. The total amounts of subscription lines are calculated depending on the billing rhythm and print below the sales items. For each billing rhythm used in the sales document, the recurring total amount is output (if it's greater than 0). The output of the total amounts is sorted by the duration of the billing rhythm. The total of the sales subscription line that was created for a contract renewal is printed separately and labeled with **Contract Renewal**. To learn more, go to [Contract renewal](../working-with-contracts/contract-renewal.md).

## View, edit and delete subscription lines

You can check whether subscription lines are entered for the sales item in the **Subscription Lines** field on a line in the sales document. You can select the field to view, edit, or delete the subscription lines.

## Shipping subscription lines

When you ship an item on an order, a subscription is automatically created if **Sales with Subscription Lines** or **Subscription Line Item** are selected in the **Subscription Line Option** field on the item. To learn more, go to [Subscription lines for items](../masterdata/items.md). The sales subscription lines for the sales item automatically transfer as subscription lines. A new subscription is created for each shipment. Delivered subscription line items automatically display as invoiced, because the subscription lines are invoiced only through contracts.

> [!NOTE]
> In sales orders, the behavior of subscription line items differs significantly from that of *normal* items in [!INCLUDE [prod_short](../../includes/prod_short.md)]. During an audit, the differences should be noted and explained to the auditor.

If subscription line items were shipped in a sales order, they automatically display as invoiced. By clicking on the **Invoiced Quantity** field, the lookup won't find a posted sales invoice. To avoid invoices with amount equals to 0 and to be able to delete the sales order, a sales invoice isn't created when you ship subscription lines items.

Subscription line items also display as invoiced in posted sales shipments, although there isn't a corresponding posted sales invoice and both the item and value ledger entry show the **Quantity invoiced** as **0**.

The item and value ledger entries for the subscription line items from sales orders are created with **Sale Amount** and **Cost Amount** equal to **0**. The item and value ledger entries for the subscription line items from sales orders are created without an **Invoiced Quantity**.

When invoiced by a contract, item and value ledger entries are created with the **Invoiced Quantity** and **Sales Amount**.

The item and its description, as well as the customer and the delivery address, transfer to the subscription. The quantity on the subscription corresponds to the quantity in the shipment. All values from the subscription lines in the order transfer to the subscription lines in the subscription. The **Shipment Date** corresponds to the **Provision Start Date** in the subscription.

A **Agreed Sub. Line Start Date** can be entered in the sales subscription line for a sales item. If a **Agreed Sub. Line Start Date** is maintained in the sales subscription line, it's used as the **Service Start Date** and **Next Billing Date** in the service. If the field is blank, the **Service Start Date** and **Next Billing Date** are determined from the **Shipment Date** and **Subscription Line Start Formula** (the field is on the subscription line package line).

Here's an example. If delivery is on the 15th of a month, and the **Subscription Line Start Formula** defines the first of the following month as the service start date, the first of the following month is used. If the **Subscription Line Start Formula** field is empty, the delivery date is used.

> [!TIP]
> **-CM+1M** calculates the first day of the following month. To learn more about formulas, go to [Work with Calendar Dates and Times](../../ui-enter-date-ranges.md).

The **Cancellation Period** fields calculate based on the **Service Start Date**. The **Cancellation possible until** field specifies the date on which a subscription line can be cancelled in due time. The caculation is as follows:

* **Service Start Date** + **Initial Term** - **Notice Period**.

The **Term until** field indicates the next potential end date of a subscription line upon regular termination. It's calculation is **Service Start Date** plus **Notice Period**. If you use an **Initial Term**, it corresponds to **Service Start Date** plus **Initial Term**.

> [!IMPORTANT]
> The subscription line isn't automatically ended when the **Term until** date is reached.

If there is an agreed end date for a subscription line, specify an **Initial Term** date and leave the **Subsequent Term** empty. This way, upon delivery, the **Service End Date** is automatically determined based on the **Service Start Date**.

To learn more about subscriptions and subscription lines, go to [Managing contracts, subscriptions, and subscription lines](../working-with-contracts/contracts-services-mgmt.md).

## Inventory picks

When an item is delivered using an inventory pick, either the posting date or the shipment date are used to calculate the service start date. The **Service Start Date for Inventory Pick** field on the Service & Contract Setup page determines which of the two options comes into play. To learn more, go to .

## Calculate orders

You can't charge subscription lines through a sales order. Although the item is billed once via the sales order, the subscription lines aren't billed via the sales order, but through a contract.

Subscription line items can't be billed at all. Subscription line items can be rentals, support, and so on, that are offered and sold. They're automatically set to invoiced on delivery. Invoicing is also done on a recurring basis through a contract.

## Archive documents

Depending on the setting in **Sales & Receivables Setup**, sales quotes are automatically archived when converted to a sales order or sales orders are automatically archived when deleted (fast tab *Archive*). Sales quotes and orders can also be archived manually using the **Archive Document** action. The sales subscription lines belonging to the lines are also archived.

## Related information

[Subscription lines](../masterdata/service-commitments.md)