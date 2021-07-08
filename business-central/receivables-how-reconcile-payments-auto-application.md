---
title: Reconcile Payments Using Automatic Application
description: Describes how to use the automatic application function to apply payments or cash receipts to their related open entries, and reconcile payments.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: payment process, direct payment posting, reconcile payment, expenses, cash receipts
ms.date: 04/01/2021
ms.author: edupont

---
# Reconcile Payments Using Automatic Application

The **Payment Reconciliation Journal** page specifies payments, either incoming or outgoing, that have been recorded as transactions on your online bank account or on a payment service and that you can apply to their related open customer, vendor, and bank account ledger entries. The lines in the journal can be filled in by importing a bank statement as a bank feed or file or by manually entering transactions that you make on your payment service.

> [!NOTE]
> The page offers automatic matching functionality that applies payments to their related open entries based on a matching of data on a bank statement line (journal line) with data on one or more open entries. Note that you can overwrite the suggested automatic applications, and you can choose to not use automatic application at all. For more information, see step 7.

A payment reconciliation journal is related to one bank account in [!INCLUDE[prod_short](includes/prod_short.md)] that reflects the online bank account where the payment transactions are recorded. Any open bank account ledger entries related to the applied customer or vendor ledger entries will be closed when you choose the **Post Payments and Reconcile Bank Account** action. This means that the bank account is automatically reconciled for payments that you post with the journal.

You can import bank transactions as .csv bank files or other format that your bank provides. If you want to import bank statements as bank feeds, you must first enable a dedicated bank integration service and then link the bank account to its related online bank account. The payment reconciliation journal will then automatically detect bank feeds when you choose the **Import Bank Transactions** action. In addition, you can set a bank account up to automatically import new bank statement feeds every hour. Transactions for payments that have already been posted as applied and/or reconciled will not be imported. You can use the Envestnet Yodlee Bank Feeds service for this, which is preinstalled in some country versions of [!INCLUDE[d365fin](includes/d365fin_md.md)]. For more information, see [Set Up the Envestnet Yodlee Bank Feeds Service](bank-how-setup-bank-statement-service.md). Alternatively, contact your Microsoft partner for help meeting your business or country requirements.

The **Map Text to Account** action lets you set up mappings between text on payments and specific debit, credit, and balancing accounts so that such payments are posted to the specified accounts when you post the payment reconciliation journal. This is useful, for example, for recurring cash receipts or expenses, such as frequent purchases of car fuel or bank fees and interest, that regularly occur on the bank statement and do not need a related business document. (See step 10 below.) For more information, see [Map Text on Recurring Payments to Accounts for Automatic Reconciliation](receivables-how-map-text-recurring-payments-accounts-auto-reconcilliation.md).

Journal lines may have no suggested application. This may be for various reason, such as a missing document or because a customer overpaid so that an excess amount exists after applying the payment on another journal line. For such cases, you can use the **Transfer Difference to Account** action to create and post the missing general ledger entry, for example for a refund, that is needed to apply the payment to. (See step 11 below) For more information, see [Reconcile Payments That Cannot be Applied.](receivables-how-reconcile-payments-cannot-apply-auto.md).

You use the **Apply Automatically** function either automatically when you import a bank file or feed with payment transactions or when you activate it, to apply payments to their related open entries based on a matching of text on a bank statement line (journal line) with text on one or more open entries. This automation is based on rules that you define on the **Payment Application Rules** page, where you also define whether an application suggestion requires review. For more information, see [Set Up Rules for Automatic Application of Payments](receivables-how-set-up-payment-application-rules.md).

On journal lines where a payment has been applied automatically to one or more open entries, the **Match Confidence** field has a value of **Low**, **Medium**, or **High** to indicate the quality of the data matching that the suggested payment application is based on.

Some payment applications require your review as defined by the used matching rule, such as lines with **Low** match confidence. Other lines require your review and manual change because there is a value in the **Difference** field. To review one or more payment applications, choose the **Lines to Review** or **Lines with Difference** field at the bottom. The **Payment Application Review** page opens showing all relevant information about the customer or vendor that the payment is applied to, the matching details, and actions to process the line, such as the **Accept Application** action. (See steps 7 and 8 below.)

