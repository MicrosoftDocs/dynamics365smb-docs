---
title: Overview of tasks to manage payments to vendors
description: Outlines tasks to manage payments to vendors or creditors, including posting payment lines and getting an overview of the balance due.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: overview
ms.search.keywords: print check, vendor payment, creditor, debt, balance due, AP
ms.search.form: 254, 256, 1190, 1191, 1227, 1228, 1229
ms.date: 06/15/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Make payments

You pay vendors or customers, or reimburse your employees, by posting payment lines on the **Payment Journal** page. The payment journal is a general journal that's optimized for making payments, and offers lots of powerful actions. For example, the **Suggest Vendor Payments** action that finds vendor payments that are due, and the **Vendor - Summary Aging** report that shows an overview of due vendor payments.  

You can start the payment process from the lists, cards, and ledger entries for vendors, customers, and employees. Each of these pages has a button that starts the payment flow and helps you fill in the payment journal.  

From the payment journal, you can print computer checks or record when checks are written. If you select **Computer Check** in the **Bank Payment Type** field, you must print lines that represent checks before you can post the payment journal.

After you post payments, you can export them to a bank file you can upload to your bank for processing.

After the payments are made at your bank, you must apply them to their related open vendor or employee ledger entries. You can apply them manually or by importing a bank statement file and applying the payments automatically. To learn more, go to [Applying Payments Automatically and Reconciling Bank Accounts](receivables-apply-payments-auto-reconcile-bank-accounts.md).

The following table describes a sequence of tasks, with links to the articles that describe them.

| To... | Go to... |
| --- | --- |
|Understand basic functions of the **Payment Journal** page, which is a based on the general journal, to prepare to post payments to vendors or employees.|[Work with General Journals](ui-work-general-journals.md)|
|Post payments to vendors or employees and refunds to customers, and optionally apply the payments to the related unpaid invoices/credit memos to close them as paid.|[Record Payments and Refunds](payables-how-post-payments-refunds.md)|
| Use a function on the **Payment Journal** page to suggest vendor payments according to selected criteria, such as due date, discount eligibility, and your liquidity. |[Suggest Vendor Payments](payables-how-suggest-vendor-payments.md) |
| Issue checks for vendor payments or customer refunds, either as print-outs or as computer checks. Void checks before or after posting. |[Make Check Payments](payables-how-work-checks.md) |
|Make electronic payments according to the EU SEPA Credit Transfer standard.|[Making Payments with AMC Banking 365 Fundamentals extension or SEPA Credit Transfer](finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md)|
| Pay a vendor by cash or check, and post the payment when you post the invoice. |[Settle Purchase Invoices Promptly](finance-how-to-settle-purchase-invoices-promptly.md) |
| Make sure that your bank only clears validated checks and amounts by sending them a file that contains vendor, check, and payment information. |[Export a Positive Pay file](finance-how-positive-pay.md) |

## Related information

[Managing Payables](payables-manage-payables.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Managing Receivables](receivables-manage-receivables.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
