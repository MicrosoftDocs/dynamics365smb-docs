---
title: Carta de Porte packing slips and transfer orders [MX]
description: Business Central supports CFDI, allowing the printing of packing slips and transfer orders with the necessary digital signature to meet Carta de Porte requirements.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: CFDI, packing slips, transfer orders, Carta de Porte
ms.date: 02/26/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Carta de Porte packing slips and transfer orders in the Mexican version

Mexican companies must be able to print and send Carta de Porte-compliant packing slips and transfer orders electronically as Comprobante Fiscal Digital por Internet (CFDI) files. As of December 1, 2021, the Waybill (Carta de Porte) complement is mandatory for taxpayers who transport goods and merchandise in the national territory. [!INCLUDE[prod_short](../../includes/prod_short.md)] supports CFDI and Carta de Porte so that you can print packing slips and transfer orders that have the required digital signature. The driver can then show the printed document if they're requested to do so.  

> [!NOTE]
> The **Carta de Porte** feature in the Mexican Business Central localization is currently at version **3.1** and becomes effective with version 24.4.
> [!IMPORTANT]
> The documents must include a digital signature, which requires a connection to a PAC, which is an authorized service provider appointed by the Mexican tax authorities (SAT). Learn more in [Set up PAC web services](how-to-set-up-pac-web-services.md).
>
> Also, as of January 2022, you must update the Carta de Porte catalogs that define the various codes. Microsoft provides a downloadable package at [this location](https://microsoft.com) that you can import using RapidStart Services. Learn more in [Import business data from other finance systems](../../across-import-data-configuration-packages.md). Alternatively, if you only use few codes, you can update the current catalogs manually.

## Get started

Before you can use [!INCLUDE[prod_short](../../includes/prod_short.md)] for Carta de Porte-compliant shipments and transfer orders, you must obtain the appropriate certification, digital stamp, and control numbers from the tax authorities. You must install the certificate on the computer where the CFDI files are generated. Learn more in [Set up electronic invoicing](how-to-set-up-electronic-invoicing.md). The [Servicio de Administracíon Tributaria](https://go.microsoft.com/fwlink/?LinkId=242772) website provides information on SAT certificates and keys.

You also must specify the web services that you use to communicate with the PAC in order to obtain digital stamps. Learn more in [Set up PAC web services](how-to-set-up-pac-web-services.md).

> [!IMPORTANT]  
> SAT has certified more than one PAC in Mexico, and you must obtain the appropriate information to communicate with the PAC of your choice.  

You must add information about STC permissions to your company information. You must also fill in more information about the vehicles that you use to transport items around, if this is something that your company does internally as opposed to using an external party. Finally, you must configure each item card to include the required information about item classification, hazardous material, and packaging type. [!INCLUDE [prod_short](../../includes/prod_short.md)] online is preconfigured to include the relevant catalogs that SAT provides so that you can fill in the various fields.  

### Add SCT permission to company information

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Company Information**, and then choose the related link.  
1. On the **Company Information** page, on the **Shipping** FastTab, in the **SCT Permission Type** field, choose the relevant type of motor transport used for the transfer of goods or merchandise by your company. The Secretaria de Comunicaciones y Transportes define the types.  
1. In the **SCT Permission No.** field, specify the relevant permission number that is issued by the Secretaria de Comunicaciones y Transportes.  

### Set up locations for Carta de Porte

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Locations**, and then choose the related link.  
1. On the **Locations** page, choose the location that you want to update, and then, on the **Location Card** page, fill in the fields on the **Electronic Document** FastTab. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)]

    For example, the **ID Ubicacion** field specifies a six-digit code that is unique for this particular location. Then, when you post a shipment that includes this location, that code is prefixed with *OR* if the location is the starting point for the transport. If the location is the destination point, the code is automatically prefixed with *DE*.
1. Repeat step 2 for any other locations that you want to configure for Carta de Porte.

### Set up vehicles for transportation

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Fixed Assets**, and then choose the related link.  
1. On the **Fixed Assets** page, add or edit the relevant vehicles.  

> [!TIP]
> The relevant fields are on the **Electronic Document** FastTab. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)]

### Configure items

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.  
1. On the **Items** list page, choose each relevant item, and then, on the **Inventory** FastTab, fill in the following fields. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)].  

    - **SAT Item Classification**  
    - **SAT Hazardous Material**  
    - **SAT Packaging Type**  

## Create sales documents and generate packing slips and transfer orders with Carta de Porte

When you create a document such as a sales order, you must fill in the fields on the **Electronic Document** FastTab, including information about your insurance company. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)]  

For each line on the document, you must also specify the **Custom Transit Number** field. This field specifies the number of the petition that protects the importation of the goods in the following format:  

- The last two digits of the validation year followed by two spaces  
- Two digits of the customs office followed by two spaces  
- Four digits of the number of the patent followed by two spaces  
- One digit corresponding to the last digit of the current year, except if a consolidated motion is initiated in the immediately preceding year or the original motion for a rectification  
- Six digits of the progressive numbering by customs  

Then, when you post the shipment, the required information is carried forward to the posted sales shipment. You can then send or print the document that now includes the Carta de Porte information.  

> [!TIP]
> The same applies when you create and post a transfer order. Learn more in [Transferring inventory between locations](../../inventory-how-transfer-between-locations.md).  

## Related information

- [Set Up Electronic Invoicing](how-to-set-up-electronic-invoicing.md)    
- [Set Up PAC Web Services](how-to-set-up-pac-web-services.md)    
- [Generate Electronic Invoices](how-to-generate-electronic-invoices.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
