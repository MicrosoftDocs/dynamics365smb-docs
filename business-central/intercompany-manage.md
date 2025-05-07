---
title: Managing intercompany transactions
description: With the Intercompany functionality, you can simplify business processes and transactions between companies within the same organization.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: concept-article
ms.date: 05/24/2024
ms.custom: bap-template
ms.search.keywords: IC, group, consolidation, affiliate, subsidiary
ms.search.form: 605, 611, 613, 615, 617, Report_512
ms.service: dynamics-365-business-central
---

# Managing intercompany transactions

Businesses with more than one legal entity with separate accounting functions can benefit from intercompany transactions. For example, it's useful for businesses that have subsidiaries in multiple international markets or regions. Or, an organization might have several companies but lack the equivalent number of accounting and administrative teams. Intercompany transactions simplify and streamline business processes and transactions between companies in the intercompany partnership.

After you specify the customer and vendor relationships for intercompany transactions, partners enter information one time in sales and purchase documents. A corresponding document is created at the other partner involved in the transaction. Mapping the chart of accounts and dimensions helps ensure that information appears in the right places.  

There are four main benefits to the intercompany functionality:  

* Increased productivity as a result of time saved and simplified transactions  
* Minimized mistakes with one-time entry of information and system-wide, automated updates  
* Transparent audit trail and full visibility into business activities and transaction histories  
* Efficient transactions with affiliate and subsidiary companies  

## Streamline the flow of business activities  

Intercompany transactions let you distribute sales and purchasing documents and general journal entries to all of your satellite offices, sales offices, or subsidiary companies. Distributing transactions saves time and increases efficiency throughout the organization by reducing data entry. It cuts down on the need to send, receive, print, and archive sales and purchasing documents.  

You're in full control of all transaction documents. For example, you can reject a document sent to you and use the **Reverse Journal Postings** and **Undo Receipts/Shipments** actions to make corrections. Or, when making a purchase from a partner or subsidiary company, you can update the purchase order as long as the selling company hasn't shipped the goods.  

When you enter a transaction, you don't need to specify the accounts to use. You just choose the intercompany partner. The intercompany functionality creates general journal lines that balance the books of both companies involved in the transaction. In receivables and payables, you assign an intercompany partner code to any customer or vendor. From that moment on, all orders and invoices for transactions between these companies produce corresponding documents in the partner company. The result is correctly balanced accounts.  

Intercompany focuses on sales and purchase documents and general journal lines, and allows transactions between multiple [!INCLUDE [prod_short](includes/prod_short.md)] databases. For example:

* Different countries/regions
* Multiple currencies
* Different charts of accounts
* Different dimensions
* Different item numbers  

Intercompany transactions use several types of entries and documents:  

* General journal entries
* Purchase and sales orders
* Purchase and sales invoices
* Credit memos
* Return orders

When you set up intercompany transactions, you create a list of intercompany partners, an intercompany chart of accounts, and intercompany dimensions. Afterward, you can create transactions in intercompany general journals.

> [!NOTE]
> The general journal by itself doesn't include currencies. It converts all amounts to the local currency at the current exchange rate.

After you set up business partners as customers and vendors, and assign them intercompany partner codes, they can exchange intercompany purchase and sales documents, including items and item charges. 

> [!NOTE]
> Companies can't use intercompany to exchange all types of data. Purchase invoices are not submitted to business partners through intercompany processes. However, sales invoices that are submitted through intercompany processes will be created as purchase invoices in the receiving company.

Consolidating financial data might be relevant for intercompany processes. For more information, see [Consolidating Financial Data from Multiple Companies](finance-consolidated-company-reporting.md).

The following table describes a sequence of tasks, with links to the articles that describe them.

|To |See|
|---|---|
|Create your intercompany vendors and customers as partners, and set up an intercompany chart of accounts.|[Set Up Intercompany](intercompany-how-setup.md)|
|Use intercompany documents or journals to post transactions with your intercompany partners.|[Work with Intercompany Documents and Journals](intercompany-how-work-documents-journals.md)|
|Organize and process incoming and outgoing transactions that you exchange with your intercompany partners.|[Manage the Intercompany Inbox and Outbox](intercompany-how-manage-intercompany-inbox.md)|
|Use intercompany transactions to distribute costs between partner companies.|[Allocate Costs to Intercompany Partners](intercompany-allocate-costs.md)|

## Related information

[Finance](finance.md)  
[Setting Up Finance](finance-setup-finance.md)  
[Work with General Journals](ui-work-general-journals.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  


[!INCLUDE[footer-include](includes/footer-banner.md)]
