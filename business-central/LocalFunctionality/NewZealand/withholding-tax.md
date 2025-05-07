---
title: Withholding Tax in the New Zealand version
description: Learn about withholding tax (WHT) scenarios in New Zealand and how to manage them effectively.
author: brentholtorf
ms.topic: concept-article
ms.devlang: al
ms.search.keywords: withholding tax scenarios, BAS submission, IRD number, New Zealand version 
ms.search.form: 11600, 28040,28041,28042,28043,28044, 28164,28165,28166,28167
ms.date: 05/07/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Withholding tax in the New Zealand version

Withholding Tax (WHT) is tax withheld by a company when making a payment to a vendor, in which the full amount owed to that vendor is reduced by the tax withheld. The withheld tax is then remitted to tax authorities during the next Business Activity Statement (BAS) submission.  

The New Zealand government requires taxes to be withheld from payment to vendors under the following circumstances:  

- The vendor is a local supplier who hasn't supplied an New Zealand Inland Revenue Department number (IRD) before the payment is processed, and the individual transaction amount is greater than the specified threshold amount.  
- The vendor is a non-resident supplier and the payment is to be made to this non-resident entity in the form of interest, royalty, or dividend payments. Currently, there's no minimum threshold amount. Withholding rates may vary due to payment, or international tax treaties existing between New Zealand and the vendor's country/region.  

Fields within **WHT Business Posting Groups** and **WHT Product Posting Groups** must be set up on the **WHT Posting Setup** page so that the correct WHT calculations are made for each vendor.  

- **WHT Calculation Rule** – This field controls how calculation applies to the **WHT Minimum Invoice Amount**, or the invoice threshold amount. The following options exist:  

  - **Less than**  
  - **Less than or equal to**  
  - **Equal to**  
  - **Greater than**  
  - **Greater than or equal to**

In New Zealand, WHT isn't calculated if the individual invoice amount is less than or equal to the threshold amount. Companies should select **Less than or equal to**.  

- **WHT Minimum Invoice Amount** – Enter the invoice threshold amount. 
- **WHT %** – Enter the relevant WHT rate for the particular combination of **WHT Business Posting Group** and **WHT Product Posting Group**. If you don't wish to calculate any withholding amount, enter 0.00.
- **Realised WHT Type** – Select **Payment** to calculate only the withholding amount at the time of payment. The other options of **Invoice** and **Earliest** don't apply to New Zealand.
- **Payable WHT Account Code** – Enter the number of the G/L account to which you want to post **Purchase WHT** for the particular combination of **WHT Business Posting Group** and **WHT Product Posting Group**. 
- **Purch. WHT Adjustment Account No.** – Select an account number for **Purchase CR/Adj Note** adjustments.
- **Revenue Types** – Drill down to the **WHT Revenue Types** page. These values determine how the combinations of WHT Business Posting Group and WHT Product Posting Group are displayed in reports. You must enter a value in order for this combination to appear in the WHT reports.

## WHT for suppliers without an IRD

Ensure that there's a valid combination of **General Business** and **General Product Posting Groups** with the correct threshold. For example, in New Zealand today, the minimum threshold is $75 with a rate of 46.50%.  

The percentage withheld is specified in **WHT Posting Setup**. The amount to be withheld is calculated automatically at the time of payment. The WHT certificate is printed automatically, and then sent to the vendor with payment. The WHT certificate explains the reasons for not sending the full invoiced amount.  

## WHT for foreign suppliers

Ensure that a valid combination of **General Business** and **General Product Posting Groups** is established for vendors for whom you need to withhold tax,other than for non-IRD.  

## Related information

- [Set Up Withholding Tax](how-to-set-up-withholding-tax.md)
- [Set Up Vendors Without IRD for Calculating the Withholding Tax](how-to-set-up-vendors-without-abn-for-calculating-the-withholding-tax.md)
- [Set Up Revenue Types for Withholding Tax](how-to-set-up-revenue-types-for-withholding-tax.md)
- [Calculate and Post Withholding Tax Settlements](how-to-calculate-and-post-withholding-tax-settlements.md)
- [View Withholding Tax Entries](how-to-view-withholding-tax-entries.md)
- [New Zealand Local Functionality](new-zealand-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
