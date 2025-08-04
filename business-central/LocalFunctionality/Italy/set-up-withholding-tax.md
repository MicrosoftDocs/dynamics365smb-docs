---
title: Set Up Withholding Tax (IT)
description: Learn how to set up withholding tax in the Italian version of Business Central, ensuring compliance for third-party services and vendor purchases.
author: brentholtorf
ms.topic: how-to
ms.search.keywords: set up withholding tax, withholding tax, withholding tax codes, vendor withholding tax, calculate withholding tax, purchase invoices, purchase invoice withholding tax, vendor payments, Italian version
ms.date: 05/23/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up withholding tax in the Italian version

Companies must pay withholding tax to the government for third-party services and vendor purchases. Withholding tax is calculated during invoice payment rather than during invoice posting.

## Steps to set up withholding tax codes

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Withholding Tax**, and then choose the link for the **Code** page.  

1. In the **Code** page, to add a new withholding code, choose the **New** action, and then enter information into the relevant fields. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)]

1. To add lines to the withholding tax code, choose the **Withhold Code Lines** action.

1. Enter information into the relevant fields. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)]

1. Repeat these steps for additional codes.  

## Set up withholding tax for vendors

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then choose the related link.

1. Open the relevant vendor's vendor card.

1. Fill in the relevant fields. Specifically for withholding tax purposes, you must add the following information:

    - The vendor's personal data.
    - The contact details for the vendor.
    - The invoicing details for the vendor.
    - The payment information for the vendor.
    - The subcontracting information for the vendor.
    - The foreign trade information for the vendor.
    - The relevant fields on the **Free Lance Fee** FastTab, such as the **Withholding Tax Code** field.

## Calculate withholding tax for purchase invoices

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Invoices**, and then choose the related link.

1. Open the relevant purchase invoice.

1. Choose the **Withhold Taxes-Soc. Sec.** action.

1. In the **Withh. Taxes-Contribution Card** page, review the information in the various fields, and make sure that the **Withholding Tax Code** field specifies the right code for the vendor.

1. To calculate the withholding tax amount before posting, choose the **Calculate** action.  

## Make a vendor payment

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Journals**, and then choose the related link.

1. To create a new payment journal line, enter the relevant information in the fields.

1. To make a vendor payment, choose the **Post** action.  

    > [!NOTE]
    > The amount in the new line in the **Payment Journal** page is the withholding tax payment amount.

## Related information

- [Print Withholding Tax Reports](how-to-print-withholding-tax-reports.md)  
- [Set Up VAT](../../finance-setup-vat.md)  
- [Record VAT](../../finance-how-report-vat.md)  
- [Italy Local Functionality](italy-local-functionality.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
