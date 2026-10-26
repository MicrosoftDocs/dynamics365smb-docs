---
title: Submit Electronic VAT and ICP Declarations in the Netherlands
description: With the eXtensible Business Reporting Language (XBRL) reporter, you can submit the ICP declaration or the VAT declaration in the required XML format.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: extensible business reporting, ICP declaration, Dutch version, Netherlands, XBRL, electronic VAT declaration, electronic ICP declaration, Netherlands
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ai-usage: ai-assisted
---

# Submit electronic VAT and ICP declarations in the Dutch version

Companies submit periodic VAT and Intracommunautaire prestaties (ICP) declarations to the Dutch tax authorities.

Use the reporting period that applies to your company and transactions. VAT returns are usually quarterly, but monthly or annual reporting can apply. Learn more in the tax authority's [VAT reporting period guidance](https://www.belastingdienst.nl/wps/wcm/connect/nl/btw/content/wijziging-aangiftetijdvak-btw). Don't assume that the ICP reporting period is always the same as the VAT reporting period.

> [!NOTE]  
> ICP declarations report qualifying supplies of goods and services to customers in other European Union (EU) countries/regions. Purchases aren't included. For goods, the merchandise must physically cross a border. An invoice address or office in another EU country/region isn't enough. The physical movement requirement doesn't apply to services.

You can submit the VAT declarations and ICP declarations in the following ways:  

- Sign in to the Dutch tax authority's portal and enter the information manually. Learn more in [Sign in for businesses](https://www.belastingdienst.nl/wps/wcm/connect/nl/ondernemers/content/inloggen-voor-ondernemers).
- Create an electronic declaration and submit the encrypted file through the Digipoort channel to the Dutch tax office. Digipoort is the electronic post office provided by the Dutch government for companies. It provides the common infrastructure for the communication of information between companies and the government, including VAT declarations. The reports are in the eXtensible Business Reporting Language (XBRL) format. Learn more in [Create Reports with XBRL](../../bi-create-reports-with-xbrl.md).

## Prepare for electronic declaration

Before you can send electronic declarations to the tax authorities, you must perform the following tasks:

