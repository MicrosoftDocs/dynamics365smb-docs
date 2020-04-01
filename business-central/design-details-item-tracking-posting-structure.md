---
    title: Design Details - Item Tracking Posting Structure | Microsoft Docs
    description: Learn how to use item ledger entries as the primary carrier of item tracking numbers.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords: design, item tracking, posting, inventory
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Design Details: Item Tracking Posting Structure
To align with inventory costing functionality and to obtain a simpler and more robust solution, item ledger entries are used as the primary carrier of item tracking numbers.  
  
Item tracking numbers on order network entities and non-order network entities are specified in the **Reservation Entry** table (T337). Item tracking numbers that are related to historical information are retrieved directly from the item ledger entries that are related to the transaction in question. This means that item ledger entries reflect the item tracking specification of the posted order line.  
  
The **Item Tracking Lines** page retrieves the information from T337 and the item ledger entries and shows it through the temporary table, **Tracking Specification** (T336). T336 also hold the temporary data in the **Item Tracking Lines page** for item tracking quantities that remain to be invoiced.  
  
## One-to-Many Relation  
The **Item Entry Relation** table, which is used to link a posted document line with its related item ledger entries, consists of two main parts:  
  
* A pointer to the posted document line, the **Order Line No.** field.  
* An entry number pointing to an item ledger entry, the **Item Entry No.** field.  
  
The functionality of the existing **Entry No.** field, which relates an item ledger entry to a posted document line, handles the typical one-to-one relation when no item tracking numbers exist on the posted document line. If item tracking numbers exist, then the **Entry No.** field is left blank, and the one-to-many relation is handled by the **Item Entry Relation** table. If the posted document line carries item tracking numbers but only relates to a single item ledger entry, then the **Entry No.** field handles the relation, and the no record is created in the **Item Entry Relation** table.  
  
## Codeunits 80 and 90  
To split the item ledger entries during posting, the code in codeunit 80 and codeunit 90, is encircled by loops that run through global temporary record variables. This code calls codeunit 22 with an item journal line. These variables are initialized when item tracking numbers exist for the document line. To keep the code simple, this looping structure is always used. If no item tracking numbers exist for the document line, then a single record is inserted, and the loop runs only once.  
  
## Posting the Item Journal  
Item tracking numbers are transferred via the reservation entries that relate to the item ledger entry, and the looping through item tracking numbers occurs in codeunit 22. This concept works in the same way when an item journal line is used indirectly to post a sale or purchase order as when an item journal line is used directly. When the item journal is used directly, the **Source Row ID** field points to the item journal line itself.  
  
## Code Unit 22  
Codeunits 80 and 90 loop the call of codeunit 22 during the invoice posting of item tracking numbers and during the invoicing of existing shipments or receipts.  
  
During quantity posting of item tracking numbers, codeunit 22 retrieves item tracking numbers from the entries in T337 that relate to the posting. These entries are placed directly on the item journal line.  
  
Codeunit 22 loops through the item tracking numbers and splits the posting into the respective item ledger entries that carry the item tracking numbers. Information about which item ledger entries are created is returned to T337 by using a temporary T336 record, which is called by a procedure in codeunit 22. This procedure is triggered when codeunit 22 has finished its run because at that point, the codeunit 22 object contains the information. When the temporary T336 record is retrieved, codeunits 80 and 90 create records in the **Item Entry Relation** table to link the created item ledger entries to the created shipment or receipt line. Codeunits 80 or codeunit 90 then converts the temporary T336 records to real T336 records that are related to the line in question. However, this conversion occurs only if the posted document line is not deleted, because it is only partially posted.  
  
## See Also  
[Design Details: Item Tracking](design-details-item-tracking.md)   
[Design Details: Item Tracking Design](design-details-item-tracking-design.md)