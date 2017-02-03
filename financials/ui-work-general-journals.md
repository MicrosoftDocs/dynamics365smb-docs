---
title: Working with General Journals | Microsoft Docs
description: Learn how general journals work.
services: project-madeira
documentationcenter: ''
author: edupont04

ms.service: project-madeira
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/03/2017
ms.author: edupont

---
# Working with General Journals
You use general journals to post financial transactions to general ledger accounts and other accounts, such as bank, customer, and vendor accounts. Posting with a general journal always creates entries on general ledger accounts. This is true even when, for example, you post a journal line to a customer account, because an entry is posted to a general ledger receivables account through a posting group.

Financials also has non-financial journals, such as the Item Journal and the Physical Inventory Journal, but these journals are not visible in the user interface.

The information that you enter in a journal is temporary and can be changed while it is in the journal. When you post the journal, the information is transferred to entries on individual accounts, where it cannot be changed. You can, however, unapply posted entries, and you can post reversing or correcting entries.

## Journal templates and batches
There are several general journal templates. Each journal template is represented by a dedicated window with particular functions and the fields that are required to support those functions, such as the **Payment Reconciliation Journal** window to process bank payments and the **Payment Journal** window to pay your vendors.

**Note**: If you export payment files to your bank from the payment journal, you must select the **Allow Payment Export** check box for the journal batch in question in the **General Journal Batches** window. For more information, see [How to: Export Payments to a Bank File](payables-how-export-payments-bank-file.md).

For each journal template, you can set up your own personal journal as a journal batch. For example, you can define your own journal batch for the payment journal that has your personal layout and settings.

An example of a personal setting that you can define on your general journal batch is to have the system help you fill amount fields. If you select the **Suggest Balancing Amount** check box on the line for your batch in the **General Journal Batches** window, then the **Amount** field on, for example, general journal lines for the same document number is automatically prefilled with the value that is required to balance the document. For more information, see [Letting Financials Suggest Values](ui-let-system-suggest-values.md).

## Main accounts and balancing accounts
If you have set up default balancing accounts for the journal batches, the balancing account will be filled in automatically when you fill in the **Account No.** field. Otherwise, fill in both the **Account No.** field and the **Bal. Account No.** field manually. A positive amount in the **Amount** field is debited to the main account and credited to the balancing account. A negative amount is credited to the main account and debited to the balancing account.

**Note**: VAT is calculated separately for the main account and the balancing account, so they can use different VAT percentage rates.

## Recurring journals
A recurring journal is a general journal with specific fields for managing transactions that you post frequently with few or no changes. Using these fields for recurring transactions, you can post both fixed and variable amounts. You can also specify automatic reversal entries for the day after the posting date and use allocation keys with the recurring entries.

## See Also
[How to: Use Allocation Keys in General Journals](ui-how-use-allocation-keys-general-journals.md)  
[Finance](finance.md)  
[Working With Financials](ui-work-product.md)
