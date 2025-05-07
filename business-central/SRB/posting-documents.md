---
title: Posting documents
description: Learn about posted documents in subscription billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: 
ms.search.form: 8071, 8053
ms.date: 05/06/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Posting documents

Posting documents are invoices and credit memos because these documents can be posted. When creating these documents using the [Recurring billing](recurring-billing.md) page, [!INCLUDE [prod_short](../includes/prod_short.md)] recognizes whether to create an invoice or a credit memo based on the amounts to settle. If the total amount over all lines to be billed is positive, an invoice is created, otherwise a credit memo is created. This applies to both customer subscription contracts and vendor subscription contracts.

The posting documents are available on the respective contract under **Related**. There are different ways to open documents that are or aren't posted. Sales documents are created from customer subscription contracts and purchasing documents from vendor subscription contracts. The documents can also be opened using the following methods:

* **Sales Invoices**

   A **Recurring Billing** filter is available in the page, which displays only the documents that belong to a contract.
* **Sales Credit Memos** 

   A **Recurring Billing** is available in the page, which displays only the documents that belong to a contract.
* **Posted Sales Invoices** 

   A **Recurring Billing** filter is available in the page, which displays only the documents that belong to a contract.
* **Posted Sales Credit Memos**

   A **Recurring Billing** filter is available in the page, which displays only the documents that belong to a contract.
* **Purchase Invoices**
* **Purchase Credit Memos**
* **Posted Purchase Invoices**
* **Posted Purchase Credit Memos**

For each document line, the details underlying the calculation can be accessed by calling **Billing Lines** (in the line menu via *Manage*).

## Additional information in contract invoices

To be able to react to different needs regarding the order of the output of information in contract invoices, in the [Invoice details](setup/general.md#invoice-details) you can specify at which position in the contract invoice which information should output. It is possible to control the output of the names of the contractor and the service recipient as well as other information about subscriptions and subscription lines.

## Post document

Posting documents for contracts can be posted and printed individually or in batches, as is usual in the purchasing and sales areas. Especially in the case of a large number of contracts, it makes sense to check the posting documents by batch after they have been generated, to post them in the batch and to print them in the batch. In addition, [Details for contract invoices](working-with-contracts/customer-contracts.md#details-for-contract-invoices) can be output per customer subscription contract invoice. These show the details relevant to the customer's contract invoice broken down in an understandable way.

When a document is posted, the associated billing lines are archived. These can be accessed via the posted document line using the **Archived Billing Lines** action.

> [!NOTE]
> When the documents are posted, the posting description in the customer ledger entries and vendor ledger entries can be used to trace from which contract the entry originates. If the document belongs to exactly one contract, the type of contract (customer or vendor contract) and the document number are included. If there are multiple contracts, **Multiple Customer Subscription Contracts** or **Multiple Vendor Subscription Contracts** (each in the user's language) is used.

## Related information

[Managing contracts, subscriptions, and subscription lines](working-with-contracts/contracts-services-mgmt.md)
