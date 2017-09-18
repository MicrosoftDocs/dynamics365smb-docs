---
title: Overview of Tasks to Manage Payments to Vendors| Microsoft Docs
description: Outlines tasks to manage payments to vendors or creditors, including posting payment lines and getting an overview of the balance due.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: print check, vendor payment, creditor, debt, balance due, AP
ms.date: 06/28/2017
ms.author: sgroespe

---
# Making Payments
When you make payments to vendors or reimbursements to employees, you post the related payment lines in the **Payment Journal** window. You can use the **Suggest Vendor Payments** function to find vendor payments that are due. You can also use the **Vendor - Summary Aging** report to get an overview of due vendor payments.

From the payment journal, you can print computer checks or record when checks are written. If you select **Computer Check** in the **Bank Payment Type** field, then any lines representing checks must be printed before the payment journal can be posted.

When the payments are posted, you can export them to a bank file for upload to your bank for processing.

After the payments are made at your bank, you must apply them to their related open vendor or employee ledger entries. You can do this manually or by importing a bank statement file and applying the payments automatically. For more information, see [Apply Payments Automatically and Reconcile Bank Accounts](receivables-apply-payments-auto-reconcile-bank-accounts.md).

The following table describes a sequence of tasks, with links to the topics that describe them.

| To | See |
| --- | --- |
|Use the **Payment Journal** window, which is a based on the general journal, to post payments to vendors or employees.|[Working with General Journals](ui-work-general-journals.md)|
| Use a function to suggest vendor payments according to selected criteria, such as due date, discount eligibility, and your liquidity. |[How to: Suggest Vendor Payments](payables-how-suggest-vendor-payments.md) |
|Reimburse employees for personal expenses during business activities by making payment to their bank account.|[How to: Record and Reimburse Employees' Expenses](finance-how-record-reimburse-employee-expenses.md)|
| Issue checks for vendor payments, either as print-outs or as computer checks. Void checks before or after posting. |[How to: Work With Checks](payables-how-work-checks.md) |
| Pay the vendor by cash or check, and post the payment when you post the invoice. |[How to: Settle Purchase Invoices Promptly](finance-how-to-settle-purchase-invoices-promptly.md) |
| Make sure that your bank only clears validated checks and amounts by sending them a file that contains vendor, check, and payment information. |[How to: Export a Positive Pay file](finance-how-positive-pay.md) |
|Export payments from the **Payment Journal** window to a bank file that you upload to your bank for processing, including EFT (electronic funds transfer) in North America. |[How to: Export Payments to a Bank File](payables-how-export-payments-bank-file.md)|  

## See Also
[Managing Payables](payables-manage-payables.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Managing Receivables](receivables-manage-receivables.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
