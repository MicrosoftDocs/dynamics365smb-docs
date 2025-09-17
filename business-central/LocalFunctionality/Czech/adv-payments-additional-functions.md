---
title: Advance Payment Additional Features (Corrections)  
description: This section explains the Advance Payment Additional Features (Corrections) in the Czech localization extension.  
author: v-pejano
ms.reviewer: v-pejano  
ms.author: v-pejano  
ms.service: dynamics-365-business-central  
ms.topic: concept-article  
ms.search.keywords: Czech, Advance Payments, Localization  
ms.date: 09/17/2025  
ms.custom: bap-template
---

# Additional Features (Corrections)

In addition to core functionality such as creating, paying, and applying advances, the Advance Payments application also provides several supplementary features to simplify work with advance documents. These additional features let you do things like:

- Reverse an advance VAT document.
- Unlink an incorrect payment from an advance.
- Add a payment to an advance retrospectively.
- Unapply an advance from a posted invoice.
- Add an advance to a posted invoice.

## Reverse an Advance VAT document

Use this function when you need to reverse a VAT document you mistakenly posted for a purchase advance payment.

To reverse an advance VAT document:

1. Choose the ![Light bulb icon that opens the Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Advance Letters**, and then choose the related link.
2. In the list, locate the paid purchase advance letter with a posted VAT document. Use the **Advance Letter Entries** function.
3. In the list of purchase advance letter entries, choose the line with **Entry Type – VAT Payment**.  

   ![Purchase Advance Invoice Entries](Media/adv-payments-additional-function-cancel.png)
4. Choose the **Post Credit Memo VAT** action.
5. A page opens with prefilled information from the **VAT Payment** line. Review and confirm with **OK**.
6. A new entry with **Entry Type – VAT Payment** and an opposite sign is created. The entry is reflected in both the general ledger and VAT entries.

To post a new VAT document for the advance again, choose the **Payment** line, and then choose **Post Payment VAT**.

## Unlink an incorrect payment from an advance

If an incorrect payment is linked to an advance, you can unlink it from the advance letter entries using **Unlink Advance Payment**. Unlinking is only possible if the payment isn't applied to a final document.

To unlink a payment from an advance:

1. Choose the ![Light bulb icon](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Advance Letters**, and choose the related link.
2. In the list, find the paid purchase advance letter.
3. Use the **Advance Letter Entries** function.
4. Choose the line with **Entry Type – Payment**.  
   ![Unlink advance payment](Media/adv-payments-additional-function-uncon.png)
5. Choose the **Unlink Advance Payment** action.
6. A new entry with **Entry Type – Payment** and an opposite sign is created. If a VAT document (line with **Entry Type – VAT Payment**) existed for the payment, a new reversed **VAT Payment** entry is also created.
7. The entry is reflected in the general ledger and VAT. New vendor/customer entries are created to reclassify the advance account to a standard balancing account.

### Unlink a payment from advance via vendor or customer entries

You can also unlink payments directly from vendor or customer entries. From a customer entry that have a **Document Type – Payment** and **Advance Letter No.**, use the **Unlink Advance Letter** function.

1. Find the vendor or customer entry used to pay the advance letter.
2. Choose **Unlink Advance Letter**.
3. A new entry with **Entry Type – Payment** and an opposite sign is created. If a VAT document existed, a reversed **VAT Payment** is also created.
4. The entry is reflected in the general ledger and VAT. New vendor or customer entries are created to reclassify the item from advance to a standard balancing account.

## Retrospective payment assignment to an advance

If you post a vendor or customer payment without linking it to an advance, you can create the link later from vendor or customer entries.

To link a payment to an advance retrospectively:

1. Find an open vendor or customer entry with **Document Type = Payment**.
2. Choose **Link Advance Letter**.
3. On the page that opens, choose **New**.
4. In the **Advance Letter No.** field, select an available advance.
5. Choose the advance, and confirm with **OK**.
6. Confirm the linking page with **OK**.
7. The payment is now linked to the advance. An entry with **Entry Type – Payment**, and possibly **VAT Payment**, is created. This is reflected in the general ledger and VAT. New vendor or customer entries are created to reclassify them from a balancing account to an advance account.

## Unapply an advance from a posted invoice

If you mistakenly applied an advance to an invoice, you can remove the link.

> [!NOTE]
> This function has a few limitations:
>
> - If multiple advances are applied to an invoice, they must all be removed together.
> - The reversal uses the same posting and VAT date as the original.
> - If the accounting period is closed or restricted, the reversal can't be done.

To unapply an advance from a posted invoice:

1. Find the posted invoice linked to the advance.
2. Choose **Unapply Advance Letter**.
3. Confirm the dialog.
4. The advance is unapplied. In advance entries, opposite **Entry Type – Usage**, and possibly **VAT Usage**, lines are created. These are reflected in the general ledger and VAT. New vendor or customer entries are created to reclassify them from a balancing account to an advance account.

## Add an advance to a posted invoice

If an advance wasn't linked when you posted a sales or purchase invoice, you can add it later from the posted invoice by using **Apply Advance Letter**.

> [!NOTE]
> This function has a few limitations:
>
> - The original posting and VAT dates are reused.
> - Preview isn't available before posting.
> - The advance amount can't exceed the remaining balance of the posted invoice. If the invoice was partially paid, adjust the advance amount manually.
> - The system doesn't auto-adjust the applied amount. You must enter it manually.

To add an advance to a posted invoice:

1. Find the posted invoice without linked advance.
2. Use **Apply Advance Letter**.
3. On the opened page, choose **New**.
4. In the **Advance Letter No.** field, select an advance.
5. Choose the advance, and confirm with **OK**.
6. Repeat for more advances if needed.
7. Adjust the **Amount** field so that it doesn't exceed the remaining invoice balance.
8. Confirm the link with **OK**.
9. The advance is now linked. Entries with **Entry Type – Usage**, and possibly **VAT Usage**, are created. These are reflected in the general ledger and VAT. New vendor or customer entries are created to reclassify them from balancing accounts to advance accounts.

## Related information

[Advance Payments for Czech Republic (extension)](ui-extensions-advance-payments-localization-cz.md)  
[Czech Local Functionality](czech-local-functionality.md)  
[Finance](../../finance.md)  
