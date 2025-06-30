---
title: Electronic invoicing in Germany
description: Learn how to set up and work with the German localization of the E-Document framework.
author: altotovi
ms.topic: article
ms.devlang: al
ms.search.keywords: E-Documents, E-Document framework, UBL, Peppol, German version
ms.search.form: 
ms.date: 06/30/2025
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
> Starting with version 26.3, the E-Document framework for the German localization supports all formats available in Germany: XRechnung (UBL only), Peppol BIS 3, and ZUGFeRD.  

To set up the format for the E-Document service, perform the following steps:  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **E-Document Services**, and then select the related link. The **E-Document Services** page displays.
1. On the **General** FastTab, select **New**. In the **Document Format** field, choose **PEPPOL BIS 3.0 DE**, **XRechnung** or **ZUGFeRD**.  
1. Configure the fields as described in [Set up e-documents](../../finance-how-setup-edocuments.md).
1. Close the page.

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

Learn more in [Use e-documents in the purchase process](../../finance-how-use-edocuments.md), which provides information about the E-Documents framework in purchase processes.

To receive all three supported file formats, you must create a separate E-Document Service for each format and specify the desired format in the **Document Format** field. The process of receiving and creating e-documents is fully automated and requires no manual intervention. This includes ZUGFeRD, which is a PDF/A format—Business Central automatically extracts the embedded XML file and processes it as a new e-document.

> [!NOTE]
> Automated e-document creation does not imply automatic creation of purchase invoices. To enable this process, proper configuration is required, or, in the case of purchase orders, you must use purchase order matching.

### Sales process

Learn more in [Use e-documents in the sales process](../../finance-how-use-edocuments.md), which provides information about the E-Documents framework in sales processes.

Because there are three available file formats, you must decide whether to use one or multiple formats based on your sales process. You can define different workflows and specify the file format for each. Each **Document Sending Profile** supports only one file format, so you can't assign multiple formats to a single customer.

## Related information

- [Set up e-documents](../../finance-how-setup-edocuments.md)  
- [How to use e-documents in sales](../../finance-how-use-edocuments.md)  
- [How to use e-documents in purchase](../../finance-how-use-edocuments-purchase.md)  
- [Germany Local Functionality](germany-local-functionality.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
