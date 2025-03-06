---
title: Set up electronic invoicing with NemHandel
description: Learn how to set up E-documents functionality with Nemhadel in Denmark.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: electronic document, electronic invoice, e-document, e-invoice, access-point, endpoint, nemhandel, denmark, dk
ms.search.form: 359, 360, 6103, 6133
ms.date: 03/03/2025
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up electronic invoicing with NemHandel

In Denmark, you can configure your e-invoicing system to work with NemHandel by using third-party certified access points. Before you begin, read the [Set the E-Documents connector with external endpoints](../../finance-how-setup-edocuments-external.md) article for information on using e-documents with external services, and establish a contract with one of the supported external certified access point providers.

Before you begin the setup, open the **Extension management** page, and verify that the following apps are installed:

- E-Document Core
- E-Documents Connector with External Endpoints
- OIOUBL
- E-Document format for OIOUBL

In Danish E-Documents functionality, you can select OIOUBL and PEPPOL BIS 3 as document formats in **E-Document Services**.

## E-Document services setup

> [!NOTE]
> To establish these connections, it's necessary to communicate with external service providers, who may require additional payment and contracts. To obtain all the necessary credentials, contact the service providers.

To set up services, complete the following steps:

### Use OIOUBL format  

1. Select the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **E-Document Services**, and then select the related link.
1. Select **New** to create the OIOUBL service.
1. Fill in all the data as explained in [Set the E-Documents connector with external endpoints](../../finance-how-setup-edocuments-external.md).
1. In the **Document Format** field, select **OIOUBL** as the export format of the electronic export setup.
1. In the **Service Integration** field, specify the service access point that you want to use.
1. Select **Setup Service Integration**, and follow the instructions for [using E-Documents Connector with External Endpoints](../../finance-how-setup-edocuments-external.md). Then close the page.

### Use Peppol format  

1. Select the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **E-Document Services**, and then select the related link.
1. Select **New** to create the PEPPOL service.
1. Fill in all the data as explained in [Set the E-Documents connector with external endpoints](../../finance-how-setup-edocuments-external.md).
1. In the **Document Format** field, select **PEPPOL BIS 3.0** as the export format of the electronic export setup.
1. In the **Service Integration** field, specify the service access point that you want to use.
1. Select **Setup Service Integration**, and follow the instructions for [using E-Documents Connector with External Endpoints](../../finance-how-setup-edocuments-external.md). Then close the page.

> [!NOTE]
> If a **GLN No.** isn't specified in the **Company Setup**, all electronic documents are exported using the company's **VAT Registration No.** as the identifier. In this case, the **VAT Scheme** using for electronic documents in Denmark is set to 0184. You can check the **VAT Scheme** value in the **Country/Region** page for each of countries. It means this value is used in all nodes when applicable. It's also added as a prefix DK to **VAT Registration No.** when applicable.  

Learn more in the [How to set up E-Documents](../../finance-how-setup-edocuments.md) article, which provides information on configuring workflows, customers, and vendors. Refer to the [Set the E-Documents connector with external endpoints](../../finance-how-setup-edocuments-external.md) article for information on using e-documents with external services.

## Related information

- [Denmark Local Functionality](denmark-local-functionality.md)  
- [How to set up e-documents in Business Central](../../finance-how-setup-edocuments.md)  
- [How to use e-documents in Business Central](../../finance-how-use-edocuments.md)  
- [How to extend e-documents in Business Central](/dynamics365/business-central/dev-itpro/developer/devenv-extend-edocuments)  
- [Invoice Sales](../../sales-how-invoice-sales.md)  
- [Record Purchases with Purchase Invoices and Orders](../../purchasing-how-record-purchases.md)  
- [Work with Business Central](../../ui-work-product.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
