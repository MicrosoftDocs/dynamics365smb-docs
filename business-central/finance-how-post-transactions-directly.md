---
title: Record expenses or income directly in G/L
description: You can create transactions on the General Journal page for business activities that don't involve a document.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: direct posting, general ledger
ms.search.form: 39, 251
ms.date: 08/06/2024
ms.service: dynamics-365-business-central
---

# Post transactions directly to the general ledger

You use general journals to post financial transactions directly to general ledger accounts and other accounts, such as bank, customer, vendor, and employee accounts.  

A typical use of the general journal is to post employees expenses during business activities for reimbursement. For more information, see [Record and Reimburse Employee Expenses](finance-how-record-reimburse-employee-expenses.md).

General journals post financial transactions directly to general ledger accounts and other accounts, such as bank, customer, vendor, and employee accounts. Posting with a general journal creates entries on general ledger accounts. Entries are created even when, for example, you post a journal line to a customer account, because an entry is posted to a general ledger receivables account through a posting group. You can personalize your version of a general journal by setting up a journal batch or template. For more information, see [Work with General Journals](ui-work-general-journals.md).

Entries that you post with documents require a credit memo process. However, you can reverse entries that you post with the general journal. For more information, see [Reverse Journal Postings and Undo Receipts/Shipments](finance-how-reverse-journal-posting.md).

## To post a transaction directly to a general ledger account

1. [!INCLUDE[open-search](includes/open-search.md)], enter **General Journals**, and then choose the related link.
2. Open the general journal batch. For more information, see [Work with General Journals](ui-work-general-journals.md).
3. On a new journal line, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

    > [!NOTE]
    > [!INCLUDE[journal-showhide-columns-inline-tip](includes/journal-showhide-columns-inline-tip.md)]
4. Repeat step 3 for all transactions that you want to post.

    > [!TIP]  
    > If you want to enter multiple transaction lines before a balance-account line, for example for one bank account, select the **Suggest Balancing Amount** checkbox on the line for your batch on the **General Journal Batches** page. The **Amount** field on the balance-account line is automatically prefilled with the value that is required to balance the transactions.
5. Choose the **Post** action to record the transactions on the specified G/L accounts.

## Related information

[Work with General Journals](ui-work-general-journals.md)    
[Record and Reimburse Employees' Expenses](finance-how-record-reimburse-employee-expenses.md)    
[Reverse Journal Postings and Undo Receipts/Shipments](finance-how-reverse-journal-posting.md)    
[Finance](finance.md)    
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
