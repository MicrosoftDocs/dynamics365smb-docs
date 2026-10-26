---
title: Set Up Withholding Tax in the New Zealand Version [NZ]
description: Learn how to set up product posting groups and business posting groups for Withholding tax (WHT) in the New Zealand version of Business Central.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: withholding tax, withholding tax setup, product posting groups, business posting groups, New Zealand version
ms.search.form: 28041, 28042, 28043, 118
ms.date: 10/23/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Set up withholding tax in the New Zealand version

Withholding tax (WHT) reduces the amount paid to a vendor by the tax withheld. You pay the withheld tax to Inland Revenue under the rules for the type of payment. WHT isn't reported through an Australian Business Activity Statement (BAS).

Before you configure WHT, confirm which payments require deductions and the applicable rates, thresholds, and exemptions. A missing IRD number doesn't make every supplier payment subject to WHT. Learn more in [Withholding tax](withholding-tax.md).

To use withholding tax, you must set up the business posting groups and product posting groups for withholding tax so that the correct WHT calculations are made for each vendor.  

[!INCLUDE [wht-posting-group-setup](../includes/AUNZ/wht-posting-group-setup.md)]

## Related information

- [Set Up Revenue Types for Withholding Tax](how-to-set-up-revenue-types-for-withholding-tax.md)
- [View Withholding Tax Entries](how-to-view-withholding-tax-entries.md)
- [Calculate and Post Withholding Tax Settlements](how-to-calculate-and-post-withholding-tax-settlements.md)
- [Withholding Tax](withholding-tax.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
