---
title: "Design Details: Item Tracking Lines Window"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "item tracking, lines"
ms.assetid: dbe7da5d-5eb1-404d-b4fd-184df2cbfcf8
caps.latest.revision: 6
ms.author: "sgroespe"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-nz"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# Design Details: Item Tracking Lines Window
Item tracking records and reservation records are created in the reservation system, and their availability is calculated dynamically. Data that is entered in the **Item Tracking Lines** window is managed in a temporary version of the **Tracking Specification** table. When the window is closed, the active data is committed to the **Reservation Entry** table and the historic data is committed to the **Tracking Specification** table. For more information, see [Design Details: Active versus Historic Item Tracking Entries](../ApplicationDesign/design-details-active-versus-historic-item-tracking-entries.md).  
  
 Lookups from the **Serial No.** and **Lot No.** fields show availability based on both the **Item Ledger Entry** table and the **Reservation Entry** table, with no date filter. The matrix of quantity fields on the header of the **Item Tracking Lines** window dynamically displays the quantities and sums of item tracking numbers that are being entered on the lines of the window. The quantities must correspond to those of the document line, which is indicated by **0** in the **Undefined** fields in the header of the window.  
  
 To coordinate the flow of serial and lot numbers through inventory, the following rules exist for entering data in the **Item Tracking Lines** window:  
  
-   For both inbound and outbound item tracking lines, you cannot enter a serial number, with or without a lot number, more than once in the same instance of the **Item Tracking Lines** window. If you try to enter any combination of serial or lot numbers that is already present in the window, then an error message blocks the data entry.  
  
-   For inbound item tracking lines, you cannot post the related document if an item of the same variant and with the same serial number is already in inventory. If you try to post a positive line for an inventory item with the same variant and serial number, then an error message blocks the posting. However, for both inbound and outbound item tracking lines on open documents, you can have the same combination of serial or lot numbers that relate to different source document lines, that is, existing in different instances of the **Item Tracking Lines** window until the related document is posted.  
  
-   If the item is set up for serial number\-specific tracking or lot number\- specific tracking, then you cannot post an outbound document line unless an item with the defined serial or lot number exists in inventory. If you try to post an outbound document line for an item with a serial lot number that is not in inventory, then an error message blocks the posting.  
  
 The rules for entering data in the **Item Tracking Lines** window also support the coupling principles that govern order tracking, planning, and reservation. For more information, see [Design Details: Item Tracking and Planning](../ApplicationDesign/design-details-item-tracking-and-planning.md).  
  
## See Also  
 [Design Details: Item Tracking](../ApplicationDesign/design-details-item-tracking.md)