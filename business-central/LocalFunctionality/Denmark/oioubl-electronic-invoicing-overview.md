---
    title: OIOUBL Electronic Invoicing Overview | Microsoft Docs
    description: Companies must send sales invoices, credit memos, finance charge memos, and reminders to the Danish public sector electronically in the Offentlig Information Online UBL (OIOUBL) format. If a company does not send these documents electronically, the authorities can deny payment.
    author: edupont04

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: edupont

---
# OIOUBL Electronic Invoicing Overview
Companies must send sales invoices, credit memos, finance charge memos, and reminders to the Danish public sector electronically in the Offentlig Information Online UBL (OIOUBL) format. If a company does not send these documents electronically, the authorities can deny payment.  

For more information about OIOUBL electronic invoicing, see [oioubl.info](http://www.oioubl.info/classes/da/index.html).  

## Implementation in [!INCLUDE[d365fin](../../includes/d365fin_md.md)]  
The current requirements for sending electronic invoices are based on OIOUBL, which is based on the Universal Business Language (UBL) version 2.0 standard. For more information, see the [OASIS UBL](https://aka.ms/OasisUblSite) web site. The generated XML documents can then be sent to the customer.  

To send documents electronically, you must assign European Article Numbering (EAN) location numbers and account codes to the relevant customers on the **Customer Card** page. For more information, see [Set Up Customers for OIOUBL](how-to-set-up-customers-for-oioubl.md). These numbers are the included when you create documents, and post or issue them. After the documents have been posted or issued, you can create electronic versions to be sent to the customer. You can submit the following types of documents:  

- Sales invoice  
- Service invoice  
- Sales credit memo  
- Service credit memo  
- Finance charge memo  
- Reminder  

The electronic documents are stored in the locations that are defined in the Sales & Receivables Setup.  

## OIOUBL Profiles

Your customers can use a profile that is based on the Danish OIOUBL definitions, or they can use a profile that is based on the OIOUBL implementation of the Northern European Subset (NES) definitions. Some profiles require responses to be sent when an electronic document is received. You can set up which profile most of your customers use. If a customer uses a different profile, you can change that in the customer card. For example, you can specify that the default profile is Procurement-OrdSim-BilSim-1.0, but that customer 10000 requires profile urn:www.nesubl.eu:profiles:profile5:ver2.0. For more information, see [Set Up OIOUBL](how-to-set-up-oioubl.md).  

For more information, see the entry on OIOUBL profiles in the frequently asked questions section at [Digitaliseringsstyrelsen](https://aka.ms/Digitaliseringsstyrelsen).  

## See Also

[Denmark Local Functionality](denmark-local-functionality.md)  
 [Set Up OIOUBL](how-to-set-up-oioubl.md)  
 [Set Up Customers for OIOUBL](how-to-set-up-customers-for-oioubl.md)  
 [Create Electronic Documents by Using OIOUBL](how-to-create-electronic-documents-by-using-oioubl.md)  
