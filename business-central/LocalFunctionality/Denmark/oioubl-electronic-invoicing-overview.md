---
title: OIOUBL Electronic Invoicing Overview | Microsoft Docs
description: Learn about how Business Central support you in the requirement for sending sales documents to the Danish public sector electronically in the OIOUBL format.
author: brentholtorf

    
ms.topic: overview
ms.devlang: al
ms.search.keywords:
ms.date: 11/11/2022
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# OIOUBL Electronic Invoicing Overview

Companies must send sales invoices, credit memos, finance charge memos, and reminders to the Danish public sector electronically in the Offentlig Information Online UBL (OIOUBL) format. If a company does not send these documents electronically, the authorities can deny payment.  

Learn more about OIOUBL electronic invoicing at [oioubl.info](http://www.oioubl.info/classes/da/index.html).  

## Implementation in [!INCLUDE[prod_short](../../includes/prod_short.md)]  

The current requirements for sending electronic invoices are based on OIOUBL, which is based on the Universal Business Language (UBL) version 2.0 standard. Learn more at [OASIS UBL](https://aka.ms/OasisUblSite) web site. The generated XML documents can then be sent to the customer.  

To send documents electronically, you must assign European Article Numbering (EAN) location numbers and account codes to the relevant customers on the **Customer Card** page. Learn more at [Set Up Customers for OIOUBL](how-to-set-up-customers-for-oioubl.md). These numbers are the included when you create documents, and post or issue them. After the documents have been posted or issued, you can create electronic versions to be sent to the customer. You can submit the following types of documents:  

- Sales invoice  
- Service invoice  
- Sales credit memo  
- Service credit memo  
- Finance charge memo  
- Reminder  

In the online version of [!INCLUDE [prod_short](../../includes/prod_short.md)] and the web client for on-premises versions, the XML file is created in your Downloads folder. For on-premises versions, the XML file is stored in the location defined on the Sales & Receivables Setup page.  

## OIOUBL Profiles

Your customers can use a profile that is based on the Danish OIOUBL definitions, or they can use a profile that is based on the OIOUBL implementation of the Northern European Subset (NES) definitions. Some profiles require responses to be sent when an electronic document is received. You can set up which profile most of your customers use. If a customer uses a different profile, you can change that in the customer card. For example, you can specify that the default profile is Procurement-OrdSim-BilSim-1.0, but that customer 10000 requires profile urn:www.nesubl.eu:profiles:profile5:ver2.0. For more information, see [Set Up OIOUBL](how-to-set-up-oioubl.md).  

For more information, see the entry on OIOUBL profiles in the frequently asked questions section at [Digitaliseringsstyrelsen](https://aka.ms/Digitaliseringsstyrelsen).  

## See Also

[Denmark Local Functionality](denmark-local-functionality.md)  
 [Set Up OIOUBL](how-to-set-up-oioubl.md)  
 [Set Up Customers for OIOUBL](how-to-set-up-customers-for-oioubl.md)  
 [Create Electronic Documents by Using OIOUBL](how-to-create-electronic-documents-by-using-oioubl.md)  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]