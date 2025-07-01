---
title: Set Up Withholding Tax [AU]
description: Learn how a company sets up withholding tax (WHT) for vendor payments on the General Ledger Setup page.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: withholding tax, WHT, vendor payments, general ledger setup, product posting groups, business posting groups, Australian Taxation Office, ATO, business activity statement, BAS, Australian business number, ABN, Australian version
ms.search.form: 28041, 28042, 28043, 118
ms.date: 03/27/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up Withholding Tax in the Australian version

Withholding Tax (WHT) is the tax withheld by a company when it makes a payment to a vendor, in which the full amount owed to the vendor is reduced by the tax withheld. The withheld tax is then remitted to the Australian Taxation Office (ATO) when the next Business Activity Statement (BAS) is submitted.  

If a supplier without an Australian Business Number (ABN) provides an invoice, a withholding tax amount must be withheld if the total amount of the invoice is more than the threshold amount. To use withholding tax, you must first enable WHT in the **General Ledger Setup** page and set up product posting groups and business posting groups for WHT.  

## Enable Withholding Tax

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Ledger Setup**, and then choose the related link.  
1. On the **Local Functionalities** FastTab, choose the **Enable WHT** field.  
1. Optionally, choose the **Round Amount for WHT Calc** field.

    If you choose this field, all WHT amounts are rounded down to the nearest number. For example, if the WHT amount on an invoice is calculated to be 33.90, and the **Round Amount for WHT Calc** field is chosen in the General Ledger Setup, then the WHT amount is rounded to 33.

[!INCLUDE [wht-posting-group-setup](../includes/AUNZ/wht-posting-group-setup.md)]

## Related information

- [Set Up Revenue Types for Withholding Tax](how-to-set-up-revenue-types-for-withholding-tax.md)  
- [View Withholding Tax Entries](how-to-view-withholding-tax-entries.md)  
- [Calculate and Post Withholding Tax Settlements](how-to-calculate-and-post-withholding-tax-settlements.md)  
- [Withholding Tax](withholding-tax.md)  
- [Australian Taxation Office (ATO)](https://www.ato.gov.au/)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
