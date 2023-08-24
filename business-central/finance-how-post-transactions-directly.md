---
title: Record expenses or income directly in G/L
description: For business activities that are not represented by a document you can create the related transactions by posting journal lines in the General Journal page.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: direct posting, general ledger
ms.search.form: 39, 251
ms.date: 06/16/2021
ms.author: bholtorf

---
# Post Transactions Directly to the General Ledger

You use general journals to post financial transactions directly to general ledger accounts and other accounts, such as bank, customer, vendor, and employee accounts.  

A typical use of the general journal is to post employees' expenditure of own money during business activities, for later reimbursement. For more information, see [Record and Reimburse Employees' Expenses](finance-how-record-reimburse-employee-expenses.md).

General journals post financial transactions directly to general ledger accounts and other accounts, such as bank, customer, vendor, and employee accounts. Posting with a general journal always creates entries on general ledger accounts. This is true even when, for example, you post a journal line to a customer account, because an entry is posted to a general ledger receivables account through a posting group. You can personalize your version of a general journal by setting up a journal batch or template. For more information, see [Work with General Journals](ui-work-general-journals.md).

Unlike for entries that are posted with documents, which require a credit memo process, you can correctly reverse entries that are posted with the general journal. For more information, see [Reverse Journal Postings and Undo Receipts/Shipments](finance-how-reverse-journal-posting.md).

## To post a transaction directly to a general ledger account

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Journals**, and then choose the related link.
2. Open the relevant general journal batch. For more information, see [Work with General Journals](ui-work-general-journals.md).
3. On a new journal line, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]    

    > [!NOTE]
    > [!INCLUDE[journal-showhide-columns-inline-tip](includes/journal-showhide-columns-inline-tip.md)]
4. Repeat step 3 for all the separate transactions that you want to post.

    > [!TIP]  
    > If you want to enter multiple transaction lines above one balance-account line, for example, for one bank account, then select the **Suggest Balancing Amount** check box on the line for your batch on the **General Journal Batches** page. Then the **Amount** field on the balance-account line is automatically prefilled with the value that is required to balance the transactions.
5. Choose the **Post** action to record the transactions on the specified G/L accounts.

## See Also

[Work with General Journals](ui-work-general-journals.md)  
[Record and Reimburse Employees' Expenses](finance-how-record-reimburse-employee-expenses.md)  
[Reverse Journal Postings and Undo Receipts/Shipments](finance-how-reverse-journal-posting.md)  
[Finance](finance.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]