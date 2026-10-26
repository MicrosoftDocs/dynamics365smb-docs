---
title: Carta de Porte Packing Slips and Transfer Orders in Mexico
description: Business Central supports CFDI, allowing the printing of packing slips and transfer orders with the necessary digital signature to meet Carta de Porte requirements.
author: brentholtorf
ms.topic: concept-article
ms.devlang: al
ms.search.keywords: CFDI, packing slips, transfer orders, Carta de Porte
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Carta de Porte packing slips and transfer orders in the Mexican version

Mexican companies must be able to print and send Carta de Porte-compliant packing slips and transfer orders electronically as Comprobante Fiscal Digital por Internet (CFDI) files. As of December 1, 2021, the Waybill (Carta de Porte) complement is mandatory for taxpayers who transport goods and merchandise in the national territory. [!INCLUDE[prod_short](../../includes/prod_short.md)] supports CFDI and Carta de Porte so that you can print packing slips and transfer orders that have the required digital signature. The driver can then show the printed document if they're requested to do so.  

> [!NOTE]
> [!INCLUDE[prod_short](../../includes/prod_short.md)] generates Carta de Porte 3.1 complements.

> [!IMPORTANT]
> The documents must include a digital signature, which requires a connection to a PAC, which is an authorized service provider appointed by the Mexican tax authorities (SAT). Learn more in [Set up PAC web services](how-to-set-up-pac-web-services.md).
>
> Keep the SAT catalogs used for Carta de Porte up to date. You can import configuration packages or maintain the relevant codes manually. Learn more in [Import business data from other finance systems](../../across-import-data-configuration-packages.md). Confirm the catalog values with SAT or your partner.

## Get started

Before you can generate Carta de Porte documents, upload the required SAT certificate to [!INCLUDE[prod_short](../../includes/prod_short.md)] and configure electronic invoicing. Learn more in [Set up electronic invoicing](how-to-set-up-electronic-invoicing.md). The [Servicio de Administración Tributaria](https://go.microsoft.com/fwlink/?LinkId=242772) website provides information on SAT certificates and keys.

You also must specify the web services that you use to communicate with the PAC in order to obtain digital stamps. Learn more in [Set up PAC web services](how-to-set-up-pac-web-services.md).

> [!IMPORTANT]  
> SAT has certified more than one PAC in Mexico, and you must obtain the appropriate information to communicate with the PAC of your choice.  

Set up the SAT addresses for the locations involved in transport, the vehicle and its SCT permissions, and the item classifications. SCT permissions are maintained on the vehicle's **Fixed Asset Card**, not on **Company Information**.

### Set up locations for Carta de Porte

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Locations**, and then choose the related link.  
1. Open the location card. In the **Electronic Document** section of **Address & Contact**, select **SAT Address ID**.
1. Select the SAT address with the relevant country/region, state, municipality, locality, suburb, and postal code. Learn more in [Set up location information](how-to-set-up-electronic-invoicing.md#set-up-location-information).
1. Repeat steps 2-3 for each location used for Carta de Porte.

### Set up vehicles for transportation

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Fixed Assets**, and then choose the related link.  
1. Add or open the fixed asset card for the vehicle.
1. On the **Electronic Document** FastTab, fill in the following fields.

    |Field|Description|
    |-----|-----------|
    |**Vehicle Licence Plate**|Enter the vehicle's licence plate.|
    |**Vehicle Year**|Enter the vehicle's year.|
    |**Vehicle Gross Weight**|Enter the vehicle's gross weight in tons.|
    |**SAT Federal Autotransport**|Select the vehicle configuration from the SAT catalog.|
    |**SCT Permission Type**|Select the SCT permission type for the vehicle.|
    |**SCT Permission No.**|Enter the corresponding SCT permission number.|

1. If you use trailers, create or update their fixed asset cards with **Vehicle Licence Plate** and **SAT Trailer Type**.

### Configure items

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Items**, and then choose the related link.  
1. Open each relevant item card and fill in the following fields on the **Inventory** FastTab. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)]

    - **SAT Item Classification**  
    - **SAT Hazardous Material**  
    - **SAT Packaging Type**  
    - **SAT Material Type** for foreign trade
    - **Gross Weight**

## Create sales documents and generate packing slips and transfer orders with Carta de Porte

When you create a sales order or transfer order, fill in the fields on the **Electronic Document** FastTab. Include the vehicle, applicable trailers, transport operators, departure date and time, transit hours and distance, weight unit, and insurance information. For foreign trade, also specify the SAT customs regime, transfer reason, international trade term, and USD exchange rate. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)]

Set up transport operators as employees with **RFC No.** and **License No.**, and then assign them through **Transport Operators** on the document. For a sales shipment, specify the destination's **SAT Address ID**. For a transfer shipment, the origin and destination addresses come from the transfer-from and transfer-to locations.

For imported goods, fill in **Custom Transit Number** where required for the transaction. The field records the customs petition number in the following format:

- The last two digits of the validation year followed by two spaces  
- Two digits of the customs office followed by two spaces  
- Four digits of the number of the patent followed by two spaces  
- One digit corresponding to the last digit of the current year, except if a consolidated motion is initiated in the immediately preceding year or the original motion for a rectification  
- Six digits of the progressive numbering by customs  

For foreign-trade shipments, also select **SAT Customs Document Type** on the relevant lines.

Then, when you post the shipment, the required information is carried forward to the posted sales shipment. You can then send or print the document that now includes the Carta de Porte information.  

> [!TIP]
> The same applies when you create and post a transfer order. Learn more in [Transferring inventory between locations](../../inventory-how-transfer-between-locations.md).  

## Related information

- [Set Up Electronic Invoicing](how-to-set-up-electronic-invoicing.md)    
- [Set Up PAC Web Services](how-to-set-up-pac-web-services.md)    
- [Generate Electronic Invoices](how-to-generate-electronic-invoices.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
