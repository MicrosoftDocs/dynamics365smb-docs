---
    title: Electronic Tax Declarations
    description: Companies must deliver their VAT and ICP declarations electronically to the tax authorities.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 01/10/2018
    ms.author: sgroespe

---
# Electronic Tax Declarations
Companies must deliver their VAT and ICP declarations electronically to the tax authorities.  

## Prepare for Electronic Declaration  
 Before you can send electronic declarations to the tax authorities you must perform the following tasks:  

1.  Request user certificates from the certification authority (CA) and import them in the application. For more information, see the [website](http://go.microsoft.com/fwlink/?LinkID=223151) of the Dutch tax office.  
2.  Register at the tax authorities for electronic declaration.  
3.  Enter general data and personal data received from the tax authorities in the **Elec. Tax Declaration Setup** window.  

For more information, see [Electronic VAT and ICP Declarations](electronic-vat-and-icp-declarations.md).  

## Create and Submit Electronic Declarations  
When the tasks stated above are finished the application can create and submit VAT and ICP declarations to the tax authorities.  

For each electronic declaration the tax authorities will send a response message. These messages must be received from the server of the tax authorities and processed.  

## Response Message from the Tax Authorities  
The tax authorities will send a response message to inform the company about the status of their electronic declarations. The first step is to import the response messages from the tax authorities in [!INCLUDE[d365fin](../../includes/d365fin_md.md)]. The second step is processing the response messages.  

The response message must be linked to the related electronic tax declaration.

If the accompanying electronic tax declaration is found then, depending on the type of the response message, different steps must be performed.  

## Acknowledgement Response Message  
If no errors were found in the electronic declaration and the data has been processed by the tax authorities, the **Status** field in the **Elec. Tax Declaration Header** table will be changed into **Acknowledgement**.  

## Declaration for a Fiscal Entity  
If a company has several companies registered as subsidiaries of a holding company, they have the option to submit the VAT declaration individually or combined for one fiscal entity. Regardless of the choice, the ICP declarations must always be submitted individually.  

The application cannot combine tax information for several companies into one electronic VAT declaration. If the company wants to combine the tax information, they have to create a VAT statement on paper for each subsidiary company and calculate the total amount for the holding company. After that these amounts can be manually entered on the website of the tax authorities.  

For each subsidiary company an electronic ICP declaration can be created and submitted to the tax authorities. These electronic ICP declarations must contain the VAT registration number of the subsidiary company and the **Fiscal Entity No.** field of the holding company, in the **Company Information** window.  

To setup electronic declarations for subsidiaries of a holding company, you must select the **Part of Fiscal Entity** field in the **Elec. Tax Declaration Setup** window.  

## Digipoort
In the Netherlands, you use Digipoort to make periodic electronic filings for VAT declarations and ICP reports in EU sales list submissions. Digipoort is the electronic post office provided by the Dutch government for companies. It provides the common infrastructure for the communication of information between companies and the government, including VAT declarations. The reports are in XBRL format. For more information, see [Digipoort Overview](digipoort-overview.md).

## See Also  
 [Electronic VAT and ICP Declarations](electronic-vat-and-icp-declarations.md)  
 [Digipoort Overview](digipoort-overview.md)
