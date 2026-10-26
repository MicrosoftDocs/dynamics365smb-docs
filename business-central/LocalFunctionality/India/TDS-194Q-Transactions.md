---
title: TDS Calculation and Transactions as per Section 194Q
description: Review the documented section 194Q TDS purchase workflow and illustrative calculation and accounting entries in Business Central for India.
author: v-debapd
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English, TDS calculation, Section 194Q
ms.date: 10/21/2026
ai-usage: ai-assisted
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# TDS calculation and transactions as per section 194Q

[!INCLUDE[vnext_preview](../../includes/vnext_preview.md)]

This article illustrates TDS calculation for section 194Q using the historical scenario from July 1, 2021. The examples assume a threshold of INR 50,00,000 and a rate of 0.10%. These values aren't guidance on current tax law. Use the rates and thresholds that apply to your transactions.

With **Calc. Over & Above Threshold** selected, TDS is calculated on the amount above the configured threshold. For example, for purchases of INR 85 lakhs and a threshold of INR 50 lakhs, the taxable amount is INR 35 lakhs and TDS at 0.10% is INR 3,500.

Provision (Calc. Over & Above Threshold) has been provided for user on TDS Rates to calculate TDS on amount that is over & above threshold.

The existing TDS calculation logic in system works for invoice and advance payment normally, below are the functions for example:

- TDS Calc. Over & Above Threshold
- Normal TDS Calculation
- TDS Calculation on Advance Payment

## TDS to be calculated on vendor invoice (through purchase invoice or purchase order)

In this scenario, the opening amount under section 194Q is INR 20,00,000. The vendor then issues invoices for INR 20,00,000 and INR 15,00,000, bringing the cumulative amount to INR 55,00,000. The configured TDS rate is 0.10%.
  
- In this case TDS calculation is as following:

  |Component|Value|
  |----------------------------------|---------------------------------------|  
  |**Initial threshold achieved value/ Opening Balance**|20,00,000|  
  |**1st Transaction, on or after 1st July 21**|2000000 – No TDS|
  |**2nd Transaction, on or after 1st July 21**|1500000 – TDS Calculated|
  |**TDS Base Amount**|500000 (Total cumulative value 5500000 -5000000)|
  |**TDS Amount**|500 (500000*0.10%)|

- On posting purchase invoice of second transaction, GL entries are as following:

  |Particulars|Amount|
  |----------------------------------|---------------------------------------|  
  |**Expense Account**|1500000|
  |**Vendor Account**|-1499500|
  |**TDS Payable Account**|-500|

## TDS to be calculated on vendor advance payment (through general or payment journal)

In the given scenario, two advance payments must made to vendor for INR 20,00,000 and 15,00,000 respectively, on which 0.10% TDS is applicable under TDS Section 194Q. Initial threshold achieved value or opening balance under section 194Q is INR 20,00,000.

- In this case TDS calculation is as following:

  | Component | Value |
  |----------------------------------|---------------------------------------|  
  |**Initial threshold achieved value/ Opening Balance**|2000000|  
  |**1st Transaction, on or after 1st July 21**|2000000 – No TDS|
  |**2nd Transaction, on or after 1st July 21**|1500000 – TDS Calculated|
  |**TDS Base Amount**|500000 (Total cumulative value 5500000 -5000000)|
  |**TDS Amount**|500 (500000*0.10%)|

- On posting the second advance payment, G/L entries are as follows:

  | Particulars | Amount |
  |----------------------------------|---------------------------------------|  
  |**Vendor Account**|1500000|
  |**Bank Account**|-1499500|
  |**TDS Payable Account**|-500|

## Related information

[TDS 194Q Overview](TDS-194Q-Section-Overview.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
