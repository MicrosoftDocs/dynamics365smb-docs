---
title: Create bank deposits
description: You can make deposits to maintain a transaction record that contains information that can be applied to outstanding invoices and credit memos.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.search.keywords: bank, deposit
ms.search.form: 10140, 10141, 10143, 10144, 10146, 10147, 10148, 36646, 1690_Primary
ms.date: 09/27/2024
ms.custom: bap-template    
---

# Create bank deposits

> [!NOTE]
> The ability to create bank deposits is new in [!INCLUDE [prod_short](includes/prod_short.md)] 2022 release wave 1 for a lot of country/region versions. If you were using [!INCLUDE [prod_short](includes/prod_short.md)] in the United States, Canada, or Mexico before that release, you might be using the earlier capabilities. You can continue, but the new capabilities will replace the old ones in a future release. To start using the new features described in this article, your administrator can go to the **Feature Management** page and turn on **Feature Update: Standardized bank reconciliation and deposits**.  

Use the **Bank Deposits** page to register deposits as a single document that posts one or more entries to a bank account. Typically, bank deposits are used to register cash deposits. The Bank Deposits page is available on the **Cash Management** menu on the Business Manager Role Center, and other Role Centers that deal with cash management.

Amounts on bank deposits can come from several sources:

* Sales, using a G/L account for revenue.
* Customers payments.
* Cash refunds from vendors, or cash payments to them. 

Bank deposit lines contain information about individual deposits, such as checks from customers. The total of the amounts on the lines must add up to the total amount of the deposit.

After you fill in the deposit information and lines, you must post it. Posting updates the relevant ledgers, including the general ledger, and the bank, customer, and vendor ledgers. Posted deposits are stored for future reference on the **Posted Bank Deposits** page.

The **Bank Deposit** report displays customer and vendor deposits with the original deposit amount, the amount of the deposit that remains open, and the amount applied. The report also shows the total posted deposit amount to reconcile.

## Before you start

There are a few things to set up before you can use bank deposits. You must have a number series and general journal template ready. You should also specify whether to post bank deposit amounts as a lump sum. That is, as a total of all the amounts on the deposit lines. Otherwise, each line is posted as an individual entry. Posting a deposit as a single bank ledger entry can make it easier to do bank reconciliation.

### Number series and lump sum deposits

You must set up a number series for bank deposits, and then specify the series in the **Bank Deposit Nos.** field on the **Sales & Receivables Setup** page. To learn more about number series, go to [Create Number Series](ui-create-number-series.md).

Also on the **Sales & Receivables Setup** page, to post deposits as lump sums rather than individual lines, turn on the **Post Bank Deposits as Lump Sum** toggle. Posting a deposit as a lump sum creates one bank ledger entry for the full amount of the deposit, which can make it easier to do bank reconciliation.

### General journal templates for bank deposits

You must also create a general journal template for deposits. You use general journals to post entries to bank, customer, vendor, fixed asset, and general ledger accounts. The journal templates design the general journal to suit the purpose of your work. That is, the fields on the journal template are exactly the ones you need.

The deposits are cash receipts, so you might want to reuse your number series for cash receipt journals. Alternatively, if you need to distinguish between bank deposit and cash receipt journal entries, use a different number series.

