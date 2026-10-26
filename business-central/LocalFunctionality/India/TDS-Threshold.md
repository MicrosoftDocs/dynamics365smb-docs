---
title: TDS with Threshold
description: Review TDS calculations with configured threshold limits, including illustrative calculations and general ledger entries in Business Central for India.
author: v-debapd
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English, TDS threshold
ms.date: 10/21/2026
ai-usage: ai-assisted
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# TDS with threshold

This article explains the requirement of threshold amount in TDS and the process of calculating TDS for such transactions.

## TDS calculation considering threshold limits

The tax rate defines the threshold and per-contract value for each TDS section. The calculation considers transactions within the tax accounting period and the vendor's **Threshold Overlook** setting. If **Threshold Overlook** is selected on **Allowed Sections**, the threshold is ignored.

The following example assumes TDS section 194C, an aggregate threshold of INR 1,00,000, a single-transaction threshold of INR 30,000, and a rate of 2%. These are illustrative assumptions, not guidance on current tax law. **Threshold Overlook** and **Calc. Over & Above Threshold** are cleared in this example.

Three transactions of INR 29,000 and a fourth transaction of INR 20,000 take place in the financial year. On the fourth transaction, the cumulative amount is INR 1,07,000, which exceeds the aggregate threshold. TDS is calculated as follows:

|Particulars|Amount Credited or Paid|TDS Rates|TDS Amount|Threshold Limit|
|--------------------|-----------------------|-----------------|----------|-------|  
|First Invoice|29000|2%|Zero|Less than Single Transaction Threshold Limit 30,000|
|Second Invoice|29000|2%|Zero|Less than Single Transaction Threshold Limit 30,000|
|Third Invoice|29000|2%|Zero|Less than Single Transaction Threshold Limit 30,000|
|Fourth Invoice|20000|2%|2,140 (2% of 1,07,000 that is, total of all invoices)|Exceeds TDS Threshold Limit 1,00,000|

1. GL Entries for TDS where payment is less than threshold limits (first transaction where vendor has given the invoice for INR 29,000) are as following:

   |Particulars|Amount|
   |----------------------------------|---------------------------------------|  
   |**Purchases Account**|29000|
   |**Vendor Account**|-29000|

1. GL Entries for TDS where payment is less than threshold limits (second transaction where vendor has given the invoice for INR 29,000) are as following:

   |Particulars|Amount|
   |----------------------------------|---------------------------------------|  
   |**Purchases Account**|29000|  
   |**Vendor Account**|-29000|

1. GL Entries for TDS where payment is less than threshold limits (third transaction where vendor has given the invoice for INR 29,000) are as following:

   |Particulars|Amount|
   |----------------------------------|---------------------------------------|  
   |**Purchases Account**|29000|  
   |**Vendor Account**|-29000|

1. G/L entries for the fourth invoice of INR 20,000, which crosses the aggregate threshold, are as follows:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Purchases Account**|20000|
    |**TDS Payable Account**|-2140|
    |**Vendor Account**|-17860|

## Related information

[TDS Provisional Entry](TDS-Provisional-Entries.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
