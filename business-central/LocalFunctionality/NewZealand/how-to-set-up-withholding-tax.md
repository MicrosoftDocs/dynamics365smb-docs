---
title: Set up withholding tax [NZ]
description: Learn how to set up product posting groups and business posting groups for Withholding tax (WHT) in the New Zealand version of Business Central.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: withholding tax, withholding tax setup, product posting groups, business posting groups, New Zealand version
ms.search.form: 28041, 28042, 28043, 118
ms.date: 05/07/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up withholding tax in the New Zealand version

Withholding tax (WHT) is the tax withheld by a company when making a payment to a vendor, and it reduces the full amount owed to the vendor. The withheld tax is then remitted to tax authorities when the next Business Activity Statement (BAS) is submitted.  

If a supplier without a New Zealand Inland Revenue Department number (IRD) provides an invoice, a withholding tax amount must be withheld if the total amount of the invoice is more than the threshold amount.  

To use withholding tax, you must set up the business posting groups and product posting groups for withholding tax so that the correct WHT calculations are made for each vendor.  

> [!NOTE]  
> As a prerequisite, you need to set up source codes for WHT settlement on the **Source Code Setup** page.  

The following procedure describes how to set up product posting groups for WHT, but the same steps also apply to setting up business posting groups for WHT.  

[!INCLUDE [wht-posting-group-setup](../includes/AUNZ/wht-posting-group-setup.md)]

## Related information

- [Set Up Revenue Types for Withholding Tax](how-to-set-up-revenue-types-for-withholding-tax.md)
- [View Withholding Tax Entries](how-to-view-withholding-tax-entries.md)
- [Calculate and Post Withholding Tax Settlements](how-to-calculate-and-post-withholding-tax-settlements.md)
- [Withholding Tax](withholding-tax.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
