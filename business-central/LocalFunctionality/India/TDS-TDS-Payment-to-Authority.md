---
title: Payment of TDS to Government Authorities
description: Select Tax Deducted at Source entries for payment to government authorities and review the payment workflow in Business Central for India.
author: v-debapd
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English, TDS payment
ms.date: 10/21/2026
ai-usage: ai-assisted
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# Payment of TDS to government authorities

Use a **Payment Journal** or **Bank Payment Voucher** to record payment of deducted TDS. The **TDS** action opens unpaid, unreversed TDS entries with a nonzero total for the payable account and T.A.N. number on the journal line. Apply additional filters, such as posting date or assessee code, to identify the entries to pay.

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Payment Journal** or **Bank Payment Voucher**, and then choose the related link.
1. Enter a **Document No.**, select the TDS payable G/L account in **Account No.**, and select **T.A.N. No.** Choose **Pay TDS** > **TDS**.
1. Select the entries to pay on the **Pay TDS** page, then choose **Pay**. The total of the selected entries is transferred to the journal line.
1. Complete the balancing bank account and other required journal fields, then post the journal. Posting marks the linked TDS entries as paid.

   GL Entries are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**TDS Payable Account**|10000|
    |**Bank Account**|-10000|

## Related information

[TDS Overview](TDS-Overview.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
