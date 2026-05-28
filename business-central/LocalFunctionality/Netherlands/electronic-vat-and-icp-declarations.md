---
title: Submit electronic VAT & ICP declarations [NL]
description: With the eXtensible Business Reporting Language (XBRL) reporter, you can submit the ICP declaration or the VAT declaration in the required XML format.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: extensible business reporting, ICP declaration, Dutch version, Netherlands, XBRL, electronic VAT declaration, electronic ICP declaration, Netherlands
ms.date: 05/08/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Submitting electronic VAT and ICP declarations in the Dutch version

Companies must submit periodic VAT and Intracommunautaire leveringen (ICP) declarations to the tax authorities.  

- VAT declarations must be submitted on a monthly or quarterly basis.
- ICP declarations must be submitted on a quarterly basis.

> [!NOTE]  
> Companies that sell goods or services to European Union (EU) countries/regions ICP declarations must submit. Purchases aren't included in this declaration. For a transaction to qualify for ICP, the merchandise must physically cross a border. It isn't enough that the location of an invoice address or the office of the vendor or customer is in another EU country/region.  

You can submit the VAT declarations and ICP declarations in the following ways:  

- Sign in to the website of the Dutch tax office and enter the information manually. Learn more on the [website](https://www.belastingdienst.nl/wps/wcm/connect/en/individuals/individuals) of the Dutch tax office.  
- Create an electronic declaration and submit the encrypted file through the Digipoort channel to the Dutch tax office. Digipoort is the electronic post office provided by the Dutch government for companies. It provides the common infrastructure for the communication of information between companies and the government, including VAT declarations. The reports are in the eXtensible Business Reporting Language (XBRL) format. Learn more in [Create Reports with XBRL](../../bi-create-reports-with-xbrl.md).

## Prepare for electronic declaration

Before you can send electronic declarations to the tax authorities, you must perform the following tasks:

1. Ensure that you obtain the certificates from the government. If you haven't, take the following steps to obtain the certificates:

    - Obtain a **PKIoverheid** client certificate for the company if you don't have one already. You can find a list of certificate providers on this [website](https://www.logius.nl/producten/toegang/pkioverheid/aansluiten/toegetreden-csps).  
    - You can register a user of Digipoort on this [website](https://aansluiten.procesinfrastructuur.nl/site/registratienieuw).
    - Download the **Digipoort WUS service signing certificate** from the [Aansluit Suite Digipoort](https://aansluiten.procesinfrastructuur.nl/site/documentatie/digipoort-migratie-instructie-voor-het-wus-koppelvlak) site. The download link is also listed in [Setting up electronic VAT and ICP declarations](how-to-set-up-electronic-vat-and-icp-declarations.md#digipoort-service-signing-certificate).

    > [!NOTE]
    > If you already submit declarations through the legacy Digipoort environment, you must migrate to the new Digipoort. Update the endpoint URLs and the service signing certificate on the **Elec. Tax Declaration Setup** page. Learn more in [Migrating to the new Digipoort](how-to-set-up-electronic-vat-and-icp-declarations.md#migrating-to-the-new-digipoort).

1. Enter general data and personal data received from the tax authorities on the **Elec. Tax Declaration Setup** page. Learn more in [Setting Up Electronic VAT and ICP Declarations](how-to-set-up-electronic-vat-and-icp-declarations.md).

1. Set up a VAT category code for all XML elements in the electronic VAT declaration. Learn more in [Set Up VAT Categories](how-to-set-up-vat-categories.md).

## Create an electronic declaration

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Elec. Tax Declarations**, and then choose the related link.  
1. On the **Elec. Tax Declaration List** page, choose the **New** action.  
1. On the **Elec. Tax Declaration Card** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](../../includes/tooltip-inline-tip_md.md)]  
1. Choose the **OK** button.

The XML elements and the accompanying data of the electronic declaration are displayed on the **Lines** FastTab on the **Elec. Tax Declaration Card** page.

The XBRL reporter ensures that all account numbers that are imported from Business Central are mapped to the XBRL elements in a report. The XBRL reporter also displays a list of errors of unmapped elements or accounts.

## Submit an electronic declaration

With the XBRL reporter, you can submit the Intracommunautaire Leveringen (ICP) declaration or the VAT declaration in the required XML format. When submitted, the file is sent to the tax authorities as defined on the **Elec. Tax Declaration Setup** page.

1. On the **Elec. Tax Declaration Card** page, choose the **Submit Electronic Tax Declaration** action.
1. Fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Client Certificate**|Select the **PKIoverheid** certificate for the company.|  
    |**Client Certificate Password**|Enter the password that encrypts the client certificate.|
    |**Service Certificate**|Select the **Digipoort Service** certificate.|

1. Choose the **OK** button.  

The electronic declaration is submitted to the tax authorities.

> [!NOTE]  
> If there are no intra-community deliveries in the declaration period, then an electronic ICP declaration is created without XML elements for the deliveries. If you submit such a declaration, an error message is displayed.

## Import a response message from the tax authorities

For each electronic declaration, the tax authorities send a response message. These messages must be received from the server of the tax authorities
and be processed. The first step is to import the response message into [!INCLUDE[prod_short](../../includes/prod_short.md)].

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Elec. Tax Decl. Response Msgs.**, and then choose the related link.  
1. Choose the **Receive Response Messages** action.  
. On the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Client Certificate**|Select the **PKIoverheid** certificate for the company.|  
    |**Client Certificate Password**|Enter the password that encrypts the client certificate.|
    |**Service Certificate**|Select the **Digipoort Service** certificate.|  

1. Choose the **OK** button.

## Process a response message from the tax authorities

When a response message is imported, it must be processed by validating its content against the related electronic declaration. If no errors are found in the electronic declaration and the data is processed by the tax authorities, then the **Status** field on the **Elec. Tax Declaration Card** page is changed to **Acknowledgement**.

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Elec. Tax Decl. Response Msgs.**, and then choose the related link.  
1. Choose the **Process Response Messages** action.  
1. On the **Process Response Messages Batch Job** page, select the appropriate filters, and then choose the **OK** button.  

   The processed information about the response message is displayed on the **Elec. Tax Decl. Response Msgs.**. page.  

1. To export a message or attachment, choose the **Export Response Message** action or the **Export Response Attachment** action.

## Related information

- [Setting Up Electronic VAT and ICP Declarations](how-to-set-up-electronic-vat-and-icp-declarations.md)  
- [Set Up VAT Categories](how-to-set-up-vat-categories.md)  
- [Create Reports with XBRL](../../bi-create-reports-with-xbrl.md)  
- [Netherlands Local Functionality](netherlands-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
