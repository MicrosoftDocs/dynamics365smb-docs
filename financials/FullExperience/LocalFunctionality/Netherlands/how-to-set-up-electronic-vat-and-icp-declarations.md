---
title: "How to: Set Up Electronic VAT and ICP Declarations"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "electronic declarations, setting up"
  - "VAT, electronic declarations"
ms.assetid: cb7ee497-eb81-409e-b104-0663c758b6ef
caps.latest.revision: 15
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "nl-nl"
---
# How to: Set Up Electronic VAT and ICP Declarations
To get your Digipoort communications to work, you may have to adjust your network settings. Digipoort uses a secure communication protocol and requires using TCP port 443. Before proceeding with the following procedure, set up your network to use this port.  
  
 To be able to create electronic VAT and ICP declarations and communicate with the tax authorities, you must first set up general information about electronic tax declarations. Your company must be registered with the tax authorities before you can send electronic declarations.  
  
### To set up electronic tax declarations  
  
1.  In the **Search** box, enter **\($ N\_11410 Elec. Tax Declaration Setup $\)**, and then choose the related link.  
  
2.  In the **\($ N\_11410 Elec. Tax Declaration Setup $\)** window, on the **General** FastTab, select the **\($ T\_11408\_10 VAT Contact Type $\)**. The options include **Tax Payer** and **Agent**. If the contact type is **Tax Payer**, the contact ID in the electronic declaration will be filled with the [\($ T\_79\_19 VAT Registration No. $\)](assetId:///b8cbe882-81ca-4d13-a81f-3e64bbf72b77) of the company.  
  
3.  Select the **\($ T\_11408\_19 ICP Contact Type $\)**. The options include **Tax Payer** and **Agent**.  
  
4.  If you want to send electronic ICP declarations for a subsidiary company of a fiscal entity, select the **\($ T\_11408\_230 Part of Fiscal Entity $\)** field.  
  
5.  On the **Numbering** FastTab, enter the number series for the **\($ T\_11408\_2 VAT Declaration Nos. Field $\)** field.  
  
6.  On the **Digipoort** FastTab, enter the data needed for the Digipoort submissions.  
  
    1.  In the **\($ T\_11408\_250 Digipoort Client Cert. Name $\)** field, enter the common name \(CN\) of the certificate you requested for use with Digipoort. You can find this information in the certificate properties of the personal certificate that you installed under the **Personal** folder in the procedure [How to: Set Up Certificates for use with Digipoort](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/how-to-set-up-certificates-for-use-with-digipoort.md).  
  
    2.  In the **\($ T\_11408\_251 Digipoort Service Cert. Name $\)** field, enter the common name of the service certificate, which may be equal to the name of the server that that you are communicating with for the Dutch government. You can find this information in the certificate properties of the public certificate that was installed in the **Trusted Publishers** folder in the procedure [How to: Set Up Certificates for use with Digipoort](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/how-to-set-up-certificates-for-use-with-digipoort.md).  
  
    3.  In the **\($ T\_11408\_252 Digipoort Delivery URL $\)** field, specify the URL for the production version of the Digipoort Aanlever service. For more information, see [http:\/\/www.logius.nl\/producten\/gegevensuitwisseling\/digipoort](http://www.logius.nl/producten/gegevensuitwisseling/digipoort).  
  
    4.  In the **\($ T\_11408\_253 Digipoort Status URL $\)** field, specify the URL for the status information that is coming from the Digipoort Statusinformatie service.  
  
     For more information, see [Digipoort Overview](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/digipoort-overview.md).  
  
 Currently, there are two sets of URLs that are provided by the Dutch Tax Administration. These are subject to change, however, and you should check the administration’s website regularly for updates.  
  
 **Production Use**  
  
-   Digipoort Delivery URL: https:\/\/www.procesinfrastructuur.nl\/wus\/2.0\/aanleverservice\/1.2  
  
-   Digipoort Status URL: https:\/\/www.procesinfrastructuur.nl\/wus\/2.0\/statusinformatieservice\/1.2  
  
 **Testing Use**  
  
-   Digipoort Delivery URL: https:\/\/preprod.procesinfrastructuur.nl\/wus\/2.0\/aanleverservice\/1.2  
  
-   Digipoort Status URL: https:\/\/preprod.procesinfrastructuur.nl\/wus\/2.0\/statusinformatieservice\/1.2  
  
## See Also  
 [How to: Submit Electronic VAT and ICP Declarations](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/how-to-submit-electronic-vat-and-icp-declarations.md)   
 [How to: Process Response Messages from Tax Authorities](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/how-to-process-response-messages-from-tax-authorities.md)