For each journal line on the **Payment Reconciliation Journal** page, you can open the **Payment Application** page to see all candidate open entries for the payment and view detailed information for each entry about the data matching that a payment application is based on. Here, you can manually apply payments or reapply payments that were applied automatically to a wrong entry. (See step 10 below.) For more information, see [Review or Apply Payments After Automatic Application](receivables-how-review-apply-payments-auto-application.md).

> [!NOTE]  
> You can start the bank transactions import at the same time as you open the **Payment Reconciliation Journal** page for an existing journal. The following procedure describes how to import bank transactions into the **Payment Reconciliation Journal** page after you have created a new journal.

## To reconcile payments using automatic application
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Reconciliation Journals**, and then choose the related link.
2. To work in a new payment reconciliation journal, choose the **New Journal** action.
3. On the **Payment Bank Account List** page, select the bank account that you want to reconcile payments for, and then choose the **OK** button.
   The **Payment Reconciliation Journal** page opens prepared for the selected bank account.
4. Choose the **Import Bank Transactions** action.
   If the bank account for the selected journal is not set up for import of bank transactions, then a dialog box will open to help you fill in the relevant fields.
5. On the **Select a file to import** page, select the file that contains the bank transactions for payments that you want to reconcile, and then choose the **Open** button.  
6. If the Envestnet Yodlee Bank Feeds service is enabled, on the **Bank Statement Filter** page that opens automatically, specify the date interval for the bank statements to be imported.

    The **Payment Reconciliation Journal** page is filled with lines for payments representing bank transactions in the imported bank statement.

     On lines for payments that have been automatically applied to their related open entries, the **Match Confidence** field has a value between **Low** and **High** to indicate the quality of the data matching that the suggested payment application is based on. In addition, the **Account Name**, **Account Type**, and **Account No.** fields are filled with information about the customer or vendor that the payment is applied to.

    The automatic applications, the matching qualities, and whether lines require review are defined by rules that you can edit to adjust the results. For more information, see [Set Up Rules for Automatic Application of Payments](receivables-how-set-up-payment-application-rules.md).

7. To review, accept/remove, or manually change multiple payment applications that have a value in the **Difference** field, choose the **Lines with Difference** action at the bottom.

    The **Payment Application Review** page opens showing the first application to review. The next application to review will be shown on the page as you process the preceding one. All relevant information about the customer or vendor that the payment is applied to, the matching details, and actions to process the line, such as the **Accept Application** and **Apply Manually** actions.

8. To review, accept/remove, or manually change multiple payment applications that are set to be reviewed, according to the payment application rule, choose the **Lines to Review** action at the bottom. The same experience as described for step 8 is presented

9. To change an automatic application, select a journal line, and then choose the **Apply Manually** action to reapply or apply the payment manually on the **Payment Application** page. For more information, see [Review or Apply Payments After Automatic Application](receivables-how-review-apply-payments-auto-application.md).

10. Select an unapplied journal line for a recurring cash receipt or expense, such as a car gasoline purchase, and then choose the **Map Text to Account** action. For more information, see [Map Text on Recurring Payments to Accounts for Automatic Reconciliation](receivables-how-map-text-recurring-payments-accounts-auto-reconcilliation.md).

    When you have finished your mapping of payment text to accounts, choose the **Apply Manually** action.

    When a text-to-account ,map is set up, the resulting automatic payment application will contain **High - Text-to-Account Mapping** in the **Match Confidence** field.

11. For a journal line has no suggested application because no ledger entry exists that it can be applied to,  choose the **Transfer Difference to Account** action to create and post the missing general ledger entry that is needed to apply the payment to. For more information, see [Reconcile Payments That Cannot be Applied.](receivables-how-reconcile-payments-cannot-apply-auto.md)

10. When no more lines require review and the **Difference** field is blank on all lines, choose the **Post** action, and then choose one of the following options:

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
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]