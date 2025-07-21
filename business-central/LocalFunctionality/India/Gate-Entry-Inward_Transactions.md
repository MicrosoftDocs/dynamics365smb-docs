---
title: Gate Entry Inward Transactions
description: Gate Entry Inward Transactions.
author: v-debapd
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English, inward gate entries, create inward gate entry, view posted gate entry, attach inward gate entry
ms.date: 06/19/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Create and attach inward gate entries

Gate Entry Inward is used to track the entry of goods into the organization.

The following processes describe how to create and attach an Inward Gate Entry.

- To create an Inward Gate Entry
- To attach an Inward Gate Entry

## Inward gate entry can be created and attached to following documents

1. Purchase Order / Purchase Invoice
1. Transfer Order
1. Sales Return order / Sales Credit memo

## Create an inward gate entry

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Inward Gate Entry List**, and then choose the related link.
1. Fill in the fields as described in the following table on the **Inward Gate Entry** header.

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Location Code**|Select the location code.|
    |**Station from**|Enter the station name from where goods are coming to factory location.|
    |**Description**|Enter gate entry description.|
    |**Item Description**|Enter item's description.|
    |**Document Date**|Document Date is populated automatically and it's system's date. User can also change the document date.|
    |**Document Time**|Document time is populated automatically and it's system's time. User can also change the document time.|
    |**Posting Date**|Posting date is populated automatically and it's same as the document date. User can also change the posting date.|
    |**Posting Time**|Posting time automatically flows and it's system's time. User can also change the posting time.|
    |**LR/RR No.**|Enter the transport details such as lorry receipt number or railway receipt number for the gate entry.|
    |**LR/RR Date**|Select the lorry receipt date or railway receipt date.|
    |**Vehicle No.**|Enter the vehicle number in which goods are coming.|

1. On the **Inward gate entry** FastTab, fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Challan No.**|Enter the challan number received.|
    |**Challan Date**|Enter the challan date.|
    |**Source Type**|Specify the source type against which you're creating the gate entry. Available options are: Blank, Sales Return Order, Purchase Order, and Transfer Receipt.|
    |**Source No.**|Select the source number for the selected source type. There's no need to select the Source No. if the Source Type is blank|
    |**Source Name**| This field shows the source name depending on the **Source Type** you have selected. If the Source Type is selected as Sales Return Order, then it shows the customer name. If the Source Type is selected as Purchase Order, then it shows the vendor name. If the Source Type is Transfer Receipt then it shows the location name.|
    |**Description**|Specify description if Source Type is blank.|

1. Select on **Action** -> **Posting** -> **Post** and post the document.

> [!NOTE]
> You can create multiple lines on Inward Gate Entry with different source type.

### View posted inward gate entry

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Posted Inward Gate Entry**, and then choose the related link.
1. In the **Posted Inward Gate Entry**, the **Status** field on the line level has the value as **Open**, it means **Posted Gate Entry – Inward** is still open for attachment. 
1. **Status** field is updated once **Purchase Order** gets posted.  

### Attach an inward gate entry if the source type is purchase order

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Purchase Order**, and then choose the related link.
1. Select the relevant purchase order and select on **Action** -> **Functions** -> **Get Gate Entry Lines**.
1. To view the attached gate entry, select on **Action** -> **Functions** -> **Attached Gate Entry**.
1. Post the purchase order document.

> [!NOTE]
>
> - Same steps also apply for attaching **Inward Gate Enry** to a **Purchase Invoice**.
> - Posted gate entry lines can also be attached to **Warehouse Receipts**.

### To attach an inward gate entry if the source type is transfer receipt

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Transfer Order**, and then choose the related link.
1. Select the required transfer order and select on **Action** -> **Functions** -> **Get Gate Entry Lines** and select.
1. To view the attached gate entry, select on **Related** -> **Receipt** -> **Attached Gate Entry**.
1. Post the transfer order document.

### Attach an inward gate entry if the source type is sales return order

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Sales Return Order**, and then choose the related link.
1. Select the required sales return order and select on **Action** -> **Functions** -> **Get Gate Entry Lines** and select.
1. To view the attached gate entry, select on **Related** -> **Warehouse** -> **Attached Gate Entry**.
1. Post the sales return order document.

> [!NOTE]
>
> - Same steps also apply for attaching an **Inward Gate Enry** to a **Sales Credit Memo**.
> - Source Type  blank is applicable only if the goods are received against **Purchase Invoice** or **Sales Credit Memo**.

## Related information

[Gate Entry Outward Transaction](Gate-Entry-Outward_Transactions.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
