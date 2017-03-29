---
title: Sales Tax and Goods and Services Tax in Canada | Microsoft Docs
description: Learn about GST and HST.
services: project-madeira
documentationcenter: ''
author: edupont04

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: sales tax, local
ms.date: 03/23/2017
ms.author: edupont

---
# Sales Tax and Goods and Services Tax in Canada
In Canada, when a vendor does not have a business presence in the province in which purchases are made, the vendor will charge the Goods and Services Tax (GST) or Harmonized Sales Tax (HST) only. However, if the province has a Provincial Sales Tax (PST), then the purchaser must still calculate the PST and pay it directly to the province. When a Provincial Tax Area Code is selected, [!INCLUDE[d365fin](includes/d365fin_md.md)] uses it to calculate the PST and post it so that there is a tax liability in both the general ledger and the tax entry records. Therefore, the tax area code selected here should be one where only the PST is included, not the GST.  

For more information about sales tax, see [Sales Tax and Tax Groups in the US and Canada](us-finance-sales-tax.md).  

## Submitting the GST/HST File
The tax information in purchase documents is used to generate a GST/HST online file transfer that you must provide to the tax authorities. This file includes goods and services tax (GST) and harmonized sales tax (HST). The file is created in a .tax file format, which can be transferred online.  

## See Also
[Finance](finance.md)  
[Setting Up Finance](finance-setup-finance.md)  
[Sales Tax and Tax Groups in the US and Canada](us-finance-sales-tax.md)  
[Working With [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
