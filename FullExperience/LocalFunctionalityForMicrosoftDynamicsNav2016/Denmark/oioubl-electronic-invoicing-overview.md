---
title: "OIOUBL Electronic Invoicing Overview"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "invoices, electronic"
  - "electronic invoices, about"
  - "OIOUBL, about"
ms.assetid: b9e88827-7f1e-468e-82cd-62eb2baa5e9a
caps.latest.revision: 14
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
---
# OIOUBL Electronic Invoicing Overview
Companies must send sales invoices, credit memos, finance charge memos, and reminders to the Danish public sector electronically in the Offentlig Information Online UBL \(OIOUBL\) format. If a company does not send these documents electronically, the authorities can deny payment.  
  
 For more information about OIOUBL electronic invoicing, see [oioubl.info](http://www.oioubl.info).  
  
## Implementation in [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]  
 The current requirements for sending electronic invoices are based on OIOUBL, which is based on the Universal Business Language \(UBL\) version 2.0 standard. For more information, see the [OASIS UBL](http://go.microsoft.com/fwlink/?LinkId=212593) website. The generated XML documents can then be sent to the customer.  
  
 To send documents electronically, you must assign European Article Numbering \(EAN\) location numbers and account codes to the relevant customers in the **\($ N\_21 Customer Card $\)** window. For more information, see [How to: Set Up Customers for OIOUBL](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Denmark/how-to-set-up-customers-for-oioubl.md). These numbers are the included when you create documents, and post or issue them. After the documents have been posted or issued, you can create electronic versions to be sent to the customer. You can submit the following types of documents:  
  
-   Sales invoice  
  
-   Service invoice  
  
-   Sales credit memo  
  
-   Service credit memo  
  
-   Finance charge memo  
  
-   Reminder  
  
 The electronic documents are stored in the locations that are defined in the [\($ N\_459 Sales & Receivables Setup $\)\-duplicate](../../Sales/-$-n_459-sales-receivables-setup-$-duplicate.md) window. For more information, see [How to: Set Up OIOUBL](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Denmark/how-to-set-up-oioubl.md).  
  
## OIOUBL Profiles  
 Your customers can use a profile that is based on the Danish OIOUBL definitions, or they can use a profile that is based on the OIOUBL implementation of the Northern European Subset \(NES\) definitions. Some profiles require responses to be sent when an electronic document is received. You can set up which profile most of your customers use. If a customer uses a different profile, you can change that in the customer card. For example, you can specify that the default profile is Procurement\-OrdSim\-BilSim\-1.0, but that customer 10000 requires profile urn:www.nesubl.eu:profiles:profile5:ver2.0. For more information, see [How to: Set Up OIOUBL](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Denmark/how-to-set-up-oioubl.md).  
  
 For more information, see the entry on OIOUBL profiles in the frequently asked questions section at [Digitaliseringsstyrelsen](http://go.microsoft.com/fwlink/?LinkId=267236).  
  
## See Also  
 [How to: Set Up OIOUBL](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Denmark/how-to-set-up-oioubl.md)   
 [How to: Set Up Customers for OIOUBL](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Denmark/how-to-set-up-customers-for-oioubl.md)   
 [How to: Create Electronic Documents by Using OIOUBL](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Denmark/how-to-create-electronic-documents-by-using-oioubl.md)   
 [EAN Location Number](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Denmark/ean-location-number.md)