---
title: Set Up Withholding Tax in the Italian Version
description: Learn how to set up withholding tax in the Italian version of Business Central, ensuring compliance for third-party services and vendor purchases.
author: brentholtorf
ms.topic: how-to
ms.search.keywords: set up withholding tax, withholding tax, withholding tax codes, vendor withholding tax, calculate withholding tax, purchase invoices, purchase invoice withholding tax, vendor payments, Italian version
ms.date: 10/21/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Set up withholding tax in the Italian version

For purchases subject to withholding tax, set up the withholding tax code and assign it to the vendor. You can calculate and review withholding amounts on the purchase invoice before posting. The payment workflow creates the withholding tax entries when you post the payment.

## Steps to set up withholding tax codes

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Withholding Tax Codes**, and then choose the related link.

1. On the **Withholding Tax Codes** page, choose **New**, and enter the code, tax details, and **Withholding Taxes Payable Acc.** [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)]

1. To add lines to the withholding tax code, choose the **Withhold Code Lines** action.

1. Enter **Starting Date**, **Withholding Tax %**, and **Taxable Base %** for each applicable rate.

1. Repeat these steps for additional codes.  

## Set up withholding tax for vendors

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Vendors**, and then choose the related link.

1. Open the vendor card.

1. On the **Free Lance Fee** FastTab, select **Withholding Tax Code**. Review the residency, individual-person, and contribution details that apply to the vendor.

## Calculate withholding tax for purchase invoices

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Purchase Invoices**, and then choose the related link.

1. Open the relevant purchase invoice.

1. Choose the **Withhold Taxes-Soc. Sec.** action.

1. In the **Withh. Taxes-Contribution Card** page, review the information in the various fields, and make sure that the **Withholding Tax Code** field specifies the right code for the vendor.

1. To calculate the withholding tax amount before posting, choose the **Calculate** action.  

## Make a vendor payment

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Payment Journals**, and then choose the related link.

1. Create a payment journal line with **Document Type** set to **Payment**, **Account Type** set to **Vendor**, and the vendor in **Account No.** Enter the payment details and select the invoice to apply the payment to.

1. Choose the **Withh.Tax-Soc.Sec.** action, and review the withholding tax and contribution amounts.
1. Confirm the calculation. Review the adjusted vendor payment line and the generated withholding tax lines before you post.
1. Choose the **Post** action.

> [!NOTE]
> The generated withholding tax line contains the withholding amount. The original vendor payment line is adjusted for withholding and applicable contributions.

## Related information

- [Print Withholding Tax Reports](how-to-print-withholding-tax-reports.md)  
- [Set Up VAT](../../finance-setup-vat.md)  
- [Record VAT](../../finance-how-report-vat.md)  
- [Italy Local Functionality](italy-local-functionality.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
