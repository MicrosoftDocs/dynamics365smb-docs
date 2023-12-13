---
title: Set electronic invoicing with NemHandel
description: Learn how to set up e-documents functionality with Nemhadel in Denmark.
author: altotovi
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: electronic document, electronic invoice, e-document, e-invoice, access-point, endpoint, nemhandel, denmark, dk
ms.search.form: 359, 360, 6103, 6133
ms.date: 12/13/2023
ms.author: altotovi
---

# Set Electronic invoicing with NemHandel 

In Denmark users can configure their e-invoicing system to work with Nemhadel via 3rd party certified access points. Before start, please first read details about [using E-documents with external services](../finance-how-setup-edocuments-external.md) and make a contract with one of supported external certified access points providers.  

Technically as a prerequisites, you must check in the **Extension management** page if you already have installed the following apps:  
- E-Document Core
- E-Documents Connector with External Endpoints
- OIOUBL
- E-Document format for OIOUBL

In a Danish E-Document functionality, users can choose OIOUBL and PEPPOL BIS 3 as document formats in **E-Document Services**.  

## E-Document Services Setup  

To set up services, follow next steps:  

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **E-Document Services**, and then select the related link.  
2. Click **New** to create OIOUBL service.   
3. Fill in all the data as explained in the [Using E-Documents Connector with External Endpoints](../../finance-how-setup-edocuments-external.md).
4. In the **Document Format** field choose the **OIOUBL** option to specify this export format of the electronic export setup. 
5. In the **Service Integration** field specify the service access point you want to use.  
6. Run the **Setup Service Integration** action and follow the instructions for [Using E-Documents Connector with External Endpoints](../../finance-how-setup-edocuments-external.md). 
7. Close the page.    
8. Click **New** to create PEPPOL service.   
9. Fill in all the data as explained in the [Using E-Documents Connector with External Endpoints](../../finance-how-setup-edocuments-external.md). 
10. In the **Document Format** field choose the **PEPPOL BIS 3.0** option to specify this export format of the electronic export setup. 
11. In the **Service Integration** field specify the service access point you want to use.  
12. Run the **Setup Service Integration** action and follow the instructions for [Using E-Documents Connector with External Endpoints](../../finance-how-setup-edocuments-external.md). 
13. Close the page.   

> [!NOTE]
> This connection requires communication with the external service providers, and they might be subject to additional payment and requiring contracts with them. To get all necessary credentials, please contact service providers. 

To configure Workflows, Customers, and Vendors, please read [How to set up E-Documents](../../finance-how-setup-edocuments.md) and [Using E-Documents Connector with External Endpoints](../../finance-how-setup-edocuments-external.md).

## See also

[Denmark Local Functionality](denmark-local-functionality.md)
[How to set up e-documents in Business Central](../../finance-how-setup-edocuments.md)
[How to use e-documents in Business Central](../../finance-how-use-edocuments.md)  
[How to extend e-documents in Business Central](/dynamics365/business-central/dev-itpro/developer/devenv-extend-edocuments)  
[Invoice Sales](../../sales-how-invoice-sales.md)  
[Record Purchases with Purchase Invoices and Orders](../../purchasing-how-record-purchases.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](../../ui-work-product.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