You also need to create a batch job for the template. To create a batch job, on the **General Journal Templates** page, choose the **Batches** action. To learn more about batches, go to [Using Journal Templates and Batches](ui-work-general-journals.md#use-journal-templates-and-batches).

## Dimensions on bank deposit lines

The lines on the bank deposit use the default dimensions you specified in the **Department Code** and **Customer group Code** fields. When you choose **Customer** or **Vendor** in the **Account Type** field, the dimensions for the customer or vendor replace the defaults. You can change the dimensions on the lines, if needed.

> [!TIP]
> Dimension on lines are set according to Default Dimension Priorities. Line dimensions prioritized over header dimensions. To avoid conflicts, you can create rules that prioritize when to use a dimension depending on the source. If you want to change how dimensions are prioritized, you can change their rankings on the **Default Dimension Priorities** page. For more information, see [To set up default dimension priorities](finance-dimensions.md#to-set-up-default-dimension-priorities).

## Create a bank deposit

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Bank Deposits**, and then choose the related link.
2. Choose **New** to open the **Bank Deposit** page.
3. Choose the general journal template that you created for bank deposits.  

    > [!NOTE]
    > If the general journal template has more than one batch, you'll be prompted to choose one.

4. In the **Bank Account No.** field, choose the bank account in which to make the deposit.

    > [!TIP]
    > You can double-check that you're depositing to the correct account by using the **Account Card** and **Account Ledger Entries** actions to look up the ledger entries for the selected bank account. For example, to check whether similar deposits were made to the account.

5. In the **Total Deposit Amount** field, enter the total amount of the deposit. This total must be the sum of the amounts on all lines.
6. Fill in the remaining fields as necessary. [!INCLUDE [tooltip-inline-tip_md](../archive/SetupAndAdministration/includes/tooltip-inline-tip_md.md)]

    The date in the **Posting Date** field and the dimensions in the **Department Code** and **Customergroup Code** fields are assigned to the lines that you create for the bank deposit. You can change them if needed.

7. Depending on whether you want to post the bank deposit as lump sum or each line individually to the bank ledger, turn the **Post as Lump Sum** toggle on or off. The default setting comes from the same toggle on the **Sales & Receivables Setup** page.

    > [!NOTE]
    > The **Currency Code** field shows the currency that is specified for the bank account you chose. You cannot choose a different currency.

8. On the **Lines** FastTab, create a new line for each cash payment that you want to deposit.
9. In the **Account Type** field, specify where the payment originated. For bank deposits, the type is typically **Customer** or **Vendor**.

    > [!NOTE]
    > You can also register a cash payment to a vendor. To do that, choose **Vendor** and then enter the payment amount as a negative number in the **Credit Amount** field on the line.

10. In the **Document No.** field, enter the document number of the invoice from which the credit amount originated. You can use a document number for each line, or the same number for all lines.

    > [!TIP]
    > Typically, you don't need to fill in the **Document Type** field for financial entries. For example, if you're depositing cash from a day's sale you leave the field blank. If you're depositing cash from a customer payment, you choose **Payment**.

11. If you're depositing a cash payment for a specific customer invoice, choose the **Apply Entries** action, and then enter the invoice number in the **Applies-to ID** field.
12. If you're ready to post the bank deposit, choose the **Post** action.

    > [!NOTE]
    > If the bank account has default dimensions where the **Value Posting** field contains **Code Mandatory**, **Same Code**, or **No Code**, you must post the deposit as a lump sum. If you don't post as a lump sum, posting might fail because the dimension values of the accounts on the bank deposit lines violate the value posting rules of the bank account.

    > [!TIP]
    > Before you post the deposit, you can use the **Test Report** action to review your data. The report shows whether there are any issues, such as missing data, that might prevent posting.  

## Apply multiple checks for multiple invoices for a customer in a lump sum deposit

You can post lump sum deposits from multiple checks on deposit lines for customer ledger entries. 

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Bank Deposits**, and then choose the related link.
2. Create or choose a line for the customer, and in the **External Document No.** field, enter the check number.
3. Choose **Apply Entries**.
4. On the **Apply Customer Entries** page, for each document you want to apply the check to, in the **Applies-to ID** field, enter the check number.
5. In the **Amount to apply** field, enter the amount on the check.

   > [!NOTE]
   > When you enter the amount to apply, the **Applies-to ID** field might reset to the bank deposit document number. Double-check the field, and if it reset, reenter the check number.  

6. Choose **OK**.
7. Repeat steps two through six for each check.

   > [!TIP]
   > Before you post the bank deposit, it's a good idea to use the **Test Report** action to validate the applications.

## Find posted bank deposits

The **Posted Bank Deposits** page lists your company's previous deposits. In the list, you can review the comments and dimensions that were specified for the deposits. You can open the bank deposit to view more details, and from there you can investigate further. For example, you can choose the **Find entries** action to view the posted bank ledger entries. From the bank ledger entry, you can find its corresponding posted general ledger entry.

If you want to look up all general ledger entries for the posted deposit lines, go to the **G/L Register** page and use the **General Ledger** action. The action shows all of the general ledger entries, including the entries for customers and vendors.

## Reverse a posted bank deposit

There are a couple of ways to reverse a posted bank deposit:

* On the **Posted Bank Deposits** page, choose the deposit, and then choose the **Undo Posting** action.
* On the **G/L Registers** page, find the register for the deposit, and then choose the **Reverse Register** action.

> [!NOTE]
> You can only reverse a register that contains a single type of entry. That is, the register must contain only customer entries or vendor entries, but not both. If a register contains both you must manually reverse the deposit.

## Related information

[Finance](finance.md)  
[Setting Up Finance](finance.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]



