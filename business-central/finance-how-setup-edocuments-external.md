---
title: Set E-Documents Connector with External Endpoints
description: Learn how to set up e-documents functionality when it is connected with the external endpoints.
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

# Set E-Documents Connector with External Endpoints 

The prerequisite for using the following features is to have installed the **E-Documents Connector with External Endpoints** app on the top of global **E-Document Core** app. This app can be used for default integration with the external (3rd party) access points to automate e-documents flow. Users are not limited only to existing integrations in this app as this app represents just some of selected connectors, but not all of them. Majority of connectors can be found in the future on the AppSource.  

## Set up the connection  

For set up process, please first visit this topic for the global [E-document core app](finance-how-setup-edocuments.md). All those steps must be followed, and in this document, you will get information about additional steps.   

After that, follow the next steps:  

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **E-Document Services**, and then select the related link.  
2. In the **Service Integration** field, select one of the offered integration codes for the endpoint service setup.  
3. Run the **Setup Service Integration** action.    
4. From the **E-Document External Connection Setup** page run the **Request Authorization Code** action to be redirected to the external service authorization webpage. Login details will be prompted. The authorization code must be copied into the **Enter Authorization Code** field. After that run the **Refresh Access Token** action to make sure you can also refresh the token. 

> [!NOTE]
> This connection requires communication with the external service providers, and they might be subject to additional payment and requiring contracts with them. To get all necessary credentials, please contact service providers.

5. Fill in the following fields on the **E-Document External Connection Setup** page:

| Field name | Description |
|--------|---------------------------|
|FileAPI URL| Specifies the file API URL |
|Fileparts URL| Specifies the fileparts URL |
|DocumentAPI URL| Specifies the document API URL |
|Company ID| Specifies the company ID |
|Send Mode| Specifies the send mode where you can choose one of the following options: **Production**, **Test**, or **Certification** |

> [!NOTE]
> You need to ask your service provider for all the previous details to establish connection with their access point.

## Set up Company information  

Before you start using E-documents you need to update your **Company Information** page. To do so, follow next steps:  

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Company Information**, and then select the related link.  
2. In addition to filling in the usual fields, you must also fill in these fields:   

| Field name | Description |
|--------|---------------------------|
|SWIFT Code | Specifies the SWIFT code (international bank identifier code) of your primary bank. |
|Bank Branch No. | Specifies the bank's branch number (4 digits). |
|VAT Registration No. | Specifies the company's VAT registration number. |

3. Close the page.  

## Set up Customers   

If you want to use customers to receive your e-documents, you must configure some specific fields. To do so, follow next steps:  

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then select the related link.  
2. Open the **Customer** card.    
3. In addition to filling in the usual fields, you must populate the **GLN** field to specify the customer in connection with electronic document sending.  
4. Also, you need to mark the **Use GLN in Electronic Documents** field if you want to specify whether the **GLN** is used in electronic documents as a party identification number. 
5. Close the page.  

## Other setups  

Before starting work, set up the E-documents **Workflows** and **Document Sending Profiles** to use your workflows. When the service connection has been established, you can start using your E-document solution.  

## Available Service Providers 

Microsoft wants to encourage the most of access-points providers to add their connectors on a top of our **E-Document Core** framework.

Currently only access point provider covered with this system is **Pagero**. Microsoft doesn't have any contractual obligation with Pagero, so you must make a contract with them to get all necessary credentials. 

As soon as we have new e-document exchange access-point providers, we will update this list. 

## See also

[How to set up e-documents in Business Central](finance-how-setup-edocuments.md)
[How to use e-documents in Business Central](finance-how-use-edocuments.md)  
[How to extend e-documents in Business Central](/dynamics365/business-central/dev-itpro/developer/devenv-extend-edocuments)  
[Financial Management](finance.md)  
[Invoice Sales](sales-how-invoice-sales.md)  
[Record Purchases with Purchase Invoices and Orders](purchasing-how-record-purchases.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
