---
title: Use Nondeductible VAT in Business Central
description: Use nondeductible VAT on purchase invoices and orders in Business Central, and adjust VAT rounding differences before you post purchase documents.
author: altotovi
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.search.keywords: VAT, non-deductible, return, settlement
ms.search.form: 50, 51, 52, 161, 187, 317, 403, 6640, 9401
ms.date: 11/11/2026
ms.custom: bap-template
ms.reviewer: bholtorf
ai-usage: ai-assisted
---

# Use nondeductible VAT in Business Central

This article explains how to use nondeductible VAT on purchase documents and adjust rounding differences before posting.

## Create a purchase invoice with nondeductible VAT

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Purchase Invoices**, and then select the related link.
1. Select **New** to create a purchase invoice, and enter the appropriate information on the invoice header.
1. In the **Lines** section, create a line with the VAT business posting group and VAT product posting group that you configured for nondeductible VAT.
1. In the **Quantity** and **Direct Unit Cost** fields, enter appropriate values.
1. Post the invoice.

The nondeductible VAT amounts are calculated from **Non-Deductible VAT %** on the **VAT Posting Setup** page. To show **Non-Deductible VAT Base** and **Non-Deductible VAT Amount** on the lines, select **Show Non-Ded. VAT In Lines** on the **VAT Setup** page.

## Create a purchase order with nondeductible VAT

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Purchase Orders**, and then select the related link.
1. Select **New** to create a purchase order, and enter the appropriate information on the document header.
1. In the **Lines** section, create a line with the VAT business posting group and VAT product posting group that you configured for nondeductible VAT.
1. In the **Quantity** and **Direct Unit Cost** fields, enter appropriate values.
1. Post the purchase order.

The nondeductible VAT amounts are calculated from **Non-Deductible VAT %** on the **VAT Posting Setup** page. To show **Non-Deductible VAT Base** and **Non-Deductible VAT Amount** on the lines, select **Show Non-Ded. VAT In Lines** on the **VAT Setup** page.

## Adjust rounded VAT amounts before document posting

If VAT amounts aren't rounded in the same way in your environment and in the external accounting system (the original invoice document), you can adjust the VAT amount before you post the document. To make this adjustment, follow these steps before you post the document.

1. On the action bar, select **Statistics**.
1. If you're working with a purchase invoice, follow these steps:

    1. In **Lines**, select the VAT amount or nondeductible VAT amount.
    1. Enter the values from the original document, and then close the **Purchase Invoice Statistics** page.

1. If you're working with a purchase order, follow these steps:

    1. On the **Invoicing** FastTab, select **No. of Tax Lines** to open the **VAT Amount Lines** page.
    1. Select the VAT amount or nondeductible VAT amount that you want to correct.
    1. Enter the values from the original document, close the **VAT Amount Lines** page, and then close the **Purchase Order Statistics** page.

To use adjustments of VAT amounts, you must enable the adjustments. On the **General Ledger Setup** page, in the **Max. VAT Difference Allowed** field, enter the maximum allowed VAT amount for correction. Then, on the **Purchases & Payables Setup** page, select **Allow VAT Difference**.

You can adjust the values of the **VAT Amount** and **Non-Deductible VAT Amount** fields. **Deductible VAT Amount** is the VAT amount minus the nondeductible VAT amount. The amount that you enter in **Non-Deductible VAT Amount** can't be more than the amount in **VAT Amount**. **Max. VAT Difference Allowed** on the **General Ledger Setup** page is checked independently for VAT and nondeductible VAT adjustments on statistics pages.

> [!IMPORTANT]
> You can't use nondeductible VAT on prepayment invoices.

## Related information

[Financial Management](finance.md)

[Set Up Calculations and Posting Methods for Value-Added Tax](finance-setup-vat.md)  

[Set up nondeductible VAT](finance-setup-nondeductible-vat.md)

[Design details about nondeductible VAT](design-details-nondeductible-vat.md)

[Report VAT to Tax Authorities](finance-how-report-vat.md)

[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
