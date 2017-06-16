---
title: Using General Journals to Post Directly to G/L| Microsoft Docs
description: Learn about using general journals to post financial transactions to general ledger accounts and other accounts, such as bank and vendor accounts.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/15/2017
ms.author: sgroespe

---
# Working with General Journals
Most financial transactions are posted to the general ledger through dedicated business documents, such as purchase invoices and sales orders. For business activities that are not represented by a document in [!INCLUDE[d365fin](includes/d365fin_md.md)], such as smaller expenses or cash receipts, you can create the related transactions by posting journal lines in the **General Journal** window. For more information, see [How to: Post Transactions Directly to the General Ledger](finance-how-post-transactions-directly.md).

You use general journals to post financial transactions directly to general ledger accounts and other accounts, such as bank, customer, and vendor accounts. Posting with a general journal always creates entries on general ledger accounts. This is true even when, for example, you post a journal line to a customer account, because an entry is posted to a general ledger receivables account through a posting group.

The information that you enter in a journal is temporary and can be changed while it is in the journal. When you post the journal, the information is transferred to entries on individual accounts, where it cannot be changed. You can, however, unapply posted entries, and you can post reversing or correcting entries. For more information, see [How to: Reverse Journal Posting](finance-how-reverse-journal-posting.md).

## Using Journal Templates and Batches
There are several general journal templates. Each journal template is represented by a dedicated window with particular functions and the fields that are required to support those functions, such as the **Payment Reconciliation Journal** window to process bank payments and the **Payment Journal** window to pay your vendors. For more information, see [Make Payments](payables-make-payments.md) and [How to: Reconcile Customer Payments Manually](receivables-how-apply-sales-transactions-manually.md).

For each journal template, you can set up your own personal journal as a journal batch. For example, you can define your own journal batch for the payment journal that has your personal layout and settings. The following tip is an example of how to personalize a journal.

> [!TIP]  
> If you select the **Suggest Balancing Amount** check box on the line for your batch in the **General Journal Batches** window, then the **Amount** field on, for example, general journal lines for the same document number is automatically prefilled with the value that is required to balance the document. For more information, see [Letting [!INCLUDE[d365fin](includes/d365fin_md.md)] Suggest Values](ui-let-system-suggest-values.md).

## Understanding Main Accounts and Balancing Accounts
If you have set up default balancing accounts for the journal batches, the balancing account will be filled in automatically when you fill in the **Account No.** field. Otherwise, fill in both the **Account No.** field and the **Bal. Account No.** field manually. A positive amount in the **Amount** field is debited to the main account and credited to the balancing account. A negative amount is credited to the main account and debited to the balancing account.

> [!NOTE]  
>   VAT is calculated separately for the main account and the balancing account, so they can use different VAT percentage rates.

## Working with Recurring journals
A recurring journal is a general journal with specific fields for managing transactions that you post frequently with few or no changes. Using these fields for recurring transactions, you can post both fixed and variable amounts. You can also specify automatic reversal entries for the day after the posting date and use allocation keys with the recurring entries.

## Working with Standard Journals
When you have created journal lines which you know you are likely to create again later, you can save them as a standard journal before you post the journal. This functionality applies to item journals and general journals.

> [!NOTE]  
>   The following procedure refers to the item journal, but the information also applies to the general journal.

### To save a standard journal
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Item Journals**, and then choose the related link.
2. Enter one or more journal lines.
3. Select the journal lines that you want to reuse.
4. Choose the **Save as Standard Journal** action.
5. In the **Save as Standard Item Journal** request window, define a new or existing standard item journal that the lines should be saved in.

    If you have already created one or more standard item journals and you want to replace one of these with the new set of item journal lines, in the Code field, select the code you want.
6. Choose the **OK** button to verify that you want to overwrite the existing standard item journal and replace all its content.
7. Select the **Save Unit Amount** field if you want to save the values in the **Unit Amount** field of the standard item journal.
8. Select the **Save Quantity** field if you want the program to save the values in the **Quantity** field.
9. Choose the **OK** button to save the standard item journal.

When you have finished saving the standard item journal, the Item Journal window is displayed so you can proceed to post it, knowing that it can easily be recreated next time you need to post the same or similar lines.

### To reuse a standard journal
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Item Journals**, and then choose the related link.
2. Choose the **Get Standard Journals** action.

    The Standard Item Journals window opens showing codes and descriptions for all existing standard item journals.
3. To review a standard item journal before you select it for reuse, choose the **Show Journal** action.

    Any changes you make in a standard item journal are implemented right away. They will be there next time you open or reuse the standard item journal in question. You should therefore be sure that the change is important enough to apply generally. Otherwise, make the specific change in the item journal after the standard item journal lines have been inserted. See step 4 below.
4. In the **Standard Item Journals** window, select the standard item journal you want to reuse, and then choose the **OK** button.

    Now the item journal is filled with the lines you saved as the standard item journal. If journal lines already existed in the item journal, the inserted lines will be placed under the existing journal lines.

    If you did not check the **Save Unit Amount** field when you used the **Save as Standard Item Journal** function job, then the **Unit Amount** field on lines that are inserted from the standard journal is automatically filled with the item’s current value, copied from the **Unit Cost** field on the item card.

    > [!NOTE]  
>   If you selected the **Save Unit Amount** or **Save Quantity** fields, you should now make sure the inserted values are correct for this particular inventory adjustment before you post the item journal.

    If the inserted item journal lines contain saved unit amounts that you do not want to post, you can quickly adjust it to the current value of the item as follows.

6. Select the item journal lines you want to adjust, and then choose the **Recalculate Unit Amount** action. This will update the Unit Amount field with the current unit cost of the item.
7. Choose the **post** action.

## See Also
[How to: Post Transactions Directly to the General Ledger](finance-how-post-transactions-directly.md)  
[How to: Reverse Journal Posting](finance-how-reverse-journal-posting.md)  
[How to: Allocate Costs and Income](year-allocate-costs-income.md)  
[Finance](finance.md)  
[Working With [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
