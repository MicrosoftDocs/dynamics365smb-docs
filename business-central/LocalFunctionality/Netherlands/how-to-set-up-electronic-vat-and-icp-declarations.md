---
    title: Set Up Electronic VAT and ICP Declarations
    description: To get your Digipoort communications to work, you may have to adjust your network settings. Digipoort uses a secure communication protocol and requires using TCP port 443.
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
# Setting Up Electronic VAT and ICP Declarations
To create electronic VAT and ICP declarations and communicate with the tax authorities, you must first set up general information about electronic tax declarations. Your company must be registered with the tax authorities before you can send electronic declarations.

When electronic declarations are set up, you can begin to declare VAT and ICP to the tax authorities. For more information, see [Submitting Electronic VAT and ICP Declarations](electronic-vat-and-icp-declarations.md).  

## To set up electronic declarations  

1. Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Elec. Tax Declaration Setup**, and then choose the related link.  
2. On the **Elec. Tax Declaration Setup** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](../../includes/tooltip-inline-tip_md.md)]
3. If you want the contact ID in the electronic declaration to be filled with the VAT registration number of the company, then select  **Tax Payer** in the **VAT Contact Type** field.
4. If you want to send electronic ICP declarations for a subsidiary company of a fiscal entity, then select the select the **Part of Fiscal Entity** check box.  

    > [!NOTE]  
    > If a company has several companies registered as subsidiaries of a holding company, they have the option to submit the VAT declaration individually or combined for one fiscal entity. To set up electronic declarations for subsidiaries of a holding company, you must select the **Part of Fiscal Entity** field on the **Elec. Tax Declaration Setup** page. You can then create an electronic declaration for only one company.<br /><br />
    If you want to combine the tax information for all subsidiaries of a holding company, you must create a VAT statement on paper for each subsidiary company and manually calculate the total amounts for the holding company. These total amounts of the holding company must be entered on the website of the tax authorities.<br /><br />
    You cannot combine tax information for ICP declarations. ICP declarations must always be submitted individually.<br /><br />
    For each subsidiary company an electronic ICP declaration can be created and submitted to the tax authorities. These electronic ICP declarations must contain the VAT registration number of the subsidiary company and the value of the **Fiscal Entity No.** field on the **Company Information** page of the holding company.

5. In the **Digipoort Delivery URL** field, specify the URL for the production version of the Digipoort Aanlever service. For more information, see [https://www.logius.nl/producten/gegevensuitwisseling/digipoort](https://www.logius.nl/producten/gegevensuitwisseling/digipoort).  
6. In the **Digipoort Status URL** field, specify the URL for the status information that is coming from the Digipoort Statusinformatie service. For more information, see [Electronic VAT and ICP Declarations](electronic-vat-and-icp-declarations.md).

## See Also  
 [Submitting Electronic VAT and ICP Declarations](electronic-vat-and-icp-declarations.md)  
 [Netherlands Local Functionality](netherlands-local-functionality.md)
