---
title: Payment of TCS to the Government Authorities
description: Learn how to deposit Tax Collected at Source (TCS) payments to government authorities in Business Central.
author: v-debapd
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English, TCS, TCS payment
ms.date: 06/27/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Payment of TCS to government authorities

The TCS collected from various transactions, needs to be deposited to the government. Payment of TCS is handled through Payment Journal/Bank Payment Voucher. Provision to select the TCS Entries, which assessee needs to pay to the government authorities depends on the basis of filters, for example, T.C.A.N, Assesses, Date, etc.

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Payment Journal** or **Bank Payment Voucher**, and then choose the related link.
1. Select the relevant TCS payable account in **Account No.** field > select the relevant TCAN in the **T.C.A.N No.** field > **Navigate** > **Tax Payments** > **TCS** > then select **TCS**.
1. Select entries and the system generates TCS payment entry on the journal line.
1. On posting of the payment journal, TCS Entries are marked as 'Paid'.

   GL Entries are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**TCS Payable Account**|10000|
    |**Bank Account**|-10000|

## Related information

[TCS Overview](TCS-Overview.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
