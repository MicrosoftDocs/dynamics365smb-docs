---
title: Reporting GST/HST in Canada
description: Learn about how to report local sales tax, and goods and services tax in Canada.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: sales tax, local
ms.date: 06/25/2021
ms.author: bholtorf

---
# Reporting Goods/Services Tax and Harmonized Sales Tax in Canada

In Canada, when a vendor does not have a business presence in the province in which purchases are made, the vendor will charge the Goods and Services Tax (GST) or Harmonized Sales Tax (HST) only. However, if the province has a Provincial Sales Tax (PST), then the purchaser must still calculate the PST and pay it directly to the province. When a Provincial Tax Area Code is selected, [!INCLUDE[prod_short](../../includes/prod_short.md)] uses it to calculate the PST and post it so that there is a tax liability in both the general ledger and the tax entry records. Therefore, the tax area code selected here should be one where only the PST is included, not the GST.  

## Submitting the GST/HST File

The tax information in purchase documents is used to generate a GST/HST online file transfer that you must provide to the tax authorities. This file includes goods and services tax (GST) and harmonized sales tax (HST). The file is created in a .tax file format, which can be transferred online. Use the GST/HST Internet File Transfer batch job to generate the .tax file.

## See Also

[Canada Local Functionality](canada-local-functionality.md)  
[Finance](../../finance.md)  
[Setting Up Finance](../../finance-setup-finance.md)  
[Reporting Sales Tax in Canada](ca-sales-tax.md)  
[Work with [!INCLUDE[prod_short](../../includes/prod_short.md)]](../../ui-work-product.md)
[Set Up Calculations and Posting Methods for Value-Added Tax](../../finance-setup-vat.md)  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]