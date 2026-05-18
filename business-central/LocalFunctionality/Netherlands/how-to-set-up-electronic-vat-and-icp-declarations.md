---
title: Electronic VAT and ICP Declarations [NL]
description: Learn how to set up electronic VAT and ICP declarations in the Dutch Version.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.date: 05/08/2026
ms.custom: bap-template
---

# Setting up electronic VAT and ICP declarations in the Dutch version

To create electronic VAT and ICP declarations and communicate with tax authorities, set up general information about electronic tax declarations. Your company must be registered with the tax authorities before you can send electronic declarations.

When electronic declarations are set up, you can begin to declare VAT and ICP to the tax authorities. Learn more in [Submitting Electronic VAT and ICP Declarations](electronic-vat-and-icp-declarations.md).  

## Set up electronic declarations  

Ensure that you upload the certificates needed to communicate with Digipoort. Use the **Certificates** page to upload a client and a service certificate. When they're added to the list of certificates, you can continue with setting up electronics declarations.

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Elec. Tax Declaration Setup**, and then choose the related link.  
1. On the **Elec. Tax Declaration Setup** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](../../includes/tooltip-inline-tip_md.md)]
1. If you want the contact ID in the electronic declaration to be filled with the VAT registration number of the company, then select  **Tax Payer** in the **VAT Contact Type** field.
1. If you want to send electronic ICP declarations for a subsidiary company of a fiscal entity, select the **Part of Fiscal Entity** checkbox.  

   > [!NOTE]  
   > If a company has several companies registered as subsidiaries of a holding company, they can submit the VAT declaration individually or combined for one fiscal entity. To set up electronic declarations for subsidiaries of a holding company, you must select the **Part of Fiscal Entity** field on the **Elec. Tax Declaration Setup** page. You can then create an electronic declaration for only one company.
   >
   > If you want to combine the tax information for all subsidiaries of a holding company, you must create a VAT statement on paper for each subsidiary company and manually calculate the total amounts for the holding company. These total amounts of the holding company must be entered on the website of the tax authorities.
   >
   > You can't combine tax information for ICP declarations. ICP declarations must always be submitted individually.
   >
   > For each subsidiary company, an electronic ICP declaration can be created and submitted to the tax authorities. These electronic ICP declarations must contain the VAT registration number of the subsidiary company and the value of the **Fiscal Entity No.** field on the **Company Information** page of the holding company.

1. On the **Digipoort** FastTab, fill in the fields as follows:

   - In the **Digipoort Delivery URL** field, specify the URL for the Digipoort Aanlever (delivery) service. Use the URL from the [Digipoort endpoint URLs](#digipoort-endpoint-urls) section.
   - In the **Digipoort Status URL** field, specify the URL for the Digipoort Statusinformatie (status) service. Use the URL from the [Digipoort endpoint URLs](#digipoort-endpoint-urls) section.
   - Select **Use Certificate Setup** to specify that the certificate codes specified in the next step must be considered to transfer data to the information service.
   - In the **Client Certificate Code** field, specify the client certificate. This certificate must be a **PKIoverheid** client certificate.
   - In the **Service Certificate Code** field, specify the WUS service signing certificate. Download the certificate from the [Digipoort service signing certificate](#digipoort-service-signing-certificate) section, then upload it on the **Certificates** page.

1. To set up endpoints, add the endpoint URLs on the **Endpoints** FastTab.

   > [!NOTE]  
   > The endpoints setup is deployed to 21.1 tenants. However, all values are blank, but the Digipoort solution still works by taking hardcoded values if there are no values in the setup. In the 21.2 release, [!INCLUDE [prod_short](../../includes/prod_short.md)] automatically runs an upgrade.

## Digipoort endpoint URLs

Use the following Digipoort production endpoint URLs.

| Service | URL |
|---|---|
| Aanlever (delivery) | `https://wus.digipoort.logius.nl/wus/2.0/aanleverservice/1.2` |
| Statusinformatie (status) | `https://wus.digipoort.logius.nl/wus/2.0/statusinformatieservice/1.2` |

Learn more at [digipoort](https://www.logius.nl/producten/gegevensuitwisseling/digipoort).

## Digipoort service signing certificate

Digipoort signs every response message with a service signing certificate. You must upload this certificate as the **Service Certificate** in [!INCLUDE[prod_short](../../includes/prod_short.md)] so that the response signature can be verified.

Download the certificate from [wus.productie.digipoort.logius.nl.cert](https://aansluiten.procesinfrastructuur.nl/site/binaries/content/assets/documentatie/nieuwe-digipoort/wus.productie.digipoort.logius.nl.cert).

Always verify that you use the most recent certificate. Logius publishes the current version on the [Aansluit Suite Digipoort](https://aansluiten.procesinfrastructuur.nl/site/documentatie/digipoort-migratie-instructie-voor-het-wus-koppelvlak) site.

## Migrating to the new Digipoort

Logius is migrating Digipoort to a new production environment with a new endpoint URL and a new service signing certificate. If your company already submits VAT or ICP declarations through Digipoort, you must migrate your connection.

To migrate your connection, follow these steps:

1. Replace the values in the **Digipoort Delivery URL** and **Digipoort Status URL** fields with the new URLs from the [Digipoort endpoint URLs](#digipoort-endpoint-urls) section.
1. Upload the new service signing certificate from the [Digipoort service signing certificate](#digipoort-service-signing-certificate) section and select it in the **Service Certificate Code** field.

When you connect to the new Digipoort, the connection to the legacy Digipoort must be terminated. For the full list of changes, go to the official [Digipoort migration instruction for the WUS interface](https://aansluiten.procesinfrastructuur.nl/site/documentatie/digipoort-migratie-instructie-voor-het-wus-koppelvlak).

> [!NOTE]
> [!INCLUDE[prod_short](../../includes/prod_short.md)] online customers don't need to install any PKIoverheid root or intermediate certificates. The [!INCLUDE[prod_short](../../includes/prod_short.md)] service the trust relationship with the new Digipoort. The only customer-side actions required are updating the endpoint URL fields and uploading the new service signing certificate.

## Related information

[Submitting Electronic VAT and ICP Declarations](electronic-vat-and-icp-declarations.md)  
[Netherlands Local Functionality](netherlands-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
