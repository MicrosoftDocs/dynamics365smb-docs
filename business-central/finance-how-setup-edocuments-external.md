---
title: Set E-Documents connector with external endpoints
description: This article explains how to set up E-Documents functionality when it's connected to external endpoints.
author: altotovi
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: electronic document, electronic invoice, e-document, e-invoice, access-point, endpoint
ms.search.form: 359, 360, 6103, 6133
ms.date: 12/13/2023
ms.author: altotovi
---

# Set E-Documents connector with external endpoints 

This article explains how to set up E-Documents functionality when it's connected to external endpoints.

Before you use the functionality described in this article, install the **E-Documents Connector with External Endpoints** app on the top of global **E-Document Core** app. This app can be used for default integration with the external (3rd party) access points to automate e-document flow. You aren't limited only to existing integrations in this app as this app represents only some of selected connectors. The majority of connectors can be found in the future on AppSource.  

## Set up the connection  

To begin your setup, follow the steps in this article, [E-document core app](finance-how-setup-edocuments.md). After you complete those steps, return to this article and complete the following steps.

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **E-Document Services**, and then select the related link.  
2. In the **Service Integration** field, select one of the offered integration codes for the endpoint service setup.  
3. Select **Setup Service Integration**.    
4. From the **E-Document External Connection Setup** page, select **Request Authorization Code** to be redirected to the external service authorization webpage. You will be prompted for your login details.
5. Copy the authorization code into the **Enter Authorization Code** field.
6. Select **Refresh Access Token** to make sure you can refresh the token. 

> [!NOTE]
> This connection requires communication with external service providers, and they might be subject to additional payment and requiring contracts. To get all necessary credentials, contact the service providers.

7. On the **E-Document External Connection Setup** page, fill in the following fields:

| Field name | Description |
|--------|---------------------------|
| FileAPI URL | Specify the file API URL. |
| Fileparts URL | Specify the fileparts URL. |
| DocumentAPI URL | Specify the document API URL. |
| Company ID | Specify the company ID. |
| Send Mode | Specify the send mode where you can select **Production**, **Test**, or **Certification**. |

> [!NOTE]
> Ask your service provider for all the previous details to establish a connection with their access point.

## Set up Company information  

Before you start using E-documents, update your **Company Information** page by following these steps.  

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Company Information**, and then select the related link.  
2. In addition to filling in the usual fields, you must also fill in these fields:   

| Field name | Description |
|--------|---------------------------|
| SWIFT Code | Specify the SWIFT code (international bank identifier code) of your primary bank. |
| Bank Branch No. | Specify the bank's branch number (4 digits). |
| VAT Registration No. | Specify the company's VAT registration number. |

3. Close the page.  

## Set up customers to receive e-documents   

If you want to alow customers to receive your e-documents, complete the following steps:

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then select the related link.  
2. Open the **Customer** card.    
3. In addition to filling in the usual fields, in the **GLN** field, specify the customer in connection with electronic document sending.  
4. Mark the **Use GLN in Electronic Documents** field to specify whether the **GLN** is used in electronic documents as a party identification number. 
5. Close the page.  

## Other setups  

Before you start working with e-documents, set up the e-documents **Workflows** and **Document Sending Profiles** to use your workflows. When the service connection has been established, you can start using your E-document solution.  

## Available service providers 

Microsoft wants to encourage access-points providers to add their connectors on a top of our **E-Document Core** framework.

Currently, the only access point provider covered with this system is **Pagero**. Microsoft doesn't have any contractual obligation with Pagero, so you must make a contract with them to get all necessary credentials. 

When we have new e-document exchange access-point providers, we will update this list. 

## See also

[How to set up e-documents in Business Central](finance-how-setup-edocuments.md)
[How to use e-documents in Business Central](finance-how-use-edocuments.md)  
[How to extend e-documents in Business Central](/dynamics365/business-central/dev-itpro/developer/devenv-extend-edocuments)  
[Financial Management](finance.md)  
[Invoice Sales](sales-how-invoice-sales.md)  
[Record Purchases with Purchase Invoices and Orders](purchasing-how-record-purchases.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
