---
title: Electronic VAT and ICP Declarations [NL]
description: This article describes how to Set Up Electronic VAT and ICP Declarations in the Dutch Version.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.date: 12/01/2022
ms.custom: bap-template
---

# Setting Up Electronic VAT and ICP Declarations in the Dutch Version

To create electronic VAT and ICP declarations and communicate with tax authorities, set up general information about electronic tax declarations. Your company must be registered with the tax authorities before you can send electronic declarations.

When electronic declarations are set up, you can begin to declare VAT and ICP to the tax authorities. For more information, see [Submitting Electronic VAT and ICP Declarations](electronic-vat-and-icp-declarations.md).  

## To set up electronic declarations  

Ensure that you've uploaded the certificates needed to communicate with Digipoort. Use the **Certificates** page to upload a client and a service certificate. When they're added to the list of certificates, you can continue with setting up electronics declarations.

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Elec. Tax Declaration Setup**, and then choose the related link.  
2. On the **Elec. Tax Declaration Setup** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](../../includes/tooltip-inline-tip_md.md)]
3. If you want the contact ID in the electronic declaration to be filled with the VAT registration number of the company, then select  **Tax Payer** in the **VAT Contact Type** field.
4. If you want to send electronic ICP declarations for a subsidiary company of a fiscal entity, select the **Part of Fiscal Entity** checkbox.  

    > [!NOTE]  
    > If a company has several companies registered as subsidiaries of a holding company, they have the option to submit the VAT declaration individually or combined for one fiscal entity. To set up electronic declarations for subsidiaries of a holding company, you must select the **Part of Fiscal Entity** field on the **Elec. Tax Declaration Setup** page. You can then create an electronic declaration for only one company.<br /><br />
    If you want to combine the tax information for all subsidiaries of a holding company, you must create a VAT statement on paper for each subsidiary company and manually calculate the total amounts for the holding company. These total amounts of the holding company must be entered on the website of the tax authorities.<br /><br />
    You cannot combine tax information for ICP declarations. ICP declarations must always be submitted individually.<br /><br />
    For each subsidiary company an electronic ICP declaration can be created and submitted to the tax authorities. These electronic ICP declarations must contain the VAT registration number of the subsidiary company and the value of the **Fiscal Entity No.** field on the **Company Information** page of the holding company.

5. On the **Digipoort** FastTab, set up the following configurations:
   - In the **Digipoort Delivery URL** field, specify the URL for the production version of the Digipoort Aanlever service. Learn more at [https://www.logius.nl/producten/gegevensuitwisseling/digipoort](https://www.logius.nl/producten/gegevensuitwisseling/digipoort).  
   - In the **Digipoort Status URL** field, specify the URL for the status information that is coming from the Digipoort Statusinformatie service. Learn more at [Electronic VAT and ICP Declarations](electronic-vat-and-icp-declarations.md).
   - Select **Use Certificate Setup** to specify that the certificate codes specified in the next step must be considered to transfer data to the information service.
   - In the **Client Certificate Code** field, specify the client certificate.
   - In the **Service Certificate Code** field, specify the service certificate.

6. To set up endpoints, add the endpoint URLs on the **Endpoints** FastTab.

    > [!NOTE]  
    > Endpoints set up will be deployed to 21.1 tenants. However, all values will be blank, but the Digipoort solution will still work by taking hardcoded values if there are no values in the setup. In the 21.2 release, [!INCLUDE [prod_short](../../includes/prod_short.md)] will automatically run an upgrade.

## See Also  

[Submitting Electronic VAT and ICP Declarations](electronic-vat-and-icp-declarations.md)  
[Netherlands Local Functionality](netherlands-local-functionality.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
