---
title: Use non-deductible VAT
description: This article explains how to use and report non-deductible VAT.
author: altotovi
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.search.keywords: VAT, non-deductible, return, settlement
ms.search.form: 50, 51, 52, 161, 187, 317, 403, 6640, 9401
ms.date: 04/26/2023
ms.custom: bap-template
ms.reviewer: bholtorf
---

# Use non-deductible VAT

This article explains how to use and report non-deductible VAT.

## Create a purchase invoice with non-deductible VAT

1. Select the ![Lightbulb that opens the Tell Me feature 3.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Invoices**, and then select the related link.
2. Select **New** to create a purchase invoice, and enter the appropriate information on the invoice header.
3. In the **Lines** section, create a new line of any type, based on the VAT business posting group and the VAT product posting group where you configure non-deductible VAT.
4. In the **Quantity** and **Direct Unit Cost** fields, enter appropriate values.

    If you selected the **Show Non-Ded. VAT In Lines** checkbox on the **VAT Setup** page, the amounts in the **Non-Deductible VAT Base** and **Non-Deductible VAT Amount** fields are calculated based on the **Non-Deductible VAT %** field on the **VAT Posting Setup** page.

5. Post the invoice.

## Create a purchase order with non-deductible VAT

1. Select the ![Lightbulb that opens the Tell Me feature 3.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders** and then select the related link.
2. Select **New** to create a purchase order, and enter the appropriate information on the document header.
3. In the **Lines** section, create a new line of any type, based on the VAT business posting group and the VAT product posting group where you configure non-deductible VAT.
4. In the **Quantity** and **Direct Unit Cost** fields, enter appropriate values.

    If you selected the **Show Non-Ded. VAT In Lines** checkbox on the **VAT Setup** page, the amounts in the **Non-Deductible VAT Base** and **Non-Deductible VAT Amount** fields are calculated based on the **Non-Deductible VAT %** field on the **VAT Posting Setup** page.

5. Post the purchase order.

## Adjust rounded VAT amounts before document posting

If VAT amounts aren't rounded in the same way in your environment and in the external accounting system (the original invoice document), you can adjust the VAT amount before you post the document. To make this adjustment, follow these steps before you post the document.

1. On the Action Pane, select **Statistic**.
2. If you're working with a purchase invoice, follow these steps:

    1. On the **Lines** FastTab, select the VAT amount or non-deductible VAT amount.
    2. Set the values that you need from the original document, and then close the **Purchase Invoice Statistics** page.

3.	If you're working with the purchase order, follow these steps:

    1. On the **Invoicing** FastTab, select **No. of Tax Lines** to open the **VAT Amounts Lines** page.
    2. Select the VAT amount or non-deductible VAT amount that you want to correct.
    3. Enter the values that you need from the original document, close the **VAT Amount lines** page, and then close the **Purchase Order Statistics** page.

To use adjustments of VAT amounts, you must enable the adjustments. On the **General Ledger Setup** page, in the **Max. VAT Difference Allowed** field, enter the maximum allowed VAT amount for correction. Then, on the **Purchases & Payables Setup** page, select **Allow VAT Difference**.

You can adjust the values of the **VAT Amount** and **Non-Deductible VAT Amount** fields. The value of the **Deductible VAT Amount** field is the result of these two values. The amount that you enter in the **Non-Deductible VAT Amount** field can't be more than the amount that you enter in the **VAT Amount** field. The **Max. VAT Difference Allowed** field on the **General Ledger Setup** page works independently for deductible and non-deductible VAT amounts on statistic pages when you want to adjust VAT amounts.

> [!IMPORTANT]
> You can't use non-deductible VAT on the prepayment invoices.

## Related information

[Financial Management](finance.md)

[Set Up Calculations and Posting Methods for Value-Added Tax](finance-setup-vat.md)  

[Set up Non-deductible VAT](finance-setup-nondeductible-vat.md)

[Design details about non-deductible VAT](design-details-nondeductible-vat.md)

[Report VAT to Tax Authorities](finance-how-report-vat.md)

[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
