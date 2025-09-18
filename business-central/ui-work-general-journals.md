---
title: Working with general journals to post directly to G/L
description: Learn about using journals to post financial transactions to general ledger accounts and other accounts, such as bank and vendor accounts.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.date: 02/06/2025
ms.custom: bap-template
ms.search.keywords: journals, recurring, accrual, renumber, bulk-post
ms.search.form: 39, 101, 102, 182, 184, 185, 201, 207, 250, 251, 253, 255, 256, 261, 262, 283, 519, 750, 751, 752, 753, 754, 755, 12409, 12410, 12411, 1290, 10101, 11400, 11402, 11403, 11405, 11300, 2000000, 2000001, 2000003, 2000020, 2000021, 2000022
---
# Work with general journals

Most financial transactions are posted to the general ledger through documents such as purchase invoices and sales orders. However by posting journal lines, you can also process business activities such as:

* Purchasing
* Payments
* Using recurring journals to post accruals
* Refunding employee expenses

Most journals are based on the general journal, and you can process all transactions on the **General Journals** page. Learn more at [Post Transactions Directly to the General Ledger](finance-how-post-transactions-directly.md).  

For example, you can use post employee expenses for reimbursement. Learn more at [Record and Reimburse Employees' Expenses](finance-how-record-reimburse-employee-expenses.md).

However, [!INCLUDE [prod_short](includes/prod_short.md)] also offers journals that are optimized for specific types of transactions, such as the *Payment Journal* for registering payments. Learn more at [Record Payments and Refunds in the Payment Journal](payables-how-post-payments-refunds.md).  

You use general journals to post financial transactions to general ledger accounts and various other accounts. The other accounts include bank, customer, vendor, and employee accounts. Posting with a general journal creates entries on general ledger accounts even when, for example, you post a journal line to a customer account. The entry is posted to a general ledger receivables account through a posting group.

The information that you enter in a journal is temporary and can be changed while it's in the journal. When you post the journal, the information is transferred to entries on individual accounts, where it can't be changed. You can, however, unapply posted entries, and you can post reversing or correcting entries. Learn more at [Reverse Journal Postings and Undo Receipts/Shipments](finance-how-reverse-journal-posting.md).

> [!NOTE]
> [!INCLUDE[journal-showhide-columns-inline-tip](includes/journal-showhide-columns-inline-tip.md)]  

## Add context to general journal transactions

When you create a journal, you can add links that give context to its transactions. When you post the journal, [!INCLUDE [prod_short](includes/prod_short.md)] copies the links to the posted journal and ledger entries the journal creates. For example, providing links can make life easier for your auditor. If you keep images of your expense receipts on your company's Sharepoint site, you can add links to the files. When you post the journal to submit your expenses, your auditor can quickly get to the receipt files.

## Use journal templates and batches

There are several general journal templates. Each journal template is represented by a dedicated page with particular functions and the fields that are required to support those functions, such as the **Payment Reconciliation Journals** page to process bank payments and the **Payment Journals** page to pay your vendors or reimburse your employees. Learn more at [Make Payments](payables-make-payments.md) and [Reconcile Customer Payments with the Cash Receipt Journal or from Customer Ledger Entries](receivables-how-apply-sales-transactions-manually.md).

For each journal template, you can set up your own personal journal as a journal batch. For example, you can define your own journal batch for the payment journal that has your personal layout and settings. The following tip is an example of how to personalize a journal.

> [!TIP]  
> If you select the **Suggest Balancing Amount** checkbox on the line for your batch on the **General Journal Batches** page, then the **Amount** field on, for example, general journal lines for the same document number is automatically prefilled with the value that is required to balance the document. Learn more at [Letting [!INCLUDE[prod_short](includes/prod_short.md)] Suggest Values](ui-let-system-suggest-values.md).

> [!TIP]
> You can add or remove fields in journals by personalizing them. Learn more at [Personalize Your Workspace](ui-personalization-user.md).

### Validating general journal batches

You can turn on a background check that helps prevent delays when posting. The check notifies you when a mistake in the financial journal you're working on will prevent you from posting the journal. On the **General Journal Batches** page, you can choose **Background Error Check** to have [!INCLUDE[prod_short](includes/prod_short.md)] validate finance journals, such as general or payment journals, while you're working on them.

When you enable the validation, the **Check Document** or **Journal Check** FactBoxes show issues in the current line and the whole batch. Validation happens when you load a finance journal batch, and when you choose another journal line. The **Issues total** tile in the FactBox shows the total number of issues that [!INCLUDE[prod_short](includes/prod_short.md)] found, and you can choose it to open an overview of the issues.

You can use the **Show Lines with Issues** and **Show All Lines** actions to toggle between journal lines that do or don't have issues. The **Journal Line Details** FactBox provides quick overview and access to data from journal lines, such as the G/L account, customer, or vendor, and the posting setup for specific accounts.

[!INCLUDE [background_doc_journal_check](includes/background_doc_journal_check.md)]  

## Understanding main accounts and balancing accounts

If you set up default balancing accounts for the journal batches on the **General Journals** page, the balancing account is filled in automatically when you fill in the **Account No.** field. Otherwise, fill in both the **Account No.** and **Bal. Account No.** fields manually. A positive amount in the **Amount** field is debited to the main account and credited to the balancing account. A negative amount is credited to the main account and debited to the balancing account.

> [!NOTE]  
> VAT is calculated separately for the main account and the balancing account, so they can use different VAT percentage rates.

## Work with recurring journals

A recurring journal is a general journal with specific fields for managing transactions that you often post with few, if any, changes. For example, transactions for expenses such as rent, subscriptions, electricity, and heat. Using recurring journals lets you post fixed and variable amounts, and specify automatic reversal entries for the day after the posting date. Allocation keys let you divide the recurring entries among various accounts. Learn more at [Allocating Recurring Journal Amounts to Several Accounts](#allocating-recurring-journal-amounts-to-several-accounts).

With a recurring journal, you create the entries that you post regularly only one time. For example, the accounts, dimensions, dimension values, and so on, stay in the journal after posting. If changes are needed, you can make them each time you post.

### Recurring Method field

The **Recurring Method** field is important. It determines how to treat the amount on the journal line after posting. For example, if you use the same amount every time you post the line, you can let the amount remain. If you'll use the same accounts and text on the line, but the amount varies every time you post, you can delete the amount after posting.

| To | See |
| --- | --- |
|F Fixed|The amount on the journal line remains after posting. Lines with amounts of zero remain in the journal, but aren't posted. You can update the amount in a later run.  |
|V Variable|The amount on the journal line is deleted after posting.|
|B Balance|The posted amount on the account on the line is allocated among the accounts specified for the line in the Gen. Jnl. Allocation table. The balance on the account is set to zero. Remember to fill in the **Allocation %** field on the **Allocations** page. For more information, see [Allocating Recurring Journal Amounts to Several Accounts](#allocating-recurring-journal-amounts-to-several-accounts).|
|RF Reversing Fixed|The amount on the journal line remains after posting, and a balancing entry is posted on the next day.|
|RV Reversing Variable|The amount on the journal line is deleted after posting, and a balancing entry is posted on the next day.|
|RB Reversing Balance|The posted amount on the account on the line is allocated among the accounts specified for the line on the **Allocations** page. The balance on the account is set to zero, and a balancing entry is posted on the next day.|
|BD Balance by Dimension|The journal line allocates costs based on a G/L account's balance by dimension. You're prompted to set the dimension filters to be used to calculate the source G/L account's balance by dimension from which you want to allocate costs. As an alternative, choose the **Set Dimension Filters** action later.|
|RBD Reversing Balance by Dimension|The journal line allocates costs based on a G/L account's reversing balance by dimension. You're prompted to set the dimension filters to use to calculate the source G/L account's balance by dimension from which you want to allocate costs. You can also choose the **Set Dimension Filters** action later.|

> [!NOTE]  
> The VAT fields can be filled in on either the recurring journal line or on the allocation journal line but not on both. That is, they can be filled in on the **Allocations** page only if the corresponding lines in the recurring journal are not filled in.

### Recurring Frequency field

This date formula field determines how often to post the entry on the journal line, and it must be filled in. Learn more at [Use Date Formulas](ui-enter-date-ranges.md#use-date-formulas).

#### Examples

If the journal line must be posted every month, enter **1M**. After every posting, the date in the **Posting Date** field will be updated to the same date in the next month.

If you want to post an entry on the last day of every month, you can take one of the following actions:

* Post the first entry on the last day of a month by entering 1D+1M-1D (1 day + 1 month - 1 day). With this formula, the posting date is calculated correctly regardless of how many days there are in the month.

* Post the first entry on any day of the month by entering 1M+CM. With this formula, the posting date will be after one full month + the remaining days of the current month.

### Expiration Date field

This field determines the date on which the line is posted for the last time. The line won't be posted after this date.

The advantage of using the Expiration Date field is that the line isn't deleted from the journal immediately. You can enter a later date so that you can use the line in the future.

If the field is blank, the line is posted every time until you delete it from the journal.

### Allocating recurring journal amounts to several accounts

On the **Recurring General Journals** page, you can choose the **Allocations** action to specify how to allocate amounts on the recurring journal line to several accounts and dimensions. Allocation acts as balancing account line for the recurring journal line.

Like a recurring journal, you enter an allocation one time and it stays in the allocation journal after posting. You don't need to enter amounts and allocations every time you post the recurring journal line.

> [!NOTE]
> You can't use allocation accounts in journal batches that have an approval workflow for creating journal lines.

If the recurring method in the recurring journal is set to **Balance** or **Reversing Balance**, dimension value codes in the recurring journal are disregarded when the account is set to zero. If you allocate a recurring line to dimension values on the **Allocations** page, only one reversing entry is created.

> [!NOTE]
> If you allocate a recurring journal line that contains a dimension value code, don't enter the same code on the **Allocations** page. If you do, the dimension values will be incorrect.  

To allocate recurring journal amounts based on dimensions, set the **Recurring Method** field to **Balance by Dimension** or **Reversing Balance by Dimension**. If the recurring method in the recurring journal is set to **Balance by Dimension** or **Reversing Balance by Dimension**, dimension value codes in the recurring journal are considered when the account is set to zero. If you allocate a recurring line to dimension values on the **Allocations** page, reversing entries are created that match the number of dimension value combinations that the balance is comprised of. If you allocate account balance through a recurring journal that contains a dimension value code, remember to use **Balance by Dimension** or **Reversing Balance by Dimension** to ensure that the dimension values are correctly balanced or reversed from the source account.  

For example, your company has a couple of business units and a handful of departments that your controllers set up as dimensions. To speed up the purchase invoice entry process, you decide to require the accounts payable clerks to enter only business unit dimensions. Since each business unit has specific allocation keys for the Department dimension, such as based on the number of employees, you can use the **BD Balance by Dimension** or **RBD Reversing Balance by Dimension** recurring methods to reallocate expenses for each business unit to the right departments based on the allocation keys.  

> [!NOTE]
> Dimensions that you set on allocation lines are not automatically calculated, and you must specify which dimension values must be set on the allocation accounts. In case you want to preserve the link between the source account dimension and the allocation account dimension, we recommend that you use the [Cost Accounting](finance-about-cost-accounting.md) capabilities instead.

#### Example: Allocating Rent Payments to Different Departments

You pay rent monthly, so you enter the amount on the cash account on a recurring journal line. On the **Allocations** page, you can use the Department dimension to divide the expense among several departments. For example, according to the number of square feet that each department occupies. The calculation is based on the allocation percentage on each line. You can allocate in different ways:

* Enter different accounts on different allocation lines to divide rental expense among several accounts.
* Enter the same account but use different dimension value codes for the Department dimension on each line.

[!INCLUDE [rev-general-journal](includes/rev-general-journal.md)]

### Calculate the reversal date

When using recurring general journals to post accruals at the end of a period, it's important to have full control over reversal entries. On the **Recurring General Journals** page, the **Reversal Date Calculation** field lets you control the date that reversal entries are posted when reversal recurring methods are used.

#### Example

Accruals are typically posted with **Fixed**, **Variable**, or **Balance** recurring methods on the journal line. The posting date of the posted amount on the account on journal line is calculated using the recurring frequency. The posting date for the balancing entry is calculated using the **Reversal Date Calculation** field, as follows:

* If the field is blank, the balancing entry will be posted the next day.
* If the field contains a date formula (for example, **5D** for five days), the balancing entry is posted with a posting date calculated using the reversal date calculation.

> [!NOTE]
> By default, the **Reversal Date Calculation** field is not available on the **Recurring General Journals** page. To use the field, you must add it by personalizing the page. For more information, see [Personalize Your Workspace](ui-personalization-user.md).

## Work with standard journals

When you create journal lines that you know you're likely to create again later, you can save them as a standard journal before you post the journal. The same applies for item journals and general journals.

> [!NOTE]
> Standard journals might not contain all of the fields you want to include in the resulting ledger entries. For example, if you're using a standard general journal to register a payment, the ledger entries won't contain the Payment Method Code field.

> [!NOTE]  
> The following procedures refer to the item journal, but the information also applies to the general journal.

### To save a standard journal

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Item Journals**, and then choose the related link.
2. Enter one or more journal lines.
3. Select the journal lines that you want to reuse.
4. Choose the **Save as Standard Journal** action.
5. In the **Save as Standard Item Journal** request page, define a new or existing standard item journal that the lines should be saved in.

    If you have one or more standard item journals, and you want to replace one of them with the new set of item journal lines, in the **Code** field, select the item journal.
6. Choose **OK** to verify that you want to replace the content of the existing standard item journal.
7. To save the values in the **Unit Amount** field of the standard item journal, choose the **Save Unit Amount** field.
8. To save the values in the **Quantity** field, choose the **Save Quantity** field.
9. Choose **OK** to save the standard item journal.

When you save the standard item journal, the Item Journal page displays so you can post it.

### To reuse a standard journal

> [!NOTE]
> Standard journals don't always have the same fields as general journals. When you use the Get Standard Journals action to copy the fields to the general journal, the general journal might have less information than if you created it manually. 

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Item Journals**, and then choose the related link.
2. Choose the **Get Standard Journals** action.
3. To review a standard item journal before you select it for reuse, choose the **Show Journal** action.

    Changes you make in a standard item journal are implemented right away, and they'll be there next time you open or reuse the standard item journal. Be sure that the change is important enough to generally apply. Otherwise, make the specific change in the item journal after the standard item journal lines are added. See step 4.
4. On the **Standard Item Journals** page, select the standard item journal to reuse, and then choose **OK**.

    The item journal contains the lines you saved. If the item journal already has lines, the new lines appear after them.

    If you didn't turn on the **Save Unit Amount** toggle when you saved the journal, the **Unit Amount** field on lines added from the standard journal contain the value from the **Unit Cost** field on the item card.

    > [!NOTE]  
    > If you turned on the **Save Unit Amount** or **Save Quantity** toggles when you saved the journal, make sure the new values are correct before you post the item journal.
    >
    > If the inserted item journal lines contain saved unit amounts that you don't want to post, you can adjust it to the current value of the item.

5. Select the item journal lines you want to adjust, and then choose the **Recalculate Unit Amount** action. This action updates the Unit Amount field with the current unit cost of the item.
6. Choose the **Post** action.

## To renumber document numbers in journals

To avoid posting errors caused by the document number, you can use the **Renumber Document Numbers** action before you post a journal.

In all journals that are based on the general journal, the **Document No.** field is editable so that you can specify different document numbers for different journal lines or the same document number for related journal lines.

If the **No. Series** field on the journal batch is filled, then the posting function in general journals requires that the document number on individual or grouped journal lines be in sequential order. Just choose the **Renumber Document Numbers** action, and relevant **Document No.** fields are then updated. If related journal lines are grouped by document number before you used the function, they remain grouped, but might be assigned a different document number.  

This function also works on filtered views.

Renumbering document numbers respects related applications, such as a payment application made from the document on the journal line to a vendor account. Accordingly, the **Applies-to ID** and **Applies-to Doc. No.** fields are updated on the ledger entries.

### To renumber documents in journals

The following procedure is based on the **General Journals** page, but applies to all other journals that are based on the general journal, such as the **Payment Journals** page.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **General Journals**, and then choose the related link.
2. When you're ready to post the journal, choose the **Renumber Document Numbers** action.

Values in the **Document No.** field are changed, where required, so that the document number on individual or grouped journal lines are in sequential order. After documents are renumbered, you can post the journal.

## Related information

[Post Transactions Directly to the General Ledger](finance-how-post-transactions-directly.md)  
[Reverse Journal Postings and Undo Receipts/Shipments](finance-how-reverse-journal-posting.md)  
[Allocate Costs and Income](year-allocate-costs-income.md)  
[Finance](finance.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Close Open Item Ledger Entries Resulting from Fixed Application in the Item Journal](finance-how-to-close-open-item-ledger-entries-resulting-from-fixed-application-in-the-item-journal.md)  
[Revalue Inventory in the Revaluation Journal](inventory-how-revalue-inventory.md)  
[Count, Adjust, and Reclassify Inventory Using Journals](inventory-how-count-adjust-reclassify.md)  
[Reconcile Customer Payments with the Cash Receipt Journal or from Customer Ledger Entries](receivables-how-apply-sales-transactions-manually.md)  
[Reconcile Vendor Payments with the Payment Journal or from Vendor Ledger Entries](payables-how-apply-purchase-transactions-manually.md)  
[Work with Intercompany Documents and Journals](intercompany-how-work-documents-journals.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
