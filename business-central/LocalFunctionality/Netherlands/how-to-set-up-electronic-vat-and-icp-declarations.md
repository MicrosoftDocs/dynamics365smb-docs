---
title: Electronic VAT and ICP Declarations [NL]
description: Learn how to set up electronic VAT and ICP declarations in the Dutch Version.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: v-soumramani
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.date: 03/18/2025
ms.custom: bap-template
---

# Setting up electronic VAT and ICP declarations in the Dutch version

To create electronic VAT and ICP declarations and communicate with tax authorities, set up general information about electronic tax declarations. Your company must be registered with the tax authorities before you can send electronic declarations.

When electronic declarations are set up, you can begin to declare VAT and ICP to the tax authorities. Learn more in [Submitting Electronic VAT and ICP Declarations](electronic-vat-and-icp-declarations.md).  

## Set up electronic declarations  

Ensure that you've uploaded the certificates needed to communicate with Digipoort. Use the **Certificates** page to upload a client and a service certificate. When they're added to the list of certificates, you can continue with setting up electronics declarations.

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Elec. Tax Declaration Setup**, and then choose the related link.  
1. On the **Elec. Tax Declaration Setup** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](../../includes/tooltip-inline-tip_md.md)]
1. If you want the contact ID in the electronic declaration to be filled with the VAT registration number of the company, then select  **Tax Payer** in the **VAT Contact Type** field.
1. If you want to send electronic ICP declarations for a subsidiary company of a fiscal entity, select the **Part of Fiscal Entity** checkbox.  

   > [!NOTE]  
   > If a company has several companies registered as subsidiaries of a holding company, they have the option to submit the VAT declaration individually or combined for one fiscal entity. To set up electronic declarations for subsidiaries of a holding company, you must select the **Part of Fiscal Entity** field on the **Elec. Tax Declaration Setup** page. You can then create an electronic declaration for only one company.<br><br/>
   If you want to combine the tax information for all subsidiaries of a holding company, you must create a VAT statement on paper for each subsidiary company and manually calculate the total amounts for the holding company. These total amounts of the holding company must be entered on the website of the tax authorities.<br><br/>
   You can't combine tax information for ICP declarations. ICP declarations must always be submitted individually.<br><br/>
   For each subsidiary company, an electronic ICP declaration can be created and submitted to the tax authorities. These electronic ICP declarations must contain the VAT registration number of the subsidiary company and the value of the **Fiscal Entity No.** field on the **Company Information** page of the holding company.

1. On the **Digipoort** FastTab, set up the following configurations:
   - In the **Digipoort Delivery URL** field, specify the URL for the production version of the Digipoort Aanlever service. Learn more on [digipoort](https://www.logius.nl/producten/gegevensuitwisseling/digipoort).  
   - In the **Digipoort Status URL** field, specify the URL for the status information that is coming from the Digipoort Statusinformatie service. Learn more in [Electronic VAT and ICP Declarations](electronic-vat-and-icp-declarations.md).
   - Select **Use Certificate Setup** to specify that the certificate codes specified in the next step must be considered to transfer data to the information service.
   - In the **Client Certificate Code** field, specify the client certificate.
   - In the **Service Certificate Code** field, specify the service certificate.

1. To set up endpoints, add the endpoint URLs on the **Endpoints** FastTab.

   > [!NOTE]  
   > Endpoints set up is deployed to 21.1 tenants. However, all values are blank, but the Digipoort solution still works by taking hardcoded values if there are no values in the setup. In the 21.2 release, [!INCLUDE [prod_short](../../includes/prod_short.md)] automatically runs an upgrade.

## Related information

- [Submitting Electronic VAT and ICP Declarations](electronic-vat-and-icp-declarations.md)  
- [Netherlands Local Functionality](netherlands-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
