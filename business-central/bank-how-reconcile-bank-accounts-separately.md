---
title: Reconcile Bank Accounts Separately| Microsoft Docs
description: Describes how your inventory value is reconciled with the general ledger.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: bank account balance, bank statement
ms.date: 06/02/2017
ms.author: sgroespe

---
# Reconcile Bank Accounts Separately
To reconcile bank accounts in [!INCLUDE[d365fin](includes/d365fin_md.md)] with statements received from the bank, you must fill in the lines in the **Bank Acc. Reconciliation** window.

> [!NOTE]  
>   You can also reconcile bank accounts in the **Payment Reconciliation Journal** window. Any open bank account ledger entries related to the applied customer or vendor ledger entries will be closed when you choose the **Post Payments and Reconcile Bank Account** action. This means that the bank account is automatically reconciled for payments that you post with the journal. For more information, see [Reconcile Payments Using Automatic Application](receivables-how-reconcile-payments-auto-application.md).

To enable import of bank statements as bank feeds, you must first set up and enable the Envestnet Yodlee Bank Feed service, and then link your bank accounts to the related online bank accounts. For more information, see [Set Up the Envestnet Yodlee Bank Feeds Service](bank-how-setup-bank-statement-service.md).

The lines in the **Bank Acc. Reconciliation** window are divided into two panes. The **Bank Statement Lines** pane shows either imported bank transactions or ledger entries with outstanding payments. The **Bank Account Ledger Entries** pane shows the ledger entries in the bank account.

The activity of finding and applying entries to be reconciled is referred to as *matching*. You can choose to perform matching automatically by using the **Match Automatically** function. Alternatively, you can manually select lines in both panes to link each bank statement line to one or more related bank account ledger entries, and then use the **Match Manually** function. The **Applied** checkbox is selected on lines where entries match.

You can fill in the **Bank Statement Lines** pane in the **Bank Acc. Reconciliation** window in the following ways:

* Automatically, by using the **Import Bank Statement** function to fill in the lines according to actual bank statements based on a file provided by the bank.
* Manually, by using the **Suggest Lines** function to fill in the lines with ledger entries for invoices that have outstanding payments.

When the value in the **Total Balance** field in the **Bank Statement Lines** pane equals the value in the **Balance To Reconcile** field in the **Bank Account Ledger Entries** pane, you can choose the **Post** action to reconcile the applied bank account ledger entries. Any non-applied bank account ledger entries will remain in the window, indicating that payments processed for the bank account are not reflected in the latest bank statement, or that some payments were received on checks.

> [!NOTE]  
>   If bank statement lines relate to check ledger entries, then you cannot use the matching functions. Instead, you must choose the **Apply Entries** action, and then select the relevant check ledger entry to match the bank statement line with.

## To fill bank reconciliation lines by importing a bank statement
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Bank Account Reconciliation**, and then choose the related link.
2. Choose the **New** action.
3. In the **Bank Account No.** field, select the relevant bank account. The bank account ledger entries that exist on the bank account appear in the **Bank Account Ledger Entries** pane.
4. In the **Statement Date** field, enter the date of the statement from the bank.
5. In the **Statement Ending Balance** field, enter the balance of the statement from the bank.
6. If you have a bank statement file, choose the **Import Bank Statement** action.
7. Locate the file, and then choose the **Open** button to import the bank transactions into the lines of the **Bank Acc. Reconciliation** window.

## To fill bank reconciliation lines with the Suggest Lines function
1. In the **Bank Acc. Reconciliation** window, choose the **Suggest Lines** action.
2. In the **Starting Date** field, enter the earliest posting date for the ledger entries to be reconciled.
3. In the **Ending Date** field, enter the latest posting date for the ledger entries to be reconciled.
4. Select the **Include Checks** check box to any suggest check ledger entries instead of the corresponding bank account ledger entries.
5. Choose the **OK** button.

## To match bank statement lines with bank account ledger entries automatically
1. In the **Bank Acc. Reconciliation** window, choose the **Match Automatically**. **The Match Bank Entries** window opens.
2. In the **Transaction Date Tolerance (Days)** field, specify the span of days before and after the bank account ledger entry posting date within which the function will search for matching transaction dates in the bank statement.

    If you enter 0 or leave the field blank, then the **Match Automatically** function will only search for matching transaction dates on the bank account ledger entry posting date.
3. Choose the **OK** button.

    All bank statement lines and bank account ledger entries that can be matched change to green font, and the **Applied** check box is selected.
4. To remove a match, select the bank statement line, and then choose the **Remove Match** action.

## To match bank statement lines with bank account ledger entries manually
1. In the **Bank Acc. Reconciliation** window, select a non-applied line in the **Bank Statement Lines** pane.
2. In the **Bank Account Ledger Entries** pane, select one or more banks account ledger entries that can be matched with the selected bank statement line. To choose multiple lines, press and hold the Ctrl key.
3. Choose the **Match Manually** action.

    The selected bank statement line and the selected bank account ledger entries change to green font, and the **Applied** check box in the right pane is selected.
4. Repeat steps 1 through 3 for all bank statement lines that are not matched.
5. To remove a match, select the bank statement line, and then choose the **Remove Match** action.

## To create missing ledger entries to match bank transactions with
Sometimes a bank statement contain amounts for interest or fees charged. Such bank transactions cannot be matched because no related ledger entries exist in [!INCLUDE[d365fin](includes/d365fin_md.md)]. You must then post a journal line for each transaction to create a related ledger entry that it can be matched with.

1. In the **Bank Acc. Reconciliation** window, choose the **Transfer to General Journal** action.  
2. In the **Trans. Bank Rec. to Gen. Jnl.** window, specify which general journal to use, and then choose the **OK** button.

    The **General Journal** window opens containing new journal lines for any banks statement lines with missing ledger entries.
3. Complete the journal line with relevant information, such as the balancing account. For more information, see [Working with General Journals](ui-work-general-journals.md).  
4. Choose the **Post** action.

    When the entry is posted, proceed to match the bank transaction with to it.
5. Refresh or reopen the **Bank Acc. Reconciliation** window. The new ledger entry will appear in the **Bank Account Ledger Entries** pane.
6. Match the bank statement line with the bank account ledger entry, either manually or automatically.

## See Also
[Managing Bank Accounts](bank-manage-bank-accounts.md)  
[Setting Up Banking](bank-setup-banking.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
