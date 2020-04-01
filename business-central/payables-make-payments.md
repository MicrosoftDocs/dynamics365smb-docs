---
title: Overview of Tasks to Manage Payments to Vendors| Microsoft Docs
description: Outlines tasks to manage payments to vendors or creditors, including posting payment lines and getting an overview of the balance due.
author: edupont04

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: print check, vendor payment, creditor, debt, balance due, AP
ms.date: 04/01/2020
ms.author: edupont

---
# Making Payments

When you make payments to vendors or customers, or reimburse your employees, you post the related payment lines on the **Payment Journal** page. The payment journal is a general journal that is optimized for making payments and includes a number of powerful functions such as the **Suggest Vendor Payments** function that finds vendor payments that are due, and the **Vendor - Summary Aging** report that shows an overview of due vendor payments.  

You can start the process of making the payment from the lists, cards, and ledger entries for vendors, customers, and employees. Each of these pages has a button that starts the payment flow and helps you fill in the payment journal.  

From the payment journal, you can print computer checks or record when checks are written. If you select **Computer Check** in the **Bank Payment Type** field, then any lines representing checks must be printed before the payment journal can be posted.

When the payments are posted, you can export them to a bank file for upload to your bank for processing.

After the payments are made at your bank, you must apply them to their related open vendor or employee ledger entries. You can do this manually or by importing a bank statement file and applying the payments automatically. For more information, see [Applying Payments Automatically and Reconciling Bank Accounts](receivables-apply-payments-auto-reconcile-bank-accounts.md).

The following table describes a sequence of tasks, with links to the topics that describe them.

| To | See |
| --- | --- |
|Understand basic functions of the **Payment Journal** page, which is a based on the general journal, to prepare to post payments to vendors or employees.|[Working with General Journals](ui-work-general-journals.md)|
|Post payments to vendors or employees and refunds to customers, and optionally apply the payments to the related unpaid invoices/credit memos to close them as paid.|[Record Payments and Refunds](payables-how-post-payments-refunds.md)|
| Use a function on the **Payment Journal** page to suggest vendor payments according to selected criteria, such as due date, discount eligibility, and your liquidity. |[Suggest Vendor Payments](payables-how-suggest-vendor-payments.md) |
| Issue checks for vendor payments or customer refunds, either as print-outs or as computer checks. Void checks before or after posting. |[Make Check Payments](payables-how-work-checks.md) |
|Make electronic payments according to the EU SEPA Credit Transfer standard.|[Making Payments with AMC Banking 365 Fundamentals extension or SEPA Credit Transfer](finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md)|
| Pay a vendor by cash or check, and post the payment when you post the invoice. |[Settle Purchase Invoices Promptly](finance-how-to-settle-purchase-invoices-promptly.md) |
| Make sure that your bank only clears validated checks and amounts by sending them a file that contains vendor, check, and payment information. |[Export a Positive Pay file](finance-how-positive-pay.md) |

## See Also
[Managing Payables](payables-manage-payables.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Managing Receivables](receivables-manage-receivables.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
