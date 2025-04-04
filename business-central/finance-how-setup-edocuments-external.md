---
title: Set the E-Documents connector with external endpoints
description: This article explains how to set up E-Documents functionality when it's connected to external endpoints.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: electronic document, electronic invoice, e-document, e-invoice, access-point, endpoint
ms.search.form: 359, 360, 6103, 6133
ms.date: 09/16/2024
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Set the E-Documents connector with external endpoints

This article explains how to set up E-Documents functionality when it's connected to external endpoints.

Before you use the functionality that's described in this article, you need to install one of the E-Documents connectors with external endpoints apps on the top of the global **E-Document Core** app. These app can be used for default integration with the external (third-party) access points to automate the e-document flow. Because these apps represent only some of the selected connectors, you aren't limited to existing integrations in it. Most of the connectors will be available directly on AppSource in the future. 

## Install E-Documents connector  

To install one of default E-Documents connector you should follow next steps: 

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **E-Document Services**, and then select the related link. 
2. Choose the **Install E-Documents integration from AppSource** action to open the **Microsoft AppSource apps** page with the list of E-Document connectors first party apps for installation.
3. When you decide which connector you would like to use select the **View on AppSource** action.
4. Install the app from the AppSource.

## Set up the connection 

[!INCLUDE[e-documents connectors](includes/edocuments-connectors-include.md)]

Based on the endpoint service provider you chose, the next steps might be different. You can find details about set up parameters for all available service providers [here](finance-edocuments-connectors.md).

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

Currently, the following list of access point providers are covered by by default in Business Central:  

- Avalara
- B2BRouter
- Logiq
- Pagero
- SignUp

Microsoft has no contractual obligation with these providers. Therefore, you must make a contract with them to get all the necessary credentials and these services can require additional licensing or payments for their services.

We'll update this list as soon as we enable new e-document exchange access point providers.  

## See also

[How to set up e-documents in Business Central](finance-how-setup-edocuments.md)    
[How to use e-documents in Business Central](finance-how-use-edocuments.md)    
[How to extend e-documents in Business Central](/dynamics365/business-central/dev-itpro/developer/devenv-extend-edocuments)    
[Financial Management](finance.md)    
[Invoice Sales](sales-how-invoice-sales.md)    
[Record Purchases with Purchase Invoices and Orders](purchasing-how-record-purchases.md)    
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)    

[!INCLUDE[footer-include](includes/footer-banner.md)]
