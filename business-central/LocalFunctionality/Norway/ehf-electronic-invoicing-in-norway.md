---
title: EHF electronic invoicing in Norway
description: Companies must send sales invoices and credit memos to the Norwegian public sector electronically in the Elektronisk Handelsformat (EHF) based on (UBL).
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords:
ms.search.form: 21, 459
ms.date: 05/21/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# EHF electronic invoicing in Norway
Companies must send sales invoices and credit memos to the Norwegian public sector electronically in the Elektronisk Handelsformat (EHF) based on Universal Business Language (UBL). If a company doesn't send these documents electronically, the authorities can deny payment. The standard supported format for electronic exchange between parties is the Ehandel.no format. For more information on EHF electronic invoicing, see [Anskaffelser.no](https://www.anskaffelser.no).  

## Implementation in [!INCLUDE[prod_short](../../includes/prod_short.md)]  
From January  2019, the requirements for sending electronic invoices are based on the PEPPOL BIS Billing 3.0 standard. For more information, see the [EHF Billing 3.0](https://anskaffelser.dev/postaward/g3/spec/current/billing-3.0/norway/) page from the Agency of Public Management and eGovernment. Companies that are already sending electronic documents in the pre-2019 format can continue to do so during 2019.

> [NOTE!]
> You can use the [Anskaffelser.dev Validator](https://anskaffelser.dev/service/validator) to validate your EHF billing formats.  

To send documents electronically, you must assign European Article Numbering (EAN) location numbers and account codes to the relevant customers on the **Customer Card** page. For more information, see [Set up customers for EHF](how-to-set-up-customers-for-ehf.md). These numbers are included when you create, post, or issue documents. After documents are posted or issued, you can create electronic versions to send to customers.  

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

## See also  
[Set up customers for EHF](how-to-set-up-customers-for-ehf.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
