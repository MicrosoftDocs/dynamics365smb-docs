---
title: Set Up Tax Deducted at Source (TDS) on Purchase of Goods under Section 194Q
description: Learn about the required setup steps for Tax Deducted at Source (TDS) under Section 194Q, in accordance with the Income Tax Act, 1961.
author: v-debapd
ms.topic: overview
ms.devlang: al
ms.search.keywords: India, local, IN, English, TDS, section 194Q
ms.date: 10/21/2026
ai-usage: ai-assisted
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# Set up tax deducted at source (TDS) on purchase of goods under section 194Q

[!INCLUDE[vnext_preview](../../includes/vnext_preview.md)]

Business Central supports Tax Deducted at Source (TDS) on purchases in the India localization.

TDS section 194Q on purchases of goods was introduced in the Finance Act, 2021, with an effective date of July 1, 2021.

The historical scenario described here concerns a buyer purchasing goods from a resident supplier. It assumes deduction on purchases or advance payments, whichever occurs earlier, a threshold of INR 50,00,000, and a TDS rate of 0.10% on the amount above the threshold. These assumptions explain the configuration, not current tax law. Configure the rates and thresholds that apply to your transactions.

## Set up TDS section 194Q

The following setups are required:

- [TDS rates](#set-up-tds-rates)
- [TDS 194Q opening](#tds-194q-opening)

## Set up TDS rates

The rate of TDS is defined by the combination of the TDS section and assessee code. The rates can vary by effective date. Configure **Calc. Over & Above Threshold** on the applicable tax rate.

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **TDS Rates**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|
    |**Calc. Over & Above Threshold**|Select to calculate TDS only on the amount above the configured threshold. If cleared, the normal threshold calculation applies without excluding the threshold amount from the taxable base. If **Threshold Overlook** is selected on the vendor's **Allowed Sections** line, the threshold is ignored. This option isn't restricted to section 194Q.|

## TDS 194Q opening

A provision has been made to upload the opening amount, if any, under TDS section 194Q. System only updates the amount in TDS Entries table for threshold calculation purposes. This amount isn't posted into G/L.

Before you run the report, fill in the vendor's **Assessee Code**, assign the section in **Allowed Sections**, and configure **TDS Above Threshold Opening** in **Source Code Setup**. The applicable TDS rate must have **Calc. Over & Above Threshold** selected.

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **TDS 194Q Opening**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Vendor No.**|Specifies the vendor number for which 194Q opening is to be posted.|
    |**Assessee Code**|Displays the assessee code from the vendor.|
    |**TDS Section Code**|Select an allowed section for the vendor for which the opening entry is to be posted.|
    |**Document No.**|Specifies the document number that appears on the TDS ledger entries.|
    |**Posting Date**|Specify the date, on which the TDS ledger entries are to be posted.|
    |**Purchase Amount**|Specify the purchase amount that must be posted into TDS Entry table as vendor’s opening entry for Section 194Q.|
    |**TDS Threshold Amount**|Displays the threshold from the applicable TDS rate.|

## Set up customer

Provision is made available on customer master to capture whether aggregate turnover of customer in the immediate previous year was below 10 crores or above 10 crores.

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Customers**, choose the related link, and open the customer card.
1. Fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|
    |**Aggregate Turnover**|This field can be used to define aggregate Turnover in the immediate previous year exceeds Rs.10 crore to an assessee. The available options are: Less than 10 Crore, More than 10 Crore.|  

## Related information

[TDS 194Q Transactions](TDS-194Q-Transactions.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
