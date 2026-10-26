---
title: Set Up Vendors Without IRD Numbers for Withholding Tax
description: Learn how to set up local vendors without IRD numbers when withholding tax applies in the New Zealand version of Business Central.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: IRD number, calculate withholding tax, vendor setup, New Zealand tax compliance
ms.search.form: 28043
ms.date: 10/23/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Set up vendors without IRD numbers for calculating the withholding tax

Use this procedure to set up a local vendor without an IRD number when withholding tax (WHT) applies to their payments. A missing IRD number doesn't mean that every supplier payment is subject to withholding tax. Confirm the applicable tax treatment and rate before you configure WHT. Learn more in [Withholding tax](withholding-tax.md).

## Set up a vendor without an IRD number

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Vendors**, and then choose the related link.  
1. Choose the required vendor, and then choose the **Edit** action.  
1. On the **Vendor Card** page, on the **Registration** FastTab, leave **IRD No.** blank and clear the **Foreign Vend** checkbox.
1. Choose the **OK** button.  

> [!NOTE]  
> The WHT rate comes from **WHT Posting Setup**. To print the certificate when you post the payment, select **Print WHT Docs. on Pay. Post** on **Purchases & Payables Setup**. Send the certificate to the vendor with the payment. Learn more in [Withholding tax](withholding-tax.md).

## Related information

- [Withholding Tax](withholding-tax.md)
- [Set Up Withholding Tax](how-to-set-up-withholding-tax.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
