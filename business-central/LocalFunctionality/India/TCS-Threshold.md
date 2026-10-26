---
title: TCS with Threshold
description: Review TCS threshold calculations and illustrative examples to understand how configured limits affect transactions in Business Central for India.
author: v-debapd
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English, TCS, threshold, threshold limits, TCS calculation, TCS threshold
ms.date: 10/21/2026
ai-usage: ai-assisted
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# TCS with threshold

This article explains the requirement of threshold amount in TCS and  the process of calculating TCS for such transactions.

## TCS calculation considering threshold limits

The tax rate defines the threshold for each TCS nature of collection. The calculation considers transactions within the tax accounting period and the customer's **Threshold Overlook** setting. Select **Threshold Overlook** on **Allowed NOC** to calculate without applying the threshold.

The following illustrative scenario assumes a threshold of INR 20,000 for TCS Type A. This threshold isn't a statement of current tax law. With **Threshold Overlook** cleared, a transaction of INR 19,000 below the threshold doesn't collect TCS. If you expect the customer's transactions to exceed the threshold and want to collect from the first transaction, select **Threshold Overlook**.

**Calc. Over & Above Threshold** on the tax rate controls whether the threshold amount is excluded from the taxable base after the threshold is crossed. It differs from **Threshold Overlook**, which ignores the threshold entirely.

1. GL Entries for TCS where payment is less than the threshold limits as follows:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Customer Account**|19000|
    |**Sales Account**|-19000|

1. For an illustrative tax-inclusive receipt of INR 10,000 with calculated TCS of INR 287 after the threshold is crossed, the G/L entries are:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Bank Account**|10000|
    |**TCS Payable Account**|-287|
    |**Customer Account**|-9713|

## Related information

[TCS Adjustment Entry](TCS-Adjustment-Entries.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
