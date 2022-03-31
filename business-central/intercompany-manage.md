---
title: Managing intercompany transactions
description: With the Intercompany functionality, you can simplify business processes and transactions between companies within the same organization.  
author: SorenGP


ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: IC, group, consolidation, affiliate, subsidiary
ms.search.form: 605
ms.date: 08/11/2021
ms.author: edupont

---
# Managing Intercompany Transactions

The intercompany transactions capabilities are designed for users who control more than one legal business entity and have set up multiple companies to separate the accounting functions of each of these entities. This broad description applies to many users, especially those operating in international markets or regions with widely disparate business cultures and regulatory environments.

Your organization may consist of several companies, but might not have the equivalent number of accounting and administrative teams. Intercompany transactions lets you simplify and streamline business processes and transactions between all of these entities.

Once you start using intercompany transactions, doing business with your subsidiary and internal partner organizations becomes as simple as engaging with your external vendors and customers. You enter intercompany transaction information only once in the appropriate documents. You can use the functionality you are already familiar with, such as receivables and payables management. Mapping facilities for the chart of accounts and dimensions help ensure that information appears in the right places.  

There are four main benefits to the Intercompany functionality:  

- Increased productivity as a result of time saved and simplified transactions  
- Minimized error potential with one-time entry of information and system-wide, automated updates  
- Complete audit trail and full visibility into business activities and transaction histories  
- Efficient, cost-effective transactions with affiliate and subsidiary companies  

## Streamlining the Flow of Business Activities  

Intercompany transactions lets you distribute sales and purchasing documents, as well as General Journal entries to all of your satellite offices, sales offices, or subsidiary companies, from within the program. Savings of time and increased efficiencies result throughout the organization as you eliminate redundant data entry and the sending, receiving, printing, and archiving of the sales and purchasing documents on paper.  

You are in full control of all transaction documents. For example, you can reject a document sent to you and, in this way, Reverse Journal Postings and Undo Receipts/Shipments that were incorrect. Or, when making a purchase from a partner or subsidiary company, you can update the purchase order as long as the selling company has not shipped any goods.  

When you enter a transaction, you do not need to specify the accounts for an individual set of books, but simply give the identification of the partner company. The intercompany functionality creates general journal lines that result in the balancing of the books of both companies involved in a transaction. In receivables and payables, you assign an intercompany partner code to any customer or vendor. From that moment on, all orders and invoices generated pertaining to transactions with these companies will produce corresponding documents in the partner company, resulting in correct balancing of the accounts.  

Intercompany transactions functionality focuses on supporting intercompany transactions with sales and purchasing documents, and with General Journal lines. Within this area, intercompany transactions allows intercompany transactions between multiple [!INCLUDE [prod_short](includes/prod_short.md)] databases, for example, in different countries/regions, as well as multiple currencies, different charts of accounts, different dimensions, and different item numbering.  

Intercompany transactions uses a number of entries and documents in intercompany transactions:  

- General Journal entries
- Purchase and sales orders
- Purchase and sales invoices
- Credit memos
- Return orders

When you set up intercompany transactions, you create a list of intercompany partners, called IC Partners, and an intercompany chart of accounts. Following these steps, you can perform intercompany general journal transactions. You set up dimensions – if needed – separately.  

> [!NOTE]
> The general journal by itself does not include currency functionality, but converts all amounts at the applicable rate to the local currency.

After you set up business partners as customers and vendors in the system, and assign them intercompany partner codes, it is possible to exchange intercompany purchase and sales documents, including items and item charges. [!INCLUDE [prod_short](includes/prod_short.md)] supports intercompany transactions between multiple databases, for example, in different countries/regions, as well as multiple currencies, different charts of accounts, different dimensions, and different item numbering.  

> [!NOTE]
> Not all types of data can be exchanged between companies in this way. Purchase invoices are not submitted to business partners through intercompany processes. But sales invoices that are submitted through intercompany processes will be created as purchase invoices in the receiving company.

Consolidating financial data may especially be relevant for intercompany processes. For more information, see [Consolidating Financial Data from Multiple Companies](finance-consolidated-company-reporting.md).

The following table describes a sequence of tasks, with links to the articles that describe them.

|To |See|
|---|---|
|Create your intercompany vendors and customers as so-called intercompany partners, and set up an intercompany chart of accounts.|[Set Up Intercompany](intercompany-how-setup.md)|
|Use intercompany documents or journals to post transactions with your intercompany partners.|[Work with Intercompany Documents and Journals](intercompany-how-work-documents-journals.md)|
|Organize and process incoming and outgoing transactions that you exchange with your intercompany partners.|[Manage the Intercompany Inbox and Outbox](intercompany-how-manage-intercompany-inbox.md)|
|Use intercompany transactions to distribute costs between partner companies.|[Allocate Costs to Intercompany Partners](intercompany-allocate-costs.md)|

## See Also

[Finance](finance.md)  
[Setting Up Finance](finance-setup-finance.md)  
[Work with General Journals](ui-work-general-journals.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  


[!INCLUDE[footer-include](includes/footer-banner.md)]
