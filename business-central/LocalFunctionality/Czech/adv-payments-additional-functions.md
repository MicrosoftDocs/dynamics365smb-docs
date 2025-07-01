# Additional Features (Corrections)

The Advance Payments application, in addition to core functionality such as creating, paying, and applying advances, also provides several supplementary features to simplify working with advance documents. These additional features include:

- Reversing an advance VAT document
- Unlinking an incorrect payment from an advance
- Adding a payment to an advance retrospectively
- Unapplying an advance from a posted invoice
- Adding an advance to a posted invoice

## Reversing an Advance VAT Document

This function is used when a VAT document was mistakenly posted for a purchase advance payment and needs to be reversed.

To reverse an advance VAT document:

1. Choose the ![Light bulb icon that opens the Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Advance Letters**, and then choose the related link.
2. In the list, locate the paid purchase advance letter with a posted VAT document. Use the **Advance Letter Entries** function.
3. In the list of purchase adv. letter entries, place the cursor on the line with **Entry Type – VAT Payment**.  
   ![Purchase Advance Invoice Entries](Media/adv-payments-additional-function-cancel.png)
4. On the action bar, choose **Post Credit Memo VAT**.
5. A page opens with prefilled information from the **VAT Payment** line. Review and confirm with **OK**.
6. A new entry with **Entry Type – VAT Payment** and opposite sign is created. The entry is reflected in both general ledger and VAT entries.

To post a new VAT document for the advance again, place the cursor on the **Payment** line and choose **Post Payment VAT**.

## Unlinking an Incorrect Payment from an Advance

If an incorrect payment was linked to an advance, it can be unlinked. This function is available from the advance letter entries using **Unlink Advance Payment**. Unlinking is only possible if the payment has not yet been applied to a final document.

### Unlinking a Payment from an Advance

To unlink a payment from an advance:

1. Choose the ![Light bulb icon](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Advance Letters**, and choose the related link.
2. In the list, find the paid purchase advance letter.
3. Use the **Advance Letter Entries** function.
4. Place the cursor on the line with **Entry Type – Payment**.  
   ![Unlink advance payment](Media/adv-payments-additional-function-uncon.png)
5. Choose the **Unlink Advance Payment** action.
6. A new entry with **Entry Type – Payment** and opposite sign is created. If a VAT document (line with **Entry Type – VAT Payment**) existed for the payment, a new reversed **VAT Payment** entry is also created.
7. The entry is reflected in general ledger and VAT. New vendor/customer entries are created to reclassify the advance account to standard balance account.

### Unlinking a Payment from Advance via Vendor/Customer Entries

Unlinking can also be done directly from vendor or customer entries. From a customer entry with **Document Type – Payment** and filled **Advance Letter No.**, use the **Unlink Advance Letter** function.

1. Find the vendor/customer entry used to pay the advance letter.
2. Choose **Unlink Advance Letter**.
3. A new entry with **Entry Type – Payment** and opposite sign is created. If a VAT document existed, a reversed **VAT Payment** is also created.
4. The entry is reflected in general ledger and VAT. New vendor/customer entries are created to reclassify the item between advance and standard balance accounts.

## Retrospective Payment Assignment to an Advance

If a vendor/customer payment was posted without being linked to an advance, it can be connected later from vendor/customer entries.

To link a payment to an advance retrospectively:

1. Find an open vendor/customer entry with **Document Type = Payment**.
2. Choose **Link Advance Letter**.
3. On the opened page, choose *New*.
4. Use the assist button in the **Advance Letter No.** field to select an available advance.
5. Place the cursor on the desired advance and confirm with **OK**.
6. Confirm the linking page with **OK**.
7. The payment is now linked to the advance. An entry with **Entry Type – Payment**, and possibly **VAT Payment**, is created. This is reflected in general ledger and VAT. New vendor/customer entries are created to reclassify from balance account to advance account.

## Unapplying an Advance from a Posted Invoice

If an advance was mistakenly applied to an invoice, the link can be removed.

Function limitations:

- If multiple advances are applied to an invoice, they must all be removed together.
- The reversal uses the same posting and VAT date as the original.
- If the accounting period is closed or restricted, the reversal cannot be performed.

To unapply an advance from a posted invoice:

1. Find the posted invoice linked to the advance.
2. Choose **Unapply Advance Letter**.
3. Confirm the dialog.
4. The advance is unapplied. In advance entries, opposite **Entry Type – Usage**, and possibly **VAT Usage**, lines are created. These are reflected in general ledger and VAT. New vendor/customer entries are created for reclassification between balance and advance accounts.

## Adding an Advance to a Posted Invoice

If an advance was not linked during posting of a sales or purchase invoice, it can be added afterward from the posted invoice using **Apply Advance Letter**.

Function limitations:

- The original posting and VAT dates are reused.
- No preview is available before posting.
- The advance amount must not exceed the remaining balance of the posted invoice. If the invoice was partially paid, the advance amount must be adjusted manually.
- The system does not auto-adjust the applied amount—user must enter it.

To add an advance to a posted invoice:

1. Find the posted invoice without linked advance.
2. Use **Apply Advance Letter**.
3. On the opened page, choose **New**.
4. Use the assist button in the **Advance Letter No.** field to select an advance.
5. Place the cursor on the desired advance and confirm with **OK**.
6. Repeat for more advances if needed.
7. Adjust the **Amount** field to not exceed the remaining invoice balance.
8. Confirm the linking with **OK**.
9. The advance is now linked. Entries with **Entry Type – Usage**, and possibly **VAT Usage**, are created. These are reflected in general ledger and VAT. New vendor/customer entries are created for reclassification between balance and advance accounts.

## See Also

[Advance Payments for Czech Republic (extension)](ui-extensions-advance-payments-localization-cz.md)  
[Czech Local Functionality](czech-local-functionality.md)  
[Finance](../../finance.md)
