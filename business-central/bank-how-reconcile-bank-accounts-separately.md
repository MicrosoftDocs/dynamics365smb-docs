---

title: Reconcile Bank Accounts
description: Learn how to reconcile transactions in Business Central with transactions in statements from your bank.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.date: 12/13/2022
ms.custom: bap-template

---
# Reconcile Bank Accounts

Bank reconciliation helps ensure that what's in your books matches the statements you receive from your bank. Bank account reconciliation compares and matches entries in the bank accounts you've set up in [!INCLUDE[prod_short](includes/prod_short.md)] with bank transactions at your bank. Reconciliation can then post the balances to your bank accounts in [!INCLUDE[prod_short](includes/prod_short.md)] to make them available to finance managers. Bank reconciliation is also a practical way to discover and resolve missing payments and bookkeeping errors.

This article describes how to reconcile bank accounts from the **Bank Acc. Reconciliation** page.

However, you can also reconcile bank accounts on the **Payment Reconciliation Journal** page when you process payments. Open bank account ledger entries related to the applied customer or vendor ledger entries will be closed when you choose the **Post Payments and Reconcile Bank Account** action. This automatically reconciles the bank account for the payments that you post with the journal. For more information, see [Applying Payments Automatically and Reconciling Bank Accounts](receivables-apply-payments-auto-reconcile-bank-accounts.md).

> [!NOTE]  
> The North American versions offers the **Bank Rec. Worksheet** page, which is better suited for checks and deposits but doesn't let you import bank statement files. To use this page instead of the **Bank Acc. Reconciliation** page, clear the **Bank Recon. with Auto. Match** field on the **General Ledger Setup** page. For more information, see [Reconciling Bank Accounts](LocalFunctionality/UnitedStates/how-to-reconcile-bank-accounts.md) under United States Local Functionality.

The lines on the **Bank Acc. Reconciliation** page are divided into two panes. The **Bank Statement Lines** pane shows either imported bank transactions or ledger entries with outstanding payments. The **Bank Account Ledger Entries** pane shows the ledger entries in the internal bank account.

Reconciling transactions in statements from your bank with bank entries in [!INCLUDE[prod_short](includes/prod_short.md)] is referred to as *matching*. There are two ways to match transactions with bank entries:

* Automatically, by using the **Match Automatically** action.
* Manually, by selecting lines in both panes to link each bank statement line to one or more bank account ledger entries, and then using the **Match Manually** action.

The **Applied** checkbox is selected on lines where entries match. For more information, see [Set Up Rules for Automatic Application of Payments](receivables-how-set-up-payment-application-rules.md). If you enter a statement ending date on the bank reconciliation after you match its lines with entries, [!INCLUDE [prod_short](includes/prod_short.md)] will undo the the matches for lines and entries that are after that date.

> [!NOTE]
> After you enter a date in the Statement Ending Date field, the Bank Acc. Reconciliation page filters the bank ledger entries to show only entries up to that date. You can only post bank reconciliations with bank ledger entries on or before the statement ending date. The filter ensures that your bank ledger is balanced with your bank statement on the statement ending date, with the difference being the outstanding payments and checks.

When the value in the **Total Balance** field in the **Bank Statement Lines** pane equals the total value of the **Balance To Reconcile** field plus the **Balance Last Statement** field in the **Bank Account Ledger Entries** pane, you can choose the **Post** action. Unmatched bank account ledger entries remain on the page, indicating discrepancies that you should resolve to reconcile the bank account.

To double-check your bank account reconciliation before you post it, use the **Test Report** action to prepare a preview of the reconciliation. The report is available in the following contexts:

* When you're preparing a bank reconciliation on the **Bank Acc. Reconciliation** page.
* When you're reconciling payments on the **Payment Reconciliation Journals** page.

Any lines that cannot be matched, indicated by a value in the **Difference** field, will remain on the **Bank Acc. Reconciliation** page after posting. They represent some kind of discrepancy that you must resolve before you can complete the bank account reconciliation. The following table describes a few typical business situations that can cause differences.

