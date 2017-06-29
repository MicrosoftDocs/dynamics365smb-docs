---
title: "EAN Location Number"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "Global Location Numbers (GLN)"
  - "European Article Numbering (EAN)"
  - "EAN location numbers, about"
ms.assetid: bc7b7247-be10-4ce8-99c0-ad8f4f8c1ee7
caps.latest.revision: 8
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
---
# EAN Location Number
A European Article Numbering \(EAN\) location number is an electronic address that you can use when you send an electronic invoice. This number uniquely identifies the buyer’s billing address. EAN location numbers can be used in countries\/regions outside Europe and are also referred to as Global Location Numbers \(GLN\).  
  
## EAN Location Numbers in FIX INCLUDE HERE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] -->  
 Departments, directorates, agencies, and other organizations in the Danish public sector have EAN location numbers, which uniquely identifies the bill\-to address of the customer. If your company has a customer who is in the public sector, you must submit invoices and other documents electronically by using Offentlig Information Online UBL \(OIOUBL\). In order to do that, you must specify the customer’s EAN location number. For more information, see [How to: Set Up Customers for OIOUBL](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Denmark/how-to-set-up-customers-for-oioubl.md).  
  
 An EAN location number has a fixed length of 13 digits. This number must be processed in its entirety. The following is an example of an EAN number.  
  
 **5790987654321**  
  
 EAN numbers start with a 3\-digit prefix allocated by EAN International. For Denmark, the first three numbers are **579**. The EAN number ends with a check digit that is calculated based on the first 12 digits.  
  
## See Also  
 [OIOUBL Electronic Invoicing Overview](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Denmark/oioubl-electronic-invoicing-overview.md)   
 [How to: Set Up Customers for OIOUBL](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Denmark/how-to-set-up-customers-for-oioubl.md)