---
title: Electronic invoicing in Germany
description: The following article provides information about how to work with the German localization of the E-Document framework.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords:
ms.search.form: 
ms.date: 12/12/2024
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: solsen
---

# Electronic invoicing in Germany

The following article provides information about how to work with the German localization of the E-Document framework.

## E-Documents framework setup

Read detailed information how to set up the E-Documents framework [here](../../finance-how-setup-edocuments.md).  

## Set up local formats  

> [!NOTE]
> Currently, the E-Document framework for the German localization supports the XRechnung (UBL) and Peppol BIS 3 formats. The ZUGFeRD format isn't supported yet.

To set up the format for the E-Document service, follow these steps:  

1. Select the [!Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **E-Document Services**, and then select the related link.
2. Select **New**, and on the **E-Document Services** page, on the **General** FastTab, in the **Document Format** field, choose **PEPPOL BIS 3.0** or **XRechnung**.  
3. Configure the fields as described in [Set up e-documents](../../finance-how-setup-edocuments.md).
4. Close the page.

## Working with E-invoices

Read detailed information about how to use the E-Documents framework in purchase [Use e-documents in the purchases process](../../finance-how-use-edocuments-purchase.md) and in the sales [Use e-documents in the sales process](../../finance-how-use-edocuments.md).  

> [!NOTE]
> E-invoicing in purchase is available starting with version 25.2. We will enable sales in version 25.3.  

## Related information

[Set up e-documents](../../finance-how-setup-edocuments.md)  
[How to use e-documents in sales](../../finance-how-use-edocuments.md)  
[How to use e-documents in purchase](../../finance-how-use-edocuments-purchase.md)  
[Germany Local Functionality](germany-local-functionality.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
