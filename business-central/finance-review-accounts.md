---
title: Review general ledger accounts 
description: You can track your progress when you review amounts in general ledger accounts.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.date: 08/06/2024
ms.custom: bap-template
ms.search.form: 20, 22207,
ms.service: dynamics-365-business-central
---

# Review amounts in general ledger accounts

You might have general ledger accounts that you frequently keep an eye on. Or you might want to speed up the review process at the end of the month. For help with keeping track of what you've done, and to speed up reviews, use the **Review Entries** action on the **Chart of Accounts** or the **G/L Account Card** page for each account. 

## Set up accounts for reviews

On the **G/L Account Card** page for each account, specify how to allow reviews in the **Review Policy** field.

|Review Policy  |Description  |
|---------|---------|
|None     | You can't mark entries for the account as reviewed. For example, use this option for accounts such as payables, receivables, and bank accounts where there are other ways to review their amounts.        |
|Allow Review     | You don't have to include entries in a review, and the amounts of the debit and credit entries don't have to balance. You remove a review, for example, if you've made a mistake.        |
|Allow Review and Match Balance     | The total amounts of the debit and credit entries in the review must match. The **Debit** and **Credit** fields show those amounts, and the **Balance** field shows the total. This setting also lets you remove a review. When you remove a review from one or more entries, the debit and credit entries must still balance.        |

## Mark entries as reviewed

Choose the entries you've reviewed, and then use the **Set selected as reviewed** action. Each time you mark one or more entries as reviewed the entries are given the same number in the **Reviewed Identifier** column. The review identifier is a handy way to keep track of the entries that were reviewed at the same time. [!INCLUDE [prod_short](includes/prod_short.md)] also records the user who did the review, and when they did it.

If you mark entries as reviewed, but regret doing so, use the **Set selected as not reviewed** action.

* If the Review allowed policy is assigned to the account, the action resets the reviewed identifier to 0 and removes the person and date and time of the review. 
* If the Review allowed and match balance policy is assigned, the credit and debit must still balance. For example, if one of the entries in a review is a mistake, you can choose another entry with the correct value. The replacement entry doesn't have to have the same reviewed identifier.

> [!TIP]
> A fast way to choose multiple entries is to hold down Ctrl or Shift while you choose the entries. *Ctrl* lets you selects specific entries, and *Shift* selects all entries between the first and last entries you select.

## Review accounts that have old entries

You might have entries from past periods that you've already reviewed or just don't need a review. You just want to start reviewing entries from, for example, the beginning of the year or accounting period. You can leave the entries as is. However, if you want to analyze data in Excel or by using Analysis Mode, mark the entries as reviewed. To learn more about analyzing entries, go to [Analyze entries](#analyze-entries). To mark the entries as reviewed, add a filter on the Filter pane to display only those entries, and then choose the **Mark selected entries as reviewed** action.

## Filter entries

To get a clearer picture, there are several ways to filter entries on the **Review G/L Entries** page.

* Use the **Show Reviewed Entries** and **Hide Reviewed Entries** actions to show only the entries you have or haven't reviewed. To clear the filters, use the **Show all entries** action.
* Use the Filter pane. For example, you might filter by account number or, if you have older entries and want to mark them all as reviewed, by a posting date.

## Analyze entries

There are a couple of ways to analyze the general ledger entries you've reviewed.

* Turn on Analysis Mode, for example, to group entries according to their reviewed identifier. To learn more about Analysis Mode, go to [Analyze List Page Data Using Analysis Mode](analysis-mode.md).
* Export the entries to Excel.

## See also

[Understand the General Ledger and Chart of Accounts](finance-general-ledger.md)    
[Set Up or Change the Chart of Accounts](finance-setup-chart-accounts.md)    
