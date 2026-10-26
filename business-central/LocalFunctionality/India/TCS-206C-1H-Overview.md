---
title: Set Up Tax Collected at Source (TCS) for Section 206C(1H)
description: Review setup for the documented section 206C(1H) TCS workflow, including customer and tax configuration, in Business Central for India.
author: v-debapd 
ms.topic: overview
ms.devlang: al
ms.search.keywords: India, local, IN, English, TCS, Section 206C
ms.date: 10/21/2026
ai-usage: ai-assisted
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# Set up tax collected at source (TCS) for Section 206C(1H)

Business Central supports the configuration of Tax Collected at Source (TCS) on receipt of payment in the India localization.

Section 206C(1H) was introduced in the Finance Bill, 2020. The historical scenario described here concerns a seller collecting TCS from a buyer on receipts for sales of goods. It uses a threshold of INR 50,00,000 in a financial year and a seller turnover criterion of INR 10,00,00,000 in the previous financial year. TCS is calculated on the amount above the threshold, with different configured rates for PAN and non-PAN customers. These historical assumptions explain the feature, not the current legal applicability of the section. Configure the rates and thresholds that apply to your transactions.

## Set up TCS section 206C(1H)

The following setups are required:

- [TCS nature of collection](TCS-Overview.md#set-up-tcs-nature-of-collection)
- [TCS rates](TCS-Overview.md#set-up-tcs-rates)

## Set up TCS nature of collection

TCS nature of collection identifies the type of receipt for TCS calculation. Use **TCS On Recpt. Of Pmt.** to configure calculation on receipt of payment.

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **TCS Nature of Collections**, and then choose the related link.
1. Fill in the fields as described in the following table.

   |Field|Description|  
   |---------------------------------|---------------------------------------|
   |**TCS On Recpt. Of Pmt.**|Select to calculate TCS on receipt of payment. A nature of collection with this option selected can't be used on sales document lines or journal lines with a document type other than Payment.|

## Set up TCS rates

The rate of TCS is defined by the combination of TCS nature of collection and assessee code. Configure **Calc. Over & Above Threshold** on the applicable tax rate.

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **TCS Rates**, and then choose the related link.
1. Fill in the fields as described in the following table.

   |Field|Description|
   |---------------------------------|---------------------------------------|  
   |**Calc. Over & Above Threshold**|Select to calculate TCS only on the amount above the configured threshold. If cleared, the normal threshold calculation applies, without excluding the threshold amount from the taxable base. If **Threshold Overlook** is selected on the customer's **Allowed NOC** line, the threshold is ignored. This option isn't restricted to section 206C(1H).|

## Related information

[TCS 206C-1H-Transaction](TCS-206C-1H-Transactions.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]