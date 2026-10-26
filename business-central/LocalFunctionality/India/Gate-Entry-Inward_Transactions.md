---
title: Create and Attach Inward Gate Entries
description: Create, post, and attach inward gate entries to purchase receipts, transfer receipts, and sales returns in Business Central for India.
author: v-debapd
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English, inward gate entries, create inward gate entry, view posted gate entry, attach inward gate entry
ms.date: 10/21/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Create and attach inward gate entries

Gate Entry Inward is used to track the entry of goods into the organization.

The following processes describe how to create and attach an Inward Gate Entry.

- To create an Inward Gate Entry
- To attach an Inward Gate Entry

## Documents for inward gate entries

- Purchase orders or purchase invoices
- Transfer orders for receipt
- Sales return orders or sales credit memos

## Create an inward gate entry

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Inward Gate Entry List**, and then choose the related link.
1. Choose **New**.
1. Fill in the fields as described in the following table on the **Inward Gate Entry** header.

   |Field|Description|  
   |---------------------------------|---------------------------------------|  
   |**Location Code**|Select the location code.|
   |**Station from**|Enter the station name from where goods are coming to factory location.|
   |**Description**|Enter gate entry description.|
   |**Item Description**|Enter item's description.|
   |**Document Date**|Defaults to the work date. Changing this date also changes **Posting Date**.|
   |**Document Time**|Document time is populated automatically and it's system's time. User can also change the document time.|
   |**Posting Date**|Defaults to the work date. You can change the posting date.|
   |**Posting Time**|Posting time automatically flows and it's system's time. User can also change the posting time.|
   |**LR/RR No.**|Enter the transport details such as lorry receipt number or railway receipt number for the gate entry.|
   |**LR/RR Date**|Select the lorry receipt date or railway receipt date.|
   |**Vehicle No.**|Enter the vehicle number in which goods are coming.|

1. In the lines, fill in the fields as described in the following table.

   |Field|Description|  
   |---------------------------------|---------------------------------------|  
   |**Challan No.**|Enter the challan number received.|
   |**Challan Date**|Enter the challan date.|
   |**Source Type**|Specify the source type against which you're creating the gate entry. Available options are: Blank, Sales Return Order, Purchase Order, and Transfer Receipt.|
   |**Source No.**|Select the source number for the selected source type. There's no need to select the Source No. if the Source Type is blank|
   |**Source Name**|Shows the bill-to customer for a sales return order, the pay-to vendor for a purchase order, or the transfer-from name for a transfer receipt.|
   |**Description**|Specify description if Source Type is blank.|

1. Select on **Action** > **Posting** > **Post** and post the document.

> [!NOTE]
> You can create multiple lines on Inward Gate Entry with different source type.
> Source number lookups are filtered by the gate entry location. A nonblank **Source Type** requires **Source No.** A blank source type requires **Description**.

### View posted inward gate entry

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Posted Inward Gate Entry List**, and then choose the related link.
1. Open the relevant entry.

Posted inward gate entry lines remain **Open** until the attached receipt is posted. Posting the purchase receipt, sales return receipt, or transfer receipt closes the attached lines.

### Attach an inward gate entry if the source type is purchase order

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Purchase Orders**, and then choose the related link.
1. Select the relevant purchase order and select on **Action** > **Functions** > **Get Gate Entry Lines**.
1. To view the attached gate entry, select on **Action** > **Functions** > **Attached Gate Entry**.
1. Post the purchase order document.

> [!NOTE]
>
> - The same steps apply to a **Purchase Invoice**, using inward gate entry lines with a blank **Source Type**.
> - Posted gate entry lines can also be attached to **Warehouse Receipts**.

### Attach an inward gate entry if the source type is transfer receipt

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Transfer Orders**, and then choose the related link.
1. Select the required transfer order and select on **Action** > **Functions** -> **Get Gate Entry Lines** and select.
1. To view the attached gate entry, choose **Related** > **Warehouse** > **Attached Gate Entry**.
1. Post the transfer receipt.

### Attach an inward gate entry if the source type is sales return order

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Sales Return Orders**, and then choose the related link.
1. Select the required sales return order and select on **Action** > **Functions** > **Get Gate Entry Lines** and select.
1. To view the attached gate entry, select on **Related** > **Warehouse** > **Attached Gate Entry**.
1. Post the sales return order document.

> [!NOTE]
>
> - For a **Sales Credit Memo**, use inward gate entry lines with a blank **Source Type**.
> - Use a blank **Source Type** for direct **Purchase Invoice** or **Sales Credit Memo** receipts.

## Related information

[Gate Entry Outward Transaction](Gate-Entry-Outward_Transactions.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
