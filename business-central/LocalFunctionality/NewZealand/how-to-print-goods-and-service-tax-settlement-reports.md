---
title: Print GST Settlement Reports in New Zealand
description: Learn how to print goods and services tax (GST) settlement reports and distinguish posting a settlement from filing a New Zealand GST return.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: GST settlement, GST settlement report, New Zealand version
ms.date: 10/23/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Print goods and services tax settlement reports in the New Zealand version

Use the **Calculate GST Settlement** report to calculate and print a goods and services tax (GST) settlement.

> [!NOTE]
> Posting a GST settlement in Business Central isn't the same as filing a GST return with Inland Revenue. New Zealand businesses file GST returns with Inland Revenue, not Australian BAS returns with the Australian Taxation Office. For filing options, including myIR, see [Filing GST](https://www.ird.govt.nz/gst/filing-and-paying-gst-and-refunds/filing-gst).

## Print a GST settlement report

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Calculate GST Settlement**, and then choose the related link.
1. On the **Options** FastTab, fill in the fields as described in the following table.

   | Field | Description |
   |-------|-------------|
   | **Settlement Account Type** | The settlement account type. |
   | **Settlement Account No.** | The general ledger account number or vendor number, based on the selected **Settlement Account Type**. |
   | **Rounding G/L Account No.** | The account to which the truncated cents are posted. |
   | **Posting Date** | The posting date for the settlement entries. |
   | **Document No.** | The document number of the settlement entries. |
   | **Description** | The settlement description. |
   | **Post** | Select to post the GST settlement entries. |
   | **Inter Company** | Select if the posting is intercompany. |

1. On the **BAS Calculation Sheet** FastTab, select the appropriate filters.
1. Choose **Print** to print the report, or choose **Preview** to view it.

## Related information

[Set Up Goods and Service Tax Posting](how-to-set-up-goods-and-service-tax-posting.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
