---
    title: Design Details - Item Tracking and Reservations | Microsoft Docs
    description: This topic talks about item tracking and reservations, and describes the concepts behind the two.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Design Details: Item Tracking and Reservations
Simultaneous use of reservation and specific item tracking is uncommon, because they both create a coupling between supply and demand. Except for situations where a customer or production planner requests a specific lot, it rarely makes sense to reserve inventory items that already carry item tracking numbers for specific application. Although it is possible to reserve items that require specific item tracking, special functionality is needed to avoid availability conflicts between order processors that request the same item-tracked items.  
  
The concept of Late Binding ensures that a nonspecific reservation of a serial number or a lot number remains loosely coupled until posting. At posting time, the reservation system can reshuffle nonspecific reservations to ensure that fixed application is possible against the serial or lot number that is actually picked. Meanwhile, the serial or lot number is made available for specific reservation in other documents that request that particular serial or lot number.  
  
A nonspecific reservation is one in which the user does not care which specific item is picked, and a specific reservation is one in which the user does care.  
  
> [!NOTE]  
>  The Late Binding functionality relates only to items that are set up with specific item tracking, and it applies only to reservations against inventory, not against inbound supply orders.  
  
Reservation of item tracking numbers falls into two categories, as shown in the following table.  
  
|Reservation|Description|  
|-----------------|---------------------------------------|  
|Specific|You select a specific serial or lot number when you reserve the inventory item from a demand, such as a sales order.<br /><br /> This is a regular reservation. It is a rigid link between supply and demand that both carry serial or lot numbers. **Note:**  The demand carries serial or lot numbers. <br /><br /> For example, you want to reserve a can of blue paint from Lot A, because the customer requests it. A can of blue paint from Lot A is shipped to the customer.|  
|Nonspecific|You do not select a specific serial or lot number when you reserve the inventory item from a demand, such as a sales order.<br /><br /> This is a state that is imposed on a reservation entry for serial or lot numbers that are not selected specifically. **Note:**  The demand does not carry serial or lot numbers. <br /><br /> For example, you want to reserve a can of blue paint from any lot for your sales order. A can of blue paint from a random serial or lot number is shipped to the customer.|  
  
The main difference between specific and nonspecific reservation is defined by the existence of serial or lot numbers on the demand side, as shown in the following table.  
  
||||  
|-|-|-|  
||**Supply**|**Demand**|  
|**Specific**|Serial or lot number.|Serial or lot number.|  
|**Nonspecific**|Serial or lot number.|No serial or lot number.|  
  
When you reserve inventory quantities from an outbound document line for an item that has item tracking numbers assigned and is set up for specific item tracking, the **Reservation** page leads you through different workflows depending on your need for the serial or lot numbers.  
  
## Specific Reservation  
When you choose **Reserve** from the outbound document line, a dialog box appears that asks you if you want to reserve specific serial or lot numbers. If you choose **Yes**, then a list is displayed with all the serial or lot numbers that are assigned to the document line. The **Reservation** page opens after you select one of the serial or lot numbers, and you can then reserve among the selected serial or lot numbers in a typical fashion.  
  
If some of the specific item tracking numbers that you are trying to reserve are held in nonspecific reservations, then a message at the bottom of the **Reservation** page informs you how many of the total reserved quantity are held in nonspecific reservations and whether they are still available.  
  
## Nonspecific Reservation  
If you choose **No** in the dialog box that appears, the **Reservation** page opens and allows you to reserve among all serial or lot numbers in inventory.  
  
Because of the structure of the reservation system, when you place a nonspecific reservation on an item-tracked item, the system must select specific item ledger entries to reserve against. Because the item ledger entries carry the item tracking numbers, the reservation indirectly reserves specific serial or lot numbers, even though you did not intend to. To handle this situation, the reservation system tries to reshuffle nonspecific reservation entries before posting.  
  
The system actually still reserves against specific entries, but then it uses a reshuffling mechanism whenever there is specific demand for the lot or serial number in the nonspecific reservation. This can be the case when you post a demand transaction, such as a sales order, consumption journal, or transfer order, for the serial or lot number, or when you try to specifically reserve the serial or lot number. The system reshuffles the reservations to make the lot or serial number available to the demand or to the specific reservation, thereby placing a different lot or serial number in the nonspecific reservation. If there is insufficient quantity in inventory, the system reshuffles as much as possible, and you receive an availability error if there is still insufficient quantity at the time of posting.  
  
> [!NOTE]  
>  On a nonspecific reservation the lot number or serial number field is blank in the reservation entry that points at the demand, such as the sale.  
  
## Reshuffle  
When a user posts an outbound document after picking the wrong serial or lot number, other nonspecific reservations are reshuffled to reflect the actual serial or lot number that is picked. This satisfies the posting engine with a fixed application between supply and demand.  
  
For all supported business scenarios, reshuffling  is possible only against positive item ledger entries that carry reservation and serial or lot numbers but without defined serial or lot numbers on the demand side.  
  
## Supported Business Scenarios  
The Late Binding functionality supports the following business scenarios:  
  
* Entering a specific serial or lot number on an outbound document with nonspecific reservation of a wrong serial or lot number.  
* Reserving a specific serial or lot number.  
* Posting an outbound document with nonspecific reservation of a serial or lot number.  
  
### Entering Serial or Lot Numbers on an Outbound Document with Wrong Nonspecific Reservation  
This is the most common of the three supported scenarios. In this case, the Late Binding functionality ensures that a user can enter a serial or lot number, which is actually picked, on an outbound document that already has a nonspecific reservation of another serial or lot number.  
  
For example, the need arises when an order processor has first made a nonspecific reservation of any serial or lot number. Later when the item is actually picked from inventory, the picked serial or lot number must be entered on the order before it is posted. The nonspecific reservation is reshuffled at posting time to ensure that the picked serial or lot number can be entered without losing the reservation and to ensure that the picked serial or lot number can be fully applied and posted.  
  
### Reserve Specific Serial or Lot Numbers  
In this business scenario, Late Binding functionality ensures that a user who is trying to reserve a particular serial or lot number that is currently nonspecifically reserved can do so. A nonspecific reservation is reshuffled at the time of reservation to free the serial or lot number for the specific request.  
  
The reshuffle happens automatically, but embedded Help is displayed at the bottom of the **Reservation** page and shows the following text:  
  
**XX of the Total Reserved Quantity are nonspecific and may be available.**  
  
In addition, the **Nonspecific Reserved Qty.** field shows how many reservation entries are nonspecific. By default, this field is not visible to users.  
  
### Posting an Outbound Document with Nonspecific Reservation of Serial or Lot Numbers  
This business scenario is supported with Late Binding functionality that enables fixed application and outbound posting of what is actually picked by reshuffling another nonspecific reservation of a serial or lot number. If reshuffling is not possible, then the following standard error message appears when the user tries to post the shipment:  
  
**Item XX cannot be fully applied.**  
  
## See Also  
[Design Details: Item Tracking](design-details-item-tracking.md)