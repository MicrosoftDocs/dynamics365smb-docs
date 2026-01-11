---
title: Welcome to subscription billing 
description: Get an overview of the features available for subscription billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: 
ms.search.form: 8067,
ms.date: 01/11/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Overview of subscription billing

Subscription billing lets you bill for contractually agreed services on a recurring basis. The integrated, flexible billing models support many subscription model scenarios for pricing models, price management, renewals, and billing periods and frequency. Using subscription billing to manage recurring invoicing of services minimizes sources of error and brings transparency into the processes from initial sales quote to the recurring invoice. All information is stored in one place, so you to always have an overview of contract management. At the same time, manual effort is reduced because you can simplify and automate processes.  

## Flexible and user-friendly subscription management

You assign the serviceable items you sell (subscriptions), whether it's the sale of an item with attached services, a rental agreement, or any other contractual agreement, to customers. While subscriptions are usually static, the associated service (subscription lines) that you invoice on a recurring basis can change while a contract is active.

## Features of subscription billing

* Create individual and automated billing periods
* Preview all existing monthly recurring billing and your upcoming invoices
* Simplify billing with billing templates
* Automatically calculate notice periods
* Use accrual-based posting of income and expenses to profit and loss accounts

## Main elements of subscription billing 

### Contracts​

When business partners sign a contract, both partners assume obligations. In subscription billing, these obligations are called *subscription lines*. Agreements with periodic billing are called *customer subscription contracts* on the customer side, and *vendor subscription contracts* on the supplier side.

Use contracts to group the subscription lines of multiple subscriptions so you can bill them together on a recurring basis. A contract in subscription billing is the technical equivalent of one or more actual contract documents that you bill to a customer.

A contract defines the commercial framework (contractual partners, invoice recipients, accounting conditions). Subscriptions, and their subscription lines, represent the components of the contract.

### Subscriptions

A subscription is something that the customer either buys, such as items, or for which a contractual agreement is results in mutual obligations. A subscription is assigned to a customer. A subscription is usually static, but the associated services (subscription lines) can change. Also, you can store additional information in a subscription that's independent of the subscription lines.

A subscription doesn't contain any billing-relevant information. That information belongs to the associated subscription lines. Subscription lines that aren't invoiced through a contract can also belong to a subscription, for example, warranties.

### Subscription lines​

Subscription lines describe the content of agreements with customers and suppliers. They exist in customer-side and vendor-side forms, and always belong to a subscription. Subscription lines contain billing information, such as the quantity to bill, the billing period, and the amount.

The subscription lines of a subscription and the creation of subscription lines are defined through a multi-level hierarchy. It includes subscription package line templates and subscription packages that you can assign to items. Subscriptions are created through the sale of these items, to which the associated subscription lines are assigned and available.

You can offer subscription lines to prospects or customers already during the sales phase. For this purpose, you can add more subscription lines to the offered items, which you can then offer simultaneously or sell at the same time.

If you sell an item in conjunction with a subscription line, a subscription is automatically created for it, where the associated subscription lines are available.

If the service is a subscription line (see Types of Services), you can add it to a contract as a component and, according to the information in the service, bill on a recurring basis.

## Flow of subscription billing​

The following illustration shows that items are set up with subscription packages with one or more subscription lines. When the quote or order is shipped, the item becomes a subscription. The subscription lines assigned to the subscription must be assigned to a contract to be billed on a recurring basis. The contract and its subscription lines contain the billing information. When posting contract invoices, contract deferrals are created. You can post the deferrals to the general ledger independently to recognize the revenue or cost of the invoices.

:::image type="content" source="../media/srbFlow.png" alt-text="Shows the flow in subscription billing.":::

## Subscription Billing Role Center​

The **Subscription Billing** Role Center collects the features for subscription billing in one place, so things are easy to find. In addition to the master and transaction data, the Role Center provides fast access to the history of posted receipts. Documents that aren't posted (open posting documents for customers or vendors), and services that aren't assigned to contracts (subscription lines without contracts) also display to alert you that something might still need to be done.

The revenues and costs figures show the current and previous month's revenues and costs that were posted in connection with contract billing.

The **Overdue** and **Not invoiced** cues indicate that subscription lines are either still to be billed (Overdue) or that a posting document hasn't been created yet (Not invoiced) for lines in a billing proposal. The cues are based on the workdate.

## Get started

To start using subscription billing features, there are a few things to set up first. For example, you must define settings for subscription contracts, job queue entries, and a few general settings. Learn more at [General setup](setup/general.md).  

## Related information

[Managing contracts, subscriptions, and subscription lines](working-with-contracts/contracts-services-mgmt.md)  
[Recurring billing](recurring-billing.md)  
