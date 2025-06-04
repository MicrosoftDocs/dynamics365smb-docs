---
title: Reporting GST/HST in Canada
description: Learn how to report local sales tax, goods and services tax in Canada.
author: brentholtorf
ms.topic: concept-article
ms.devlang: al
ms.search.keywords: sales tax, local
ms.date: 02/04/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Reporting goods/services tax and harmonized sales tax in Canada

In Canada, when a vendor doesn't have a business presence in the province in which purchases are made, the vendor charges the Goods and Services Tax (GST) or Harmonized Sales Tax (HST) only. However, if the province has a Provincial Sales Tax (PST), then the purchaser must still calculate the PST and pay it directly to the province. When a Provincial Tax Area Code is selected, [!INCLUDE[prod_short](../../includes/prod_short.md)] uses it to calculate the PST and post it so that there's a tax liability in both the general ledger and the tax entry records. Therefore, the tax area code selected here should be one where only the PST is included, not the GST.  

## Submitting the GST/HST file

The tax information in purchase documents is used to generate a GST/HST online file transfer that you must provide to the tax authorities. This file includes goods and services tax (GST) and harmonized sales tax (HST). The file is created in a *.tax* file format, which can be transferred online. Use the GST/HST Internet File Transfer batch job to generate the *.tax* file.

## Related information

- [Canada Local Functionality](canada-local-functionality.md)  
- [Finance](../../finance.md)  
- [Setting Up Finance](../../finance-setup-finance.md)  
- [Reporting Sales Tax in Canada](ca-sales-tax.md)  
- [Work with [!INCLUDE[prod_short](../../includes/prod_short.md)]](../../ui-work-product.md)
- [Set Up Calculations and Posting Methods for Value-Added Tax](../../finance-setup-vat.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
