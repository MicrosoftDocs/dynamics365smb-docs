---
title: Reconcile Bank Accounts
description: This topic describes how to reconcile the transactions in your internal bank accounts with the transactions in statements from your bank.
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: bank account balance, bank statement
ms.search.form: 379, 388, 1290, 10124
ms.date: 06/14/2021
ms.author: bholtorf

---
# Reconcile Bank Accounts

You perform bank reconciliation to make sure that your various business transactions and expenses are reflected correctly in the company books. You do this by comparing and matching entries in your internal bank accounts with bank transactions at your bank, and then posting the balances to your internal bank accounts to make totals available to finance managers. Bank reconciliation is also a practical way to discover and resolve missing payments and bookkeeping errors.

The following describes how to perform bank reconciliation with the **Bank Acc. Reconciliation** page.

> [!TIP]
> You can also reconcile bank accounts on the **Payment Reconciliation Journal** page when you process payments. Any open bank account ledger entries related to the applied customer or vendor ledger entries will be closed when you choose the **Post Payments and Reconcile Bank Account** action. This automatically reconciles the bank account for the payments that you post with the journal. For more information, see [Applying Payments Automatically and Reconciling Bank Accounts](receivables-apply-payments-auto-reconcile-bank-accounts.md).

> [!NOTE]  
> In the North American versions, you can also perform this work on the **Bank Rec. Worksheet** page, which is better suited for checks and deposits but does not offer import of bank statement files. To use this page instead of the **Bank Acc. Reconciliation** page, clear the **Bank Recon. with Auto. Match** field on the **General Ledger Setup** page. For more information, see [Reconciling Bank Accounts](LocalFunctionality/UnitedStates/how-to-reconcile-bank-accounts.md) under United States Local Functionality.

The lines on the **Bank Acc. Reconciliation** page are divided into two panes. The **Bank Statement Lines** pane shows either imported bank transactions or ledger entries with outstanding payments. The **Bank Account Ledger Entries** pane shows the ledger entries in the internal bank account.

Reconciling bank transactions with internal bank entries is referred to as *matching*. You can choose to perform matching automatically by using the **Match Automatically** function. Alternatively, you can manually select lines in both panes to link each bank statement line to one or more related bank account ledger entries, and then use the **Match Manually** function. The **Applied** check box is selected on lines where entries match. For more information, see [Set Up Rules for Automatic Application of Payments](receivables-how-set-up-payment-application-rules.md).

> [!NOTE]  
> If bank statement lines relate to check ledger entries, you cannot use the matching functions. Instead, you must choose the **Apply Entries** action, and then select the relevant check ledger entry to match the bank statement line with.

When the value in the **Total Balance** field in the **Bank Statement Lines** pane equals the total value of the **Balance To Reconcile** field plus the **Balance Last Statement** field in the **Bank Account Ledger Entries** pane, you can choose the **Post** action. Unmatched bank account ledger entries remain on the page, indicating discrepancies that you should resolve to reconcile the bank account.

Any lines that cannot be matched, indicated by a value in the **Difference** field, will remain on the **Bank Acc. Reconciliation** page after posting. They represent some kind of discrepancy that you must resolve before you can complete the bank account reconciliation. Typical business situations that may cause differences:

