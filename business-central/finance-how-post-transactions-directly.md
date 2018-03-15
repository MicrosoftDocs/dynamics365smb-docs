---
title: Record expenses or income directly in G/L| Microsoft Docs
description: For business activities that are not represented by a document in, such as smaller expenses or cash receipts, you can create the related transactions by posting journal lines in the General Journal window.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: direct posting, general ledger
ms.date: 06/28/2017
ms.author: sgroespe

---
# Post Transactions Directly to the General Ledger
Most financial transactions are posted to the general ledger through dedicated business documents, such as purchase invoices and sales orders. For business activities that are not represented by a document in [!INCLUDE[d365fin](includes/d365fin_md.md)], such as smaller expenses or cash receipts, you can create the related transactions by posting journal lines in the **General Journal** window.

A typical use of the general journal is to post employees' expenditure of own money during business activities, for later reimbursement. For more information, see [Record and Reimburse Employees' Expenses](finance-how-record-reimburse-employee-expenses.md).

General journals post financial transactions directly to general ledger accounts and other accounts, such as bank, customer, vendor, and employee accounts. Posting with a general journal always creates entries on general ledger accounts. This is true even when, for example, you post a journal line to a customer account, because an entry is posted to a general ledger receivables account through a posting group. You can personalize your version of a general journal by setting up a journal batch or template. For more information, see [Working with General Journals](ui-work-general-journals.md).

Unlike for entries that are posted with documents, which require a credit memo process, you can correctly reverse entries that are posted with the general journal. For more information, see [Reverse Postings](finance-how-reverse-journal-posting.md).

## To post a transaction directly to a general ledger account
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **General Journals**, and then choose the related link.
2. Open the relevant general journal batch. For more information, see [Working with General Journals](ui-work-general-journals.md).
3. On a new journal line, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]    
4. Repeat step 3 for all the separate transactions that you want to post.

    > [!TIP]  
    > If you want to enter multiple transaction lines above one balance-account line, for example, for one bank account, then select the **Suggest Balancing Amount** check box on the line for your batch in the **General Journal Batches** window. Then the **Amount** field on the balance-account line is automatically prefilled with the value that is required to balance the transactions.
5. Choose the **Post** action to record the transactions on the specified G/L accounts.

## See Also
[Working with General Journals](ui-work-general-journals.md)  
[Record and Reimburse Employees' Expenses](finance-how-record-reimburse-employee-expenses.md)  
[Reverse Postings](finance-how-reverse-journal-posting.md)  
[Finance](finance.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
