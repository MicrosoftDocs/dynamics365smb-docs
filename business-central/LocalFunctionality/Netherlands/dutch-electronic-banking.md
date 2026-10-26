---
title: Dutch Electronic Banking in Business Central
description: Learn how to create electronic payment files and direct debit files, and import electronic bank statements from supported bank software.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: Dutch electronic banking, electronic banking, Dutch version, electronic payment files, direct debit files, import bank statements, telebanking, payment files, electronic bank statements, bank statement import, Netherlands
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Dutch electronic banking

Electronic banking functionality allows you to create electronic payment files and direct debit files, and to import electronic bank statements from supported bank software.  

## Telebanking overview

Using Telebanking, you can export payments, import bank statements, and collect data to forward to the bank. Learn more in [Telebanking](telebanking.md).  

Create payment proposals from **Telebank - Bank Overview**. Import and reconcile electronic statements in the **Bank/Giro Journal**.

### Payment files

You can make payment proposals for paying open invoices to suppliers. Payment proposals can be edited manually prior to processing to add or remove payment invoices, or to change payment amounts. After processing a proposed payment batch, you can transfer electronic payment files to the bank. If an error occurs in the payment file while importing into the banking software, you can make a copy of the payment file to resubmit to the bank.  

You can make domestic payments and international payments using the designated formats. Learn more in [Telebanking](telebanking.md).  

### Direct debit files

You can create a payment proposal to collect payment from customer bank accounts. You can edit payment proposals manually to add or remove invoices, or to change collection amounts. After processing a proposed payment batch, you can transfer electronic direct debit files to the bank. If an error occurs in the direct debit file while importing into the banking software, you can make a copy of the direct debit file to resubmit to the bank.  

Use a collection format supported by your bank and configured export protocol, such as SEPA direct debit. Learn more in [Create proposals](how-to-create-proposals.md) and [Activate SEPA payments](how-to-activate-sepa-payments.md).

### Bank statement import

You can import bank statements from supported bank software, and reconcile them with incoming and outgoing payments. You can also reconcile bank charges and interest earned.  

Learn more in [Import and Reconcile Bank Statements](how-to-import-and-reconcile-bank-statements.md).  

## Related information

- [Telebanking](telebanking.md)  
- [Enter and Post Cash and Bank/Giro Journals](how-to-enter-and-post-cash-and-bank-or-giro-journals.md)  
- [Import and Reconcile Bank Statements](how-to-import-and-reconcile-bank-statements.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
