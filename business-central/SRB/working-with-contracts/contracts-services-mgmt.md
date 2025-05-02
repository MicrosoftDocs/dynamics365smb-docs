---
title: Contracts and services management
description: You can manage contracts and services in subscription and recurring billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: 
ms.search.form: 
ms.date: 08/14/2024
ms.service: dynamics-365-business-central
---

# Managing contracts, subscriptions, and subscription lines

Contracts, subscriptions and services are required for recurring billing.

[Subscription lines in subscription billing](../masterdata/service-commitments.md) describe the monetary content of agreements with customers and suppliers, as well as termination dates. They can only be created in a [subscription](service-objects.md). The subscription defines the essential information about the end user and the actual content, which is to be billed on a recurring basis.

## Contracts

Contracts are used to organize subscription lines for billing to customers and suppliers. If something is to be invoiced via a separate invoice, this can be set up via a separate contract. Subscription lines have as **Partners** either *Customer* or *Vendor*. Subscription lines set up as *Customer* go into customer subscription contracts. Subscription lines set up as *Vendor* go into vendor subscription contracts.

## Overview of the fields in the subscription lines and contract lines

* The **Service Start Date** describes the date from which the subscription line is valid and can be invoiced.
* The **Service End Date** is the date the subscription line ends and can no longer be billed. The date can be entered manually when a subscription line is terminated.
* **Planned Subscription Lines Exist** shows that a [Contract renewal](contract-renewal.md) has happened for this subscription line, but the renewal is not yet valid because the subscription line has not yet been fully invoiced.
* The **Next Billing Date** indicates the due date of the next billing. The date is automatically recalculated during the billing run. The date is *grayed out* if invoiced to Service End Date.
* The **Calculation Base Amount** is the basis of valuation of the subscription line. When selling an item with additional recurring subscription lines, the Calculation Base Amount is the value of the item.
* The **Billing Rhythm** specifies the Dateformula for rhythm in which the service is invoiced. Using a Dateformula rhythm can be, for example, a monthly, a quarterly or a yearly invoicing.
* The **Calculation Base %** is the percentage from the **Calculation Base Amount** which is used to price the subscription line.
* The **Price** is calculated from the **Calculation Base Amount** and the **Calculation Base %**. It is always valid for the entire **Calculation Base Amount**. I.e. it is an annual price if a year is entered in Calculation Base Period and a monthly price if a month is entered in Calculation Base Period.
* The **Discount %** indicates the percentage discount for the subscription line.
* The **Discount Amount** indicates the discount applied to the subscription line.
* The **Service Amount** is the result of the price, discount, and quantity of the Subscription.
* The **Calculation Base Period** indicates the period to which the Service Amount applies. For example, enter 1M if the amount refers to one month or 12M if the amount refers to one year.
**Invoicing via** specifies whether the service is charged recurrently or only stores information about the sale (e.g. for warranty extensions). Subscription lines with the *Contract* option can be called into contracts and billed recurring.
*The **Partner** specifies whether the subscription lines are in Accounts Receivable or Accounts Payable. Accordingly, subscription lines can be called into customer or vendor subscription contracts and invoiced via A/P or sales invoices.
* The **Contract** indicates the contract through which the subscription lines will be billed.
* The **Initial Term** indicates the minimum term of the subscription lines. If the field is filled in and no **Subsequent Term** is entered, the **Service End Date** is automatically set to the end of the initial term.
*The **Subsequent Term** specifies the duration of the automatic extension after the initial term. In addition, it determines the rhythm of updating **Cancellation Possible Until** and **Term Until**. If the field is blank and either the initial term or the notice period are set at the same time, the **Service End Date** is automatically set to the expiration date of the initial term or the notice period.
* **Cancellation Possible Until** indicates the last date for timely cancellation. The date is determined by the **Initial Term**, the **Subsequent Term**, and the **Cancellation Period**. A 12 month Initial Term with a 3 month notice period means that the due date for termination is 9 months. A Subsequent Term of 12 months postpones the deadline by 12 months when the **Cancellation Possible Until** date is reached.

## Invoice discounts

It is possible - permanently or for a limited period - to grant a flat discount (invoice discount) for the entire contract. This can be used, for example, if the customer changes the license model or if a permanent discount on the subscription line is subsequently agreed.

The discount can only be defined in the [Service commitment templates​](../masterdata/service-commitments.md#service-commitment-templates) and the [Service commitment packages​](../masterdata/service-commitments.md#service-commitment-packages). Amounts for service commitment packages that allow discounts act as discounts in billing. The process of creating a subscription and billing is identical to the established processes. When creating the billing prosal via [Recurring billing](../recurring-billing.md), billing lines created for contract lines with discounts are created with a negative quantity and therefore a negative Service Amount. This discount amount is subsequently taken into account when posting documents are created.

> [!NOTE]
> A service commitment package in which an invoice discount is defined can only be assigned to items with **Service Commitment Option** chosen in the **Service Commitment Item** field.

Invoice discounts are applicable to both customer and vendor subscription contracts. They're also taken into regards in credit Memos and in contract deferrals.

## Related information

[Customer subscription contracts](customer-contracts.md)  
[Vendor subscription contracts](vendor-contracts.md)