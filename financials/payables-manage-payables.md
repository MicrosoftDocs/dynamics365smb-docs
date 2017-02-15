---
title: Managing Payables| Microsoft Docs
description: Managing Payables
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: project-madeira
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/14/2017
ms.author: sgroespe

---
# Managing Payables
A big part of managing accounts payable is paying your vendors. You can use functions to add payments lines for purchase invoices that are due in the **Payment Journal** window. To send transactions to your bank, you can export multiple payment journal lines to a file, and then upload the file to your bank. You can also make payments by check, including transmitting checks as electronic payments.

Another typical task is to apply outgoing payments to their related vendor ledger entries in order to close purchase invoices or purchase credit memos as paid. You can do this in the **Payment Reconciliation Journal** window by importing a bank statement file to register the payments. The payments are applied to open vendor or customer ledger entries by matching payment text and entry information. There are various ways to review and change the matches before you post the journal. You can choose to close any open bank account ledger entries related to the applied ledger entries when you post the journal. The bank account is automatically reconciled when all payments are applied.

Alternatively, you can apply outgoing payments manually in the **Payment Journal** window or from the related vendor ledger entries.

The following table describes a sequence of tasks within accounts payable, with links to the topics that describe them.

| To | See |
| --- | --- |
| Generate due vendor payments prioritized according to payment discounts and overdue penalties. Optionally, export the payments to a bank file when posting. |[Make Payments](payables-make-payments.md) |
| Apply vendor payments automatically to unpaid purchase invoices by importing a bank statement file. |[Apply Payments Automatically and Reconcile Bank Accounts](receivables-apply-payments-auto-reconcile-bank-accounts.md) |
| Apply vendor payments to unpaid purchase invoices manually. |[How to: Reconcile Vendor Payments Manually](payables-how-apply-purchase-transactions-manually.md) |

## See Also
[Purchasing](purchasing-manage-purchasing.md)  
[Managing Receivables](receivables-manage-receivables.md)  
[General Business Functionality](ui-across-business-areas.md)  
[Working With [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)]](ui-work-product.md)
