---
title: Payment of TCS to Government Authorities
description: Select Tax Collected at Source entries for payment to government authorities and review the payment workflow in Business Central for India.
author: v-debapd
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English, TCS, TCS payment
ms.date: 10/21/2026
ai-usage: ai-assisted
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# Payment of TCS to government authorities

Use a **Payment Journal** or **Bank Payment Voucher** to record payment of collected TCS. The **TCS** action opens unpaid, unreversed TCS entries with a nonzero total for the payable account and T.C.A.N. number on the journal line. Apply additional filters, such as posting date or assessee code, to identify the entries to pay.

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Payment Journal** or **Bank Payment Voucher**, and then choose the related link.
1. Enter a **Document No.**, select the TCS payable G/L account in **Account No.**, and select **T.C.A.N. No.** Choose **Tax Payments** > **TCS**.
1. Filter the **Pay TCS** page to the entries to pay, then choose **Pay**. The total of the filtered entries is transferred to the journal line.
1. Complete the balancing bank account and other required journal fields, then post the journal. Posting marks the linked TCS entries as paid.

   GL Entries are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**TCS Payable Account**|10000|
    |**Bank Account**|-10000|

## Related information

[TCS Overview](TCS-Overview.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
