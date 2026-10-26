---
title: Setup for GST TDS and GST TCS
description: Learn how to configure GST TDS and GST TCS in Business Central for India, including setup steps and compliance requirements.
author: v-debapd
ms.topic: overview
ms.devlang: al
ms.search.keywords: India, local, IN, English, GST TDS setup, GST TCS setup
ms.date: 10/21/2026
ai-usage: ai-assisted
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# Setup for GST TDS and GST TCS 

This article explains the requirement and the process of setting up GST TDS and GST TCS.

> [!NOTE]
> The statutory background below includes historical rates and thresholds. It isn't current-rate guidance. Confirm the requirements for your transaction date, and configure the tax rates with the appropriate effective date.

## Understand GST TDS

As per Section 51 of CGST Act, recipient of goods and services shall deduct TDS of 2% on payment amount where contract amount exceeds INR 250000. The recipient issues a certificate for the tax amount deducted against the payment made for contract to supplier. Recipient pays the deducted amount to government and the same is reflected in supplier’s electronic ledger entry, which the supplier can further adjust against liability.

## Understand GST TCS

As per Section 52 of CGST Act, 2017, every e-commerce operator is required to collect tax at the rate of 1% (0.5% of CGST and 0.5% of SGST for intrastate supply or 1% of IGST on interstate supply) on the net value of taxable supplies provided the supplier is supplying goods or services through e-commerce operator (online market place) and consideration with respect to the supply is to be collected by the said e-commerce operator The taxable supplies includes total sales and returns.

The GST TCS amount collected by e-commerce operator shall be paid to GSTIN and the same is reflected as available credit for supplier in their electronic cash ledger that can be utilized to set off liability.

Corrections are allowed before GST TCS amount is paid to GSTIN by e-commerce operator.
Hence, there will not be any refund or negative credit. If refund of payment is to be paid by supplier to e-commerce operator then, full amount (without GST TCS) shall be considered.
GST TCS to be calculated on Invoice amount excluding GST. The Credit Memo amount excluding GST should be deducted from Invoice amount for the period before calculating GST TCS.
GST TCS can be calculated for a given period, which can be week, fortnight or a month.
GST TDS is applicable only for Registered Suppliers. The calculation of GST TCS is provided on Bank or Cash Payment and Receipt Vouchers.

## Set up GST TDS/TCS

This setup is required for calculation of GST TDS and GST TCS on payment to vendor or receipt from customer.

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Tax Types**, and then choose the related link.
1. Select **GST TDS TCS**, and then choose **Tax Rates**.
1. Fill in the fields as described in the following table.

    |Field|Description|
    |---------------------------------|  ---------------------------------------|
    |**GST TDS TCS Type**|Specify the relevant type, for example: TDS, TCS.|
    |**Effective Date**|Specify the effective date.|
    |**CGST**|Specify the relevant percentage for component CGST.|
    |**SGST**|Specify the relevant percentage for component SGST.|
    |**IGST**|Specify the relevant percentage for component IGST.|

On a cash or bank voucher, select **TDS** or **TCS** in **GST TDS/GST TCS** and enter **GST TDS/TCS Base Amount**. The document type must be **Payment**, and the customer or vendor must be **Registered**. For vendor TCS, enter **GST TCS State Code** before selecting **TCS**.

GST TDS and GST TCS use separate accounts in **GST Posting Setup**. They aren't the same as income-tax TDS or TCS, which use nature of deduction or nature of collection setup.

## Related information

[GST TCS on Payment](GST-TCS-on-Payment.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
