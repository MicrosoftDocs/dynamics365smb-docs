---
title: Advance Payments and Invoices [CZ]
description: Learn about Czech-specific functionality for advance payments and invoices, including document types, VAT handling, and process workflows.
author: ACMartinKunes
ms.topic: article
ms.search.keywords: Czech, Advance payment, Advance invoices, Payables, Finance, CZ, Cash, tax documents, tax credit memo, life cycle, deduction of advance, linking tool, factboxes, internal documents, output documents printout, Czech local functionality, Czech version
ms.date: 10/08/2026
ms.reviewer: bholtorf
ms.author: bholtorf
ms.service: dynamics-365-business-central
ai-usage: ai-assisted
---

# Advance payments and invoices in the Czech version

The Advance Invoices and Payments feature is used to generate invoices and to make payments before goods or services have been delivered or before the production has begun. The Advance Invoices and Payments feature includes advance invoices, advance payments, advance payments subject to VAT, and tax documents. The document types and document requirements for this feature are listed below:

## Advance invoices

- Used to request money in advance.
- The document isn't accounted and doesn't have a tax voucher.
- Documents are created in advance of invoices templates (document groups) with predefined accounting and number series of related documents.
- Advance invoice templates define whether or not you're obliged to post VAT.
- Advance invoices can be created from purchase orders, invoices, or as a separate document with no links to any documents.
- Free advances can be additionally linked with documents before posting the final invoice.

## Life cycle of advance invoice

An advance invoice has its own life cycle, which is defined by its **Status** field:

- **New** - the advance invoice can be edited.
- **To Pay** - the advance invoice is released and ready for settlement; payment is expected.
- **To Use** - the advance invoice is paid and ready to be applied to a final document.
- **Closed** - final status after the advance invoice has been fully applied or manually closed.

## Advance payments

- The payment made against an advance invoice.
- Proportional advance payments with regard to posting and billing, in journals and banknotes.
- Received advance payments aren't receivables, they're liabilities.
- Issued advance payments aren't payables (liabilities), they're receivables.
- Advance payments may be subject to VAT. Czech legislation lays down rules for whether the advance payments are subject to VAT.
- Received advance payments are classified based on the date of receipt.
- Issued advance payments are classified based on the date of tax documents receipt.
- Any unspent part of advance payments can be returned.
- Posting payment for a payment can be made on the basis of an advance invoice.
- Posted invoice with a link to advance invoice can be disconnected.
- The advance invoice can be paid by multiple payments.
- Received advance invoices are posted as liabilities.
- Advance payments in foreign currency based on agreed data.

## Tax documents (tax credit memo)

- Documents specifying the paid VAT from received advance payments.
- It isn't possible to claim VAT from advance payments without receiving tax documents issued for advance payments.
- VAT calculation improvements comply with the legislation of the Czech Republic.
- Documents are declaring the VAT paid on the advance payments received/issued.
- Tax documents/tax credits are created in relation to the advance invoice to which the payment was made.
- The module includes functions for automatically generating tax documents when posting an advance payment.
- For advance payments, it's possible to correct the tax documents before they're posted because of their billing based on the received document from the creditor.
- The Advance Invoice mode without a tax document allows VAT to be applied only on the final invoice, if its performance meets the conditions of Section 28 of the Value Added Tax Act.
- The tax document for the released payment can be charged only on the basis of the received document from the creditor, therefore the purchase advance invoice allows the change of the regime with/without VAT also during its processing.
- Calculation of VAT on advance invoices based on the Value Added Tax Act (§ 37a, § 92).
- The new module also works with VAT in the payer registration mode in another EU country/region.

## Deduction of advance

- Deduction of advance payments and already paid or claimed VAT from final invoices.
- Deduction is done when posting final invoice proportionally.
- The module offers a tool for linking advance invoices with the final document.
- It's possible to change/supplement/cancel the linking of the advance invoice with the final document before it's posted.
- It's possible to link multiple advance invoices to the final document in one step.
- The tool parameters can be influenced by how the final deferral is interconnected with advance invoices.
- For better control/correction of the final invoice tax, order statistics and invoices have been expanded to include bookmarks informing you of your payment usage and VAT paid/claimed.
- Deduction of the advance invoice from the final invoice can be canceled with all accounting entries that were used for the deduction.
- When using an advance invoice in a foreign currency, the exchange rate differences are quantified.

## Linking tool for an advance invoice and a final document

The tool provides a choice of different ways to link the lines of the final document to the lines of backup payments:

- Mode of linking advance invoices paid/unpaid.
- Linking by amounts remaining or billing the final document.
- Linking based on VAT rates.

## FactBoxes - customer/vendor statistics

The customer and vendor card statistical information windows were supplemented with an **Advances** field that shows the number of open advance letters (status **To Pay** or **To Use**) for the customer or vendor. Selecting the field opens the list of those advance letters.

## Internal and output documents printout

A set of documents are created that take into account Czech legislation and practices.

Output documents (printed for the customer or vendor):

- Sales - Advance Letter
- Purchase - Advance Letter
- Sales - Advance VAT Document
- Purchase - Advance VAT Document
- Sales - Invoice with Advance
- Purchase - Invoice with Advance

Internal documents (control reports):

- Sales Advance Letters
- Purchase Advance Letters
- Sales Advance Letters VAT
- Purchase Advance Letters VAT

## Related information

- [Czech Local Functionality](czech-local-functionality.md)  
- [Finance](../../finance.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
