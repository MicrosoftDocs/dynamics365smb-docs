---
title: Set the E-Documents connector with external endpoints
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

# Set the E-Documents connector with external endpoints

This article explains how to set up E-Documents functionality when it's connected to external endpoints.

Before you use the functionality that's described in this article, install the **E-Documents Connector with External Endpoints** app on the top of the global **E-Document Core** app. This app can be used for default integration with the external (third-party) access points to automate the e-document flow. Because this app represents only some of the selected connectors, you aren't limited to existing integrations in it. Most of the connectors will be available on AppSource in the future.

## Set up the connection

To begin your setup, follow the steps in [E-document core app](finance-how-setup-edocuments.md). After you complete those steps, return to this article, and complete the following steps:

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **E-Document Services**, and then select the related link.
2. In the **Service Integration** field, select one of the integration codes that are offered for the endpoint service setup.
3. Select **Setup Service Integration**.
4. On the **E-Document External Connection Setup** page, select **Request Authorization Code**. You're redirected to the external service authorization webpage and prompted for your sign-in details.
5. Copy the authorization code into the **Enter Authorization Code** field.
6. Select **Refresh Access Token** to make sure that you can refresh the token.

    > [!NOTE]
    > This connection requires communication with external service providers that might be subject to additional payment and require contracts with them. To get all the necessary credentials, contact the service providers.

7. On the **E-Document External Connection Setup** page, fill in the following fields:

    | Field name | Description |
    |---|---|
    | FileAPI URL | Specify the file API URL. |
    | Fileparts URL | Specify the fileparts URL. |
    | DocumentAPI URL | Specify the document API URL. |
    | Company ID | Specify the company ID. |
    | Send Mode | Specify the send mode. You can select **Production**, **Test**, or **Certification**. |

    > [!NOTE]
    > Ask your service provider for all the previous details to establish a connection with their access point.

## Set up company information

Before you start using e-documents, update your **Company Information** page by completing the following steps:

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Company Information**, and then select the related link.
2. In addition to filling in the usual fields, you must also fill in the following fields:

    | Field name | Description |
    |---|---|
    | SWIFT Code | Specify the SWIFT code (international bank identifier code) of your primary bank. |
    | Bank Branch No. | Specify the bank's four-digit branch number. |
    | VAT Registration No. | Specify the company's value-added tax (VAT) registration number. |

3. Close the page.

## Set up customers to receive e-documents

To enable customers to receive your e-documents, complete the following steps:

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then select the related link.
2. Open the **Customer** card.
3. In addition to filling in the usual fields, in the **GLN** field, specify the customer in connection with the sending of electronic documents.
4. Mark the **Use GLN in Electronic Documents** field to indicate whether the Global Location Number (GLN) is used as a party identification number in electronic documents.
5. Close the page.

## Other setup

Before you start to work with e-documents, set up the e-document **workflows** and **document sending profiles** to use your workflows. After the service connection is established, you can start to use your e-document solution.

## Available service providers

Microsoft wants to encourage access point providers to add their connectors on top of our **E-Document Core** framework.

Currently, Pagero is the only access point provider that's covered by this system. Microsoft has no contractual obligation with Pagero. Therefore, you must make a contract with them to get all the necessary credentials.

We will update this list as we get new e-document exchange access point providers.

## See also

[How to set up e-documents in Business Central](finance-how-setup-edocuments.md)  
[How to use e-documents in Business Central](finance-how-use-edocuments.md)  
[How to extend e-documents in Business Central](/dynamics365/business-central/dev-itpro/developer/devenv-extend-edocuments)  
[Financial Management](finance.md)  
[Invoice Sales](sales-how-invoice-sales.md)  
[Record Purchases with Purchase Invoices and Orders](purchasing-how-record-purchases.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
