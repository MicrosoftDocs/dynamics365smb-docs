---
    title: How to Set Up Electronic VAT and ICP Declarations
    description: To get your Digipoort communications to work, you may have to adjust your network settings. Digipoort uses a secure communication protocol and requires using TCP port 443.
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
# Set Up Electronic VAT and ICP Declarations
To get your Digipoort communications to work, you may have to adjust your network settings. Digipoort uses a secure communication protocol and requires using TCP port 443. Before proceeding with the following procedure, set up your network to use this port.  

To be able to create electronic VAT and ICP declarations and communicate with the tax authorities, you must first set up general information about electronic tax declarations. Your company must be registered with the tax authorities before you can send electronic declarations.  

## To set up electronic tax declarations  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Elec. Tax Declaration Setup**, and then choose the related link.  
2.  In the **Elec. Tax Declaration Setup** window, on the **General** FastTab, select the **VAT Contact Type**.

    The options include **Tax Payer** and **Agent**. If the contact type is **Tax Payer**, the contact ID in the electronic declaration will be filled with the VAT registration number of the company.  

3.  Select the **ICP Contact Type**. The options include **Tax Payer** and **Agent**.  
4.  If you want to send electronic ICP declarations for a subsidiary company of a fiscal entity, select the **Part of Fiscal Entity** field.  
5.  On the **Numbering** FastTab, enter the number series for the **VAT Declaration Nos. Field** field.  
6.  On the **Digipoort** FastTab, enter the data needed for the Digipoort submissions.  

    1.  In the **Digipoort Client Cert. Name** field, enter the common name (CN) of the certificate you requested for use with Digipoort. You can find this information in the certificate properties of the personal certificate that you installed under the **Personal** folder. For more information, see [Set Up Certificates for use with Digipoort](how-to-set-up-certificates-for-use-with-digipoort.md).  
    2.  In the **Digipoort Service Cert. Name** field, enter the common name of the service certificate, which may be equal to the name of the server that that you are communicating with for the Dutch government. You can find this information in the certificate properties of the public certificate that was installed in the **Trusted Publishers** folder. For more information, see [Set Up Certificates for use with Digipoort](how-to-set-up-certificates-for-use-with-digipoort.md).  
    3.  In the **Digipoort Delivery URL** field, specify the URL for the production version of the Digipoort Aanlever service. For more information, see [http://www.logius.nl/producten/gegevensuitwisseling/digipoort](http://www.logius.nl/producten/gegevensuitwisseling/digipoort).  
    4.  In the **Digipoort Status URL** field, specify the URL for the status information that is coming from the Digipoort Statusinformatie service.  

    For more information, see [Digipoort Overview](digipoort-overview.md).  

Currently, there are two sets of URLs that are provided by the Dutch Tax Administration. These are subject to change, however, and you should check the administration’s website regularly for updates.  

**Production Use**  

- Digipoort Delivery URL: https://www.procesinfrastructuur.nl/wus/2.0/aanleverservice/1.2  
- Digipoort Status URL: https://www.procesinfrastructuur.nl/wus/2.0/statusinformatieservice/1.2  

**Testing Use**  

- Digipoort Delivery URL: https://preprod.procesinfrastructuur.nl/wus/2.0/aanleverservice/1.2  
- Digipoort Status URL: https://preprod.procesinfrastructuur.nl/wus/2.0/statusinformatieservice/1.2  

## See Also  
 [Submit Electronic VAT and ICP Declarations](how-to-submit-electronic-vat-and-icp-declarations.md)   
 [Process Response Messages from Tax Authorities](how-to-process-response-messages-from-tax-authorities.md)
