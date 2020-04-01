---
    title: Tax Identification Types for Mexico
    description: All customers and vendors must a have federal tax identification number. The identification type used for a customer or vendor depends on whether the customer or vendor is classified as a company or as a person.

    services: project-madeira 
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Tax Identification Types for Mexico
All customers and vendors must a have federal tax identification number. The identification type used for a customer or vendor depends on whether the customer or vendor is classified as a company or as a person.  

## Available Tax Identification Types  
In Mexico, a legal entity, such as a company or a person, is assigned a tax identification number according to two types.  

### Registro Federal de Contribuyentes (RFC)  

This tax identification type can be applied to companies and to people. An RFC number for a company is 12 characters, while an RFC number for a person is 13 characters.  

### Cédula de identification fiscal con clave única de registro de población (CURP)  
This tax identification type can only be applied to people. A CURP number is 18 characters.  

When you create a new customer or vendor in [!INCLUDE[d365fin](../../includes/d365fin_md.md)], you specify whether the customer or vendor is a company or a person, and then you specify the tax identification type. The tax identification type and the tax identification number are included in any reports that reference tax information about a customer or vendor.  

## See Also  
 [Mexico Local Functionality](mexico-local-functionality.md)