| Difference | Reason | Resolution |
|------------|--------|------------|
| A transaction in your bank account in [!INCLUDE[prod_short](includes/prod_short.md)] isn't in the bank statement. | The bank transaction wasn't created although a posting was made in [!INCLUDE[prod_short](includes/prod_short.md)]. | Create the missing transaction (or prompt a debitor to make it). Then reimport the bank statement file or enter the transaction manually. |
| A transaction on the bank statement doesn't exist as a document or journal line in [!INCLUDE[prod_short](includes/prod_short.md)]. | A bank transaction was made without a corresponding posting in [!INCLUDE[prod_short](includes/prod_short.md)], for example a journal line posting for an expense. | Create and post the missing entry. To learn a quick way to do that, see [To create missing ledger entries to match bank transactions with](bank-how-reconcile-bank-accounts-separately.md#to-create-missing-ledger-entries-to-match-bank-statement-lines). |
| A transaction in the internal bank account corresponds to a bank transaction but some information is too different to give a match. | Information, such as the amount or the customer name, was entered differently in the bank transaction or the internal posting. | Review the information, and then manually match the two. Optionally, correct the mismatch. |

You must resolve the differences, for example, by creating the missing entries and correcting non-matching information or by making missing money transactions, until you can complete and post the bank account reconciliation.

You can fill in the **Bank Statement Lines** pane on the **Bank Acc. Reconciliation** page in the following ways:

* Automatically, by using the **Import Bank Statement** function to fill in the **Bank Statement Lines** pane with bank transactions according to an imported file or stream provided by the bank.
* Manually, by using the **Suggest Lines** function to fill in the **Bank Statement Lines** pane according to invoices in [!INCLUDE[prod_short](includes/prod_short.md)] that have outstanding payments.

## To add bank statement lines by importing a bank statement

The **Bank Statement Lines** pane will be filled with bank transactions according to an imported file or stream provided by the bank.

To import bank statements as bank feeds, you must set up the Envestnet Yodlee Bank Feed service. The setup includes linking your bank accounts in [!INCLUDE[prod_short](includes/prod_short.md)] to the related online bank accounts. For more information, see [Set Up the Envestnet Yodlee Bank Feeds Service](bank-how-setup-bank-statement-service.md).  

> [!TIP]
> You can also import bank statement files in comma or semicolon delimited format (.CSV). Use the **Set up a bank statement file format** assisted setup to define bank statement import formats and attach the format to a bank account. You can then use these formats when you import bank statements in the **Bank Account Reconciliation** page.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Bank Account Reconciliation**, and then choose the related link.
2. Choose the **New** action.
3. In the **Bank Account No.** field, select the relevant bank account. The bank account ledger entries that exist on the bank account appear in the **Bank Account Ledger Entries** pane.
4. In the **Statement Date** field, enter the date of the statement from the bank.
5. In the **Statement Ending Balance** field, enter the balance of the statement from the bank.
6. If you have a bank statement file, choose the **Import Bank Statement** action.
7. Locate the file, and then choose the **Open** button to import the bank transactions into the **Bank Statement Lines** pane on the **Bank Acc. Reconciliation** page.

## To fill in bank reconciliation lines with the Suggest Lines action

The **Bank Statement Lines** pane will be filled according to invoices in [!INCLUDE[prod_short](includes/prod_short.md)] that have outstanding payments.  

1. On the **Bank Acc. Reconciliation** page, choose the **Suggest Lines** action.
2. In the **Starting Date** field, enter the earliest posting date for the ledger entries to be reconciled.
3. In the **Ending Date** field, enter the latest posting date for the ledger entries to be reconciled.

    > [!NOTE]
    > Typically, the ending date will match the date specified in the **Statement Date** field. However, if you want to reconcile transactions for only part of a period, you can enter a different ending date.

4. If you don't want the bank account ledger entries to include unmatched open reversed entries, choose the **Exclude Reversed Entries** toggle. By default, the list of bank account ledger entries will include reversed entries up to the statement date.
5. Choose the **OK** button.

## To match bank statement lines with bank account ledger entries automatically

