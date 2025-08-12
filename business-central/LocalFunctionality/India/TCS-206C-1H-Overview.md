---
title: Setting up Tax Collected at Source for the section 206C(1H)
description: Describes the essential setup steps for implementing Tax Collected at Source under section 206C(1H).
author: v-debapd 
ms.topic: overview
ms.devlang: al
ms.search.keywords: India, local, IN, English, TCS, Section 206C
ms.date: 06/27/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up tax collected at source (TCS) for Section 206C(1H)

Business Central has included Tax Collected at Source (TCS) Section 206C(1H) Feature in Indian Localization.

A new TCS section 206C (1H) has been introduced in finance bill 2020. As per new section, a seller has to collect TCS from buyer on any sales of Goods, where aggregate value of sales exceeds INR 50,00,000 (Threshold Amount) within same financial year. TCS to be collected on amount that is over & above INR 50,00,000, for example: Threshold amount is INR 50,00,000, TCS to be collected on amount that is more than INR 50,00,000. TCS % varies for PAN and Non-PAN customers. A Seller whose turnover is more than INR 10,00,00,000 Crore in previous financial year is eligible to collect TCS under section 206C(1H).

## Set up TCS Section 206C(1H)

### Following is the list of setups that are required

- [TCS Nature of Collection](tcs-overview.md#)
- [TCS Rates](tcs-overview.md#set-up-tcs-rates)

## Set up TCS nature of collection

TCS Nature of Collection represents the various types of payments received for which TCS rates have been specified under the provisions of section 206C(1H) of the Income Tax Act 1961. A new field 'TCS On Recpt Of Pmt.' has been added on the setup.

1. Choose the ![Search for Page or Report](image/search_small.png "Search for Page or Report icon") icon, enter **TCS Nature of Collection**, and then choose the related link.
1. Fill in the fields as described in the following table.

   |Field|Description|  
   |---------------------------------|---------------------------------------|
   |**TCS On Recpt Of Pmt.**|User will not be able to select TCS Nature of Collection on sales invoice and credit memo lines where 'TCS on Recpt. Of Pmt.' is TRUE.|

## Set up TCS rates

Rate of TCS is defined in combination of TCS nature of collection and assessee code. A new field 'Calc. Over & Above Threshold' has been added on the setup.

1. Choose the ![Search for Page or Report](image/search_small.png "Search for Page or Report icon") icon, enter **Tax Type** > **TCS** > **Action** > **Tax Rates**, and then choose the related link.
1. Fill in the fields as described in the following table.

   |Field|Description|
   |---------------------------------|---------------------------------------|  
   |**Calc. Over & Above Threshold**|This field is created in TCS Setup table, by selecting this field, system calculates TCS on amount that is over & above threshold. If this field isn't selected in TCS Setup, system will calculate TCS normally, that is, system will calculate TCS after crossing the specified threshold amount. If user selects Threshold Overlook field on NOD/NOC Lines, then system calculates TCS normally, that is, calculate TCS from INR 1 onwards without considering threshold amount. This field can be selected for any TCS group, there's no restriction for selecting this for only 1H.|

## Related information

[TCS 206C-1H-Transaction](TCS-206C-1H-Transactions.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]