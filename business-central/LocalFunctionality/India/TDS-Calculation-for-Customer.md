---
title: TDS for Customer
description: Calculate and track TDS on customer transactions, and review illustrative payment and accounting entries in the India localization of Business Central.
author: v-debapd
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English, TDS for customer, TDS certificate
ms.date: 10/21/2026
ai-usage: ai-assisted
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# TDS for customer

This article explains the process of calculating TDS on customer payments.

The example assumes a TDS rate of 2% for illustration. Use the rate that applies to your transactions; this example isn't guidance on current tax law.

## TDS calculation and tracking of TDS certificate receivable

TDS can be deducted on receiving payment from customer. TDS can be calculated on the following documents:

- General Journal
- Cash Receipt Voucher
- Bank Receipt Voucher
- Cash Receipt Journal

TDS certificate is receivable from customer on receiving the advance payment or issuing sales invoice to customer. TDS Certificate Receivable can be tracked through following documents:

- General Journal
- Cash Receipt Voucher
- Bank Receipt Voucher
- Cash Receipt Journal
- Sales Invoice

### Set up a journal line for customer TDS

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **General Journal**, **Cash Receipt Journal**, **Bank Receipt Voucher**, or **Cash Receipt Voucher**, and then choose the related link.
1. Select **Customer** in Account Type and select relevant customer code in **Account No.** field. Select **G/L Account** or **Bank Account** in Bal. Account Type and select relevant cash or bank account in **Bal. Account No.** field.
1. Select **TDS Certificate Receivable**, and then select **TDS Section Code** on the journal line. The section must be assigned to the customer in **TDS Customer Allowed Sections**. Check the **Location Code** and **T.A.N. No.** for the transaction.

### Mark a transaction for certificate tracking

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **General Journal**, **Cash Receipt Journal**, **Bank Receipt Voucher**, **Cash Receipt Voucher**, or **Sales Invoice**, and then choose the related link.
1. **TDS Certificate Receivable** should be marked true on **Journal** line or **Sales Invoice** header.
1. **TDS Certificate Receivable** identification flows into Customer Ledger Entry on posting of the document.

### Calculate TDS on a customer receipt

- In the given scenario, advance payment received from customer for INR 50,000 on which 2% TDS is applicable under TDS Section 194C.

  In this case TDS calculation is as following:

    |Component|Value|
    |----------------------------------|---------------------------------------|  
    |**TDS Base Amount**|50000|  
    |**TDS Amount**|1000 (50000*2%)|

  GL Entries are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Customer Account**|-50000|
    |**TDS Receivable Account**|1000|
    |**Bank Account**|49000|

### Identify the transaction for a receivable certificate

Identify the payment or invoice for which you expect a TDS certificate. Selecting **TDS Certificate Receivable** on a sales invoice tracks the certificate; it isn't the same as calculating TDS on a receipt journal line.

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **General Journal**, **Cash Receipt Journal**, **Bank Receipt Voucher**, **Cash Receipt Voucher**, or **Sales Invoice**, and then choose the related link.
1. **TDS Certificate Receivable** should be marked true on **Journal** line or **Sales Invoice** header.
1. **TDS Certificate Receivable** identification flows into Customer Ledger Entry on posting of the document.

## Related information

[TDS Certificate Update](TDS-Certificate-Update.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