The **Bank Acc. Reconciliation** page offers automatic matching functionality based on a matching of text on a bank statement line (left pane) with text on one or more bank account ledger entries (right pane). You can overwrite the suggested automatic matching, and you can choose to not use automatic matching at all. For more information, see [To match bank statement lines with bank account ledger entries manually](bank-how-reconcile-bank-accounts-separately.md#to-match-bank-statement-lines-with-bank-account-ledger-entries-manually).

You can investigate the basis for matches by using the **Match Details** action. For example, the details will include the names of the fields that contained matching values.  

1. On the **Bank Acc. Reconciliation** page, choose the **Match Automatically**. The **Match Bank Entries** page opens.
2. In the **Transaction Date Tolerance (Days)** field, specify the span of days before and after the bank account ledger entry posting date within which the action will search for matching transaction dates in the bank statement.

    If you enter 0 or leave the field blank, the **Match Automatically** action will only search for matching transaction dates on the bank account ledger entry posting date.
3. Choose the **OK** button.

    The lines are color coded to make it easier to understand what to do with them. All bank statement lines and bank account ledger entries that can be matched change to green font, and the **Applied** checkbox is selected. Bank account ledger entries that are already matched on other bank reconciliations are shown in blue font.
4. To remove a match, select the bank statement line, and then choose the **Remove Match** action.

> [!TIP]
> You can use a mix of manual and automatic matching. If you have manually matched entries, automatic matching will not overwrite your selections.

## To match bank statement lines with bank account ledger entries manually

> [!TIP]
> When matching lines and entries manually, the **Show All**, **Show Reversed Entries**, **Hide Reversed Entries**, and **Show Nonmatched** actions can make it easier to get an overview. By default, the bank account ledger entries don't include unmatched reversed entries. To include these entries in the list and match them manually, choose the **Show Reversed Entries** action. If you choose to hide reversed entries after you've made one or more matches, the matched entries are still shown.

1. On the **Bank Acc. Reconciliation** page, select a non-applied line in the **Bank Statement Lines** pane.
2. In the **Bank Account Ledger Entries** pane, select one or more banks account ledger entries that can be matched with the selected bank statement line. To choose multiple lines, select and hold the <kbd>CTRL</kbd> key and then choose the lines.

   > [!TIP]
   > You can also manually match multiple bank statement lines with one bank account ledger entry. For example, this might be useful if your bank deposit contained several payment methods, such as credit cards from different issuers, and your bank lists those as separate lines.
3. Choose the **Match Manually** action.

    The selected bank statement line and the selected bank account ledger entries change to green font, and the **Applied** checkbox in the right pane is selected.
4. Repeat steps 1 through 3 for all bank statement lines that aren't matched.

> [!TIP]
> To remove a match, select the bank statement line, and then choose the **Remove Match** action. If you have matched multiple bank statement lines to a ledger entry, and need to remove one or more of the matched lines, all of the manual matches are removed for the ledger entry when you choose **Remove Match**.

## To create missing ledger entries to match bank statement lines

Sometimes bank statement contains amounts for interest or fees charged. Such bank statement lines can't be matched because there aren't related ledger entries in [!INCLUDE[prod_short](includes/prod_short.md)]. You must then post a journal line for each transaction to create a related ledger entry that it can be matched with.

1. On the **Bank Acc. Reconciliation** page, choose the **Transfer to General Journal** action.  
2. On the **Trans. Bank Rec. to Gen. Jnl.** page, specify which general journal to use, and then choose the **OK** button.

    The **General Journal** page opens containing new journal lines for any banks statement lines with missing ledger entries.
3. Complete the journal line with relevant information, such as the balancing account. For more information, see [Work with General Journals](ui-work-general-journals.md).  
4. To review the result of posting before you post, choose the **Test Report** action. The **Bank Account Statement** report opens and shows the same fields as at the header of the **Bank Acc. Reconciliation** page.
5. Choose the **Post** action.

    After the entry is posted, match the bank statement line to it.
6. Refresh or reopen the **Bank Acc. Reconciliation** page. The new ledger entry will appear in the **Bank Account Ledger Entries** pane.
7. Match the bank statement line with the bank account ledger entry, either manually or automatically.

## Find outstanding transactions in previous periods

You can use the Bank Statement report to find outstanding transactions in previous periods. Outstanding transactions were opened before the statement date and haven't been closed, or were closed after the bank reconciliation was posted.

When you run the Bank Statement report from the Bank Statement List page, you can turn on the **Outstanding Entries** toggle, and the report will include a section that lists outstanding entries.

**Example**
We have bank account ledger entries A, B, and C in our bank account for the month of August. When we reconcile our bank account for August we find a bank statement line that matches entry A, but none for B and C. So we post the reconciliation with entry A reconciled and B and C as outstanding entries.

In September, we receive a payment for entry B and decide to reconcile our bank account. If we run the Bank Statement report before posting the reconciliation, we'll have one reconciled transaction and one outstanding.

If we print the report for August we'll have outstanding transactions for our B and C entries, even though we closed entry B in September.

## Undo a bank account reconciliation

If you find a mistake in a posted bank reconciliation, you can use the **Undo** action on the **Bank Account Statement List** page to correct it. When you undo a posted bank reconciliation, the entries are moved to the **Bank Reconciliation** page and marked as **Open**, meaning they aren't reconciled. You can then correct the bank reconciliation and post it again.

> [!NOTE]
> In the North American version, to use the Undo feature for posted bank reconciliations and bank statements you must turn on the **Bank Recon. with Auto-Match** toggle on the **General Ledger Setup** page. The Undo feature is not available for bank statements posted from bank reconciliation worksheets.

### Reusing the bank statement number

The bank statement number used for the new bank reconciliation is taken from the bank account as is the Balance Last Statement. You can change these values before you start a new bank reconciliation. However, when you create a new bank reconciliation, [!INCLUDE[d365fin](includes/d365fin_md.md)] checks whether the statement number is already assigned to a posted bank statement. If the number is in use, but you want the new bank statement to use it instead, you can use the **Change Statement No.** action on the **Bank Acc. Reconciliation** page.

### Examples

The following examples show how to fix a mistake on a posted bank reconciliation, with or without using the same statement number.

#### Example 1

You did bank reconciliations for January, February, and March. The bank statement number was 100 for March. Later, you discover that March only included entries until the 30th, which means entries for the 31st are missing. So, you need to redo the bank reconciliation for March. In this case, we'll open the **Bank Acc. Statement** page, choose the statement for March, and then choose **Undo**. 

The new bank reconciliation is given the statement number 101. To reassign the number 100, choose **Change Statement No.** and enter **100**. 

> [!TIP]
> Remember to set the appropriate Statement ending date (in this example, that is March 31), and edit the **Balance Last Statement** field. 

#### Example 2

You did bank reconciliations for January, February, June, and July. You discover that February was incorrect. Let's assume it had statement number 100. Like Example 1, you use the Undo and Change Statement No. actions to change the statement number as in example #1 above and you can now redo February bank reconciliation.  

After you post the corrected bank reconciliation for February, on the corresponding Bank Account card the **Last Statement No.** field will show **100**, and the **Balance Last Statement** field will show the ending balance for the February statement. 

If the next bank reconciliation you do is for March, [!INCLUDE[d365fin](includes/d365fin_md.md)] will assign 101 as the statement number and give it the correct **Balance Last Statement**.

If the next bank reconciliation you do is for August, consider changing the values in the **Last Statement No.** and **Balance Last Statement** fields on the **Bank Account** card before you create the next bank reconciliation, or use the **Change Statement No.** action and also change the value in the **Balance Last Statement** field on the bank reconciliation page.

> [!NOTE]
> The statement number is important when you do bank reconciliations with imported CAMT files that contain statement numbers, or when you reconcile based on printed bank statements. If you just download a range of bank transactions from your online bank, the statement number is usually not important.  
>
> The Balance Last Statement is kept on the bank account to minimize mistakes when doing bank reconciliations, but it's also editable, allowing you to do your bank reconciliations in any order you want. This also means that if you undo a bank statement, the new ending balance might not be the balance last statement on the next bank statement. There's no feature that allows you to move a balance forward to all subsequent bank statements, so be aware of this when using Undo.  

## Avoid Direct Posting

Don't use a G/L account that allows direct posting in your bank account posting group. Direct posting will break the connection between the bank account ledger entry and the G/L account ledger entry. When you reconcile your bank account, the entries posted directly to the G/L account won't be included and it will be difficult to complete the reconciliation.

This mistake often happens when entering an opening balance for a bank account. It's important that you don't post the opening balance directly to the general ledger. Entries in the G/L account that are posted directly to the G/L account will cause problems. For example, these entries might prevent you from reconciling your bank account. For foreign currency bank accounts, the entries can cause differences to accumulate after you post more bank reconciliations due to currency exchange rate adjustments. Often, you post the opening bank balance directly to the bank account, and the amount then ends up in the G/L account. Alternatively, you reverse it later against the G/L account that you use to balance the opening general ledger balance. In both cases, you must balance any direct posting to the G/L account before you start your first bank reconciliation, and especially so if the bank account is in a foreign currency.

## See related [Microsoft training](/training/modules/bank-reconciliation-dynamics-365-business-central/index)

## See Also
[Reconciling Bank Accounts](bank-manage-bank-accounts.md)  
[Applying Payments Automatically and Reconciling Bank Accounts](receivables-apply-payments-auto-reconcile-bank-accounts.md)  
[Setting Up Banking](bank-setup-banking.md)  
[Set Up Rules for Automatic Application of Payments](receivables-how-set-up-payment-application-rules.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
