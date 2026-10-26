---
title: Set Up Goods and Services Tax Posting in New Zealand
description: Learn how to set up GST posting groups, tax rates, and general ledger accounts for purchases and sales in the New Zealand version of Business Central.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: GST, tax posting setup, tax setup, New Zealand
ms.date: 10/23/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Set up goods and services tax posting in the New Zealand version

Goods and services tax (GST) applies to most goods and services. In New Zealand, you report GST to Inland Revenue in a GST return. Learn more in [Filing GST](https://www.ird.govt.nz/gst/filing-and-paying-gst-and-refunds/filing-gst).

To set up posting details for GST, define the posting groups, GST rate, and accounts to which GST is posted. Set up this information for each combination of business posting groups and product posting groups that you use.

## Set up GST posting

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **VAT Posting Setup**, and then choose the related link.
1. Fill in the fields as described in the following table.

    | Field | Description |
    |-------|-------------|
    | **VAT Bus. Posting Group** | The VAT business posting group code. |
    | **VAT Prod. Posting Group** | The VAT product posting group code. |
    | **VAT Identifier** | The code used to group similar VAT setups. For example, group setups that have a common VAT percentage. |
    | **VAT %** | The tax rate. |
    | **VAT Calculation Type** | The method used to calculate tax on purchases and sales. |
    | **Sales VAT Account** | The general ledger account for sales tax. Leave this field blank if **VAT Calculation Type** is **Reverse Charge VAT**. |
    | **Purchase VAT Account** | The general ledger account for purchase tax. |
    | **Reverse Chrg. VAT Acc.** | The general ledger account for reverse charge tax. You can enter an account only if **VAT Calculation Type** is **Reverse Charge VAT**. |

1. Choose **OK**.

## Related information

[Print Goods and Service Tax Settlement Reports](how-to-print-goods-and-service-tax-settlement-reports.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
