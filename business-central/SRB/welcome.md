---
title: Welcome to subscription and recurring billing 
description: Get an overview of the features available for subscription and recurring billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: 
ms.search.form: 
ms.date: 08/14/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Overview of subscription billing

Subscription billing lets you bill for contractually agreed services on a recurring basis. The integrated, flexible billing models support many subscription model scenarios for pricing models, price management, renewals, and billing periods and frequency. Using subscription billing to manage recurring invoicing of services minimizes sources of error and brings transparency into the processes from initial sales quote to the recurring invoice. All information is stored in one place, so you to always have an overview of contract management. At the same time, manual effort is reduced because you can simplify and automate processes.  

## Flexible and user-friendly subscription management

You assign the serviceable items you sell (service objects), whether it's the sale of an item with attached services, a rental agreement, or any other contractual agreement, to customers. While service objects are usually static, the associated service (service commitments) that you invoice on a recurring basis can change while a contract is active.

## Features of subscription and recurring billing

* Create individual and automated billing periods
* Preview all existing monthly recurring billing and your upcoming invoices
* Simplify billing with billing templates
* Automatically calculate notice periods
* Use accrual-based posting of income and expenses to profit and loss accounts

## Main elements of subscription billing 

### Contracts​

When business partners sign a contract, both partners assume obligations. In subscription billing, these obligations are called *service commitments*. Agreements with periodic billing are called *customer contracts* on the customer side, and *vendor contracts* on the supplier side.

Use contracts to group the service commitments of multiple service objects so you can bill them together on a recurring basis. A contract in subscription billing is the technical equivalent of one or more actual contract documents that you bill to a customer.

A contract defines the commercial framework (contractual partners, invoice recipients, accounting conditions). Service objects, and their service commitments, represent the components of the contract.

### Service objects​

A service object is something that the customer either buys, such as items, or for which a contractual agreement is results in mutual obligations. A service object is assigned to a customer. The service object is usually static, but the associated services (service commitments) can change. Also, you can store additional information in the service object that's independent of the service commitments.

A service object doesn't contain any billing-relevant information. That information belongs to the associated service commitments. Service commitments that aren't invoiced through a contract can also belong to a service object, for example, warranties.

### Service commitments​

Service commitments describe the content of agreements with customers and suppliers. They exist in customer-side and vendor-side forms, and always belong to a service object. Service commitments contain billing information, such as the quantity to bill, the billing period, and the amount.

The service commitments of a service object and the creation of service commitments are defined through a multi-level hierarchy. It includes service commitment templates and service commitment packages that you can assign to items. Service objects are created through the sale of these items, to which the associated service commitments are assigned and available.

You can offer service commitments to prospects or customers already during the sales phase. For this purpose, you can add more service commitments to the offered items, which you can then offer simultaneously or sell at the same time.

If you sell an item in conjunction with a service commitment, a service object is automatically created for it, where the associated service commitments are visible. <!--Don't understand what we mean by "visible" here-->

If the service is a service commitment (see Types of Services), you can add it to a contract as a component and, according to the information in the service, bill on a recurring basis.

## Flow of subscription billing​

The following illustration shows that items are set up with service commitment packages with one or more service commitments. When the quote or order is shipped, the item becomes a service object. The service commitments assigned to the service object must be assigned to a contract to be billed on a recurring basis. The contract and its service commitments contain the billing information. When posting contract invoices, contract deferrals are created. You can post the deferrals to the general ledger independently to recognize the revenue or cost of the invoices.

:::image type="content" source="../media/srbFlow.png" alt-text="Shows the flow in subscription billing.":::

## Subscription & Recurring Billing Role Center​

The **Subscription & Recurring Billing** Role Center collects the features for recurring billing in one place, so things are easy to find. In addition to the master and transaction data, the Role Center provides fast access to the history of posted receipts. Documents that aren't posted (open posting documents for customers or vendors), and services that aren't assigned to contracts (services commitments without contracts) also display to alert you that something might still need to be done.

The revenues and costs figures show the current and previous month's revenues and costs that were posted in connection with contract billing.

The **Overdue** and **Not invoiced** cues indicate that service commitments are either still to be billed (Overdue) or that a posting document hasn't been created yet (Not invoiced) for lines in a billing proposal. The cues are based on the workdate.

## Related information

[Managing contracts, service objects, and services commitments](working-with-contracts/contracts-services-mgmt.md)  
[Recurring billing](recurring-billing.md)  
