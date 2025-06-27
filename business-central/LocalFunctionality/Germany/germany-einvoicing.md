---
title: Electronic invoicing in Germany
description: Learn how to set up and work with the German localization of the E-Document framework.
author: altotovi
ms.topic: article
ms.devlang: al
ms.search.keywords: E-Documents, E-Document framework, UBL, Peppol, German version
ms.search.form: 
ms.date: 03/10/2025
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Electronic invoicing in Germany

This article provides information on how to work with the German localization of the E-Document framework.

## E-Documents framework setup

Learn more in [Set up e-documents](../../finance-how-setup-edocuments.md), which provides information about setting up the E-Documents framework.

### Set up local formats  

> [!NOTE]
> Starting with version 26.3, the E-Document framework for the German localization supports all formats availeble in Germany: XRechnung (UBL only), Peppol BIS 3, and ZUGFeRD.  

To set up the format for the E-Document service, follow these steps:  

1. Select the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **E-Document Services**, and then select the related link. The **E-Document Services** page displays.
2. On the **General** FastTab, select **New**. In the **Document Format** field, choose **PEPPOL BIS 3.0 DE**, **XRechnung** or **ZUGFeRD**.  
3. Configure the fields as described in [Set up e-documents](../../finance-how-setup-edocuments.md).
4. Close the page.

### Use buyer reference on the E-invoice

When you configure e-invoices in the sales process, make sure to display your buyer reference on the invoice. Follow these steps to set up how you use buyer references:  

1. Select the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **E-Document Services**, and then select the related link. The **E-Document Services** page displays.
1. On the **Export** FastTab, select the **Buyer Reference Mandatory** field to specify whether the buyer reference is mandatory for the document.
1. Select where you use buyer references by choosing one of the options in the **Buyer Reference** field.  
   1. If you choose the **Your reference** option, you're required to populate the **Your reference** field on the sales document.
   1. If you choose the **Customer reference**, the system uses the **E-Invoice Routing No** from the **Customer** card.  
1. Close the page.

## Work with E-invoices

### Purchase process 

Learn more in [Use e-documents in the purchases process](../../finance-how-use-edocuments.md), which provides information about the E-Documents framework in purchase processes.  

To receive all three supported file formats, you must create a separate E-Document Service for each one, specifying the desired format in the Document Format field. The process of receiving and creating E-Documents is fully automated, requiring no manual intervention. This includes ZUGFeRD, which is a PDF/A format—Business Central will automatically extract the embedded XML file and process it as a new E-Document.  

> [NOTE!]
> Automated **E-Document** creation does not imply automatic creation of purchase invoices. To enable this process, proper configuration is required, or, in the case of purchase orders, the use of purchase order matching is necessary.  

### Sales process 

Learn more in [Use e-documents in the purchases process](../../finance-how-use-edocuments.md), which provides information about the E-Documents framework in purchase processes.  

Since there are three available file formats, you’ll need to decide whether to use one or multiple formats based on your sales process. You can define different workflows and specify the desired file format for each. Note that each **Document Sending Profile** supports only one file format, so it’s not possible to assign multiple formats to a single customer. 

## Related information

- [Set up e-documents](../../finance-how-setup-edocuments.md)  
- [How to use e-documents in sales](../../finance-how-use-edocuments.md)  
- [How to use e-documents in purchase](../../finance-how-use-edocuments-purchase.md)  
- [Germany Local Functionality](germany-local-functionality.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
