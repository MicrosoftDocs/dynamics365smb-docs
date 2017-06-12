---
title: "Report 347"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "347 report, about"
  - "Report 347, about"
ms.assetid: 4d5f482d-0cb1-4a48-b2d1-5b52d874e8f9
caps.latest.revision: 33
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "es-es"
---
# Report 347
**Report 347** is a required annual report sent by all companies to the tax authorities to reflect the sales or purchases in a given period. This report also includes entries such as payment in cash that was received in the period. **Report 347** is generated in a format that is approved by the tax authorities. This file can be uploaded to the Spanish Tax Agency website or submitted on CD\-ROM. For more information, see the [Spanish Tax Agency](http://www.aeat.es/wps/portal/Home?channel=1af861cd949a1010VgnVCM100000d7005a80____&ver=L&site=56d8237c0bc1ff00VgnVCM100000d7005a80____&idioma=es_ES&menu=0&img=0) website.  
  
## File Format for Report 347  
 The file format for **Report 347** includes at least one responsible company, a deponent, and a customer\/vendor register. A responsible company is a company that submits the information to the Spanish Tax Agency. Deponent information comes from the **Company Information** table and the request form. Customer information comes from the **Customer** table, the **Cust. Ledger Entry** table, and the **G\/L Entry** table. Vendor information comes from the **Vendor** table and the **Vendor Ledger Entry** table.  
  
> [!NOTE]  
>  If there are no file records, the file is not created and an error message is displayed.  
  
## File Format Restrictions for Report 347  
 Before creating **Report 347**, the following file format restrictions will be considered:  
  
-   All amounts must be positive.  
  
-   All text must be capitalized.  
  
-   All alphanumeric fields must be left\-aligned.  
  
-   All numeric fields must be right\-aligned.  
  
-   If the company receives payments in cash that are over the predefined official threshold for these transactions, a four\-digit year must be included. The year indicates when the invoices that are related to receivables were posted.  
  
-   Special characters must be converted to standard characters.  
  
-   If the field has no value, it will be blank for alphanumeric fields and populated with zeros for numeric fields.  
  
## See Also  
 [Spain Local Functionality](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Spain/spain-local-functionality.md)   
 [How to: Create Report 347](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Spain/how-to-create-report-347.md)   
 [Make 347 Declaration](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Spain/-$-b_10707-make-347-declaration-$-.md)   
 [347 Declaration Labels](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Spain/-$-r_10708-347-declaration-labels-$-.md)