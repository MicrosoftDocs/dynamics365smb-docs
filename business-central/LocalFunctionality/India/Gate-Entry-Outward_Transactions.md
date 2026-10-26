---
title: Create and Attach Outward Gate Entries
description: Learn how to create and manage outward gate entries for tracking the exit of goods from your organization in Business Central (India localization).
author: v-debapd
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English, outward gate entries, create outward gate entry, view posted gate entry, attach outward gate entry
ms.date: 10/21/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Create and attach outward gate entries

Gate Entry Outward is used to track the exit of goods from the organization.

The following processes describe how to create and attach an Outward Gate Entry.

- To create an Outward Gate Entry
- To view an attached Outward Gate Entry

Outward gate entry lines reference the following posted documents:

- Sales shipments
- Transfer shipments
- Purchase return shipments

## Create an outward gate entry

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Outward Gate Entry List**, and then choose the related link.
1. Choose **New**.
1. Fill in the fields as described in the following table on the **Outward Gate Entry** header.

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Location Code**|Select the location code.|
    |**Station To**|Enter the station name, to which goods are dispatching from factory location.|
    |**Description**|Enter general description in this field.|
    |**Item Description**|Enter item's description, which you're dispatching.|
    |**Document Date**|Defaults to the work date. Changing this date also changes **Posting Date**.|
    |**Document Time**|Document time is automatically populated and it's system's time. User can also change the document time.|
    |**Posting Date**|Defaults to the work date. You can change the posting date.|
    |**Posting Time**|Posting time is automatically populated and it's system's time. User can also change the posting time.|
    |**LR/RR No.**|Enter the transport details such as lorry receipt number or railway receipt number for the gate entry.|
    |**LR/RR Date**|Select the lorry receipt date or railway receipt date.|
    |**Vehicle No.**|Enter the vehicle number in which goods are being dispatched.|

1. In the lines, fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Challan No.**|Enter the challan number received.|
    |**Challan Date**|Enter the challan date.|
    |**Source Type**|Select blank, **Sales Shipment**, **Purchase Return Shipment**, or **Transfer Shipment**.|
    |**Source No.**|Select the source number for the selected source type. There's no need to select the **Source No.** if the **Source Type** is blank.|
    |**Source Name**|Shows the bill-to customer for a sales shipment, the pay-to vendor for a purchase return shipment, or the transfer-to name for a transfer shipment.|
    |**Description**|Specify description if Source Type is blank.|

1. Select **Action** > **Posting** > **Post** and post the document.

> [!NOTE]
> You can also create multiple lines on Outward Gate Entry with different source types.
> Source number lookups are filtered by the gate entry location. A nonblank **Source Type** requires **Source No.** A blank source type requires **Description**.

### View posted outward gate entry

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Posted Outward Gate Entry List**, and then choose the related link.
1. Open the relevant entry to review its source document and transport details.

The **Attached Gate Entry** action on a posted shipment shows posted outward gate entry lines filtered by that shipment's source type and number. Unlike inward entries, this process references a shipment that is already posted.

### View attached outward gate entry if the source type is sales shipment

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Posted Sales Shipments**, and then choose the related link.
1. Select the required posted sales shipment and select **Related** > **Shipment** > **Attached Gate Entry** and select.

### View attached outward gate entry if the source type is transfer shipment

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Posted Transfer Shipments**, and then choose the related link.
1. Select the required posted transfer shipment and select **Related** > **Shipment** > **Attached Gate Entry**.
1. On this page, you can view the attached gate entry with the transfer shipment.

### View an outward gate entry if the source type is purchase return shipment

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Posted Return Shipments**, and then choose the related link.
1. Select the required posted return shipment and select **Related** > **Return Shpt.** > **Attached Gate Entry**.
1. On this page, you can view the attached gate entry with the purchase return shipment.

## Related information

[Gate Entry Overview](Gate-Entry-001-Basic-Setup.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
