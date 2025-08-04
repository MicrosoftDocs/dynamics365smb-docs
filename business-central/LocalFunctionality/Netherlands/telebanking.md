---
title: Telebanking
description: Telebanking allows you to electronically generate and exchange payments and collections with your bank based on sales and purchase transactions.
author: brentholtorf
ms.topic: concept-article
ms.devlang: al
ms.search.keywords: telebanking, Dutch version, Netherlands, payment history, exchange protocols
ms.date: 03/20/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Telebanking

Based on both sales and purchase transactions, telebanking enables you to generate your payments and collections and interchange them with your bank electronically. This includes the export of payment and collection data that need to be forwarded to the bank and the import of bank statements sent to you by the bank.  

## Transactions

In general, all financial interactions with vendors and customers are done through either purchase or sales invoices and credit memos. As soon as these transactions are registered and posted, payments, or collections can be carried out by your company.  

## Proposals

Based on vendor and customer ledger entries, telebanking enables you to generate payment and collection proposals. This can be done for any bank that is set up for your company. Both domestic and foreign payments and collections are possible.  

You can set up [!INCLUDE[prod_short](../../includes/prod_short.md)] to combine payments to or collections from the same bank account automatically.  

When a proposal is agreed upon, it should be processed into a payment history.  

> [!NOTE]  
> In general, for any open vendor and customer ledger entries, a proposal can be generated if it meets a number of criteria. Learn more in [Create Proposals](how-to-create-proposals.md).  

## Payment histories

A payment history is nothing more than a proposal except for the fact that data on a payment history can't be modified. The payment or collection data is ready to be exported and forwarded to the bank. Learn more in [Create and Export Payment History](how-to-create-and-export-payment-history.md).  

## Bank statements

For all your financial interactions through your bank, the bank can send you electronic bank statements. These statements can be imported into the Bank/Giro Journals. If you want, you can have [!INCLUDE[prod_short](../../includes/prod_short.md)] automatically reconcile these statements during this import process and determine whether a statement can be applied to open ledger entries for the relevant vendor/customer. Learn more in [Import and Reconcile Bank Statements](how-to-import-and-reconcile-bank-statements.md).  

> [!NOTE]  
> The currency of the imported transactions must match the currency that is specified on the bank account in [!INCLUDE[prod_short](../../includes/prod_short.md)].  

## Exchange protocols

For both exporting and importing, a number of protocols are defined. [!INCLUDE[prod_short](../../includes/prod_short.md)] supports the following protocols:  

- BTL91 (export). This cross-border protocol is no longer accepted in the Netherlands as of May 1, 2019. This protocol is replaced by the Generic Payment File protocol.
- BBV (export)  
- PAYMUL (export)  
- Generic Payment File (export). Can be used for cross-border Non-EUR transfers.
- Rabobank mut.asc (import)  
- Rabobank vvmut.asc (import)  
- Rabobank ASCII (import)  
- SEPA CAMT  

## Related information

[Invoice Sales](../../sales-how-invoice-sales.md)   
[Record Purchases](../../purchasing-how-record-purchases.md)   
[Create Proposals](how-to-create-proposals.md)   
[Create and Export Payment History](how-to-create-and-export-payment-history.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
