---
title: Match Purchase Invoice Drafts to Purchase Orders
description: Learn how to match incoming purchase invoice draft lines to purchase orders and receipts, review warnings, and prepare invoices for posting.
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.topic: how-to
ms.date: 09/27/2026
ai-usage: ai-assisted
ms.search.keywords: purchase invoice draft, purchase order matching, receipt matching, payables agent, e-document
ms.search.form: 6103, 9308
---

# Review and match incoming invoice drafts to orders

When an incoming vendor invoice relates to one or more purchase orders, you can match each purchase document draft line to the corresponding order lines and receipts. The matches remain linked to the unposted purchase invoice after you finalize the draft. You can then review the invoice and post it when the receipt requirements are met.

Payables Agent can propose purchase order matches as part of processing an invoice. Review the proposed matches and warnings before you let the agent finalize the draft. Business Central validates compatibility, allocates quantities, and enforces receipt requirements. The agent never posts the invoice.

## How Business Central finds available purchase order lines

Business Central first identifies the vendor for the incoming invoice. If the extracted **Purchase Order No.** contains a value, Business Central takes the first 20 characters and looks for an exact match with an internal purchase order number. If that order is available, the **Available Purchase Order Lines** page initially shows its eligible lines. If the referenced order isn't available, the page instead shows eligible order lines for the identified vendor.

The available lines meet these conditions:

- The order's pay-to vendor is the identified vendor.
- If the draft line has a unit of measure, the order line has the same unit of measure.
- The order line isn't already assigned to another line in the same or another draft. A line already assigned to the current draft line remains available.

This order-number lookup is an exact Business Central document-number match. It isn't fuzzy matching or an AI confidence score.

## Review proposed matches

On the **Purchase document draft** page, review these fields for each line:

- **Order line match** shows the matched order number and line description. It indicates when the line is matched to multiple lines or orders.
- **Warnings** shows the result of Business Central validations. Select the value to view details.

Use the actions in the **Order matching** group to investigate or change a match:

- **Match to order lines** opens **Available Purchase Order Lines**.
- **Specify receipt lines** lets you choose posted receipt lines for the matched order lines.
- **Open matched orders** opens the matched order or a list when more than one order is matched.
- **Open matched receipts** opens the matched receipt or a list when more than one receipt is matched.
- **Remove match** removes the order and receipt matches for the draft line.

On **Available Purchase Order Lines**, use **Open purchase order** to inspect an order before selecting it. Use **Remove matches** to clear all order matches for the current draft line.

## Match a draft line

You can match a draft line to one or more compatible purchase order lines. This multiline selection is a Business Central capability. Payables Agent doesn't necessarily select multiple order lines autonomously for one invoice line.

1. On the **Purchase document draft** page, select the invoice line.
1. Select **Line** > **Order matching** > **Match to order lines**.
1. On **Available Purchase Order Lines**, review the order, quantity received, quantity invoiced, unit price, and expected receipt date.
1. Select one or more lines, and then select **OK**.
1. Review **Order line match** and **Warnings** on the draft line.

All selected order lines must have the same vendor, line type and number, and unit of measure. When the draft becomes a purchase invoice, the invoice and order must also have the same buy-from vendor, pay-to vendor, and currency.

Business Central allocates the invoice quantity across the selected order lines in selection order, up to the quantity that remains to invoice on each line. If you select multiple order lines, Business Central copies dimensions from the first selected line to the draft line. Review the dimensions if the selected lines use different dimensions.

## Understand order-match warnings

The **Warnings** field can show the following values. These warnings come from deterministic Business Central validations. They don't represent AI confidence and don't start an approval workflow. You don't have to clear every warning before you finalize the draft.

