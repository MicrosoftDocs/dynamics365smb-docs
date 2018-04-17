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
ms.date: 04/17/2018
ms.author: sgroespe

---
# Make Check Payments
You can issue electronic and manual checks in [!INCLUDE[d365fin](includes/d365fin_md.md)]. Both methods use the payment journal to issue checks to vendors. You can also void checks and view check ledger entries.

The following procedure shows how to pay a vendor with a computer checks by applying the payment to the relevant vendor invoice, printing the check, and then posting the payment as paid. This results in positive vendor ledger entries, applied to negative bank ledger entries, and physical checks for processing in the bank.

You can pay with two types of checks. For both types, the **Bal. Account Type** or the **Account Type** field must contain **Bank Account**.

- **Computer Check**: Select this option if you want to print a check for the amount on the payment journal line. You must print the checks before you can post the journal lines. You can only select **Computer Check** if
- **Manual Check**: Select this option if you have created a check manually and want to create a corresponding check ledger entry for this amount. By using this option, you cannot print the check.

> [!NOTE]  
> To make sure that your bank only clears validated checks and amounts, you can send them a file that contains vendor, check, and payment information. For more information, see [Export a Positive Pay file](finance-how-positive-pay.md).

Your printer must be correctly set up with the check forms, and you must define which check layout to use. For more information, see [Define Check Layouts](finance-how-define-check-layouts.md)

## To pay a vendor invoice with a computer check
You can have payment lines filled in automatically by using the **Suggest Vendor Payments** function. Alternatively, if you know who to pay, you can fill in the **Vendor No.** and **Applies-to Doc No.** fields manually.  

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Payment Journals**, and then choose the related link.
2. Fill in the journal with the relevant payment or payments, for example by using the **Suggest Vendor Payments** function. All applies-to information is then also entered on the payment lines. For more information, see [Suggest Vendor Payments](payables-how-suggest-vendor-payments.md).
3. Alternatively, if you know who to pay, in the **Account No.** field, select the vendor in question.
4. In the **Payment Method Code** field, select CHECK.
5. For manual entry, choose the **Applies-to Doc No.** field, and then, in the **Apply Vendor Entries** window, select the relevant invoice, and then choose the **OK** button.

    Many fields, such as the **Amount** field, are now filled in with information from the selected invoice.
6. In the **Bank Payment Type** field, select **Computer Check**.
7. Choose **Print Check** action.
8. In the **Check** window, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
9. Choose the **Send to** button, select the **PDF Document** option, and then choose the **OK** button.

    The physical checks can now be brought to the bank for processing. Proceed to post the payment as applied to the vendor and thereby paid in the system.
10. Choose the **Post** action.

Fully applied vendor ledger entries and bank ledger entries are created.

    > [!NOTE]  
>   If you want to print and pay checks in more than one currency from different bank accounts, you must run the **Print Check** batch job separately for each currency and specify the appropriate bank account.

## To cancel printed checks that are not posted
You can cancel non-posted checks after they have been printed by using the **Void Check** action in the **Payment Journal** window.

1. In the **Payment Journal** window, choose the **Void Check**, and then choose which checks to cancel.

## To void checks
When check payment have been posted, you can only cancel (void) checks from the resulting bank ledger entries.

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Bank Accounts**, and then choose the related link.
2. Select the relevant bank account, choose the **Edit** action, and then choose the **Check Ledger Entries** action.
3. In the **Check Ledger Entries** window, choose the **Void Check** action.
4. Select the **Void Check Only** check box.
5. Choose the **OK** button.

## To view a summary of posted checks
If you want to review posted checks, for example to verify multiple checks paid to one vendor, you can use the **Bank Account - Cheque Details** report.
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Bank Account - Cheque Details**, and then choose the related link.
2. Set filters as relevant, and then choose the **Preview** button.

## See Also
[Managing Payables](payables-manage-payables.md)  
[Setting Up Banking](bank-setup-banking.md)  
[Export a Positive Pay file](finance-how-positive-pay.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
