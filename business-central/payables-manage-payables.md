---
title: Overview of Tasks to Manage Accounts Payable| Microsoft Docs
description: Outlines tasks to manage accounts payable, for example, paying creditors or applying outgoing payments to ledger entries to close invoices or credit memos.
author: edupont04

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: vendor payment, creditor, debt, balance due, AP
ms.date: 04/01/2020
ms.author: edupont

---
# Managing Payables

A big part of managing accounts payable is paying your vendors, or reimbursing your employees for expenses. You can use functions to add payments lines for purchase invoices that are due on the **Payment Journal** page. To send transactions to your bank, you can export multiple payment journal lines to a file, and then upload the file to your bank. You can also make payments by check, including transmitting checks as electronic payments.

Another typical task is to apply outgoing payments to their related vendor or employee ledger entries in order to close purchase invoices, purchase credit memos, or employee accounts as paid. You can do this on the **Payment Reconciliation Journal** page by importing a bank statement file to register the payments. The payments are applied to open vendor, customer, or employee ledger entries by matching payment text and entry information. There are various ways to review and change the matches before you post the journal. You can choose to close any open bank account ledger entries related to the applied ledger entries when you post the journal. The bank account is automatically reconciled when all payments are applied.

Alternatively, you can apply outgoing payments manually on the **Payment Journal** page or from the related vendor or employee ledger entries.

The following table describes a sequence of tasks within accounts payable, with links to the topics that describe them.

| To | See |
| --- | --- |
| Generate due vendor payments or employee reimbursements, prepare check payments, and export payments to a bank file when posting. |[Making Payments](payables-make-payments.md) |
| Apply vendor payments automatically to unpaid purchase invoices by importing a bank statement file. |[Applying Payments Automatically and Reconciling Bank Accounts](receivables-apply-payments-auto-reconcile-bank-accounts.md) |
| Apply vendor payments to unpaid purchase invoices manually. |[Reconcile Vendor Payments with the Payment Journal or from Vendor Ledger Entries](payables-how-apply-purchase-transactions-manually.md) |
|Ensure correct inventory valuation by assigning added item costs, such as freight, physical handling, insurance, and transportation that you incur when purchasing.|[Use Item Charges to Account for Additional Trade Costs](payables-how-assign-item-charges.md)|
|Reimburse employees for personal expenses during business activities by making payment to their bank account.|[Record and Reimburse Employees' Expenses](finance-how-record-reimburse-employee-expenses.md)|

## See Related Training at [Microsoft Learn](/learn/paths/process-customer-vendor-payments-dynamics-365-business-central/)

## See Also
[Purchasing](purchasing-manage-purchasing.md)  
[Managing Receivables](receivables-manage-receivables.md)  
[Use Item Charges to Account for Additional Trade Costs](payables-how-assign-item-charges.md)  
[General Business Functionality](ui-across-business-areas.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

## [!INCLUDE[d365fin](includes/free_trial_md.md)]  