| Warning | What it means | What you need to do |
|---------|---------------|---------------------|
| **No warnings** | Business Central didn't find a unit, quantity, receipt, over-receipt, or price issue for the match. | No action is required. |
| **Unit of measure information is missing** | Business Central can't determine valid unit-of-measure information for a matched item line. | Add or correct the unit of measure. This warning blocks finalization. |
| **Exceeds quantity received** | The invoice quantity is greater than the quantity received but not yet invoiced. | You can finalize the draft, but receipts must cover the full invoice quantity before posting. Alternatively, use **Receipt on Invoice** for eligible matched lines. |
| **Exceeds remaining to invoice** | The invoice quantity is greater than the ordered quantity that remains to invoice. | Reduce the invoice quantity or select order lines with enough remaining quantity before posting. |
| **Over-receipt** | Invoicing the remaining ordered quantity closes the order line, but a larger quantity was received. | Review the difference. You don't have to clear this warning to finalize the draft. |
| **Price difference** | The invoice's net unit cost differs from the weighted net unit cost of the selected order lines by more than the allowed tolerance. | Review the price and correct it if the difference isn't acceptable. You don't have to clear this warning to finalize the draft. |
| **Multiple warnings** | More than one validation applies. | Select the value and follow the guidance for each warning. |

The price comparison uses the invoice line amount after its total discount and compares it with the quantity-weighted direct unit cost after line discounts on the matched order lines. Differences at or below the currency rounding precision don't produce a warning. Larger differences produce **Price difference** only when the percentage exceeds **E-Document Matching Difference %** on the **Purchases & Payables Setup** page.

## Match receipts and partial invoices

A draft line can relate to multiple orders and multiple posted receipts. Business Central uses receipt quantities that you didn't invoice and can allocate a partial invoice across those receipts.

Business Central suggests available receipt coverage when it finalizes the draft. To control which posted receipts cover a draft line, select **Specify receipt lines** and select receipt lines that together cover the full invoice quantity. You can select only receipts that belong to the matched order lines.

If a posted receipt line has item tracking, you must invoice the remaining quantity on that receipt line in full. Business Central can't assign part of an item-tracked receipt because the invoice match doesn't specify which serial, lot, or package numbers apply.

## Finalize and post the invoice

Finalizing and posting are separate actions:

1. Review every proposed match and warning on the **Purchase document draft** page.
1. Correct unmatched lines and any missing or incompatible values. Unmatched lines continue through the existing classification and manual review process. Don't assume that freight, item charges, or other extra lines are matched automatically.
1. Confirm the review when Payables Agent requests it.
1. Payables Agent finalizes the draft into an unposted purchase invoice. It doesn't post the invoice.
1. Open the purchase invoice and review the persistent order and receipt links before posting.

A missing unit of measure on a matched item line blocks finalization. Other quantity warnings can remain when the draft is finalized, but Business Central requires the full invoice quantity to be allocated to posted receipts before posting.

If you enable **Receipt on Invoice** on eligible matched order lines, posting the purchase invoice first receives the matched quantity on those orders and then invoices it. Otherwise, post the receipts or associate existing posted receipt lines before you post the invoice.

## Limitations and compatibility requirements

The following limitations apply:

- You can't match **Charge (Item)** lines and order lines with prepayments.
- The invoice line and order lines must have the same line type, number, and unit of measure.
- The finalized invoice and order must have the same buy-from vendor, pay-to vendor, and currency.
- You must invoice in full a posted receipt line with item tracking.
- **Receipt on Invoice** isn't available for lines that require item tracking, use a location with directed put-away and pick, or already have any posted receipts.
- You can select existing posted receipts explicitly when they have a remaining quantity to invoice.
- Lines that you can't match require classification or manual review.

## Related information

- [Payables Agent overview](payables-agent.md)
- [Set up Payables Agent](payables-agent-setup.md)
- [Combine receipts or purchase order lines on a single invoice](purchasing-how-to-combine-receipts.md)
- [Use e-documents in the purchase process](finance-how-use-edocuments-purchase.md)
- [Record purchases with purchase invoices and orders](purchasing-how-record-purchases.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
