---
title: Set Up Reverse Charges on VAT [UK]
description: Learn how you can use reverse charge VAT accounting for a specific range of items to prevent Missing Trader Intercommunity Fund Fraud (MTIC).
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: MTIC, Missing Trader Intercommunity Fund Fraud, reverse charge VAT, VAT accounting
ms.search.form:
ms.date: 02/19/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up reverse charge VAT in the British version

In [!INCLUDE[prod_short](../../includes/prod_short.md)], you can use reverse charge VAT accounting for a specific range of items to prevent Missing Trader Intercommunity Fund Fraud (MTIC), also known as carousel fraud. This feature is supplemented by the **Reverse Charge Sales List** report. The VAT accounting changes affect companies trading in electronic goods and integrated circuit devices, such as mobile telephones, microprocessors, and central processing units. These goods apply to reverse charges.

> [!IMPORTANT]  
> Legislative information may be subject to change by HM Revenue & Customs (HMRC). For more information, see the [HMRC website](https://www.gov.uk/government/organisations/hm-revenue-customs).  

## Reverse charges on VAT  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Business Posting Groups**, and then choose the related link.  
1. Create a new VAT business posting group. Set up the needed VAT product posting groups.  
1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Ledger Setup**, and then choose the related link.  
1. On the **Reverse Charge** FastTab, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](../../includes/tooltip-inline-tip_md.md)]  
1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales & Receivables Setup**, and then choose the related link.  
1. On the **Reverse Charge** FastTab, fill in the fields as necessary.
1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchases & Payables Setup** and then choose the related link.  
1. On the **Reverse Charge** FastTab, fill in the fields as necessary.
1. To set up items subject to reverse charge, select the item, and open the **Item Card** page.  
1. On the **Invoicing** FastTab, fill in the **Reverse Charge Applies** field.  

## Reverse charge sales list

This report displays sales of goods which are subject to reverse charge. The report is based on information in the VAT Entry table. You use it to report to the customs and tax authorities the reverse charge sales.  

Examples of goods subject to reverse charge:  

- Mobile telephones.  
- Computer chips  

Consult the [HMRC website](https://www.gov.uk/government/organisations/hm-revenue-customs) for the list of goods subject to reverse charge.  

## Related information

[United Kingdom Local Functionality](united-kingdom-local-functionality.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
