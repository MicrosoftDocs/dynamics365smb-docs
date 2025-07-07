---
title: Electronic invoicing in Norway
description: Learn how to electronically send sales invoices and credit memos to the Norwegian public sector using EHF, which is based on Universal Business Language (UBL).
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: EHF, UBL, electronic invoicing, e-invoicing, Norwegian version
ms.search.form: 21, 459, 359, 360, 6103, 6133
ms.date: 05/12/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Electronic invoicing in Norway

Companies must send sales invoices and credit memos to the Norwegian public sector electronically in the Elektronisk Handelsformat (EHF) based on Universal Business Language (UBL). If a company doesn't send these documents electronically, the authorities can deny payment. The standard supported format for electronic exchange between parties is the Ehandel.no format. Learn more at [Anskaffelser.no](https://www.anskaffelser.no), which provides information about EHF electronic invoicing.

## New E-Documents framework

This article explains how to set up E-Documents functionality connected to external endpoints.

> [!NOTE]
> Before you use the features that this article describes, install the **E-Documents Connector with External Endpoints** app or another connector to use on the top of the global **E-Document Core** app. This app can be used for default integration with the external (non-Microsoft) access points to automate the e-document flow.

### Set up the connection

[!INCLUDE [edocuments-connectors-include](../../includes/edocuments-connectors-include.md)]

Based on the endpoint service provider you chose, the next steps might be different. Learn more in [Connect E-Documents to external access points](../../finance-edocuments-connectors.md), which provides information about the setup parameters for all available service providers.

### Set up company information

Before you start using e-documents, update your **Company Information** page by completing the following steps:

1. Select the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Company Information**, and then select the related link.
1. In addition to the usual fields, you must also fill in the fields as described in the following table:

    | Field name | Description |
    |---|---|
    | SWIFT Code | Specify the SWIFT code (international bank identifier code) of your primary bank. |
    | Bank Branch No. | Specify the bank's four-digit branch number. |
    | VAT Registration No. | Specify the company's value-added tax (VAT) registration number. |

1. Close the page.

### Set up customers to receive e-documents

To enable customers to receive your e-documents, complete the following steps:

1. Select the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then select the related link.
1. Open the **Customer Card** page for the customer.
1. In addition to the usual fields, in the **GLN** field, specify the customer you send electronic documents.
1. Mark the **Use GLN in Electronic Documents** field to indicate whether the global location number (GLN) is used as a party identification number in electronic documents.
1. Close the page.

### Other setups

Before you start to work with e-documents, set up the workflows and document sending profiles to use. After you create the service connection, you can use your e-document solution.

### Available service providers

Microsoft wants to encourage access point providers to add their connectors to our **E-Document Core** framework.

Currently, there are only a couple of access point providers, and Microsoft has no contractual obligations with them. To get the credentials required to use the access points, contact the providers.

We'll update this list as we get new e-document exchange access point providers.

## Legacy electronic invoicing

This article describes the legacy features for electronic invoicing localized for use in Norway. [!INCLUDE [prod_short](../../includes/prod_short.md)] offers an improved e-documents framework that we recommend you use instead.  

### Implementation in [!INCLUDE[prod_short](../../includes/prod_short.md)]  

From January 2019, the requirements for sending electronic invoices are based on the PEPPOL BIS Billing 3.0 standard. Learn more at [EHF Billing 3.0](https://anskaffelser.dev/postaward/g3/spec/current/billing-3.0/norway/) page from the Agency of Public Management and eGovernment. Companies that are already sending electronic documents in the pre-2019 format can continue to do so during 2019.

> [NOTE!]
> You can use the [Anskaffelser.dev Validator](https://anskaffelser.dev/service/validator) to validate your EHF billing formats.  

To send documents electronically, you must assign European Article Numbering (EAN) location numbers and account codes to the relevant customers on the **Customer Card** page. Learn more in [Set up customers for EHF](how-to-set-up-customers-for-ehf.md). These numbers are included when you create, post, or issue documents. After documents are posted or issued, you can create electronic versions to send to customers.  

[!INCLUDE[prod_short](../../includes/prod_short.md)] exports certain electronic documents in EHF version 3.0, which uses UBL version 2.1. You can submit the following types of documents:  

- Sales and service invoices
- Sales and service credit memos

[!INCLUDE[prod_short](../../includes/prod_short.md)] exports other electronic documents in version 1.6, which uses UBL version 2.0. You can submit the following types of documents:  

- Finance charge memo  
- Reminder  

You can specify where to store electronic documents on the **Sales & Receivables Setup** page. You can also use the [Document exchange functionality](../../across-how-to-set-up-electronic-document-sending-and-receiving.md) to generate and send them.

## VAT treatment  

VAT percentages and the type of transaction determine the VAT Type that is exported in the electronic document.  

|XML|Type| 
|---------|----------|  
|S|Outgoing VAT, ordinary rate|
|H|Outgoing VAT, reduced rate – food and beverage|
|R|Outgoing VAT, reduced rate – raw fish|
|AA|Outgoing VAT, low rate|
|AE|VAT Reverse Charge|
|L|Canary Islands general indirect tax|
|M|Tax for production, services, and importation in Ceuta and Melilla|
|G|Free export item, tax not charged|
|O|Services outside scope of tax|
|E|VAT Exempt|
|Z|VAT Exempt (goods and services not included in the VAT regulations)|
|K|VAT exempt for European Economic Area (EEA) intra-community supply of goods and services|

## VAT scheme

Make sure you set up the correct value in the **VAT Scheme** field on the **Countries/Regions** page.

## Related information

- [Set up e-documents](../../finance-how-setup-edocuments.md)  
- [Use e-documents in the sales process](../../finance-how-use-edocuments.md)  
- [How to extend e-documents in Business Central](/dynamics365/business-central/dev-itpro/developer/devenv-extend-edocuments)  
- [Set up customers for EHF](how-to-set-up-customers-for-ehf.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
