---
    title: Insert topic title| Microsoft Docs
    description: Insert description
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# EAN Location Number
A European Article Numbering \(EAN\) location number is an electronic address that you can use when you send an electronic invoice. This number uniquely identifies the buyer’s billing address. EAN location numbers can be used in countries\/regions outside Europe and are also referred to as Global Location Numbers \(GLN\).  
  
## EAN Location Numbers in ADD INCLUDE<!--[!INCLUDE[navnow](includes/navnow_md.md)]-->  
 Departments, directorates, agencies, and other organizations in the Danish public sector have EAN location numbers, which uniquely identifies the bill-to address of the customer. If your company has a customer who is in the public sector, you must submit invoices and other documents electronically by using Offentlig Information Online UBL \(OIOUBL\). In order to do that, you must specify the customer’s EAN location number. For more information, see [How to: Set Up Customers for OIOUBL](how-to-set-up-customers-for-oioubl.md).  
  
 An EAN location number has a fixed length of 13 digits. This number must be processed in its entirety. The following is an example of an EAN number.  
  
 **5790987654321**  
  
 EAN numbers start with a 3-digit prefix allocated by EAN International. For Denmark, the first three numbers are **579**. The EAN number ends with a check digit that is calculated based on the first 12 digits.  
  
## See Also  
 [OIOUBL Electronic Invoicing Overview](oioubl-electronic-invoicing-overview.md)   
 [How to: Set Up Customers for OIOUBL](how-to-set-up-customers-for-oioubl.md)