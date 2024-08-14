---
title: Posting Documents
hide_title: true
sidebar_label: Posting Documents
slug: /srb/posting-documents
---

# Posting Documents
Posting Documents are invoices and credit memos because these documents can be posted. When creating these documents via **[Recurring Billing](/docs/srb/recurring-billing.md)**, the system recognizes whether an invoice or a credit memo is to be created based on the amounts to be settled. If the total amount over all lines to be billed is positive, an invoice is created, otherwise a credit memo is created. This applies to both Customer Contracts and Vendor Contracts.
The Posting Documents created are then available for calling up in the respective contract under **Related**. There are separate calls for documents that have not yet been posted and documents that have already been posted. Sales documents are created from Customer Contracts and purchasing documents from Vendor Contracts. The documents can also be called using the following methods:
* **Sales Invoices** (Role Center or Alt+Q) <br/>.
A filter *Recurring Billing* is available in the page, which displays only the documents that belong to a contract.
* **Sales Credit Memos** (Role Center or Alt+Q) <br/>
A filter *Recurring Billing* is available in the page, which displays only the documents that belong to a contract.
* **Posted Sales Invoices** (Role Center or Alt+Q) <br/>
A filter *Recurring Billing* is available in the page, which displays only the documents that belong to a contract.
* **Posted Sales Credit Memos** (Role Center or Alt+Q) <br/>
A filter *Recurring Billing* is available in the page, which displays only the documents that belong to a contract.
* **Purchase Invoices** (Role Center or Alt+Q)
* **Purchase Credit Memos** (Role Center or Alt+Q)
* **Posted Purchase Invoices** (Role Center or Alt+Q)
* **Posted Purchase Credit Memos** (Role Center or Alt+Q)

For each document line, the details underlying the calculation can be accessed by calling **Billing Lines** (in the line menu via *Manage*).


## Additional information in contract invoices
In order to be able to react to different needs regarding the order of the output of information in contract invoices, it is possible to specify via [Setup](/docs/srb/setup/general.md#invoice-details) at which position in the contract invoice which information should be output. It is possible to control the output of the names of the contractor and the service recipient as well as other information about Service Objects and Service Commitments.


## Invoice and Credit Memo Preview
In addition to the **Preview Posting** from Business Central, DYCE also provides a [Print Preview](/docs/general/essentials/print-preview.md) for Sales invoices and credit memos that have not yet been posted.


## Post document
Posting Documents for contracts can be posted and printed individually or in batches, as is usual in the purchasing and sales areas. Especially in the case of a large number of contracts, it makes sense to check the Posting Documents by batch after they have been generated, to post them in the batch and to print them in the batch. In addition, **[Contract Details](/docs/srb/working-with-contracts/customer-contracts.md#details-for-contract-invoices)** can be output per customer contract invoice. These show the details relevant to the customer's contract invoice broken down in an understandable way.

When a document is posted, the associated billing lines are archived. These can be subsequently accessed via the posted document line (call **Archived Billing Lines** in the line menu via *Manage*) or the corresponding contract line (call **Archived Billing Lines** in the line menu via *Contract line*).

:::note Posting Description in Customer and Vendor Ledger Entries
When the documents are posted, the Posting Description in the Customer Ledger Entries and Vendor Ledger Entries can be used to trace from which contract the entry originates. If the document belongs to exactly one contract, the type of contract (Customer or Vendor Contract) and the Document No. are included. If there are multiple contracts, "Multiple Customer Contracts" or "Multiple Vendor Contracts" (each in the user's language) is used.
:::