---
title: Transactions Between Companies in the Same Organization| Microsoft Docs
description: With the Intercompany functionality, you can simplify business processes and transactions between companies within the same organization.  
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: IC, group, consolidation, affiliate, subsidiary
ms.date: 04/01/2020
ms.author: sgroespe

---
# Managing Intercompany Transactions
Your organization may consist of several companies, but might not have the equivalent number of accounting and administrative teams. The Intercompany functionality lets you do business with your subsidiary and internal partner organizations in the same way as you engage with your external vendors and customers. You enter intercompany transaction information only once in the appropriate documents. You can use the functionality you are already familiar with, such as receivables and payables management. Mapping facilities for the chart of accounts and dimensions help ensure that information appears in the right places.  

There are four main benefits to the Intercompany functionality:  

- Increased productivity as a result of time saved and simplified transactions  
- Minimized error potential with one-time entry of information and system-wide, automated updates  
- Complete audit trail and full visibility into business activities and transaction histories  
- Efficient, cost-effective transactions with affiliate and subsidiary companies  

You are in full control of all transaction documents. For example, you can reject a document sent to you and, in this way, Reverse Journal Postings and Undo Receipts/Shipments that were incorrect. Or, when making a purchase from a partner or subsidiary company, you can update the purchase order as long as the selling company has not shipped any goods.  

When you enter a transaction, you do not need to specify the accounts for an individual set of books, but simply give the identification of the partner company. The Intercompany functionality creates general journal lines that result in the balancing of the books of both companies involved in a transaction. In receivables and payables, you assign an intercompany partner code to any customer or vendor. From that moment on, all orders and invoices generated pertaining to transactions with these companies will produce corresponding documents in the partner company, resulting in correct balancing of the accounts.  

 After you set up business partners as customers and vendors in the system, and assign them intercompany partner codes, it is possible to exchange intercompany purchase and sales documents, including items and item charges. The Intercompany functionality allows intercompany transactions between multiple databases, for example, in different countries/regions, as well as multiple currencies, different charts of accounts, different dimensions, and different item numbering.  

Consolidating financial data may especially be relevant in connection with intercompany processes. For more information, see [Consolidating Financial Data from Multiple Companies](finance-consolidated-company-reporting.md).

The following table describes a sequence of tasks, with links to the topics that describe them.

 |To |See|
 |---|---|
 |Create your intercompany vendors and customers as so-called intercompany partners, and set up an intercompany chart of accounts.|[Set Up Intercompany](intercompany-how-setup.md)|
 |Use intercompany documents or journals to post transactions with your intercompany partners.|[Work with Intercompany Documents and Journals](intercompany-how-work-documents-journals.md)|
 |Organize and process incoming and outgoing transactions that you exchange with your intercompany partners.|[Manage the Intercompany Inbox and Outbox](intercompany-how-manage-intercompany-inbox.md)|

## See Also
[Finance](finance.md)  
[Setting Up Finance](finance-setup-finance.md)  
[Working with General Journals](ui-work-general-journals.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

## [!INCLUDE[d365fin](includes/free_trial_md.md)]  
