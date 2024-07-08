---
title: Set up electronic invoicing with NemHandel
description: Learn how to set up e-documents functionality with Nemhadel in Denmark.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: electronic document, electronic invoice, e-document, e-invoice, access-point, endpoint, nemhandel, denmark, dk
ms.search.form: 359, 360, 6103, 6133
ms.date: 12/13/2023
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Set up electronic invoicing with NemHandel

In Denmark, you can configure your e-invoicing system to work with NemHandel by using third-party certified access points. Before you begin, read about how to [use e-documents with external services](../../finance-how-setup-edocuments-external.md), and make a contract with one of the supported external certified access point providers.

Before you begin the setup, open the **Extension management** page, and verify that the following apps are installed:

- E-Document Core
- E-Documents Connector with External Endpoints
- OIOUBL
- E-Document format for OIOUBL

In Danish E-Documents functionality, you can select OIOUBL and PEPPOL BIS 3 as document formats in **E-Document Services**.

## E-Document Services setup

> [!NOTE]
> These connections requires communication with external service providers that might be subject to additional payment and require contracts with them. To get all the necessary credentials, contact the service providers.

To set up services, complete the following steps:   

### To use OIOUBL format  

1. Select the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **E-Document Services**, and then select the related link.
2. Select **New** to create the OIOUBL service.
3. Fill in all the data as explained in [Set the E-Documents connector with external endpoints](../../finance-how-setup-edocuments-external.md).
4. In the **Document Format** field, select **OIOUBL** as the export format of the electronic export setup.
5. In the **Service Integration** field, specify the service access point that you want to use.
6. Select **Setup Service Integration**, and follow the instructions for [using E-Documents Connector with External Endpoints](../../finance-how-setup-edocuments-external.md). Then close the page.

### To use Peppol format  

1. Select the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **E-Document Services**, and then select the related link.
2. Select **New** to create the PEPPOL service.
3. Fill in all the data as explained in [Set the E-Documents connector with external endpoints](../../finance-how-setup-edocuments-external.md).
4. In the **Document Format** field, select **PEPPOL BIS 3.0** as the export format of the electronic export setup.
5. In the **Service Integration** field, specify the service access point that you want to use.
6. Select **Setup Service Integration**, and follow the instructions for [using E-Documents Connector with External Endpoints](../../finance-how-setup-edocuments-external.md). Then close the page.

> [!NOTE]
> If you do not have a **GLN No.** specified in the **Company Setup**, then export of all electronic documents will be using the company's **VAT Registration No.** as identifier in the electronic documents. In this case the **VAT Scheme** using for electronic documents in Denmark has been set to 0184. You can check the **VAT Scheme** value in the **Country/Region** page for each of countries. It means this value is used in all nodes when applicable. It is also added a prefix DK to **VAT Registration No.** when applicable.  

To configure workflows, customers, and vendors, see [How to set up E-Documents](../../finance-how-setup-edocuments.md) and [Set the E-Documents connector with external endpoints](../../finance-how-setup-edocuments-external.md). 

## See also

[Denmark Local Functionality](denmark-local-functionality.md)  
[How to set up e-documents in Business Central](../../finance-how-setup-edocuments.md)  
[How to use e-documents in Business Central](../../finance-how-use-edocuments.md)  
[How to extend e-documents in Business Central](/dynamics365/business-central/dev-itpro/developer/devenv-extend-edocuments)  
[Invoice Sales](../../sales-how-invoice-sales.md)  
[Record Purchases with Purchase Invoices and Orders](../../purchasing-how-record-purchases.md)  
[Work with Business Central](../../ui-work-product.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
