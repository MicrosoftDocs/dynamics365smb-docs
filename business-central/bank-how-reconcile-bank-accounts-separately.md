---
title: Reconcile bank accounts
description: Learn how to reconcile transactions in Business Central with transactions in statements from your bank.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.date: 10/01/2024
ms.custom: bap-template
---

# Reconcile bank accounts

Bank reconciliation helps ensure that what's in your books matches the statements you receive from your bank. Bank account reconciliation compares and matches entries in the bank accounts you set up in [!INCLUDE[prod_short](includes/prod_short.md)] with bank transactions at your bank. Reconciliation can then post the balances to your bank accounts in [!INCLUDE[prod_short](includes/prod_short.md)] to make them available to finance managers. Bank reconciliation is also a practical way to discover missing payments and resolve bookkeeping errors.

This article describes how to reconcile bank accounts from the **Bank Acc. Reconciliation** page.

However, you can also reconcile bank accounts on the **Payment Reconciliation Journal** page when you process payments. Open bank account ledger entries related to the applied customer or vendor ledger entries close when you choose the **Post Payments and Reconcile Bank Account** action. This action automatically reconciles the bank account for the payments that you post with the journal. Learn more in [Applying Payments Automatically and Reconciling Bank Accounts](receivables-apply-payments-auto-reconcile-bank-accounts.md).

> [!NOTE]  
> The North American versions offers the **Bank Rec. Worksheet** page, which is better suited for checks and deposits but doesn't let you import bank statement files. To use this page instead of the **Bank Acc. Reconciliation** page, clear the **Bank Recon. with Auto. Match** field on the **General Ledger Setup** page. Learn more in [Reconciling Bank Accounts](LocalFunctionality/UnitedStates/how-to-reconcile-bank-accounts.md) under United States Local Functionality.

The lines on the **Bank Acc. Reconciliation** page are divided into two panes. The **Bank Statement Lines** pane shows either imported bank transactions or ledger entries with outstanding payments. The **Bank Account Ledger Entries** pane shows the ledger entries in the internal bank account.

## About bank reconciliation

Reconciling transactions in statements from your bank with bank entries in [!INCLUDE[prod_short](includes/prod_short.md)] is referred to as *matching*. There are three ways to match transactions with bank entries:

* Automatically, by using the **Match Automatically** action.
* Automatically, by using the **Reconcile with Copilot** action.

  This action is available as part of the bank reconciliation assist (preview) feature, which an AI-powered feature. Learn more in [Reconcile bank accounts with Copilot](bank-reconciliation-with-copilot.md).
* Manually, by selecting lines in both panes to link each bank statement line to one or more bank account ledger entries, and then using the **Match Manually** action.

The **Applied** checkbox is selected on lines where entries match. Learn more in [Set Up Rules for Automatic Application of Payments](receivables-how-set-up-payment-application-rules.md). If you enter a statement ending date on the bank reconciliation after you match its lines with entries, [!INCLUDE [prod_short](includes/prod_short.md)] will undo the matches for lines and entries that are after that date.

> [!NOTE]
> After you enter a date in the **Statement Date** field, the **Bank Acc. Reconciliation** page filters the bank ledger entries to show only entries up to that date. You can only post bank reconciliations with bank ledger entries on or before the statement ending date. The filter ensures that your bank ledger is balanced with your bank statement on the statement ending date, with the difference being the outstanding payments and checks.

When the value in the **Total Balance** field in the **Bank Statement Lines** pane equals the total value of the **Balance To Reconcile** field plus the **Balance Last Statement** field in the **Bank Account Ledger Entries** pane, you can choose the **Post** action. Unmatched bank account ledger entries remain on the page, indicating discrepancies that you should resolve to reconcile the bank account.

Any lines that can't be matched, indicated by a value in the **Difference** field, will remain on the **Bank Acc. Reconciliation** page after posting. They represent some kind of discrepancy that you must resolve before you can complete the bank account reconciliation. The following table describes a few typical business situations that can cause differences.

