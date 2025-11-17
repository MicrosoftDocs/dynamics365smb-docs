---
title: Set up the E-Documents connector with external endpoints
description: This article explains how to set up E-Documents functionality when connected to external endpoints.
author: altotovi
ms.author: altotovi
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: electronic document, electronic invoice, e-document, e-invoice, access-point, endpoint
ms.search.form: 359, 360, 6103, 6133
ms.date: 11/17/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Set up the E-Documents connector with external endpoints

This article explains how to set up E-Documents functionality when connected to external endpoints.

Before you use the functionality that this article describes, you must install the **E-Document Core** app and one of the E-Documents connectors with external endpoints apps. You can use these apps for default integration with the external, non-Microsoft, access points to automate the e-document flow. Because these apps represent only some of the selected connectors, you aren't limited to existing integrations.

## Install an E-Documents connector  

To install an E-Documents connector, follow these steps:

1. [!INCLUDE[open-search](includes/open-search.md)], enter **E-Document Services**, and then select the related link.
2. Choose the **Install E-Documents integration from AppSource** action to open the **Microsoft AppSource apps** page.
3. Choose the connector you want, and then select the **View on AppSource** action.
4. Install the app from the AppSource.

## Set up the connection

[!INCLUDE[e-documents connectors](includes/edocuments-connectors-include.md)]

Based on the endpoint service provider, the next steps might be different. You can find details about set up parameters for all available service providers [here](finance-edocuments-connectors.md).

## Set up company information

Before you start using e-documents, update your **Company Information** page by completing the following steps:

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Company Information**, and then select the related link.
2. In addition to filling in the usual fields, you must also fill in the following fields:

    | Field name | Description |
    |---|---|
    | SWIFT Code | Specifies the SWIFT code (international bank identifier code) of your primary bank. |
    | Bank Branch No. | Specifies the bank's four-digit branch number. |
    | VAT Registration No. | Specifies the company's value-added tax (VAT) registration number. |
    | GLN | Specifies your company in connection with electronic document exchange. |
    | Use GLN in Electronic Document | Specifies whether the GLN is used in electronic documents as a party identification number. |

4. Close the page.

## Set up customers to receive e-documents

To enable customers to receive your e-documents, complete the following steps:

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Customers**, and then select the related link.
2. Open the **Customer** card.
3. In addition to filling in the usual fields, in the **GLN** field, specify the customer you send electronic documents to.
4. Turn on the **Use GLN in Electronic Documents** toggle to indicate whether to use the global location number (GLN) as an identification number in electronic documents.
5. Close the page.

## Other setup

Before you start to work with e-documents, set up the e-document **workflows** and **document sending profiles** to use your workflows. After the service connection is established, you can start to use your e-document solution.

## Available service providers

Microsoft wants to encourage access point providers to add their connectors on top of our **E-Document Core** app.

The following list of access point providers are covered by default:  

- Avalara
- B2BRouter
- Continia
- Logiq
- Pagero
- SignUp
- ForNAV

Microsoft has no contractual obligations with these providers. Therefore, you must make a contract with them to get the necessary credentials. The services might require extra licensing or payments for their services.

## Related information

[How to set up e-documents in Business Central](finance-how-setup-edocuments.md)  
[How to use e-documents in Business Central](finance-how-use-edocuments.md)  
[How to extend e-documents in Business Central](/dynamics365/business-central/dev-itpro/developer/devenv-extend-edocuments)  
[Financial Management](finance.md)  
[Invoice Sales](sales-how-invoice-sales.md)  
[Record Purchases with Purchase Invoices and Orders](purchasing-how-record-purchases.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
