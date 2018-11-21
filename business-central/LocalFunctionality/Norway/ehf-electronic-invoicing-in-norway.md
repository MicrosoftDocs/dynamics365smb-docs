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
 The current requirements for sending electronic invoices are based on the Universal Business Language (UBL) version 2.1 standard. For more information, see the https://aka.ms/OasisUblSite web site. The generated XML documents can then be sent to the customer.  

 To send documents electronically, you must assign European Article Numbering (EAN) location numbers and account codes to the relevant customers in the **Customer Card** page. For more information, see [Set Up Customers for EHF](how-to-set-up-customers-for-ehf.md). These numbers are included when you create documents, and post or issue them. After the documents have been posted or issued, you can create electronic versions to be sent to the customer.  

 [!INCLUDE[d365fin](../../includes/d365fin_md.md)] exports certain electronic documents in version 2.0, which uses UBL version 2.1. You can submit the following types of documents:  

- Sales invoice  
- Service invoice  
- Sales credit memo  
- Service credit memo  

 [!INCLUDE[d365fin](../../includes/d365fin_md.md)] exports other electronic documents in version 1.6, which uses UBL version 2.0. You can submit the following types of documents:  

- Finance charge memo  
- Reminder  

The electronic documents are stored in the locations that are defined in the Sales & Receivables Setup.  

## VAT Treatment  
 VAT percentages and the type of transaction determine the VAT Type that is exported in the electronic document.  

|XML|Type|Percentage Rate|  
|---------|----------|---------------------|  
|S|Outgoing VAT, ordinary rate|25|  
|H|Outgoing VAT, reduced rate – food and beverage|15|  
|R|Outgoing VAT, reduced rate – raw fish|11.11|  
|AA|Outgoing VAT, low rate|8|  
|E|VAT Exempt|0|  
|Z|VAT Exempt (goods and services not included in the VAT regulations)|None, reported as 0|  
|K|Emission allowances for private or public businesses – buyer calculates VAT|None, reported as 0|  

## See Also  
 [Set Up Customers for EHF](how-to-set-up-customers-for-ehf.md)
