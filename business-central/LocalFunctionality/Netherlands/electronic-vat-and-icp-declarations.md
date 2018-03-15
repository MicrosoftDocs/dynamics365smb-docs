---
    title: Electronic VAT and ICP Declarations
    description: Companies must submit periodic VAT and ICP declarations.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# Electronic VAT and ICP Declarations
Companies must submit periodic VAT and ICP declarations.  

VAT declarations must be submitted on a monthly or quarterly basis.  

Companies that sell goods or services to European Union (EU) countries must submit Intracommunautaire leveringen (ICP) declarations on a quarterly basis. Purchases are not included in this declaration. For these intracommunautaire transactions, it is required that the merchandise have crossed the border physically. It is not enough that the location of an invoice address or the office of the vendor or customer is in another EU country or region.  

> [!NOTE]  
>  Before you can send electronic declarations to the tax authorities you must register your company for electronic declaration. The information that the tax authorities need depends on the sign method your company will use, PIN or PKI. For both methods, you have to send the form "Aanmeldingsformulier voor elektronisch berichtenverkeer met de belastingdienst" to the tax authorities.  
>   
>  For more information, see the [website](http://go.microsoft.com/fwlink/?LinkID=223151) of the Dutch tax office.  

## Submitting Electronic Tax Declarations  
You can submit the VAT declarations and ICP declarations in the following ways:  

- Log on to the website of the Dutch tax office and enter the information manually. For more information, see the [website](http://go.microsoft.com/fwlink/?LinkID=223151) of the Dutch tax office.  

    For ICP declarations, you can enter a maximum of 99 lines.  

- Create an electronic declaration and submit the encrypted file through Simple Mail Transfer Protocol (SMTP) server to the Dutch tax office.  

The electronic VAT declaration contains the posted VAT and the calculated duty liable to the customs authorities for a specified period. The data of the VAT declaration is based on the definition of the VAT statement in the **VAT Statement Line** table. For more information, see VAT Statement Line.  

The data of the ICP declaration is based on the **VAT Entry** table. For more information, see VAT Entry.  

## Electronic Tax Declaration Methods  
You can submit the VAT and ICP declarations electronically to the tax authorities using the following methods:  

**Personal identification number (PIN) method**  
 Uses a PIN code to sign the declaration. If you submit your declarations using the PIN method, you must create a PIN code for your company and deliver it to the tax authorities. This code helps the tax authorities to identify the company that has submitted the electronic declaration. This PIN code is not stored in the database. Therefore, you must save the PIN code in a secure location.  

> [!WARNING]  
>  The tax authorities are reconsidering whether to accept declarations that are signed using a PIN code. For more information, see the [website](http://go.microsoft.com/fwlink/?LinkID=223151) of the Dutch tax office.  

**Public Key Infrastructure (PKI) method**  
 Uses digital certificates to encrypt messages and verify digital signature. If you submit your declarations using the PKI method, you must also have additional certificates, generic parameters, and other parameters when you use the PKI method. For more information, see the [website](http://go.microsoft.com/fwlink/?LinkID=223151) of the Dutch tax office.  

## Contact Information  
The electronic VAT and ICP declarations contain contact information about the taxpayer or the agent. For more information, see VAT Registration No..  

## See Also  
 [Electronic Tax Declarations](electronic-tax-declarations.md)   
 [Set Up VAT Categories](how-to-set-up-vat-categories.md)   
 [Create Electronic VAT and ICP Declarations](how-to-create-electronic-vat-and-icp-declarations.md)   
 [Process Response Messages from Tax Authorities](how-to-process-response-messages-from-tax-authorities.md)
