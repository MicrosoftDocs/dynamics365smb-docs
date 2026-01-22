---
title: Connect E-Documents to external access points
description: Learn how to set up E-Documents in Business Central to send and receive electronic documents with different external access points.
author: altotovi
ms.topic: how-to
ms.devlang: al
ms.search.keywords: electronic document, electronic invoice, e-document, e-invoice, access-point, endpoint, connector, Peppol
ms.search.form: 
ms.date: 07/02/2025
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: solsen
ms.custom: bap-template
---

# Connect E-Documents to external access points

[!INCLUDE [e-documents connectors](includes/edocuments-connectors-include.md)]

You can use E-Documents in Business Central to send and receive electronic documents with your business partners. To receive documents, you need to connect E-Documents to an external access point that handles the communication and validation of the documents.

 > [!NOTE]
 > These connections require communication with external service providers who might require other payments and contracts. To get the credentials you need, contact the service providers.

The steps to connect E-Documents to an external access point depend on the type of connector you choose.

## Available service providers

[!INCLUDE[prod_short](includes/prod_short.md)] supports Pagero, Avalara, Logiq, SignUp, and B2BRouter access points for e-documents. If we add more connectors, we'll update this article with the parameters when they're ready. You can also find more connectors on Marketplace.

> [!NOTE]
> This article doesn't explain how to connect with local service providers. You can learn more about the local service providers that [!INCLUDE[prod_short](includes/prod_short.md)] supports in the country-specific documentation.  

Microsoft doesn't have a contractual obligation with Pagero and Avalara. You must have a contract with them if you want to use their connectors.

## Pagero service

1. On the **E-Document Service** page, change the **Service Integration** to **Pagero**.
2. On the **E-Document Service** page, select the **Setup Service Integration** action.  
3. On the **E-Document External Connection Setup** page, select the **Open OAuth 2.0 setup** action to open the **OAuth 2.0 Setup** page.  
4. On the **OAuth 2.0 setup** page, select the **Request Authorization Code** action. You're redirected to the external service authorization webpage and prompted to sign-in.
5. Copy the authorization code into the **Enter Authorization Code** field.  
6. Select **Refresh Access Token** to make sure that you can refresh the token.
7. On the **E-Document External Connection Setup** page, fill in the following fields:

    | Field name | Description |
    |---|---|
    | FileAPI URL | Specify the file API URL. |
    | Fileparts URL | Specify the fileparts URL. |
    | DocumentAPI URL | Specify the document API URL. |
    | Company ID | Specify the company ID. |
    | Send Mode | Specify the send mode. You can select **Production**, **Test**, or **Certification**. |

8. Continue with the [nonservice provider setup steps](finance-how-setup-edocuments-external.md).  

## Avalara service

1. On the **E-Document Service** page, change the **Service Integration** to **Avalara**.  
2. On the **E-Document Service** page, select the **Setup Service Integration** action.  
3. On the **Avalara Connection Setup** page, enter the **Client ID** and **Client Secret** fields. In the **Send Mode** field, choose the **Production**, **Test**, or **Certification** option, based on your plans.
4. Select the **Select Avalara Company Id** action, and choose the company. Make sure you fill in the **Company Name** and **Company ID** fields.  
5. Select the **Select Avalara Mandate** action, and select the right **E-Document Service**, and then choose the **Country Mandate** code on the **Avalara Mandate List** page.
6. Return to the **E-Document Service** page, and validate that the **Avalara Mandate** field on the **Avalara** FastTab is set with the value you chose.
7. Continue with the [nonservice provider setup steps](finance-how-setup-edocuments-external.md).

## Logiq service

1. On the **E-Document Service** page, change the **Service Integration** to **Logiq**. 
2. On the **E-Document Service** page, select the **Setup Service Integration** action.  
3. On the **Logiq Connection Setup** page, enter tokens to the **Client ID** and **Client Secret** fields, and then choose the **Environment** as **Pilot** or **Production**.
4. Run the **User Setup** action and enter your credentials. Choose the **API Engine** (Engine 1 or Engine 3) based on the instructions from the provider.
5. Select the **Get Tokens** to access tokens for the current user.
6. Continue with the [nonservice provider setup steps](finance-how-setup-edocuments-external.md).

## SignUp service (ExFlow)

1. On the **E-Document Service** page, change the **Service Integration** to **ExFlow E-Invoicing**.  
2. On the **E-Document Service** page, select the **Setup Service Integration** action.  
3. On the **Logiq Connection Setup** page, enter the **Client ID** and **Client Secret** fields and the **Authentication URL** to specify the URL to connect to Microsoft Entra.  
4. Fill in the **Service URL** field with the URL you got from your provider. In the **Environment Type** field, specify whether you want to use it for test or production.
5. Run the **Open Onboarding** action to start the onboarding process with your provider in a new browser window.  
6. Continue with the [nonservice provider setup steps](finance-how-setup-edocuments-external.md).

## B2BRouter service

1. On the **E-Document Service** page, change the **Service Integration** to **B2BRouter**.  
2. On the **E-Document Service** page, select the **Setup Service Integration** action.
3. On the **B2BRouter Connection Setup** page, enter the **API-KEY** to specify the key you'll use for your B2BRouter environment and the **ProjectID** field to specify the project name for the B2BRouter environment.
4. If you want to use this connector in sandbox mode, select the **Staging Mode** field.  
5. Continue with the [nonservice provider setup steps](finance-how-setup-edocuments-external.md).

## Related information

[How to set up e-documents in Business Central](finance-how-setup-edocuments.md)  
[How to set up e-documents connector with external endpoints](finance-how-setup-edocuments-external.md)  
[How to use e-documents in Business Central](finance-how-use-edocuments.md)  
[How to extend e-documents in Business Central](/dynamics365/business-central/dev-itpro/developer/devenv-extend-edocuments)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