1. Get the certificates required for Digipoort:

    - Obtain a **PKIoverheid** client certificate for the company if you don't have one already. You can find a list of certificate providers on this [website](https://www.logius.nl/producten/toegang/pkioverheid/aansluiten/toegetreden-csps).  
    - You can register a user of Digipoort on this [website](https://aansluiten.procesinfrastructuur.nl/site/registratienieuw).
    - Download the **Digipoort WUS service signing certificate** from the [Aansluit Suite Digipoort](https://aansluiten.procesinfrastructuur.nl/site/documentatie/digipoort-migratie-instructie-voor-het-wus-koppelvlak) site. The download link is also listed in [Setting up electronic VAT and ICP declarations](how-to-set-up-electronic-vat-and-icp-declarations.md#digipoort-service-signing-certificate).

    > [!NOTE]
    > If you already submit declarations through the legacy Digipoort environment, you must migrate to the new Digipoort. Update the endpoint URLs and the service signing certificate on the **Elec. Tax Declaration Setup** page. Learn more in [Migrating to the new Digipoort](how-to-set-up-electronic-vat-and-icp-declarations.md#migrating-to-the-new-digipoort).

1. Enter general data and personal data received from the tax authorities on the **Elec. Tax Declaration Setup** page. Learn more in [Setting Up Electronic VAT and ICP Declarations](how-to-set-up-electronic-vat-and-icp-declarations.md).

1. For the **Electronic Tax Declarations** workflow, set up VAT category codes for the XML elements in the VAT declaration. Learn more in [Set up VAT categories](how-to-set-up-vat-categories.md). For VAT returns with version **DigitalTaxDecl**, use box number mappings instead.

## Create an electronic declaration

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Electronic Tax Declarations**, and then choose the related link.
1. On the **Electronic Tax Declarations** page, choose the **New** action.
1. On the **Elec. Tax Declaration Card** page, select **VAT Declaration** or **ICP Declaration** in the **Declaration Type** field. Fill in **Declaration Period**, **Declaration Year**, and **Our Reference**.
1. Choose the **Create Electronic Tax Declaration** action.
1. For a VAT declaration, select the **VAT Template Name** and **VAT Statement Name**. For an ICP declaration, set any required VAT entry filters.
1. Choose the **OK** button.

The XML elements and the accompanying data of the electronic declaration are displayed on the **Lines** FastTab on the **Elec. Tax Declaration Card** page.

VAT declaration amounts come from the selected VAT statement and its electronic tax declaration category codes. ICP declaration amounts come from qualifying VAT entries for the declaration period.

## Submit an electronic declaration

You can submit the ICP declaration or VAT declaration in XBRL format. The file is sent to the tax authorities through the connection configured on the **Elec. Tax Declaration Setup** page.

1. On the **Elec. Tax Declaration Card** page, choose the **Submit Electronic Tax Declaration** action.
1. If a certificate request page opens, fill in the fields as described in the following table, and then choose **OK**.

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Client Certificate**|Select the **PKIoverheid** certificate for the company.|  
    |**Client Certificate Password**|Enter the password for the client certificate file.|
    |**Service Certificate**|Select the **Digipoort Service** certificate.|

The electronic declaration is submitted to the tax authorities.

When **Use Certificate Setup** is selected on the **Elec. Tax Declaration Setup** page, the submission uses the configured certificates without opening a certificate request page. On-premises deployments that don't use certificate setup use the configured certificate names.

> [!NOTE]  
> If there are no qualifying VAT entries for the period, the generated ICP declaration has no supply or service amounts. Check whether an ICP declaration is required before submitting it.

## Import a response message from the tax authorities

For each electronic declaration, the tax authorities send a response message. These messages must be received from the server of the tax authorities
and be processed. The first step is to import the response message into [!INCLUDE[prod_short](../../includes/prod_short.md)].

1. Open the submitted declaration on the **Elec. Tax Declaration Card** page.
1. Choose the **Response Messages** action to open the messages for that declaration.
1. Choose the **Receive Response Messages** action.
1. If a certificate request page opens, specify the **Client Certificate**, **Client Certificate Password**, and **Service Certificate**, and then choose **OK**.

When **Use Certificate Setup** is selected, the configured certificates are used without a certificate request page.

## Process a response message from the tax authorities

After importing response messages, process them to update the declaration status. Depending on the response codes, the status becomes **Acknowledged**, **Warning**, or **Error**. An acknowledgement doesn't override an earlier warning or error.

1. Open the declaration and choose **Response Messages**.
1. On the **Elec. Tax Decl. Response Msgs.** page, choose **Process Response Messages**. The action processes received messages for the declaration without opening a request page.
1. Review the **Processing Status**, response message, and declaration status.
1. To save the selected response message, choose the **Export Response Message** action.

The processing action uses the **Declaration Type** and **Declaration No.** filters. Other page filters don't limit which received messages are processed.

## Submit a VAT return with DigitalTaxDecl

The Dutch Digital Tax Declaration app also supports VAT submission from the **VAT Returns** page. This workflow is separate from the **Electronic Tax Declarations** workflow above and doesn't submit ICP declarations.

Before you use this workflow:

- Configure Digipoort and select **Use Certificate Setup** on the **Elec. Tax Declaration Setup** page.
- On the **Company Information** page, enter **VAT Registration No.** If **Part of Fiscal Entity** is selected on **Elec. Tax Declaration Setup**, also enter **Fiscal Entity No.** on **Company Information**.
- On the **General Ledger Setup** page, set **Local Currency** to **Euro**.
- Fill in the taxpayer contact name and phone number. If **VAT Contact Type** is **Agent**, fill in the agent's contact ID, name, address, post code, city, and phone number instead.
- Map the VAT statement lines by **Box No.** This workflow uses box numbers, not the electronic tax declaration category codes used by the workflow above. Learn more in [Map box numbers for VAT returns](how-to-set-up-vat-categories.md#map-box-numbers-for-vat-returns).

To submit a VAT return:

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **VAT Returns**, and then choose the related link.
1. Create a return and select **DigitalTaxDecl** in the **Version** field.
1. Enter the reporting period. In **Additional Information**, enter a reference that starts with `OB-` and contains only uppercase letters, digits, and hyphens.
1. Choose **Suggest Lines**, select the VAT statement and reporting options, and review the resulting amounts.
1. Choose **Release** and resolve any validation errors.
1. Choose **Submit** to send the return through Digipoort.
1. Choose **Receive Response** to open the response messages for the return. Choose **Receive Response Messages**, and then **Process Response Messages**.

For this workflow, processed response codes update the VAT return status to **Accepted** or **Rejected**. An acceptance response doesn't override an earlier rejection.

## Related information

- [Setting Up Electronic VAT and ICP Declarations](how-to-set-up-electronic-vat-and-icp-declarations.md)  
- [Set Up VAT Categories](how-to-set-up-vat-categories.md)  
- [Create Reports with XBRL](../../bi-create-reports-with-xbrl.md)  
- [Netherlands Local Functionality](netherlands-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
