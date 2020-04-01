---
title: Use Automatic Application to Reconcile Payments | Microsoft Docs
description: Describes how to use the automatic application function to apply payments or cash receipts to their related open entries, and reconcile payments.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: payment process, direct payment posting, reconcile payment, expenses, cash receipts
ms.date: 04/01/2020
ms.author: sgroespe

---
# Reconcile Payments Using Automatic Application
The **Payment Reconciliation Journal** page specifies payments, either incoming or outgoing, that have been recorded as transactions on your online bank account and that you can apply to their related open customer, vendor, and bank account ledger entries. The lines in the journal are filled by importing a bank statement as a bank feed or file.

> [!NOTE]
> The page offers automatic matching functionality that applies payments to their related open entries based on a matching of text on a bank statement line (journal line) with text on one or more open entries. Note that you can overwrite the suggested automatic applications, and you can choose to not use automatic application at all. For more information, see step 7.

A payment reconciliation journal is related to one bank account in [!INCLUDE[d365fin](includes/d365fin_md.md)] that reflects the online bank account where the payment transactions are recorded. Any open bank account ledger entries related to the applied customer or vendor ledger entries will be closed when you choose the **Post Payments and Reconcile Bank Account** action. This means that the bank account is automatically reconciled for payments that you post with the journal.

If you want to import bank statements as bank feeds, you must first enable the Envestnet Yodlee Bank Feeds service and then link the bank account to its related online bank account. The payment reconciliation journal will then automatically detect bank feeds when you choose the **Import Bank Transactions** action. In addition, you can set a bank account up to automatically import new bank statement feeds every hour. Transactions for payments that have already been posted as applied and/or reconciled will not be imported. For more information, see [Set Up the Envestnet Yodlee Bank Feeds Service](bank-how-setup-bank-statement-service.md).

With the **Map Text to Account** action, you can set up mappings between text on payments and specific debit, credit, and balancing accounts so that such payments are posted to the specified accounts when you post the payment reconciliation journal. See step 8. For more information, see [Map Text on Recurring Payments to Accounts for Automatic Reconciliation](receivables-how-map-text-recurring-payments-accounts-auto-reconcilliation.md).

Similar functionality exists to reconcile excess amounts on payment reconciliation journal lines on an ad-hoc basis. For more information, see [Reconcile Payments That Cannot be Applied.](receivables-how-reconcile-payments-cannot-apply-auto.md)

You use the **Apply Automatically** function, either automatically when you import a bank file or feed with payment transactions or when you activate it, to apply payments to their related open entries based on a matching of text on a bank statement line (journal line) with text on one or more open entries. For more information, see [Set Up Rules for Automatic Application of Payments](receivables-how-set-up-payment-application-rules.md).

On journal lines where a payment has been applied automatically to one or more open entries, the **Match Confidence** field has a value between Low and High to indicate the quality of the data matching that the suggested payment application is based on. In addition, the **Account Type** and **Account No.** fields are filled with information about the customer or vendor that the payment is applied to. If you have set up a text-to-account mapping, the automatic application can result in a match confidence value of **High - Text-to-Account Mapping**.

For each journal line on the **Payment Reconciliation Journal** page, you can open the **Payment Application** page to see all candidate open entries for the payment and view detailed information for each entry about the data matching that a payment application is based on. Here, you can manually apply payments or reapply payments that were applied automatically to a wrong entry. For more information, see [Review or Apply Payments After Automatic Application](receivables-how-review-apply-payments-auto-application.md).

> [!NOTE]  
> You can start the bank transactions import at the same time as you open the **Payment Reconciliation** Journal page for an existing payment reconciliation journal on the **Payment Reconciliation Journals** page. The following procedure describes how to import bank transactions into the **Payment Reconciliation Journal** page after you have created a new journal.

## To reconcile payments using automatic application
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Reconciliation Journals**, and then choose the related link.
2. To work in a new payment reconciliation journal, choose the **New Journal** action.
3. On the **Payment Bank Account List** page, select the bank account that you want to reconcile payments for, and then choose the **OK** button.
   The **Payment Reconciliation Journal** page opens prepared for the selected bank account.
4. Choose the **Import Bank Transactions** action.
   If the bank account for the selected journal is not set up for import of bank transactions, then a dialog box will open to help you fill in the relevant fields.
5. On the **Select a file to import** page, select the file that contains the bank transactions for payments that you want to reconcile, and then choose the **Open** button.  
6. If the Bank Statement service is enabled, on the **Bank Statement Filter** page that opens automatically, specify the date interval for the bank statements to be imported.

    The **Payment Reconciliation Journal** page is filled with lines for payments representing bank transactions in the imported bank statement.

    On lines for payments that have been automatically applied to their related open entries, the **Match Confidence** field has a value between **Low** and **High** to indicate the quality of the data matching that the suggested payment application is based on. In addition, the **Account Type** and **Account No.** fields are filled with information about the customer or vendor that the payment is applied to.
7. Select a journal line, and then, choose the **Apply Manually** action to review, reapply, or apply the payment manually on the **Payment Application** page. For more information, see [Review or Apply Payments After Automatic Application](receivables-how-review-apply-payments-auto-application.md).

    When you have finished your manual application, the **Match Confidence** field on the journal line that you have processed manually contains **Accepted**.
8. Select an unapplied journal line for a recurring cash receipt or expense, such as a car gasoline purchase, and then choose the **Map Text to Account** action. For more information, see [Map Text on Recurring Payments to Accounts for Automatic Reconciliation](receivables-how-map-text-recurring-payments-accounts-auto-reconcilliation.md)
9. When you have finished your mapping of payment text to accounts, choose the **Apply Manually** action.
10. When you are content that all payments on the journal lines are correctly applied or set to direct posting, choose the **Post** action, and then choose one of the options:

    - **Post Payments and Reconcile Bank Accounts** - To post the payments as applied and also close the related bank account ledger entries as reconciled.
    - **Post Payments Only** - To only post the payments as applied, but leave the related bank account ledger entries open. Required that you reconcile the bank account separately,  for example: For more information, see [Reconcile Bank Accounts](bank-how-reconcile-bank-accounts-separately.md).
    - **Test Report** - To review the result of posting before you post. The **Bank Account Statement** report opens and shows the same fields as at the bottom of the **Payment Reconciliation Journal** page.

When you post the payment reconciliation journal, the applied open entries memos are closed, and the related customer, vendor, or general ledger accounts are updated. For payments on journal lines based on text-to-account mapping, the specified customer, vendor, and general ledger accounts are updated. For all journal lines, bank account ledger entries are created. If you choose the **Post Payments and Reconcile Bank Account** action, any open bank account ledger entries related to the applied customer or vendor ledger entries will be closed. This means that the bank account is automatically reconciled for payments that you post with the journal.

You can compare the value in the **Balance on Bank Account After Posting** field together with the value in the **Statement Ending Balance** field to track when the bank account is reconciled based on payments that you post.

> [!NOTE]  
>   If you do not want to reconcile the bank account from the **Payment Reconciliation Journal** page, then you must use the **Bank Acc. Reconciliation** page. For more information, see [Reconcile Bank Accounts](bank-how-reconcile-bank-accounts-separately.md).

## See Also
[Managing Receivables](receivables-manage-receivables.md)  
[Sales](sales-manage-sales.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