| Difference | Reason | Resolution |
|------------|--------|------------|
| A transaction in your bank account in [!INCLUDE[prod_short](includes/prod_short.md)] isn't in the bank statement. | The bank transaction wasn't created although a posting was made in [!INCLUDE[prod_short](includes/prod_short.md)]. | Create the missing transaction (or prompt a debitor to make it). Then reimport the bank statement file or enter the transaction manually. |
| A transaction on the bank statement doesn't exist as a document or journal line in [!INCLUDE[prod_short](includes/prod_short.md)]. | A bank transaction was made without a corresponding posting in [!INCLUDE[prod_short](includes/prod_short.md)], for example a journal line posting for an expense. | Create and post the missing entry. Learn more about a quick way in [To create missing ledger entries to match bank transactions with](bank-how-reconcile-bank-accounts-separately.md#to-create-missing-ledger-entries-to-match-bank-statement-lines). |
| A transaction in the internal bank account corresponds to a bank transaction but some information is too different to give a match. | Information, such as the amount or the customer name, was entered differently in the bank transaction or the internal posting. | Review the information, and then manually match the two. Optionally, correct the mismatch. |

You must resolve the differences. For example, create the missing entries and correct unmatched information until you can complete and post the bank account reconciliation.

You can fill in the **Bank Statement Lines** pane on the **Bank Acc. Reconciliation** page in the following ways:

* Automatically, by using the **Import Bank Statement** function to fill in the **Bank Statement Lines** pane with bank transactions according to an imported file or stream provided by the bank.
* Manually, by using the **Suggest Lines** function to fill in the **Bank Statement Lines** pane according to invoices in [!INCLUDE[prod_short](includes/prod_short.md)] that have outstanding payments.

## Add bank statement lines by importing a bank statement

The **Bank Statement Lines** pane shows bank transactions according to an imported file or stream provided by the bank.

To import bank statements as bank feeds, you must set up the Envestnet Yodlee Bank Feed service. The setup includes linking your bank accounts in [!INCLUDE[prod_short](includes/prod_short.md)] to the related online bank accounts. Learn more in [Set Up the Envestnet Yodlee Bank Feeds Service](bank-how-setup-bank-statement-service.md).  

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

The **Bank Statement Lines** pane is filled in according to invoices in [!INCLUDE[prod_short](includes/prod_short.md)] that have outstanding payments.  

1. On the **Bank Acc. Reconciliation** page, choose the **Suggest Lines** action.
2. In the **Starting Date** field, enter the earliest posting date for the ledger entries to be reconciled.
3. In the **Ending Date** field, enter the latest posting date for the ledger entries to be reconciled.

    > [!NOTE]
    > Typically, the ending date will match the date specified in the **Statement Date** field. However, if you want to reconcile transactions for only part of a period, you can enter a different ending date.

4. If you don't want the bank account ledger entries to include unmatched open reversed entries, choose the **Exclude Reversed Entries** toggle. By default, the list of bank account ledger entries include reversed entries up to the statement date.
5. Choose the **OK** button.

## Match bank statement lines with bank account ledger entries automatically

