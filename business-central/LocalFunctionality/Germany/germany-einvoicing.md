---
title: Electronic Invoicing in Germany
description: The following article provides information how to work with German localization of E-Document framework.
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

# Electronic Invoicing in Germany

The following article provides information about how to work with the German localization of the E-Document framework.

## E-Documents Framework Setup

Read detailed information how to set up the E-Documents framework [here](../../finance-how-setup-edocuments.md).  

## Local Formats Setup  

> [!NOTE] 
> Currently the E-Document for German localization supports XRechnung (UBL) and Peppol BIS 3 formats. ZUGFeRD format isn't supported yet.

Set up the format for the E-Document service by following these steps:  

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **E-Document Services**, and then select the related link.
2. Select **New**, and then, on the **E-Document Services** page, on the **General** FastTab, in the **Document Format** field choose **PEPPOL BIS 3.0** or **XRechnung**.  
3. Configure the fields as described [here](../../finance-how-setup-edocuments.md).
4. Close the page.

## Working with E-invoices

Read detailed information about how to use the E-Documents framework in purchase [here](../../finance-how-use-edocuments-purchase.md) and in the sales [here]](../../finance-how-use-edocuments.md).  

> [!NOTE]
> E-invoicing in purchase is available starting with version 25.2, and sales will be enabled from version 25.3.  

## Related information

[Set up e-documents](finance-how-setup-edocuments.md)    
[How to use e-documents in sales](finance-how-use-edocuments.md)    
[How to use e-documents in purchase](finance-how-use-edocuments-purchase.md)  
[Germany Local Functionality](germany-local-functionality.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
