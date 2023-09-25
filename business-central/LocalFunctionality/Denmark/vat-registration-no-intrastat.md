---
title: VAT Registration No. for Intrastat [DK]
description: Learn how to set up a VAT registration number as specified by the Danish Intrastat requirements.
author: altotovi

ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.form: 328
ms.date: 05/09/2022
ms.author: altotovi

---
# VAT Registration Number Setup for Intrastat in the Danish Version

[!INCLUDE[intrastat-2022w2](../../includes/intrastat-2022w2.md)]

In Denmark, the VAT-VIES requirements mean that you specify a unique VAT number in the **VAT Registration No** field on the customer or vendor cards. But reporting for Intrastat requires a VAT registration number in the submitted files that consists of the country code and the VAT registration number.

## To set up VAT registration numbers for Intrastat

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Setup**, and then choose the related link.  
2. To specify how the VAT number for customers will be created in the Intrastat file, choose one of the available options in the **Customer VAT No. on File** field. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)]  
3. To specify how the VAT number for vendors will be created in the Intrastat File, choose one of the available options in the **Vendor VAT No. on File** field.  

You can choose between the following options:

* VAT registration number  
* Country code + VAT registration number  
* VAT registration number without the country code  

Depending on your choices, the relevant numbers will be concatenated from the values of the **VAT Reg. No.** and **EU Country Code** fields.  

## See also

[Denmark Local Functionality](denmark-local-functionality.md)  
[Set Up Intrastat Reporting](../../finance-how-setup-report-intrastat.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
