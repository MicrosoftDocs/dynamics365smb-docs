---
title: Record and reimburse employees' expenses
description: Post employees' expenses with the general journal to the employee's account  then post a payment to their bank account to reimburse the business-related expense.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: reimbursement
ms.search.form: 63, 234, 625, 5224, 5237, 5238, 5239, 5240
ms.date: 08/07/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Record and reimburse employees' expenses

[!INCLUDE[prod_short](includes/prod_short.md)] supports transactions for employees in a similar way as for vendors. Accordingly, employee posting groups exist to make sure that employee ledger entries are posted to the relevant accounts in the general ledger.

> [!NOTE]  
> Reimbursement payments to employees do not support discounts and payment tolerances.

If employees spend their own money during business activities, you can post the expense to the employee's account. Then you can reimburse the employee by making a payment to the employee's bank account, similarly to how you pay vendors.  

This article explains how to record the expense in the books and how to reimburse the employee. Your organization might have a portal or app where employees can submit their expense reports.

[!INCLUDE [prod_short](includes/prod_short.md)] is flexible enough to suit many different practices. The exact account numbers to use depend on your organization's configuration and processes.  

You can use general journals for employee accounts to register employee expenses and reimbursement transactions in foreign currencies, and then easily track the amounts and compare them to receipts. Leave your calculator in your desk drawer—Business Central can adjust the exchange rate for you. When you use general journals to post transactions for employee accounts, such as when you reimburse expenses, you can use the **Currency Code** field to specify the currency for the transactions. Specifying a currency lets you use the same features as when you register transactions in the customer and vendor ledgers. For example, employees can register an expense in euros but get paid in dollars.

To ensure that the exchange rate for the amounts is up to date, you can adjust employee balances when you run the currency exchange rate batch job. If you want to use the exchange rate table, but settle employee balances in your local currency, you can exclude employee accounts when you adjust exchange rates.

## To record an employee's expense

You post employees' expenses on the **General Journal** page.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Journals**, and then choose the related link.  
2. Open the relevant general journal batch. For more information, see [Work with General Journals](ui-work-general-journals.md).
3. On a new journal line, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

    > [!NOTE]
    > [!INCLUDE[journal-showhide-columns-inline-tip](includes/journal-showhide-columns-inline-tip.md)]
4. Repeat step 3 for all the expenses that the employee has incurred.

    > [!TIP]  
    > If you want to enter multiple expense lines above one balance-account line for the employee's bank account, then select the **Suggest Balancing Amount** check box on the line for your batch on the **General Journal Batches** page. Then the **Amount** field on the balance-account line is automatically prefilled with the value that is required to balance the expenses.
5. Choose the **Post** action to record the expenses on the employee's account.

## To reimburse an employee

You reimburse employees by posting payments to their bank account on the **Payment Journal** page.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Journals**, and then choose the related link.
2. Open the relevant payment journal batch. For more information, see [Work with General Journals](ui-work-general-journals.md).
3. Fill in the fields as necessary. For more information, see [Making Payments](payables-make-payments.md).
4. Alternatively, choose the **Suggest Employee Payment** action to automatically insert journal lines for pending employee reimbursements.
5. Choose the **Post** action to register the reimbursement.  

## To reconcile reimbursements with employee ledger entries

You apply employee payments to their related open employee ledger entries in the same way as you do for vendor payments, for example on the **Payment Reconciliation Journals** page, based on the related bank statement entries. For more information, see [Applying Payments Automatically and Reconciling Bank Accounts](receivables-apply-payments-auto-reconcile-bank-accounts.md). Alternatively, you can apply manually on the **Employee Ledger Entries** page. For more information, see the related [Reconcile Vendor Payments with the Payment Journal or from Vendor Ledger Entries](payables-how-apply-purchase-transactions-manually.md).  

## Related information

[Post Transactions Directly to the General Ledger](finance-how-post-transactions-directly.md)    
[Work with General Journals](ui-work-general-journals.md)    
[Reverse Journal Postings and Undo Receipts/Shipments](finance-how-reverse-journal-posting.md)    
[Finance](finance.md)    
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)    


[!INCLUDE[footer-include](includes/footer-banner.md)]
