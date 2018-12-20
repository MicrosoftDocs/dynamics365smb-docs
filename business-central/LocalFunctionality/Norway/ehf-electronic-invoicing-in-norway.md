---
    title: EHF Electronic Invoicing in Norway
    description: Companies must send sales invoices and credit memos to the Norwegian public sector electronically in the Elektronisk Handelsformat (EHF) based on Universal Business Language (UBL).

    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 10/01/2018
    ms.author: sgroespe

---
# EHF Electronic Invoicing in Norway
Companies must send sales invoices and credit memos to the Norwegian public sector electronically in the Elektronisk Handelsformat (EHF) based on Universal Business Language (UBL). If a company does not send these documents electronically, the authorities can deny payment. The standard supported format for electronic exchange between parties is the Ehandel.no format.  

For more information on EHF electronic invoicing, see [E-Procurement](https://www.anskaffelser.no/public-procurement-information-english).  

## Implementation in [!INCLUDE[d365fin](../../includes/d365fin_md.md)]  
 From January 2019 the requirements for sending electronic invoices are based on the PEPPOL 3.0 BIS Billing 3.0 standard. Please see [https://test-vefa.difi.no/ehf/g3/billing-3.0/norway/](https://test-vefa.difi.no/ehf/g3/billing-3.0/norway/) for more information. Companies already sending electronic documents in the pre-2019 format can continue doing so during 2019. The generated XML documents can then be sent to the customer manually or through the [Document Exchange functionality](../../across-how-to-set-up-electronic-document-sending-and-receiving.md).

 To send documents electronically, you must assign European Article Numbering (EAN) location numbers and account codes to the relevant customers on the **Customer Card** page. For more information, see [Set Up Customers for EHF](how-to-set-up-customers-for-ehf.md). These numbers are included when you create documents, and post or issue them. After the documents have been posted or issued, you can create electronic versions to be sent to the customer.  

 [!INCLUDE[d365fin](../../includes/d365fin_md.md)] exports certain electronic documents in EHF version 3.0, which uses UBL version 2.1. You can submit the following types of documents:  

- Sales and Service invoices
- Sales and Service credit memos

 [!INCLUDE[d365fin](../../includes/d365fin_md.md)] exports other electronic documents in version 1.6, which uses UBL version 2.0. You can submit the following types of documents:  

- Finance charge memo  
- Reminder  

The electronic documents are stored in the locations that are defined in the Sales & Receivables Setup or they can be generated and handled by the [Document Exchange functionality](../../across-how-to-set-up-electronic-document-sending-and-receiving.md). 

## VAT Treatment  
 VAT percentages and the type of transaction determine the VAT Type that is exported in the electronic document.  

|XML|Type| 
|---------|----------|  
|S|Outgoing VAT, ordinary rate|
|H|Outgoing VAT, reduced rate – food and beverage|
|R|Outgoing VAT, reduced rate – raw fish|
|AA|Outgoing VAT, low rate|
|AE|VAT Reverse Charge|
|L|Canary Islands general indirect tax|
|M|Tax for production, services and importation in Ceuta and Melilla|
|G|Free export item, tax not charged|
|O|Services outside scope of tax|
|E|VAT Exempt|
|Z|VAT Exempt (goods and services not included in the VAT regulations)|
|K|VAT exempt for EEA intra-community supply of goods and services|

## See Also  
 [Set Up Customers for EHF](how-to-set-up-customers-for-ehf.md)
