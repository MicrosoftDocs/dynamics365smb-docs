---
title: Set Up Dutch Electronic VAT and ICP Declarations
description: Set up Dutch electronic VAT and ICP declarations in Business Central, including contact details, Digipoort service endpoints, and certificate settings.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.date: 10/20/2026
ms.custom: bap-template
ai-usage: ai-assisted
---

# Set up electronic VAT and ICP declarations in the Dutch version

To create electronic VAT and ICP declarations and communicate with tax authorities, set up general information about electronic tax declarations. Your company must be registered with the tax authorities before you can send electronic declarations.

When electronic declarations are set up, you can begin to declare VAT and ICP to the tax authorities. Learn more in [Submitting Electronic VAT and ICP Declarations](electronic-vat-and-icp-declarations.md).  

## Set up electronic declarations  

Upload the certificates needed to communicate with Digipoort. Use the **Certificates** page to upload a client certificate and a service certificate. Then set up electronic declarations.

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Elec. Tax Declaration Setup**, and then choose the related link.  
1. On the **Elec. Tax Declaration Setup** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](../../includes/tooltip-inline-tip_md.md)]
1. Set **VAT Contact Type** and **ICP Contact Type** to **Tax Payer** or **Agent**, as appropriate for each declaration type. Fill in the taxpayer contact details or the agent contact details. For an agent, **Agent Contact ID** is the BECON number.
1. If you want to send electronic ICP declarations for a subsidiary company of a fiscal entity, select the **Part of Fiscal Entity** checkbox.  

   > [!NOTE]  
   > If a company has several companies registered as subsidiaries of a holding company, they can submit the VAT declaration individually or combined for one fiscal entity. To set up electronic declarations for subsidiaries of a holding company, you must select the **Part of Fiscal Entity** field on the **Elec. Tax Declaration Setup** page. You can then create an electronic declaration for only one company.
   >
   > To combine tax information for subsidiaries, prepare a VAT statement for each company and calculate the combined amounts separately. The electronic declaration doesn't consolidate multiple companies. Enter the combined amounts through the tax authority's portal.
   >
   > You can't combine tax information for ICP declarations. ICP declarations must always be submitted individually.
   >
   > For each subsidiary company, an electronic ICP declaration can be created and submitted to the tax authorities. These electronic ICP declarations must contain the VAT registration number of the subsidiary company and the value of the **Fiscal Entity No.** field on the **Company Information** page of the holding company.

1. On the **Digipoort** FastTab, fill in the fields as follows:

   - In the **Digipoort Delivery URL** field, specify the URL for the Digipoort Aanlever (delivery) service. Use the URL from the [Digipoort endpoint URLs](#digipoort-endpoint-urls) section.
   - In the **Digipoort Status URL** field, specify the URL for the Digipoort Statusinformatie (status) service. Use the URL from the [Digipoort endpoint URLs](#digipoort-endpoint-urls) section.
   - Select **Use Certificate Setup** to use the certificates selected in the following fields when sending declarations and receiving responses. This setting is required for VAT returns submitted with version **DigitalTaxDecl**.
   - In the **Client Certificate Code** field, specify the client certificate. This certificate must be a **PKIoverheid** client certificate.
   - In the **Service Certificate Code** field, specify the WUS service signing certificate. Download the certificate from the [Digipoort service signing certificate](#digipoort-service-signing-certificate) section, then upload it on the **Certificates** page.

1. On the **Endpoints** FastTab, review the XBRL schema version and taxonomy endpoints. These fields control the declaration format, not the Digipoort delivery and status services. Leave a field blank to use the default value supplied by your installed application version. Only enter an override when you need a different supported taxonomy.

## Digipoort endpoint URLs

Use the following Digipoort production endpoint URLs.

| Service | URL |
|---|---|
| Aanlever (delivery) | `https://wus.digipoort.logius.nl/wus/2.0/aanleverservice/1.2` |
| Statusinformatie (status) | `https://wus.digipoort.logius.nl/wus/2.0/statusinformatieservice/1.2` |

Confirm the current production endpoints and migration requirements with [Logius Digipoort guidance](https://www.logius.nl/onze-dienstverlening/gegevensuitwisseling/digipoort).

## Digipoort service signing certificate

Digipoort signs every response message with a service signing certificate. You must upload this certificate as the **Service Certificate** in [!INCLUDE[prod_short](../../includes/prod_short.md)] so that the response signature can be verified.

Download the certificate from [wus.productie.digipoort.logius.nl.cert](https://aansluiten.procesinfrastructuur.nl/site/binaries/content/assets/documentatie/nieuwe-digipoort/wus.productie.digipoort.logius.nl.cert).

Always verify that you use the most recent certificate. Logius publishes the current version on the [Aansluit Suite Digipoort](https://aansluiten.procesinfrastructuur.nl/site/documentatie/digipoort-migratie-instructie-voor-het-wus-koppelvlak) site.

## Migrating to the new Digipoort

Logius is migrating Digipoort to a new production environment with a new endpoint URL and a new service signing certificate. If your company already submits VAT or ICP declarations through Digipoort, you must migrate your connection.

Logius states that the Belastingdienst stops accepting messages through the old Digipoort on December 1, 2026. Complete the migration before that date. Learn more in the [Logius Digipoort guidance](https://www.logius.nl/onze-dienstverlening/gegevensuitwisseling/digipoort).

To migrate your connection, follow these steps:

1. Replace the values in the **Digipoort Delivery URL** and **Digipoort Status URL** fields with the new URLs from the [Digipoort endpoint URLs](#digipoort-endpoint-urls) section.
1. Upload the new service signing certificate from the [Digipoort service signing certificate](#digipoort-service-signing-certificate) section and select it in the **Service Certificate Code** field.

When you connect to the new Digipoort, the connection to the legacy Digipoort must be terminated. For the full list of changes, go to the official [Digipoort migration instruction for the WUS interface](https://aansluiten.procesinfrastructuur.nl/site/documentatie/digipoort-migratie-instructie-voor-het-wus-koppelvlak).

> [!NOTE]
> [!INCLUDE[prod_short](../../includes/prod_short.md)] online customers don't need to install PKIoverheid root or intermediate certificates. The service manages the trust relationship with Digipoort. Update both endpoint URL fields and upload and select the new service signing certificate. Keep your client certificate valid.

## Related information

[Submitting Electronic VAT and ICP Declarations](electronic-vat-and-icp-declarations.md)  
[Netherlands Local Functionality](netherlands-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
