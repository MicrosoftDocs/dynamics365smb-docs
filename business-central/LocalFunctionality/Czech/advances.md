---
title: Czech Local Functionality - Advance payments and invoices | Microsoft Docs
description: This section describes Czech local functionality - Advance payments and invoices
author: ACMartinKunes

ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords: Czech, Advance payment, Advance invoices, Payables, Finance, CZ, Cash
ms.date: 04/01/2020
ms.reviewer: v-pejano
ms.author: v-makune
---

# Advance Payments and Invoices  

The Advance Invoices and Payments feature is used to generate invoices and to make payments before goods or services have been delivered or before the production has begun. The Advance Invoices and Payments feature includes advance invoices, advance payments, advance payments subject to VAT, and tax documents. The document types and document requirements for this feature are listed below:

## Advance Invoices

- Used to request money in advance.
- The document is not accounted and does not have a tax voucher.
- Documents are created in advance of invoices templates (document groups) with predefined accounting and number series of related documents.
- Advance invoice templates define whether or not you are obliged to post VAT.
- Advance invoices can be created from purchase orders, invoices, or as a separate document with no links to any documents.
- Free advances can be additionally linked with documents before posting the final invoice.

## Life Cycle of Advance invoice

An advance invoice has its own life cycle, which is defined by states:
- **Open** - an advance invoice can be edited.
- **Prepayment** - payment of advance invoice is expected.
- **Invoice preparation** - a tax receipt for the received/issued payment is expected.
- **Preparation** of the final invoice - the advance invoice is ready to be drawn.
- **Closed** - final status after the advance invoice has been exhausted.

## Advance Payments

- The payment made against an advance invoice.
- Proportional advance payments with regard to posting and billing, in journals and banknotes.
- Received advance payments are not receivables, they are liabilities.
- Issued advance payments are not payables (liabilities), they are receivables.
- Advance payments may be subject to VAT. Czech legislation lays down rules for whether the advance payments are subject to VAT.
- Received advance payments are classified based on the date of receipt.
- Issued advance payments are classified based on the date of tax documents receipt.
- Any unspent part of advance payments can be returned.
- Posting payment for a payment can be made on the basis of an advance invoice.
- Posted invoice with a link to advance invoice can be disconnected.
- The advance invoice can be paid by multiple payments.
- Received advance invoices are posted as liabilities.
- Advance payments in foreign currency based on agreed data.

## Tax Documents (Tax Credit Memo)

- Documents specifying the paid VAT from received advance payments.
- It is not possible to claim VAT from advance payments without receiving tax documents issued for advance payments.
- VAT calculation improvements comply with the legislation of the Czech Republic.
- Documents are declaring the VAT paid on the advance payments received/issued.
- Tax documents/tax credits are created in relation to the advance invoice to which the payment was made.
- The module includes functions for automatically generating tax documents when posting an advance payment.
- For advance payments, it is possible to correct the tax documents before they are posted because of their billing based on the received document from the creditor.
- The Advance Invoice mode without a tax document allows VAT to be applied only on the final invoice, provided that its performance meets the conditions of Section 28 of the Value Added Tax Act.
- The tax document for the released payment can be charged only on the basis of the received document from the creditor, therefore the purchase advance invoice allows the change of the regime with / without VAT also during its processing.
- Calculation of VAT on advance invoices based on the Value Added Tax Act (§ 37a, § 92).
- The new module also works with VAT in the payer registration mode in another EU country.

## Deduction of Advance

- Deduction of advance payments and already paid or claimed VAT from final invoices.
- Deduction is done when posting final invoice proportionally.
- The module offers a tool for linking advance invoices with the final document.
- It is possible to change/supplement/cancel the linking of the advance invoice with the final document before it is posted.
- It is possible to link multiple advance invoices to the final document in one step.
- The tool parameters can be influenced by how the final deferral is interconnected with advance invoices.
- For better control/correction of the final invoice tax, order statistics and invoices have been expanded to include bookmarks informing you of your payment usage and VAT paid/claimed.
- Deduction of the advance invoice from the final invoice can be canceled with all accounting entries that were used for the deduction.
- When using an advance invoice in a foreign currency, the exchange rate differences are quantified.

## Linking Tool for an Advance Invoice and a Final Document

The tool provides a choice of different ways to link the lines of the final document to the lines of backup payments:

- Mode of linking advance invoices paid/unpaid.
- Linking by amounts remaining or billing the final document.
- Linking based on VAT rates.

## FactBoxes - Customer/Vendor Statistics

The customer and vendor card statistical information windows were supplemented with information about advances:
- Invoiced Amount of Advance
- Advances - Open
- Advances - Prepare Payments
- Advances - Preparing an Invoice
- Advances - Preparing the end Invoices

## Internal and Output Documents Printout

A set of documents are created that take into account Czech legislation and practices.

Output Documents:
- Advance Invoice
- VAT Document to Received Payment
- VAT Document to Tax Credit Memo
- Sale Invoice

Internal Documents:
- Sales Advance Letter List
- Purch. Advance Letter List
- VAT List on Purch. Adv. Letter
- VAT List on Sales Adv. Letter

## See Also
[Czech Local Functionality](czech-local-functionality.md)  
[Finance](finance.md)
