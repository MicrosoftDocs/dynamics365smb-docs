---
title: Set Up Reverse Charges on VAT [UK]
description: Learn how you can use reverse charge VAT accounting for a specific range of items to prevent Missing Trader Intercommunity Fund Fraud (MTIC).
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: MTIC, Missing Trader Intercommunity Fund Fraud, reverse charge VAT, VAT accounting
ms.search.form:
ms.date: 10/19/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Set up reverse charge VAT in the British version

In [!INCLUDE[prod_short](../../includes/prod_short.md)], you can use reverse charge VAT accounting for a specific range of items to prevent Missing Trader Intercommunity Fund Fraud (MTIC), also known as carousel fraud. This feature is supplemented by the **Reverse Charge Sales List** report. The VAT accounting changes affect companies trading in electronic goods and integrated circuit devices, such as mobile telephones, microprocessors, and central processing units. These goods apply to reverse charges.

> [!IMPORTANT]  
> Legislative information may be subject to change by HM Revenue & Customs (HMRC). For more information, see the [HMRC website](https://www.gov.uk/government/organisations/hm-revenue-customs).  

## Reverse charges on VAT

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **VAT Business Posting Groups**, and then choose the related link.
1. Create a new VAT business posting group. Set up the needed VAT product posting groups.  
1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **General Ledger Setup**, and then choose the related link.
1. On the **Reverse Charge** FastTab, turn on **Threshold applies**, and enter the applicable **Threshold Amount**. The amount field is available only when **Threshold applies** is turned on. Confirm the appropriate threshold with HMRC.
1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Sales & Receivables Setup**, and then choose the related link.
1. On the **Reverse Charge** FastTab, specify **Reverse Charge VAT Posting Gr.** for reverse charge sales, **Domestic Customers** for domestic UK customers, and **Invoice Wording** for the text to print on reverse charge invoices.
1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Purchases & Payables Setup**, and then choose the related link.
1. On the **Reverse Charge** FastTab, specify **Reverse Charge VAT Posting Gr.** for reverse charge purchases and **Domestic Vendors** for domestic UK vendors.
1. To set up items subject to reverse charge, select the item, and open the **Item Card** page.  
1. On the **Prices & Sales** FastTab, turn on **Reverse Charge Applies**.

For sales, the automatic reverse charge check also requires a VAT registration number on the document and a VAT business posting group that matches **Domestic Customers**. The amount to invoice for reverse charge items must meet the configured threshold.

## Reverse charge sales list

This report displays sales of goods which are subject to reverse charge. The report is based on information in the VAT Entry table. You use it to report to the customs and tax authorities the reverse charge sales.  

Examples of goods subject to reverse charge:  

- Mobile telephones.  
- Computer chips  

Consult the [HMRC website](https://www.gov.uk/government/organisations/hm-revenue-customs) for the list of goods subject to reverse charge.  

To export a CSV file from the report, select **Create Submission File** on the report request page. Use **Calendar Source** to choose **System** or **AccPeriod** for the reporting periods.

## Related information

[United Kingdom Local Functionality](united-kingdom-local-functionality.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
