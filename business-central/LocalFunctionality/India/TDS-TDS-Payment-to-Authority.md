---
title: Payment of TDS to Government Authorities
description: Learn how to pay Tax Deducted at Source (TDS) to government authorities in Business Central.
author: v-debapd
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English, TDS payment
ms.date: 06/30/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Payment of TDS to government authorities

The TDS that has been deducted on various transactions, needs to be deposited to the government. Payment of TDS is handled through Payment Journal or General Journal. Provision available to select the TDS Entries, which assessee needs to pay to government authorities depends on the basis of filters, for example – TAN, Assesses, Date, etc.

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Payment Journal** or **Bank Payment Voucher**, and then choose the related link.
1. Select the relevant TDS payable account number in **Account No.** field > Select relevant TAN in **T.A.N No.** field > **Navigate** > **Pay TDS** > then select **TDS**. Select the entries and system generates TDS payment entry in the journal line.
1. On posting of the payment journal, TDS Entries are marked as 'Paid'.

   GL Entries are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**TDS Payable Account**|10000|
    |**Bank Account**|-10000|

## Related information

[TDS Overview](TDS-Overview.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
