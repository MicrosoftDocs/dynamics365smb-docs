---
title: Electronic invoicing in Germany
description: The following article provides information on how to work with the German localization of the E-Document framework.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: E-Documents, E-Document framework
ms.search.form: 
ms.date: 01/16/2025
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: soumramani
---

# Electronic invoicing in Germany

The following article provides information on how to work with the German localization of the E-Document framework.

## E-Documents framework setup

Read detailed information on how to set up the E-Documents framework [here](../../finance-how-setup-edocuments.md).  

### Set up local formats  

> [!NOTE]
> Currently, the E-Document framework for the German localization supports the XRechnung (UBL) and Peppol BIS 3 formats. The ZUGFeRD format isn't supported yet.

To set up the format for the E-Document service, follow these steps:  

1. Select the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **E-Document Services**, and then select the related link. The **E-Document Services** page displays.
2. On the **General** FastTab, select **New**. In the **Document Format** field, choose **PEPPOL BIS 3.0** or **XRechnung**.  
3. Configure the fields as described in [Set up e-documents](../../finance-how-setup-edocuments.md).
4. Close the page.

### Using buying reference on the E-invoice

When you configure e-invoices in the sales process, make sure to display your buyer reference on the invoice. Follow these steps to set up how you use buyer references:  

1. Select the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **E-Document Services**, and then select the related link. The **E-Document Services** page displays.
2. On the **Export** FastTab, select the **Buyer Reference Mandatory** field to specify whether the buyer reference is mandatory for the document.
3. Select where you use buyer references by choosing one of the options in the **Buyer Reference** field.  
   1. If you choose the **Your reference** option, you're required to populate the **Your reference** field on the sales document.
   2. If you choose the **Customer reference**, the system uses the **E-Invoice Routing No** from the **Customer** card.  
4. Close the page.

## Working with E-invoices

Read detailed information about how to use the [E-Documents framework in purchase processes](../../finance-how-use-edocuments-purchase.md) and in [sales processes](../../finance-how-use-edocuments.md).  

> [!NOTE]
> E-invoicing in purchase processes is available starting with version 25.2, and its enablement in the sales starting from version 25.3.  

## Related information

[Set up e-documents](../../finance-how-setup-edocuments.md)  
[How to use e-documents in sales](../../finance-how-use-edocuments.md)  
[How to use e-documents in purchase](../../finance-how-use-edocuments-purchase.md)  
[Germany Local Functionality](germany-local-functionality.md)  
[!INCLUDE[footer-include](../../includes/footer-banner.md)]