| Difference | Reason | Resolution |
|------------|--------|------------|
| A transaction in the internal bank account is not on the bank statement. | The bank transaction did not occur although a posting was made in [!INCLUDE[prod_short](includes/prod_short.md)]. | Make the missing money transaction (or prompt a debitor to make it), and then re-import the bank statement file or enter the transaction manually. |
| A transaction on the bank statement does not exist as a document or journal line in [!INCLUDE[prod_short](includes/prod_short.md)]. | A bank transaction was made without a corresponding posting in [!INCLUDE[prod_short](includes/prod_short.md)], for example a journal line posting for an expense. | Create and post the missing entry. For information on a quick way to initiate this, see [To create missing ledger entries to match bank transactions with](bank-how-reconcile-bank-accounts-separately.md#to-create-missing-ledger-entries-to-match-bank-statement-lines-with). |
| A transaction in the internal bank account corresponds to a bank transaction but some information is too different to give a match. | Information, such as the amount or the customer name, was entered differently in connection with the bank transaction or the internal posting. | Review the information, and then manually match the two. Optionally, correct the information mismatch. |

You must resolve the differences, for example by creating missing entries and correcting non-matching information, or by making missing money transactions, until the bank account reconciliation is completed and posted.

You can fill in the **Bank Statement Lines** pane on the **Bank Acc. Reconciliation** page in the following ways:

* Automatically, by using the **Import Bank Statement** function to fill in the **Bank Statement Lines** pane with bank transactions according to an imported file or stream provided by the bank.
* Manually, by using the **Suggest Lines** function to fill in the **Bank Statement Lines** pane according to invoices in [!INCLUDE[prod_short](includes/prod_short.md)] that have outstanding payments.

## To fill bank reconciliation lines by importing a bank statement

The **Bank Statement Lines** pane will be filled with bank transactions according to an imported file or stream provided by the bank.

To enable import of bank statements as bank feeds, you must first set up and enable the Envestnet Yodlee Bank Feed service, and then link your bank accounts to the related online bank accounts. For more information, see [Set Up the Envestnet Yodlee Bank Feeds Service](bank-how-setup-bank-statement-service.md).  

> [!TIP]
> You can also import bank statement files in comma or semicolon delimited format (.CSV). Use the **Set up a bank statement file format** assisted setup to define bank statement import formats and attach the format to a bank account. You can then use these formats when you import bank statements in the **Bank Account Reconciliation** page.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Bank Account Reconciliation**, and then choose the related link.
2. Choose the **New** action.
3. In the **Bank Account No.** field, select the relevant bank account. The bank account ledger entries that exist on the bank account appear in the **Bank Account Ledger Entries** pane.
4. In the **Statement Date** field, enter the date of the statement from the bank.
5. In the **Statement Ending Balance** field, enter the balance of the statement from the bank.
6. If you have a bank statement file, choose the **Import Bank Statement** action.
7. Locate the file, and then choose the **Open** button to import the bank transactions into the **Bank Statement Lines** pane on the **Bank Acc. Reconciliation** page.

## To fill bank reconciliation lines with the Suggest Lines function

The **Bank Statement Lines** pane will be filled according to invoices in [!INCLUDE[prod_short](includes/prod_short.md)] that have outstanding payments.  

1. On the **Bank Acc. Reconciliation** page, choose the **Suggest Lines** action.
2. In the **Starting Date** field, enter the earliest posting date for the ledger entries to be reconciled.
3. In the **Ending Date** field, enter the latest posting date for the ledger entries to be reconciled.

> [!NOTE]
> Typically, the ending date will match the date specified in the **Statement Date** field. However, if you want to reconcile transactions for only part of a period, you can enter a different ending date. 

1. Select the **Include Checks** check box to any suggest check ledger entries instead of the corresponding bank account ledger entries.
1. Choose the **OK** button.

## To match bank statement lines with bank account ledger entries automatically

The **Bank Acc. Reconciliation** page offers automatic matching functionality based on a matching of text on a bank statement line (left pane) with text on one or more bank account ledger entries (right pane). Note that you can overwrite the suggested automatic matching, and you can choose to not use automatic matching at all. For more information, see [To match bank statement lines with bank account ledger entries manually](bank-how-reconcile-bank-accounts-separately.md#to-match-bank-statement-lines-with-bank-account-ledger-entries-manually).

Auto-matching matches entries based on a set of payment application rules. For more information, see [Set Up Rules for Automatic Application of Payments](receivables-how-set-up-payment-application-rules.md). You can investigate the basis for matches by using the **Match Details** action. For example, the details will include the names of the fields that contained matching values.  

1. On the **Bank Acc. Reconciliation** page, choose the **Match Automatically**. **The Match Bank Entries** page opens.
2. In the **Transaction Date Tolerance (Days)** field, specify the span of days before and after the bank account ledger entry posting date within which the function will search for matching transaction dates in the bank statement.

    If you enter 0 or leave the field blank, the **Match Automatically** action will only search for matching transaction dates on the bank account ledger entry posting date.
3. Choose the **OK** button.

    All bank statement lines and bank account ledger entries that can be matched change to green font, and the **Applied** check box is selected.
4. To remove a match, select the bank statement line, and then choose the **Remove Match** action.

> [!TIP]
> You can use a mix of manual and automatic matching. If you have manually matched entries, automatic matching will not overwrite your selections. 

## To match bank statement lines with bank account ledger entries manually
1. On the **Bank Acc. Reconciliation** page, select a non-applied line in the **Bank Statement Lines** pane.
2. In the **Bank Account Ledger Entries** pane, select one or more banks account ledger entries that can be matched with the selected bank statement line. To choose multiple lines, press and hold the CTRL key.

   > [!TIP]
   > You can also manually match multiple bank statement lines with one bank account ledger entry. For example, this might be useful if your bank deposit contained several payment methods, such as credit cards from different issuers, and your bank lists those as separate lines. 
3. Choose the **Match Manually** action.

    The selected bank statement line and the selected bank account ledger entries change to green font, and the **Applied** check box in the right pane is selected.
4. Repeat steps 1 through 3 for all bank statement lines that are not matched.

> [!TIP]
> To remove a match, select the bank statement line, and then choose the **Remove Match** action. If you have matched multiple bank statement lines to a ledger entry, and need to remove one or more of the matched lines, all of the manual matches are removed for the ledger entry when you choose **Remove Match**. 

## To create missing ledger entries to match bank statement lines with

Sometimes a bank statement contain amounts for interest or fees charged. Such bank statement lines cannot be matched because no related ledger entries exist in [!INCLUDE[prod_short](includes/prod_short.md)]. You must then post a journal line for each transaction to create a related ledger entry that it can be matched with.

1. On the **Bank Acc. Reconciliation** page, choose the **Transfer to General Journal** action.  
2. On the **Trans. Bank Rec. to Gen. Jnl.** page, specify which general journal to use, and then choose the **OK** button.

    The **General Journal** page opens containing new journal lines for any banks statement lines with missing ledger entries.
3. Complete the journal line with relevant information, such as the balancing account. For more information, see [Working with General Journals](ui-work-general-journals.md).  
4. To review the result of posting before you post, choose the **Test Report** action. The **Bank Account Statement** report opens and shows the same fields as at the header of the **Bank Acc. Reconciliation** page.
5. Choose the **Post** action.

    When the entry is posted, proceed to match the bank statement line to it.
6. Refresh or reopen the **Bank Acc. Reconciliation** page. The new ledger entry will appear in the **Bank Account Ledger Entries** pane.
7. Match the bank statement line with the bank account ledger entry, either manually or automatically.

## Undo a bank account reconciliation
If you discover a mistake in a posted bank reconciliation, you can use the **Undo** action on the **Bank Acc. Statement** page to correct the mistake. When you undo a posted bank reconciliation, the entries will be moved to the **Bank Reconciliation** page and marked as **Open**, meaning they are not reconciled. You can then correct the bank reconciliation and post it again.

> [!NOTE]
> In the North American version, to use the Undo feature for posted bank reconciliations and bank statements you must turn on the **Bank Recon. with Auto-Match** toggle on the **General Ledger Setup** page. The Undo feature is not available for bank statements posted from bank reconciliation worksheets.

### Reusing the bank statement number
The bank statement number used for the new bank reconciliation is taken from the bank account as is the Balance Last Statement. You can change these values before you start a new bank reconciliation. However, when you create a new bank reconciliation, [!INCLUDE[d365fin](includes/d365fin_md.md)] checks whether the statement number is already assigned to a posted bank statement. If the number is in use, but you want the new bank statement to use it instead, you can use the **Change Statement No.** action on the **Bank Acct. Reconciliation** page.

### Examples
The following are a few examples of how to fix a mistake on a posted bank reconciliation with or without using the same statement number.

#### Example 1
You did bank reconciliations for January, February, and March. The bank statement number was 100 for March. Later, you discover that March only included entries until the 30th, which means entries for the 31st are missing. So, you need to redo the bank reconciliation for March. In this case, we'll open the **Bank Acc. Statement** page, choose the statement for March, and then choose **Undo**. 

The new bank reconciliation is given the statement number 101. To reassign the number 100, choose **Change Statement No.** and enter **100**. 

> [!TIP]
> Remember to set the appropriate Statement ending date (in this example, that is March 31), and edit the **Balance Last Statement** field. 

#### Example 2
You did bank reconciliations for January, February, June, and July. You discover that February was incorrect. Let's assume it had statement number 100. As in the Example 1, you use the Undo and Change Statement No. actions to change the statement number as in example #1 above and you can now redo February bank reconciliation.  

After you post the corrected bank reconciliation for February, on the corresponding Bank Account card, the **Last Statement No.** field will show **100**, and the **Balance Last Statement** field will show the ending balance for the February statement. 

If the next bank reconciliation you do is for March, [!INCLUDE[d365fin](includes/d365fin_md.md)] will assign 101 as the statement number and give it the correct **Balance Last Statement**.

If the next bank reconciliation you do is for August, consider changing the values in the **Last Statement No.** and **Balance Last Statement** fields on the **Bank Account** card before you create the next bank reconciliation, or use the Change Statement No. action and also change the value in the "Balance Last Statement" field on the bank reconciliation page.

> [!NOTE]
> The statement number is important when you do bank reconciliations with imported CAMT files that contain statement numbers, or when you reconcile based on printed bank statements. If you just download a range of bank transactions from your online bank, the statement number is usually not important. 
>
>The Balance Last Statement is kept on the bank account to minimize mistakes when doing bank reconciliations, but it's also editable, allowing you to do your bank reconciliations in any order you want. This also means that if you undo a bank statement, the new ending balance might not be the balance last statement on the next bank statement. There's no feature that allows you to move a balance forward to all subsequent bank statements, so be aware of this when using Undo. 

## See Related Training at [Microsoft Learn](/learn/modules/bank-reconciliation-dynamics-365-business-central/index)

## See Also

[Reconciling Bank Accounts](bank-manage-bank-accounts.md)  
[Applying Payments Automatically and Reconciling Bank Accounts](receivables-apply-payments-auto-reconcile-bank-accounts.md)  
[Setting Up Banking](bank-setup-banking.md)  
[Set Up Rules for Automatic Application of Payments](receivables-how-set-up-payment-application-rules.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]