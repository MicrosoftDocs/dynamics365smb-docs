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
# Electronic Tax Declarations
Companies must deliver their VAT and ICP declarations electronically to the tax authorities.  
  
## Prepare for Electronic Declaration  
 Before you can send electronic declarations to the tax authorities you must perform the following tasks:  
  
1.  Request user certificates from the certification authority \(CA\) and import them in the application. For more information, see the [website](http://go.microsoft.com/fwlink/?LinkID=223151) of the Dutch tax office.  
  
2.  Register at the tax authorities for electronic declaration.  
  
3.  Enter general data and personal data received from the tax authorities in the Elec. Tax Declaration Setup Window window.  
  
 For more information, see [Electronic VAT and ICP Declarations](electronic-vat-and-icp-declarations.md).  
  
## Create and Submit Electronic Declarations  
 When the tasks stated above are finished the application can create and submit VAT and ICP declarations to the tax authorities.  
  
 For each electronic declaration the tax authorities will send a response message. These messages must be received from the server of the tax authorities and processed.  
  
## Response Message from the Tax Authorities  
 The tax authorities will send a response message to inform the company about the status of their electronic declarations. The first step is to import the response messages from the tax authorities in [!INCLUDE[d365fin](../../includes/d365fin_md.md)]. The second step is processing the response messages.  
  
 The response message must be linked to the related electronic tax declaration. For more information, see Elec. Tax Declaration Header Table. If no accompanying electronic tax declaration is found, an error message will appear.  
  
 If the accompanying electronic tax declaration is found then, depending on the type of the response message, different steps must be performed.  
  
## Acknowledgement Response Message  
 If no errors were found in the electronic declaration and the data has been processed by the tax authorities, the Status Field field in the **Elec. Tax Declaration Header** table will be changed into **Acknowledgement**.  
  
## Declaration for a Fiscal Entity  
 If a company has several companies registered as subsidiaries of a holding company, they have the option to submit the VAT declaration individually or combined for one fiscal entity. Regardless of the choice, the ICP declarations must always be submitted individually.  
  
 The application cannot combine tax information for several companies into one electronic VAT declaration. If the company wants to combine the tax information, they have to create a VAT statement on paper for each subsidiary company and calculate the total amount for the holding company. After that these amounts can be manually entered on the website of the tax authorities.  
  
 For each subsidiary company an electronic ICP declaration can be created and submitted to the tax authorities. These electronic ICP declarations must contain the VAT Registration No. of the subsidiary company and the Fiscal Entity No. Field of the holding company out of the Company Information table.  
  
 To setup electronic declarations for subsidiaries of a holding company, you must place a check mark in the field Part of Fiscal Entity Field in the Elec. Tax Declaration Setup Window window.  
  
## See Also  
 [Electronic VAT and ICP Declarations](electronic-vat-and-icp-declarations.md)   
 [OBSOLETE: General Parameters and Certificates](OBSOLETE:%20General%20Parameters%20and%20Certificates.md)   
 [OBSOLETE: How to: Set Up PKI-Based User Certificates for Electronic Tax Declarations](OBSOLETE:%20How%20to:%20Set%20Up%20PKI-Based%20User%20Certificates%20for%20Electronic%20Tax%20Declarations.md)   
 [OBSOLETE: How to: Register for Electronic VAT and ICP Declarations](OBSOLETE:%20How%20to:%20Register%20for%20Electronic%20VAT%20and%20ICP%20Declarations.md)   
 Elec. Tax Declaration Setup Window