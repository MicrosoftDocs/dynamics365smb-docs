---
title: Gate Entry Outward Transactions
description: Learn how to create and manage outward gate entries for tracking the exit of goods from your organization in Business Central (India localization).
author: v-debapd
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English, outward gate entries, create outward gate entry, view posted gate entry, attach outward gate entry
ms.date: 06/19/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Create and attach outward gate entries

Gate Entry Outward is used to track the exit of goods from the organization.

The following processes describe how to create and attach an Outward Gate Entry.

- To create an Outward Gate Entry
- To view an attached Outward Gate Entry

**Outward gate entry can be created and attached to the following documents.**

1. Sales Order / Sales Invoice
1. Transfer Shipment
1. Purchase Return Order/ Purchase Credit Memo

## Create an outward gate entry

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Outward Gate Entry List**, and then choose the related link.
1. Fill in the fields as described in the following table on the **Onward Gate Entry** header.

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Location Code**|Select the location code.|
    |**Station To**|Enter the station name, to which goods are dispatching from factory location.|
    |**Description**|Enter general description in this field.|
    |**Item Description**|Enter item's description, which you're dispatching.|
    |**Document Date**|Document date is automatically populated and it's system's date. User can also change the document date.|
    |**Document Time**|Document time is automatically populated and it's system's time. User can also change the document time.|
    |**Posting Date**|Posting date is automatically populated and it's same as the document date. User can also change the posting date.|
    |**Posting Time**|Posting time is automatically populated and it's system's time. User can also change the posting time.|
    |**LR/RR No.**|Enter the transport details such as lorry receipt number or railway receipt number for the gate entry.|
    |**LR/RR Date**|Select the lorry receipt date or railway receipt date.|
    |**Vehicle No.**|Enter the vehicle number in which goods are being dispatched.|

1. On the **Onward gate entry** FastTab, fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Challan No.**|Enter the challan number received.|
    |**Challan Date**|Enter the challan date.|
    |**Source Type**|Specify the source type against which you're creating the gate entry. Available options are: Blank, Sales Return Order, Purchase Order, and Transfer Receipt.|
    |**Source No.**|Select the source number for the selected source type. There's no need to select the **Source No.** if the **Source Type** is blank.|
    |**Source Name**| This field shows the source name depending on the **Source Type** you have selected. If the Source Type is selected as Sales Return Order, then it shows the customer name. If the Source Type is selected as Purchase Order, then it shows the vendor name. If the Source Type is Transfer Receipt then it shows the location name.|
    |**Description**|Specify description if Source Type is blank.|

1. Select **Action** > **Posting** > **Post** and post the document.

> [!NOTE]
> You can also create multiple lines on Outward Gate Entry with different source types.

### View posted outward gate entry

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Posted Outward Gate Entry**, and then choose the related link.
1. In the **Posted Outward Gate Entry**, the **Status** field on the line level has the value as **Open**, it means **Posted Gate Entry – Outward** is still open for attachment.
1. **Status** field is updated once source document gets posted.  

System automatically attaches the Outward Gate Entry with the source number you have entered.

### View attached outward gate entry if the source type is sales shipment

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Posted Sales Shipment**, and then choose the related link.
1. Select the required posted sales shipment and select **Related** > **Shipment** > **Attached Gate Entry** and select.

### View attached outward gate entry if the source type is transfer shipment

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Posted Transfer Shipment**, and then choose the related link.
1. Select the required posted transfer shipment and select **Related** > **Shipment** > **Attached Gate Entry**.
1. On this page, you can view the attached gate entry with the transfer shipment.

### View an outward gate entry if the source type is purchase return shipment

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Posted Return Shipment**, and then choose the related link.
1. Select the required posted return shipment and select **Related** > **Return Shpt.** > **Attached Gate Entry**.
1. On this page, you can view the attached gate entry with the purchase return shipment.

## Related information

[Gate Entry Overview](Gate-Entry-001-Basic-Setup.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
