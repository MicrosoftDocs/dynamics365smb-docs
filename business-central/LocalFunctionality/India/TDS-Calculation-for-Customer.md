---
title: TDS calculation for Customer
description: Describes the process for calculating and tracking TDS on customer transactions.
author: v-debapd
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English, TDS for customer, TDS certificate
ms.date: 06/30/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# TDS for customer

This article explains the process of calculating TDS on customer payments.

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

#### Mandatory fields for TDS calculation on general journal, cash receipt journal, bank receipt voucher, and cash receipt voucher at the time of TDS calculation

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **General Journal**, **Cash Receipt Journal**, **Bank Receipt Voucher** or **Cash Receipt Voucher**, and then choose the related link.
1. Select **Customer** in Account Type and select relevant customer code in **Account No.** field. Select **G/L Account** or **Bank Account** in Bal. Account Type and select relevant cash or bank account in **Bal. Account No.** field.
1. **TDS Certificate Receivable** field should be marked true and then select relevant **TDS Section** on journal line, **Location Code** field shouldn't be blank.

#### Mandatory fields for TDS certificate receivable tracking on general journal, cash receipt journal, bank receipt voucher, cash receipt voucher, and sales invoice

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **General Journal**, **Cash Receipt Journal**, **Bank Receipt Voucher**, **Cash Receipt Voucher** or **Sales Invoice**, and then choose the related link.
1. **TDS Certificate Receivable** should be marked true on **Journal** line or **Sales Invoice** header.
1. **TDS Certificate Receivable** identification flows into Customer Ledger Entry on posting of the document.

#### TDS to be calculated on customer receipts (through general journal, cash receipt journal, bank receipt voucher, cash receipt voucher)

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

#### TDS certificate is receivable against payment received from customer or against customer sales invoice

It's required to identify the payment or invoice transaction against which TDS certificate is receivable while receiving the payment from customer who has deducted TDS or issuing the sales invoice on which TDS has been deducted, it's required to identify the payment or invoice transaction against which TDS certificate is receivable.

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **General Journal**, **Cash Receipt Journal**, **Bank Receipt Voucher**, **Cash Receipt Voucher** or **Sales Invoice**, and then choose the related link.
1. **TDS Certificate Receivable** should be marked true on **Journal** line or **Sales Invoice** header.
1. **TDS Certificate Receivable** identification flows into Customer Ledger Entry on posting of the document.

## Related information

[TDS Certificate Update](TDS-Certificate-Update.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
