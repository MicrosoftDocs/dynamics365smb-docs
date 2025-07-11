---
title: TCS calculation considering threshold limits
description: Explains how TCS is calculated in relation to threshold limits.
author: v-debapd
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English, TCS, threshold, threshold limits, TCS calculation, TCS threshold
ms.date: 06/27/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# TCS with threshold

This article explains the requirement of threshold amount in TCS and  the process of calculating TCS for such transactions.

## TCS calculation considering threshold limits

TCS threshold defines the threshold limit for each TCS Nature of Collection. TCS can be deducted only if the total transaction with the assessee exceeds the threshold limit in the financial year.

If a payment under TCS Type A is below Threshold INR 20,000, no tax is collected. Another factor to be considered is the aggregate of total payments to be made in a year. If for a customer it's expected that the threshold limit would be crossed eventually, it means Threshold is overlooked. Hence, payments received from customers can cross the TCS threshold of INR 20,000. However, if the payment expected is below the threshold limit defined, TCS isn't collected.

1. GL Entries for TCS where payment is less than the threshold limits, as follows:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Customer Account**|19000|
    |**Sales Account**|-19000|

1. GL Entries for TCS where payment is more than (exceeding) Threshold limits, as follows:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Bank Account**|10000| 
    |**TCS Payable Account**|287| 
    |**Customer Account**|-9713|

## Related information

[TCS Adjustment Entry](TCS-Adjustment-Entries.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
