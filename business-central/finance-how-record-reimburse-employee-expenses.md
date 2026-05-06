---
title: Record and reimburse employees' expenses
description: Post employees' expenses with the general journal to the employee's account  then post a payment to their bank account to reimburse the business-related expense.
author: brentholtorf
ms.topic: how-to
ms.search.keywords: reimbursement
ms.search.form: 63, 234, 625, 5224, 5237, 5238, 5239, 5240
ms.date: 04/24/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Record and reimburse employees' expenses

[!INCLUDE[prod_short](includes/prod_short.md)] supports transactions for employees in a similar way as for vendors. Accordingly, employee posting groups exist to make sure that employee ledger entries are posted to the relevant accounts in the general ledger.

> [!NOTE]  
> Reimbursement payments to employees don't support discounts and payment tolerances.

If employees spend their own money during business activities, you can post the expense to the employee's account. Then you can reimburse the employee by making a payment to the employee's bank account, similarly to how you pay vendors.  

This article explains how to record expenses in the books and reimburse employees in scenarios where employees submit expense reports and expect reimbursement.

[!INCLUDE [prod_short](includes/prod_short.md)] is flexible enough to suit many different practices. The exact account numbers depend on your organization's configuration and processes.  

You can use **Payment Journals** for employee accounts to register reimbursement transactions in foreign currencies, and then easily track the amounts and compare them to receipts. Leave your calculator in your desk drawer—Business Central can adjust the exchange rate for you. When you use **Payment Journals** to post transactions for employee accounts, such as when you reimburse expenses, you can use the **Currency Code** field to specify the currency for the transactions. Specifying a currency lets you use the same features as when you register transactions in the customer and vendor ledgers. For example, employees can register an expense in euros but get paid in dollars.

To ensure that the exchange rate is accurate, run the currency exchange rate batch job to adjust employee balances. To use the exchange rate table but settle employee balances in your local currency, exclude employee accounts when you adjust exchange rates.

## Reimburse an employee

You reimburse employees by posting payments to their bank account on the **Payment Journal** page.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Payment Journals**, and then choose the related link.
2. Open the relevant payment journal batch. For more information, see [Work with General Journals](ui-work-general-journals.md).
3. Fill in the fields as necessary. For more information, see [Making Payments](payables-make-payments.md).
4. Alternatively, choose the **Suggest Employee Payment** action to automatically insert journal lines for pending employee reimbursements.
5. Choose the **Post** action to register the reimbursement.  

## Reconcile reimbursements with employee ledger entries

You apply employee payments to their related open employee ledger entries in the same way as you do for vendor payments, for example on the **Payment Reconciliation Journals** page, based on the related bank statement entries. For more information, see [Applying Payments Automatically and Reconciling Bank Accounts](receivables-apply-payments-auto-reconcile-bank-accounts.md). Alternatively, you can apply manually on the **Employee Ledger Entries** page. For more information, see the related [Reconcile Vendor Payments with the Payment Journal or from Vendor Ledger Entries](payables-how-apply-purchase-transactions-manually.md).  

## After reimbursement   

Once reimbursement is completed in the **Payment Journal**, you can notify the employee.  

To do this, open the **Posted Expense Report** and choose the **Send Reimbursement Notification** action. This sends an email to the employee confirming that the reimbursement for the expense report has been processed. 


## Related information

[Post Transactions Directly to the General Ledger](finance-how-post-transactions-directly.md)  
[Work with General Journals](ui-work-general-journals.md)  
[Reverse Journal Postings and Undo Receipts/Shipments](finance-how-reverse-journal-posting.md)  
[Finance](finance.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
