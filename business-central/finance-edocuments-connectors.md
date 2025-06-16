---
title: Connect E-Documents to external access points
description: Learn how to set up E-Documents in Business Central to send and receive electronic documents with different external access points.
author: altotovi
ms.topic: how-to
ms.devlang: al
ms.search.keywords: electronic document, electronic invoice, e-document, e-invoice, access-point, endpoint, connector, Peppol
ms.search.form: 
ms.date: 09/17/2024
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: solsen
---

# Connect E-Documents to external access points

[!INCLUDE [e-documents connectors](includes/edocuments-connectors-include.md)]

You can use E-Documents in Business Central to send and receive electronic documents with your business partners. To receive documents, you need to connect E-Documents to an external access point that handles the communication and validation of the documents. 

 > [!NOTE]
 > These connections require communication with external service providers who might be subject to additional payment and require contracts with them. To obtain all the necessary credentials, contact the service providers.

The steps to connect E-Documents to an external access point depend on the type of connector you choose.    

> [!NOTE]
> Ask your service provider for all the necessary details to establish a connection with their access point that follows.  

## Pagero service

1. On the **E-Document External Connection Setup** page, select the **Open OAuth 2.0 setup** action to open the **OAuth 2.0 Setup** page.  
2. On the **OAuth 2.0 setup** page, select the **Request Authorization Code** action. You're redirected to the external service authorization webpage and prompted for your sign-in details.
3. Copy the authorization code into the **Enter Authorization Code** field.  
4. Select **Refresh Access Token** to make sure that you can refresh the token. 
5. On the **E-Document External Connection Setup** page, fill in the following fields:

    | Field name | Description |
    |---|---|
    | FileAPI URL | Specify the file API URL. |
    | Fileparts URL | Specify the fileparts URL. |
    | DocumentAPI URL | Specify the document API URL. |
    | Company ID | Specify the company ID. |
    | Send Mode | Specify the send mode. You can select **Production**, **Test**, or **Certification**. |

6. Continue with the [nonservice provider setup steps](finance-how-setup-edocuments-external.md).  

## Avalara service

> [!NOTE]
> The Avalara connector in [!INCLUDE[prod_short](includes/prod_short.md)] is available from version 25.1

1. On the **Avalara Connection Setup** page, enter the **Client ID** and **Client Secret** fields. In the **Send Mode** field, choose the **Production**, **Test**, or **Certification** option, based on your plans. 
2. Select the **Select Avalara Company Id** action, and choose the right company. Make sure you enter values into the **Company Name** and **Company ID** fields.  
3. Select the **Select Avalara Mandate** action, and select the right **E-Document Service**, and then pick appropriate **Country Mandate** code on the **Avalara Mandate List** page. 
4. Navigate back to the **E-Document Service** page, and validate that the **Avalara Mandate** field in the **Avalara** FastTab is set with the value you chose. 
5. Continue with the [non-service provider setup steps](finance-how-setup-edocuments-external.md).

## Available service providers

At this moment, [!INCLUDE[prod_short](includes/prod_short.md)] supports Pagero and Avalara access points for e-documents, but more access points are in the process of development. This page is updated with the parameters for new connectors when they're ready. You can also find more connectors on AppSource.

> [!NOTE]
> This page doesn't show how to connect with the local service providers. If [!INCLUDE[prod_short](includes/prod_short.md)] support some of them, it will be explained in the country-specific documentation.  

Microsoft doesn't have a contractual obligation with Pagero and Avalara. That means, if you want to use their connectors, you must have a contract with them.

## Related information

- [How to set up e-documents in Business Central](finance-how-setup-edocuments.md)  
- [How to set up e-documents connector with external endpoints](finance-how-setup-edocuments-external.md)    
- [How to use e-documents in Business Central](finance-how-use-edocuments.md)    
- [How to extend e-documents in Business Central](/dynamics365/business-central/dev-itpro/developer/devenv-extend-edocuments)    
- [Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)    

[!INCLUDE[footer-include](includes/footer-banner.md)]
