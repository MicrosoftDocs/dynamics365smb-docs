---
title: Issue, print, cancel, and void checks
description: Describes how to issue checks using the payment journal, print checks, and void or view check ledger entries in Business Central.  
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: payment journal, print check, vendor payment, creditor, debt, balance due, AP
ms.search.form: 256, 404, 
ms.date: 07/17/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Make check payments

You can issue electronic and manual checks in [!INCLUDE[prod_short](includes/prod_short.md)]. Both methods use the payment journal to issue checks to vendors. You can also void checks and view check ledger entries.

The following procedure shows how to pay a vendor with a computer checks by:

- Applying the payment to the relevant vendor invoice.
- Printing the check.
- Posting the payment as paid.

These steps result in positive vendor ledger entries that are applied to negative bank ledger entries, and physical checks for processing in the bank.

You can pay with two types of checks. For both types, the **Bal. Account Type** or the **Account Type** field must contain **Bank Account**.

- **Computer Check**: Select this option if you want to print a check for the amount on the payment journal line. You must print the checks before you can post the journal lines.
- **Manual Check**: Select this option if you have created a check manually and want to create a corresponding check ledger entry for this amount. By using this option, you can't print the check.

> [!NOTE]  
> To make sure that your bank only clears validated checks and amounts, you can send them a file that contains vendor, check, and payment information. To learn more, go to [Export a Positive Pay file](finance-how-positive-pay.md).

> [!IMPORTANT]
> Your printer must be correctly set up with the check forms, and you must define which check layout to use. To learn more, go to [Select a Check Layout](finance-how-define-check-layouts.md). Alternatively, you can send the check as a PDF file, for example.  

You can print up to 10 invoices on a page for a check stub. If a check applies to more than 10 invoices, when you print the stub we void the check on the first page and print the word VOID on the check. We then print the remainder of the invoices and the total check amount on the second page.

## To pay a vendor invoice with a check

The following describes how to pay a vendor by check. The steps are similar to refund a customer by check.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Payment Journals**, and then choose the related link.
2. Fill in the payment journal lines. To learn more, go to [Record Payments and Refunds](payables-how-post-payments-refunds.md).
3. In the **Payment Method Code** field, select **Check**.
4. Choose the **Print Check** action.
5. On the **Check** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
6. If your printer is set up to print checks, choose the **Print** button. Otherwise, choose the **Send to** button, select the **PDF Document** option, choose the **OK** button, and then print the PDF document.

    You can now send the physical checks to the vendors.
7. Choose the **Post** action.

    The payment is applied to the vendor and paid. Fully applied vendor ledger entries and bank ledger entries are created.

> [!NOTE]  
> If you want to print and pay checks in more than one currency from different bank accounts, you must run the **Print Check** batch job separately for each currency and specify the appropriate bank account.

## To cancel printed checks that aren't posted

You can cancel non-posted checks after they have been printed by using the **Void Check** action on the **Payment Journal** page.

1. On the **Payment Journal** page, choose the **Void Check**, and then choose which checks to cancel.

## To void checks

After you post a check payment, you can only cancel (void) a check from the resulting bank ledger entries.

> [!IMPORTANT]
> If the check is applied to an invoice, unapply the payment first so that the invoice can be repaid. To learn more, go to [To unapply an application of vendor entries](payables-how-apply-purchase-transactions-manually.md#to-unapply-an-application-of-vendor-entries). The steps are the same for customers. After you unapply the payment, void the check. If the check was printed but didn't pay an invoice, then choose **Void Check Only** as described in this section.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Bank Accounts**, and then choose the related link.
2. Select the relevant bank account, and then choose the **Check Ledger Entries** action.
3. On the **Check Ledger Entries** page, choose the **Void Check** action.
4. Select the **Void Check Only** checkbox.
5. Choose the **OK** button.

## To view a summary of posted checks

If you want to review posted checks, for example to verify multiple checks paid to one vendor, you can use the **Bank Account - Check Details** report.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Bank Account - Check Details**, and then choose the related link.
2. Set filters as relevant, and then choose the **Preview** button.

## Related information

[Making Payments](payables-make-payments.md)  
[Managing Payables](payables-manage-payables.md)  
[Setting Up Banking](bank-setup-banking.md)  
[Export a Positive Pay file](finance-how-positive-pay.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
