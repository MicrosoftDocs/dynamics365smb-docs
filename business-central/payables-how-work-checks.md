---
title: Issue, Print, Cancel, and Void Checks| Microsoft Docs
description: Describes how to issue checks using the payment journal, print checks, and void or view check ledger entries in Business Central.  
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: payment journal, print check, vendor payment, creditor, debt, balance due, AP
ms.date: 04/01/2020
ms.author: sgroespe

---
# Make Check Payments
You can issue electronic and manual checks in [!INCLUDE[d365fin](includes/d365fin_md.md)]. Both methods use the payment journal to issue checks to vendors. You can also void checks and view check ledger entries.

The following procedure shows how to pay a vendor with a computer checks by applying the payment to the relevant vendor invoice, printing the check, and then posting the payment as paid. This results in positive vendor ledger entries, applied to negative bank ledger entries, and physical checks for processing in the bank.

You can pay with two types of checks. For both types, the **Bal. Account Type** or the **Account Type** field must contain **Bank Account**.

- **Computer Check**: Select this option if you want to print a check for the amount on the payment journal line. You must print the checks before you can post the journal lines.
- **Manual Check**: Select this option if you have created a check manually and want to create a corresponding check ledger entry for this amount. By using this option, you cannot print the check.

> [!NOTE]  
> To make sure that your bank only clears validated checks and amounts, you can send them a file that contains vendor, check, and payment information. For more information, see [Export a Positive Pay file](finance-how-positive-pay.md).

Your printer must be correctly set up with the check forms, and you must define which check layout to use. For more information, see [Select a Check Layout](finance-how-define-check-layouts.md)

You can print up to 10 invoices on a page for a check stub. If a check applies to more than 10 invoices, when you print the stub we void the check on the first page and print the word VOID on the check. We then print the remainder of the invoices and the total check amount on the second page.

## To pay a vendor invoice with a computer check
The following describes how to pay a vendor by check. The steps are similar to refund a customer by check.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Journals**, and then choose the related link.
2. Fill in the payment journal lines. For more information, see [Record Payments and Refunds](payables-how-post-payments-refunds.md).
3. In the **Payment Method Code** field, select **Check**.
4. In the **Bank Payment Type** field, select **Computer Check**.
5. Choose the **Print Check** action.
6. On the **Check** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
7. Choose the **Send to** button, select the **PDF Document** option, and then choose the **OK** button.

    The physical checks can now be brought to the bank for processing. Proceed to post the payment as applied to the vendor and thereby paid in the system.
8. Choose the **Post** action.

Fully applied vendor ledger entries and bank ledger entries are created.

> [!NOTE]  
> If you want to print and pay checks in more than one currency from different bank accounts, you must run the **Print Check** batch job separately for each currency and specify the appropriate bank account.

## To cancel printed checks that are not posted
You can cancel non-posted checks after they have been printed by using the **Void Check** action on the **Payment Journal** page.

1. On the **Payment Journal** page, choose the **Void Check**, and then choose which checks to cancel.

## To void checks
When check payment have been posted, you can only cancel (void) checks from the resulting bank ledger entries.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Bank Accounts**, and then choose the related link.
2. Select the relevant bank account, choose the **Edit** action, and then choose the **Check Ledger Entries** action.
3. On the **Check Ledger Entries** page, choose the **Void Check** action.
4. Select the **Void Check Only** check box.
5. Choose the **OK** button.

## To view a summary of posted checks
If you want to review posted checks, for example to verify multiple checks paid to one vendor, you can use the **Bank Account - Check Details** report.
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Bank Account - Check Details**, and then choose the related link.
2. Set filters as relevant, and then choose the **Preview** button.

## See Also
[Making Payments](payables-make-payments.md)  
[Managing Payables](payables-manage-payables.md)  
[Setting Up Banking](bank-setup-banking.md)  
[Export a Positive Pay file](finance-how-positive-pay.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
