---
    title: Design Details - Item Tracking Lines Page | Microsoft Docs
    description: Read about how to managethe flow of serial and lot numbers in your inventory.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords: design, inventory, item, tracking, serial number, lot number
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Design Details: Item Tracking Lines Page
Item tracking records and reservation records are created in the reservation system, and their availability is calculated dynamically. Data that is entered on the **Item Tracking Lines** page is managed in a temporary version of the **Tracking Specification** table. When the page is closed, the active data is committed to the **Reservation Entry** table and the historic data is committed to the **Tracking Specification** table. For more information, see [Design Details: Active versus Historic Item Tracking Entries](design-details-active-versus-historic-item-tracking-entries.md).  
  
Lookups from the **Serial No.** and **Lot No.** fields show availability based on both the **Item Ledger Entry** table and the **Reservation Entry** table, with no date filter. The matrix of quantity fields on the header of the **Item Tracking Lines** page dynamically displays the quantities and sums of item tracking numbers that are being entered on the lines of the page. The quantities must correspond to those of the document line, which is indicated by **0** in the **Undefined** fields in the header of the page.  
  
To coordinate the flow of serial and lot numbers through inventory, the following rules exist for entering data on the **Item Tracking Lines** page:  
  
* For both inbound and outbound item tracking lines, you cannot enter a serial number, with or without a lot number, more than once in the same instance of the **Item Tracking Lines** page. If you try to enter any combination of serial or lot numbers that is already present on the page, then an error message blocks the data entry.  
* For inbound item tracking lines, you cannot post the related document if an item of the same variant and with the same serial number is already in inventory. If you try to post a positive line for an inventory item with the same variant and serial number, then an error message blocks the posting. However, for both inbound and outbound item tracking lines on open documents, you can have the same combination of serial or lot numbers that relate to different source document lines, that is, existing in different instances of the **Item Tracking Lines** page until the related document is posted.  
* If the item is set up for serial number-specific tracking or lot number- specific tracking, then you cannot post an outbound document line unless an item with the defined serial or lot number exists in inventory. If you try to post an outbound document line for an item with a serial lot number that is not in inventory, then an error message blocks the posting.  
  
The rules for entering data on the **Item Tracking Lines** page also support the coupling principles that govern order tracking, planning, and reservation. For more information, see [Design Details: Item Tracking and Planning](design-details-item-tracking-and-planning.md).  
  
## See Also  
[Design Details: Item Tracking](design-details-item-tracking.md)