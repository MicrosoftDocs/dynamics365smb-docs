---
title: VAT Registration No. for Intrastat [DK]
description: Learn how to set up a VAT registration number as specified by the Danish Intrastat requirements.
author: altotovi
ms.reviewer: v-soumramani
ms.topic: conceptual
ms.search.keywords: VAT registration number, Intrastat, Denmark
ms.search.form: 328
ms.date: 03/04/2025
ms.author: altotovi
ms.service: dynamics-365-business-central
---

# VAT registration number setup for Intrastat in the Danish version

[!INCLUDE[intrastat-2022w2](../../includes/intrastat-2022w2.md)]

In Denmark, the VAT-VIES requirements mean that you specify a unique VAT number in the **VAT Registration No** field on the customer or vendor cards. But reporting for Intrastat requires a VAT registration number in the submitted files that consists of the country code and the VAT registration number.

## Set up VAT registration numbers for Intrastat

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Setup**, and then choose the related link.  
1. To specify how the VAT number for customers should be created in the Intrastat file, choose one of the available options in the **Customer VAT No. on File** field. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)]  
1. To specify how the VAT number for vendors should be created in the Intrastat File, choose one of the available options in the **Vendor VAT No. on File** field.  

You can choose between the following options:

* VAT registration number  
* Country code + VAT registration number  
* VAT registration number without the country code  

Depending on your choices, the relevant numbers are concatenated from the values of the **VAT Reg. No.** and **EU Country Code** fields.  

## Related information

- [Denmark Local Functionality](denmark-local-functionality.md)  
- [Set Up Intrastat Reporting](../../finance-how-setup-report-intrastat.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