The **Bank Acc. Reconciliation** page offers automatic matching functionality based on a matching of text on a bank statement line (left pane) with text on one or more bank account ledger entries (right pane). You can overwrite the suggested automatic matching, and you can choose to not use automatic matching at all. Learn more in [Match bank statement lines with bank account ledger entries manually](#match-bank-statement-lines-with-bank-account-ledger-entries-manually).

You can investigate the basis for matches by using the **Match Details** action. For example, the details include the names of the fields that contained matching values.  

1. On the **Bank Acc. Reconciliation** page, choose the **Match Automatically**. The **Match Bank Entries** page opens.
2. In the **Transaction Date Tolerance (Days)** field, specify the span of days before and after the bank account ledger entry posting date within which the action searches for matching transaction dates in the bank statement.

    If you enter 0 or leave the field blank, the **Match Automatically** action only searches for matching transaction dates on the bank account ledger entry posting date.
3. Choose the **OK** button.

    The lines are color coded to make it easier to understand what to do with them. Bank statement lines and bank account ledger entries that are matched on the current bank reconciliation change to bold green font. Bank account ledger entries that are matched on other bank reconciliations are shown in italic blue font.
4. To remove a match, select the bank statement line, and then choose the **Remove Match** action.

> [!TIP]
> You can use a mix of manual and automatic matching. If you have manually matched entries, automatic matching will not overwrite your selections.

## Match bank statement lines with bank account ledger entries manually

> [!TIP]
> When matching lines and entries manually, the **Show All**, **Show Reversed Entries**, **Hide Reversed Entries**, and **Show Nonmatched** actions can make it easier to get an overview. By default, the bank account ledger entries don't include unmatched reversed entries. To include these entries in the list and match them manually, choose the **Show Reversed Entries** action. If you choose to hide reversed entries after you've made one or more matches, the matched entries are still shown.

> [!NOTE]
> You can't post a bank reconciliation if you do many-to-one matching and the combined amounts contain differences. This is true even if the combined differences balance to zero.
>
> Here's an example of a many-to-one matching that has differences. The value of 200 for bank statement entry 1 is matched to two bank ledger entries that have a total value of 180. The difference is 20. The value of 350 for bank statement 2 is matched to two other bank ledger entries that have a total value of 370. The difference is -20, which balances the value of 20 for bank statement 1.  
>
> To post a bank reconciliation with differences on the lines, post the differences and then match them against the posted entries.

1. On the **Bank Acc. Reconciliation** page, select an unapplied line in the **Bank Statement Lines** pane.
2. In the **Bank Account Ledger Entries** pane, select one or more banks account ledger entries that can be matched with the selected bank statement line. To choose multiple lines, select and hold the CTRL key, and then choose the lines.

   > [!TIP]
   > You can also manually match multiple bank statement lines with one bank account ledger entry. For example, this might be useful if your bank deposit contained several payment methods, such as credit cards from different issuers, and your bank lists those as separate lines.
3. Choose the **Match Manually** action.

    The selected bank statement line and the selected bank account ledger entries change to green font, and the **Applied** checkbox in the right pane is selected.
4. Repeat steps 1 through 3 for all bank statement lines that aren't matched.

> [!TIP]
> To remove a match, select the bank statement line, and then choose the **Remove Match** action. If you have matched multiple bank statement lines to a ledger entry, and need to remove one or more of the matched lines, all of the manual matches are removed for the ledger entry when you choose **Remove Match**.

## Validate your bank reconciliation

To double-check your bank account reconciliation before you post it, use the **Test Report** action to preview the reconciliation. The report is available in the following contexts:

* When you're preparing a bank reconciliation on the **Bank Acc. Reconciliation** page.
* When you're reconciling payments on the **Payment Reconciliation Journal** page.

Lines that can't be matched stay on the **Bank Acc. Reconciliation** page after posting. These lines contain a value in the **Difference** field. The difference represents a discrepancy that you must resolve before you can complete the bank account reconciliation. The following table describes a few typical business situations that can cause differences.

| Difference | Reason | Resolution |
|------------|--------|------------|
| A transaction in your bank account in [!INCLUDE[prod_short](includes/prod_short.md)] isn't in the bank statement. | The bank transaction wasn't created although a posting was made in [!INCLUDE[prod_short](includes/prod_short.md)]. | Create the missing transaction (or prompt a debitor to make it). Then reimport the bank statement file or enter the transaction manually. |
| A transaction on the bank statement doesn't exist as a document or journal line in [!INCLUDE[prod_short](includes/prod_short.md)]. | A bank transaction was made without a corresponding posting in [!INCLUDE[prod_short](includes/prod_short.md)], for example a journal line posting for an expense. | Create and post the missing entry. Learn more about a quick way in [To create missing ledger entries to match bank transactions with](bank-how-reconcile-bank-accounts-separately.md#to-create-missing-ledger-entries-to-match-bank-statement-lines). |
| A transaction in the internal bank account corresponds to a bank transaction but some information is too different to give a match. | Information, such as the amount or the customer name, was entered differently in the bank transaction or the internal posting. | Review the information, and then manually match the two. Optionally, correct the mismatch. |

You must resolve the differences. For example, create the missing entries and correct unmatched information until you can complete and post the bank account reconciliation.

> [!NOTE]
> The Bank Reconciliation page and Test Report assume you're only reconciling within the period up until the statement ending date. If you match a bank statement line to a bank ledger entry before you enter a statement ending date, and then enter a statement ending date that is after the ending date for the bank ledger entry, the data in the Test Report will be incorrect.

The following table describes fields on the Test Report that can help you complete the bank reconciliation.

|Field  |Description  |
|---------|---------|
|Statement Date| The date specified in the **Statement Date** field on the **Bank Acc. Reconciliation** page.|
|Balance Last Statement|The balance specified in the **Balance Last Statement** field on the **Bank Acc. Reconciliation** page. This field is filled in automatically from the most recent reconciliation for the same bank account. The value is zero if it's is your first bank account reconciliation.|
|Statement Ending Balance|The balance specified in the **Statement Ending Balance** field on the **Bank Acc. Reconciliation** page. |
|G/L Account No. <*number*> Balance at <*date*> | The balance on the G/L account on the statement ending date. This value is the unfiltered balance as of that date. If your bank uses your local currency, this balance should be the same as your bank account balance (shown on the right side of the report header) when you match all statement lines. An empty **()** in the name of this field means that your bank uses local currency.<br><br>A discrepancy in this field and the previous ones might indicate that you posted directly to the G/L account. It might also indicate that you're using the same G/L account for multiple banks, which we don't recommend. Banks are linked to the general ledger through the bank account posting group specified for the account.<br><br>The Test Report shows a warning if you have direct postings, even if the balance for the posting is zero. Direct postings that aren't balanced often lead to accumulated differences for future bank reconciliations. You should check the general ledger balance and ledger entries before you post the bank reconciliation. Learn more in about direct posting in [Avoid Direct Posting](#avoid-direct-posting).|
|G/L Account No. <*number*> Balance (<*LCY*>) at <*date*>| The balance on the G/L account on the statement ending date in local currency. The balance is converted to the bank account's currency using the exchange rate that was valid on the statement ending date. This value is the unfiltered balance as of that date. You compare to this balance to the **G/L Account No. <*number*> Balance at <*date*>* field if your bank uses a foreign currency. The value in the G/L Account No. <*number*> Balance at <*date*> field for local currency might differ slightly because currency conversion can result in small differences. Your bank's balance should be very close to this balance.  |
|Bank Account Balance at <*date*>| The balance on the bank account at the statement ending date.|
|Sum of Differences    | The sum of the differences for the statement lines. To access the details, turn on the **Print Outstanding Transactions** toggle when you enter criteria for the report. A difference is a bank statement line that isn't matched completely to one or more bank ledger entries. You can't post a bank account reconciliation that has differences. You can post a bank reconciliation that contains bank ledger entries that aren't matched to statement lines. This value is shown in the **Outstanding Bank Transactions** field and in a separate section if you turn on the Print Outstanding Transactions toggle.      |
|Statement Balance     | The value specified in the **Statement Ending Balance** field on the **Bank Acc. Reconciliation** page.  |
|Outstanding Bank Transactions     | The sum of unmatched, non-check bank ledger entries that have a posting date on or before the statement ending date. This happens when you register transactions before they're registered in your bank. For example, at the end of a period. When you create the next bank reconciliation, you can reconcile these entries.        |
|Outstanding Checks     | The sum of unmatched bank ledger entries for checks that have a posting date on or before the statement ending date. This happens when you register transactions before they're registered in your bank. For example, this can happen for checks if a vendor doesn't cash a check in the same period you registered it. When you create the next bank reconciliation, you can reconcile these entries.        |
|Bank Account Balance     | The sum of the values for the bank statement ending balance, outstanding bank transactions, and outstanding checks. After you handle all differences on matched entries, this balance matches your bank balance. For example, you accounted for all matched entries and the entries you couldn't match for this bank statement. You can post the reconciliation.        |

> [!TIP]
> If you run the **Test Report** from the **Payment Reconciliation Journal** page, [!INCLUDE [prod_short](includes/prod_short.md)] calculates the value in the **Statement Ending Balance** as follows:
>
> * balance last statement + sum of all lines in the payment reconciliation journal
>
> You can use the value to compare to your bank statement.

## To create missing ledger entries to match bank statement lines

Sometimes bank statement contains amounts for interest or fees charged. Such bank statement lines can't be matched because there aren't related ledger entries in [!INCLUDE[prod_short](includes/prod_short.md)]. You must then post a journal line for each transaction to create a related ledger entry that it can be matched with.

1. On the **Bank Acc. Reconciliation** page, choose the **Transfer to General Journal** action.  
2. On the **Trans. Bank Rec. to Gen. Jnl.** page, specify which general journal to use, and then choose the **OK** button.

    The **General Journals** page opens with new journal lines for any banks statement lines that are missing ledger entries.
3. Complete the journal line with information such as the balancing account. For more information, see [Work with General Journals](ui-work-general-journals.md).  
4. To review the result of posting before you post, choose the **Test Report** action, and then choose an option for accessing the report. The **Bank Account Statement** report shows the same fields as at the header of the **Bank Acc. Reconciliation** page.
5. Choose the **Post** action.

    After the entry is posted, match the bank statement line to it.
6. Refresh or reopen the **Bank Acc. Reconciliation** page. The new ledger entry appears in the **Bank Account Ledger Entries** pane.
7. Match the bank statement line with the bank account ledger entry, either manually or automatically.

## Find outstanding transactions in previous periods

You can use the Bank Statement report to find outstanding transactions in previous periods. Outstanding transactions were opened before the statement date and aren't closed, or were closed after the bank reconciliation was posted.

When you run the Bank Statement report from the **Bank Account Statement List** page, you can turn on the **Outstanding Entries** toggle, and the report includes a section that lists outstanding entries.

**Example**
We have bank account ledger entries A, B, and C in our bank account for the month of August. When we reconcile our bank account for August we find a bank statement line that matches entry A, but none for B and C. So we post the reconciliation with entry A reconciled and B and C as outstanding entries.

In September, we receive a payment for entry B and decide to reconcile our bank account. If we run the Bank Statement report before posting the reconciliation, we get one reconciled transaction and one outstanding.

If we print the report for August we get outstanding transactions for our B and C entries, even though we closed entry B in September.

> [!NOTE]
> The Bank Statement report has some known limitations if you import or manually enter bank transactions after you post a bank reconciliation.
>
> You can enter bank ledger entries on any date and with any posting date, so you don't always have to do it in a strict chronological order.. When you do a bank reconciliation, you reconcile a bank statement to the bank ledger entries you have registered up to the time you post the reconciliation, and with the posting date of the entries. Typically, that means a posting date on or before the statement ending date.
>
> When you post a bank reconciliation, [!INCLUDE [prod_short](includes/prod_short.md)] takes a snapshot of the data and uses it to fill in the bank statement report's header. But, the outstanding transactions sections are actual lookups to the bank ledger entries that existed up to the actual date and time you posted the bank reconciliation. The totals in the lines typically match the totals in the header. However, if you import bank ledger entries after you posted the bank reconciliation, but the posting dates are before the statement ending date, the totals in the header might not match the totals in the outstanding transactions sections.

## Undo a bank account reconciliation

If you find a mistake in a posted bank reconciliation, you can use the **Undo** action on the **Bank Account Statement List** page to correct it. When you undo a posted bank reconciliation, the entries are moved to the **Bank Account Reconciliations** page and marked as **Open**, meaning they aren't reconciled. You can then correct the bank reconciliation and post it again.

> [!NOTE]
> In the North American version, to use the Undo feature for posted bank reconciliations and bank statements you must turn on the **Bank Recon. with Auto-Match** toggle on the **General Ledger Setup** page. The Undo feature is not available for bank statements posted from bank reconciliation worksheets.

### Reusing the bank statement number

The bank statement number used for the new bank reconciliation is taken from the bank account as is the Balance Last Statement. You can change these values before you start a new bank reconciliation. However, when you create a new bank reconciliation, [!INCLUDE[d365fin](includes/d365fin_md.md)] checks whether the statement number is already assigned to a posted bank statement. If the number is in use, but you want the new bank statement to use it instead, you can use the **Change Statement No.** action on the **Bank Acc. Reconciliation** page.

### Examples

The following examples show how to fix a mistake on a posted bank reconciliation, with or without using the same statement number.

#### Example 1

You did bank reconciliations for January, February, and March. The bank statement number was 100 for March. Later, you discover that March only included entries until the 30th, which means entries for the 31st are missing. So, you need to redo the bank reconciliation for March. In this case, we open the **Bank Account Statement List** page, choose the statement for March, and then choose **Undo**.

The new bank reconciliation is given the statement number 101. To reassign the number 100, choose **Change Statement No.** and enter **100**. 

> [!TIP]
> Remember to set the appropriate Statement ending date (in this example, that is March 31), and edit the **Balance Last Statement** field. 

#### Example 2

You did bank reconciliations for January, February, June, and July. You discover that February was incorrect. Let's assume it had statement number 100. Like Example 1, you use the Undo and Change Statement No. actions to change the statement number as in example #1 and you can now redo February bank reconciliation.  

After you post the corrected bank reconciliation for February, on the corresponding Bank Account card the **Last Statement No.** field will show **100**, and the **Balance Last Statement** field will show the ending balance for the February statement. 

If the next bank reconciliation you do is for March, [!INCLUDE[d365fin](includes/d365fin_md.md)] will assign 101 as the statement number and give it the correct **Balance Last Statement**.

If the next bank reconciliation you do is for August, consider changing the values in the **Last Statement No.** and **Balance Last Statement** fields on the **Bank Account** card before you create the next bank reconciliation, or use the **Change Statement No.** action and also change the value in the **Balance Last Statement** field on the bank reconciliation page.

> [!NOTE]
> The statement number is important when you do bank reconciliations with imported CAMT files that contain statement numbers, or when you reconcile based on printed bank statements. If you just download a range of bank transactions from your online bank, the statement number is usually not important.  
>
> The Balance Last Statement is kept on the bank account to minimize mistakes when doing bank reconciliations, but it's also editable, allowing you to do your bank reconciliations in any order you want. This also means that if you undo a bank statement, the new ending balance might not be the balance last statement on the next bank statement. There's no feature that allows you to move a balance forward to all subsequent bank statements, so be aware of this when using Undo.  

## Avoid direct posting

Don't use a G/L account that allows direct posting in your bank account posting group. Direct posting breaks the connection between the bank account ledger entry and the G/L account ledger entry. When you reconcile your bank account, the entries posted directly to the G/L account aren't included, which makes it difficult to complete the reconciliation.

This mistake often happens when entering an opening balance for a bank account. It's important that you don't post the opening balance directly to the general ledger. Entries in the G/L account that are posted directly to the G/L account causes problems. For example, these entries might prevent you from reconciling your bank account. For foreign currency bank accounts, the entries can cause differences to accumulate after you post more bank reconciliations due to currency exchange rate adjustments. Often, you post the opening bank balance directly to the bank account, and the amount then ends up in the G/L account. Alternatively, you reverse it later against the G/L account that you use to balance the opening general ledger balance. In both cases, you must balance any direct posting to the G/L account before you start your first bank reconciliation, and especially so if the bank account is in a foreign currency.

## Related information

[Reconciling Bank Accounts](bank-manage-bank-accounts.md)  
[Reconcile bank accounts using bank reconciliation assist (preview)](bank-reconciliation-with-copilot.md)  
[Applying Payments Automatically and Reconciling Bank Accounts](receivables-apply-payments-auto-reconcile-bank-accounts.md)  
[Setting Up Banking](bank-setup-banking.md)  
[Set Up Rules for Automatic Application of Payments](receivables-how-set-up-payment-application-rules.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
