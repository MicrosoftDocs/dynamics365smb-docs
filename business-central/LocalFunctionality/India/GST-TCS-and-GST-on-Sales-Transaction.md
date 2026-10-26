---
title: Calculation of TCS as per the Income Tax Act, 1961 and GST on Sales Transactions
description: Calculate income tax TCS and GST on sales transactions, and review illustrative calculation and accounting entries in Business Central for India.
author: v-debapd
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English, TCS, IT Act, Income Tax Act, sales transactions
ms.date: 10/21/2026
ai-usage: ai-assisted
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# Calculation of TCS as per the Income Tax Act, 1961 and GST on sales transactions

This article describes a sales invoice that includes GST and TCS under the Income Tax Act, 1961. This TCS uses **TCS Nature of Collection**. It's separate from GST TCS on cash or bank vouchers.

The process of calculation of TCS and GST has been explained in this document.

## Create a sales invoice

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Sales Invoices**, and then choose the related link.
1. Select **Customer** on **Sales Invoice** header.
1. Select **Item** on **Sales Invoice** line. GST Group Code, HSN/SAC Code shouldn't be blank on the Item.
1. Select **TCS Nature of Collection** on the sales line. The nature of collection must be allowed for the customer and must not be configured as **TCS on Recpt. Of Pmt.**

For example, there's a sales invoice for INR 10,000 and 18% GST (that is, 9% CGST and 9% SGST/UTGST in case of Intra-State or Intra-Union Territory transaction or 18% IGST in case of Inter-State transaction) and 1% TCS as per Income Tax Act, 1961 has to be charged on the invoice amount.

The example assumes a TCS base that excludes GST. Confirm the configured TCS base, thresholds, and rates for your transaction; the example rates aren't current-rate guidance.

- GST calculation appears in the Fact Box as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|  
    |**CGST**|900|  
    |**SGST**|900|
    |**TCS**|100|

- On posting of sales invoice, GL Entries are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Customer Account**|11900|  
    |**SGST/UTGST Payable Account**|-900|  
    |**CGST Payable Account**|-900|
    |**TCS Payable Account**|-100|
    |**Sales Account**|-10000|

> [!TIP]
> In case of Inter-State Sales, IGST is calculated with TCS as per the Income Tax Act, 1961.

## Related information

[GST Kerala Flood Cess](GST-and-Kerala-Flood-Cess-on-Sales.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
