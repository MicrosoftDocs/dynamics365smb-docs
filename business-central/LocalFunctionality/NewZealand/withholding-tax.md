---
title: Withholding Tax in the New Zealand Version
description: Learn how to configure withholding tax rates and thresholds, manage vendor payments, and print WHT certificates in the New Zealand version.
author: brentholtorf
ms.topic: concept-article
ms.devlang: al
ms.search.keywords: withholding tax scenarios, schedular payments, IRD number, New Zealand version
ms.search.form: 11600, 28040,28041,28042,28043,28044, 28164,28165,28166,28167
ms.date: 10/23/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Withholding tax in the New Zealand version

Withholding tax (WHT) reduces the amount paid to a vendor by the tax withheld. You pay the withheld tax to Inland Revenue under the rules for the type of payment.

Before you configure WHT, identify the type of payment and check the applicable Inland Revenue rules:

- *Schedular payments* are payments to contractors for certain kinds of work. Rates, exemptions, and notification requirements depend on the contractor's circumstances. A missing IRD number doesn't make every supplier payment subject to withholding tax. See [Deductions from payments to contractors](https://www.ird.govt.nz/income-tax/withholding-taxes/schedular-payments/making-schedular-payments/deductions-from-payments-to-contractors).
- *Non-resident withholding tax* applies to New Zealand payments of interest, dividends, and royalties to non-residents. Rates can vary by payment type and any applicable tax treaty. Check the deduction and reporting obligations for these payments. See [Non-resident withholding tax](https://www.ird.govt.nz/income-tax/withholding-taxes/non-resident-withholding-tax-nrwt).

These are different tax obligations. The WHT posting setup doesn't replace the required Inland Revenue reporting or establish which payments are taxable.

Fields within **WHT Business Posting Groups** and **WHT Product Posting Groups** must be set up on the **WHT Posting Setup** page so that the correct WHT calculations are made for each vendor.  

- **WHT Calculation Rule**: This field identifies transactions for which WHT isn't deducted by comparing the invoice amount with **WHT Minimum Invoice Amount**. The following options exist:

  - **Less than**  
  - **Less than or equal to**  
  - **Equal to**  
  - **Greater than**  
  - **Greater than or equal to**

For example, if WHT must not be calculated on invoices at or below a threshold, select **Less than or equal to**. Use a threshold only when it applies to the type of payment.

- **WHT Minimum Invoice Amount**: Enter the invoice threshold amount.
- **WHT %**: Enter the relevant WHT rate for the particular combination of **WHT Business Posting Group** and **WHT Product Posting Group**. If you don't wish to calculate any withholding amount, enter 0.00.
- **Realized WHT Type**: Select **Payment** to calculate only the withholding amount at the time of payment. The other options of **Invoice** and **Earliest** don't apply to New Zealand.
- **Payable WHT Account Code**: Enter the number of the G/L account to which you want to post **Purchase WHT** for the particular combination of **WHT Business Posting Group** and **WHT Product Posting Group**.
- **Purch. WHT Adj. Account No.**: Select an account number for **Purchase CR/Adj Note** adjustments.
- **Revenue Type**: Select a value from the **WHT Revenue Types** page. These values determine how the combinations of WHT Business Posting Group and WHT Product Posting Group are displayed in reports. You must enter a value in order for this combination to appear in the WHT reports.

## WHT for suppliers without an IRD

Set up a valid combination of **WHT Business Posting Group** and **WHT Product Posting Group** with the rate and any threshold that apply to the payment. Don't use a single threshold or rate for all vendors. Confirm the notification requirements and rates in [Deductions from payments to contractors](https://www.ird.govt.nz/income-tax/withholding-taxes/schedular-payments/making-schedular-payments/deductions-from-payments-to-contractors) before you configure the setup.

The percentage withheld is specified in **WHT Posting Setup**. The amount to be withheld is calculated automatically at the time of payment. To print the certificate when you post the payment, select **Print WHT Docs. on Pay. Post** on **Purchases & Payables Setup**. You can also use **Print WHT Certificate** on **Payment Journals** before posting. Send the certificate to the vendor with the payment. The WHT certificate explains the reasons for not sending the full invoiced amount.

## WHT for foreign suppliers

Set up a valid combination of **WHT Business Posting Group** and **WHT Product Posting Group** for foreign vendors whose payments are subject to withholding tax. Confirm the applicable Inland Revenue rate and any exemptions for the type of payment.

## Related information

- [Set Up Withholding Tax](how-to-set-up-withholding-tax.md)
- [Set Up Vendors Without IRD for Calculating the Withholding Tax](how-to-set-up-vendors-without-abn-for-calculating-the-withholding-tax.md)
- [Set Up Revenue Types for Withholding Tax](how-to-set-up-revenue-types-for-withholding-tax.md)
- [Calculate and Post Withholding Tax Settlements](how-to-calculate-and-post-withholding-tax-settlements.md)
- [View Withholding Tax Entries](how-to-view-withholding-tax-entries.md)
- [New Zealand Local Functionality](new-zealand-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
