---
title: Reservation Entry table - Features that update the Reservation Entry table
description: Learn how to troubleshoot data inconsistency issues in the Reservation Entry table.
author: brentholtorf
ms.topic: concept-article
ms.search.keywords:
ms.date: 04/07/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ms.custom: bap-template
---

# Reservation Entry table: introduction

This article provides guidance to help you understand and troubleshoot data inconsistency issues in the **Reservation Entry** table (Table 337). The first part introduces the features that generate or modify the data. It also covers several fields in the Reservation Entry table. The article also describes how entries in the Reservation Entry table are generated, deleted, or modified when you process transfer orders or run planning features.

The Reservation Entry table handles and stores reservation, item tracking, and order tracking information.

When it handles item tracking with partial posting, the table works with the **Tracking Specification** table (Table 336). Data entered in the **Item Tracking Lines** page by the user is created in a temporary version of Table 336 and is committed to Table 337 and the Tracking Specification table when the page is closed.

In general terms, the data generated in the **Reservation Entry** table depends on which features you use and which parameters you set for the item. These settings include:

- Order Tracking policy
- Reservation policy
- Planning features executed
- Reordering and manufacturing policy
- Planning parameters on the item or stock-keeping unit card
- Item Tracking Code

## Features that update the Reservation Entry table

This section introduces the features that generate or modify data in the Reservation Entry table.

### Order Tracking policy

If the **Order Tracking Policy** field on an item is set to **None**, [!INCLUDE[prod_short](includes/prod_short.md)] doesn't create reservation entries in the Reservation Entry table unless you run **Net Change Plan**, **Regenerative Plan**, **Reservation**, or **Item Tracking**. Additionally, without order tracking enabled, you can have reservation entries when using the Manufacturing-to-Order or Assembly-to-Order policies.

You can consider setting the **Order Tracking Policy** to **None** if you don't require tracking of demand against a supply, or vice versa. Order tracking features or the planning engine track supply against demand. We don't recommend that you use order tracking together with planning functionality.

When you set the **Order Tracking Policy** field to **Tracking Only**, [!INCLUDE[prod_short](includes/prod_short.md)] always creates entries in table 337 whenever an order is created for the item, but the **Reservation Status** in table 337 isn't always strictly set to **Tracking**. Consider the following scenario:

> [!NOTE]  
> The work date is set as 01/23/2026 (MM/DD/YYYY) for all examples. 
  
1. Create an item with **Order Tracking Policy** field set to **Tracking Only**.  
1. Create a purchase order. [!INCLUDE[prod_short](includes/prod_short.md)] creates a reservation entry with the **Reservation Status** of **Surplus** because the purchase order isn't yet allocated to a demand.
1. Create a sales order. [!INCLUDE[prod_short](includes/prod_short.md)] creates another reservation entry with a **Reservation Status** of **Tracking**.

[!INCLUDE [prod_short](includes/prod_short.md)] updates the reservation status created in step 2 to **Tracking**. This concept is called **dynamic tracking*.

By setting the **Order Tracking Policy** field on the item to **Tracking Only**, you can use the order tracking feature to get an overview of which supply the demand is allocated to, and vice versa.

> [!NOTE]  
> Tracking features don't replace planning functionality. Planning considers all items, demands, and supplies together to provide planning proposals that optimize customer service levels and balance inventory levels.

### Reservation policy

A reservation consists of a pair of records in the Reservation Entry table with a **Reservation Status** of **Reservation**, which shares the same entry number. One record has the **Positive** field enabled and points to the supply. The **Positive** field isn't enabled for the other record, and points to the demand. The fields **Source Type**, **Source Ref. No.**, and **Source ID** highlight the reservation link between the demand and supply.

The information in the **Source Type** field is the table the reservation **Entry No.** field is related to. For example, if it's a demand (negative) entry, then it could be the **Sales Order** table (Table 37) or the **Planning Component** (Table 99000829).

The **Source ID** field contains the ID of the document in the table referenced by the **Source Type**.

The **Source Ref. No.** field contains a reference number for the line, to which the reservation **Entry No.** is related. If the entry is related to a sale or purchase line, a journal line, or a requisition line, information in this field is copied from the **Line No.** field. If the entry is related to an entry in the *Item Ledger Entry* table (Table 32), information in this field is copied from the **Entry No.** field of the *Item Ledger Entry* table.

When you use the reservation policy option **Always** in combination with order tracking, both are normally in sync. However, when the reservation is removed or the receipt date of supply is moved forward past the demand due date, the order tracking is removed. You can also encounter an error message, in which [!INCLUDE[prod_short](includes/prod_short.md)] asks what to do with existing reservations. The following example illustrates this scenario.

1. Create a new item called **COMP**. Set the following fields:
  - **Replenishment System**: Purchase
  - **Order Tracking Policy**: Tracking Only
  - **Reserve**: Always
2. Create a second item called **FG**. Set the following fields:
  - **Replenishment System**: Prod. Order
  - **Order Tracking Policy**: Tracking Only
  - **Reserve**: Always
3. Create a second item called **FG**. Set the following fields:
  - **Item**: COMP
  - **Quantity Per**: 1
4. Certify the Production BOM No. BOM FG and assign against Item FG.
5. Create a purchase order. Set the following fields:
  - **Item**: COMP
  - **Quantity**: 10
  - **Location Code**: BLUE
  - **Expected Receipt Date**: 01/24/2026
6. Create a sales order. Set the following fields:
  - **Shipment Date**: 02/14/2026
  - **Location Code**: BLUE
  - **Item**: COMP
  - **Quantity**: 10

> [!NOTE]  
> Automatic reservation ran between the purchase and sales order. Additionally, order tracking was created between the purchase and sales orders.

7. Create a manual released production order. Set the following fields:
  - **Item**: 02/14/2026
  - **Quantity**: 10
  - **Location**: BLUE
  - **Due Date**: 02/01/2026
8. On the **Home** tab, in the Process group, choose **Refresh Production Order**.
9. Open the components list and look up Item COMP.

> [!NOTE]  
> No reservation or order tracking is created because a reservation already exists against the sales order created in Step 6.

Suppose that the item is needed more urgently on the released production order created in Step 7. So next, in the following steps we cancel the reservation from the sales order that was created in Step 6. Notice how order tracking is handled.

10. Look up the sales order for Item COMP from Step 6 and cancel the reservation.
11. Open the purchase order from Step 5 and notice that order tracking is now created between the purchase order and the component needed from the released production order.
12. Recreate the reservation between the component needed from the released production order and the supply from the purchase order in Step 5.

> [!NOTE]  
> The reservation isn't re-created. You must do that manually.

13. Change the **Expected Receipt Date** field on the purchase order header at Step 5 from 01/24/2026 to 02/05/2026.

[!INCLUDE[prod_short](includes/prod_short.md)] displays the following warning message:

   Reservations exist for this order. These reservations are canceled if a data conflict is caused by this change. Do you want to continue?

14. Choose **Yes**. Look up the reservation and order tracking entries from the purchase order.

> [!NOTE]  
> The existing reservation is canceled and you must recreate it manually. The order, however, is dynamic and was recreated to exist between the purchase order and the sales order. The reason is the demand for the released production order (02/01/2026) is before the expected receipt date of the supply.

### Planning calculated

Using the requisition worksheet or the planning worksheet generates entries in the Reservation Entry table with the **Reservation Status** field set to **Tracking**, **Reservation**, or **Surplus**. There should always be a matching pair with the same entry number of positive and negative value in the **Quantity (Base)** field when the status is **Tracking** or **Reservation**. The **Source Type** field is the demand type, that is, table 37 for the negative quantity and a planning table, for example, table 246, for the positive quantity. The **Source ID** field is **PLANNING**.

For nonallocated supply or demand, [!INCLUDE[prod_short](includes/prod_short.md)] sets the **Reservation Status** field to **Surplus**. For example, you can have a reservation status of **Surplus** when the existing inventory is below the safety stock quantity or demand is linked to the forecast.

The **Untracked Planning Element** table (Table 99000855) holds information about untracked quantities displayed when you do a lookup from the order tracking page to see untracked quantities or choose a Warning Icon in the planning worksheet. The table contains entries that account for an untracked surplus quantity in the order tracking network.

These entries are generated during the planning run and explain where the untracked surplus quantity in the order tracking lines came from. This untracked surplus can come from:

- Production forecast
- Blanket orders
- Safety stock quantity
- Reorder point
- Maximum inventory
- Reorder quantity
- Maximum order quantity
- Minimum order quantity
- Order multiple
- Dampener (% of lot size)

In the *Reservation Entry* table, as on the purchase, transfer and production orders, there's a **Planning Flexibility** field. This field defines whether the planning engine considers the supply represented by these supply orders when it calculates action messages. If the field contains **Unlimited**, the planning engine includes the line when it calculates action messages. If the field contains the **None**, the line is firm and unchangeable, and the planning engine doesn't include the line when it calculates action messages. The feature is managed in the Reservation Entry table by the field with the same name.

### Reordering and manufacturing policy

If you run planning for an item with the reordering policy set to **Order**, [!INCLUDE[prod_short](includes/prod_short.md)] creates entries in the *Reservation Entry* table with the reservation status of **Reservation** instead of **Tracking**.

The **Source Type** and **Source ID** fields has the equivalent treatment of other reordering policies. However, in the **Binding** field in the Reservation Entry table, [!INCLUDE[prod_short](includes/prod_short.md)] enters **Order-to-Order**.

The **Binding** field is filled in to control supply orders that are bound to specific demand. For example, production orders that are created directly from a sales order. The field displays Order-to-Order when the entry is tied specifically to a demand or a supply (Automatic Reservation). The demand can be related to sales or component needs.

### Item tracking and prospect reservation entry

The **Prospect** reservation status can be created in the Reservation Entry table when you aren't using order tracking. For example, on a consumption journal line you assign item tracking to the component. However, if the item is already order tracked, [!INCLUDE[prod_short](includes/prod_short.md)] might create more prospect reservation entries. This process is demonstrated in EXAMPLE 2 related to transfer orders in this article.

When you view or modify the **Item tracking lines** page, the collective contents of the Tracking Specification table (Table 336) and Reservation Entry table are presented in a temporary version of Table 336. This data ensures that historic and active item tracking data is accessed as one.

Reservations fall into two categories: 

- Nonspecific reservations, where lot and serial numbers aren't specified at the time of reservation
- Specific reservations, where you reserve specific lot or serial numbers from inventory.

On a nonspecific reservation, the **Lot No.** or **Serial No.** field is blank in the **Entry No.** of Table 337 pointing at the demand (for instance, the sale). Because of the structure of the reservation logic in [!INCLUDE[prod_short](includes/prod_short.md)], when you place a nonspecific reservation on an item-tracked item in inventory, [!INCLUDE[prod_short](includes/prod_short.md)] must select specific item ledger entries to reserve against.

Because item ledger entries carry the item tracking information, the reservation indirectly reserves specific lot or serial numbers. However, with **Late Binding**, [!INCLUDE[prod_short](includes/prod_short.md)] reserves against specific entries, but then uses a reshuffling mechanism when posting.

### Source Subtype, Suppressed Action Msg., Action Message Adjustment, and Disallow Cancellation fields

This section describes the **Source Subtype**, **Suppressed Action Msg.**, **Action Message Adjustment**, and **Disallow Cancellation** fields in the **Reservation Entry** table. Scenarios are provided to demonstrate the use of the **Suppressed Action Msg.**, **Action Message Adjustment** and **Disallow Cancellation** fields. The **Action Message Adjustment** field is used for the order tracking policy feature Tracking and Action Message. The **Disallow Cancellation** field is used for the Assembly-to-Order feature.

#### Source Subtype

The **Source Subtype** field indicates which source subtype the reservation entry is related to. If the entry is related to a purchase or sales line, the field is copied from the **Document Type** field on the line. If the entry is related to a journal line, the field is copied from the **Entry Type** field on the journal line.

#### Suppressed Action Msg.

The **Suppressed Action Msg.** field records when an existing supply was already partially processed. For example, when a purchase order was already partially received or a production order has consumptions posted against it.

When you run planning, [!INCLUDE[prod_short](includes/prod_short.md)] marks this field and sets the **Reservation Entry Status** field to **Surplus**. The following example serves as an illustration.

1. Open Item 80001. Set the following fields:
  - **Reordering Policy**: Lot-for-Lot
  - **Reserve**: Optional
  - **Order Tracking Policy**: None
2. Create a sales order. Set the following fields:
  - **Item**: 80001
  - **Location**: Blank/None
  - **Quantity**: 10
  - **Shipment Date**: 2/15/2026
3. Open the **Requisition Worksheets** and run the **Calculate Plan** batch job for Item 80001.
  - **Starting Date**: 01/23/2026
  - **Ending Date**: 03/01/2026
4. A planning suggestion is given to replenish the quantity of 10 with a new purchase order and **Due Date** 02/15/2026.
5. On the **Actions** tab, in the Functions group, choose **Carry Out Action** Message to create a purchase order with **Expected Receipt Date** 02/15/2026.
6. Open the purchase order from Step 5 and set **Qty. to Receive** to 2 and post only Receipt.
7. Open the sales order from Step 2 and change **Shipment Date** to 02/10/2026.
8. Open the **Requisition Worksheets** and run **Calculate Plan** for Item 80001
  - **Starting Date**: 01/23/2026
  - **Ending Date**: 03/01/2026
9. A planning suggestion is given to replenish quantity of 8 with a new purchase order and **Due Date** 02/10/2026.

The status information in Table 337 is shown in the following illustration.

Entry No. 28 in Table 337 has reservation status **Tracking** to match the existing inventory on Item Ledger Entry 318 for 2 units, and the outstanding demand in Sales Order Table 37. The subsequent Entry No. 29 also has reservation status **Tracking** and links the remaining quantity of 8 units between the demand in Sales Order Table 37 and the suggested supply in Requisition Line Table 246.

Entry No. 30 is the existing purchase order is partially received with quantity 2. As a result, the **Reservation Status** field is Surplus, and [!INCLUDE[prod_short](includes/prod_short.md)] sets the **Quantity (Base)** field to *8* (remaining balance) and the **Suppressed Action Msg.** field is enabled.

#### Action Message Adjustment

The **Action Message Adjustment** field displays the change in the supply side of the order tracking that results when you accept the related action messages. A value appears here only when the facilities for both order tracking and action messages are active (Order Tracking policy set to Tracking & Action Msg.). The value is calculated based on the data in the *Action Message Entry* table (Table 99000849). The following example serves as an illustration.
1. Open item 80002. Set the following field:
 - **Order Tracking Policy**: Tracking and Action Msg.
2. Create a sales order. Set the following fields:
  - **Item**: 80002
  - **Location**: BLUE
  - **Quantity**: 100
3. Open the **Order Planning** page, and run the **Calculate Plan** batch job.
4. Select the sales order from Step 2 and run the **Make Orders** batch job.
5. On the sales order from Step 2, change the **Quantity** field from 100 to 105.
The status information in Table 337 is shown in the following illustration.
6. Entry No. 34 has the field **Action Message Adjustment** in Table 337 enabled for 5 units with reservation status Surplus. As the sales order was increased at Step 5, [!INCLUDE[prod_short](includes/prod_short.md)] created this reservation because more supply is required.
7. Open the **Planning Worksheets** page, and choose **Get Action Messages**. [!INCLUDE[prod_short](includes/prod_short.md)] suggests increasing the purchase order quantity from 100 to 105.

#### Disallow cancellation

The **Disallow Cancellation** field indicates that the reservation entry represents the link between a sales order line and an assembly order. You can't delete this reservation because it helps maintain the synchronization that occurs when an item is assembled to order. The following example serves as an illustration.

1. Create a purchase order. Set the following fields:
  - **Base Unit of Measure**: PCS
  - Any default posting groups
  - **Replenishment System**: Assembly
  - **Assembly Policy**: Assemble-to-Order
  - **Order Tracking Policy**: Tracking Only
2. Create a new item called Assemble COMP. Set the following fields:
  - **Base Unit of Measure**: PCS
  - Any default posting groups
  - **Replenishment System**: Purchase
  - **Order Tracking Policy**: Tracking Only
3. Open item Assemble FG, and on the **Navigate** tab, in the **Assembly/Production** group, choose **Assembly**, and then choose **Assembly BOM**. On the Assembly BOM, set the following fields:
  - **Type**: Item
  - **No.**: Assemble COMP
  - **Quantity per**: 1
Choose the **OK** button.
4. Open an item journal and increase the inventory of Assemble COMP to quantity 10 against location BLUE and post the journal line.
5. Create a sales order. Set the following fields:
  - **Item**: Assemble FG
  - **Location**: BLUE
  - **Quantity**: 1
The status information in Table 337 is shown in the following illustration.

Entry No. 82 has Reservation Status Surplus as 9 units of the Assemble Comp on inventory and has no demand. Entry No. 84 is tracking reservation entries between the demand on the Assembly Line Table 901 and its supply on item ledger entry 346.

Entry No. 86 has Binding Order-to-Order with Reservation Status Reservation. Additionally, the **Disallow Cancellation** field is enabled as the assembly policy is set as Assemble to Order for item Assembly FG. Finally, the **Planning Flexibility** field is set to **None**, because [!INCLUDE[prod_short](includes/prod_short.md)] doesn't let the planning logic delete the reservation.

#### Quantity available to pick and reservations

Item quantities exist both as warehouse entries and as item ledger entries. These two entry types contain different information about where items are and whether they're available. Warehouse entries define an item’s availability by bin and bin type, which is called bin content. Item ledger entries define an item’s availability by its reservation to outbound documents. Special functionality exists in the picking algorithm to calculate the quantity that's available to pick when bin content is coupled with reservations. The picking algorithm subtracts:

- Quantities that are reserved for other outbound documents.
- Quantities on existing pick documents.
- Quantities that are picked but not shipped or consumed. 

The result displays in the **Available Qty. to Pick** field in the **Pick Worksheet** page. The value is also calculated when you create warehouse picks directly from outbound documents such as sales orders, production consumption, or outbound transfers.

*Quantity available to pick = quantity in pick bins - quantity on picks and movements – (reserved quantity in pick bins + reserved quantity on picks and movements).*

The following example illustrates how the value in the quantity available to pick is calculated.

1. Create a new item called Warehouse Item. Set the following fields:
  - **Base Unit of Measure**: PCS
  - Any default posting groups
  - **Replenishment System**: Purchase
  - **Reserve Policy**: Always
  - **Order Tracking Policy**: Tracking Only
2. Create a purchase order against vendor 60000. Set the following fields:
  - **Item**: Warehouse Item
  - **Location**: WHITE
  - **Quantity**: 100
3. Release the purchase order and create the warehouse receipt.
4. Post the warehouse receipt and register the warehouse put-away for quantity 100.
5. Create a second purchase order against vendor 60000. Set the following fields:
  - **Item**: Warehouse Item
  - **Location**: WHITE
  - **Quantity**: 10
6. Release the purchase order and create the warehouse receipt.
7. Post the warehouse receipt ONLY. Don't register the warehouse put away.
8. Create a sales order. Set the following fields:
  - **Item**: Warehouse Item
  - **Location**: WHITE
  - **Quantity**: 10
Reserved Quantity is automatically set to 10 due to the Reserve policy being set to Always.
9. Create a sales order. Set the following fields:
  - **Item**: Warehouse Item
  - **Location**: WHITE
  - **Quantity**: 100
Reserved Quantity is automatically set to 100 due to the reserve policy being set to **Always**.
10. Release the first sales order from Step 8 and create a warehouse shipment.
11. Release the warehouse shipment, and choose **Create Pick**.
The following error message displays:
  *Nothing to Handle.*
The reason is that the available quantity to pick is zero. The quantity is calculated as follows:
   Quantity on Inventory = 110
   Quantity available to pick = 100

> [!NOTE]  
> Quantity on the put-away or receive bin isn't available to pick.
   
   Total reserved against sales orders is 110
   Quantity available to pick = 100 – 110 = zero.

Registering the warehouse put-away in Step 7 enables the creation of the warehouse pick in Step 11.

## Illustrations for using transfer orders and planning

### Transfer orders

When using transfer orders and the item is shipped but not fully received, in the Reservation Entry table you get a reservation status Surplus. The location code is the transfer-to Location.

The **Source Ref. No.** field is calculated by the last Line Entry Number + Line Entry Number of the Item on the posted Transfer Shipment.

When order tracking is activated and there's no demand (sales order or consumption), [!INCLUDE[prod_short](includes/prod_short.md)] creates two entries in Table 337 with reservation status Surplus. One is against the *Transfer Line* Table 5741 and the other is against the Item Ledger Entry Table 32.

#### Example 1

1. Open items 80003 and 80004 and set the field **Tracking Policy** to *Tracking Only*. Leave the other fields as default.
2. Open an Item journal and increase the inventory of these items to quantity 10 each against location RED and post the journal lines.
3. Create a transfer order from location RED to BLUE for these two items: Item 80003 on Transfer Order Line 10000 and Item 80004 on the second line 20000, both for 10 units.
4. Post only the shipment part of the transfer order without any warehouse features.
The posted transfer shipment is shown in the following illustration.
The status information in Table 337 is shown in the following illustration.
5. Compare the results on the posted transfer shipment with the entries in Table 337.

The following table describes what happens in certain fields against reservation entry 40.

|Field|Description|  
|---------------------------------|---------------------------------------|  
|**Reservation Status**|Surplus as Item 80003 is set up with order tracking but no demand exists.|  
|**Location Code**|Transfer-to code location BLUE.|  
|**Source Type**|Transfer Line Table 5741.|  
|**Source ID**|Document No. of the transfer order 1011.|
|**Source Ref. No.**|Total Line No. 20000 + Line No. 10000 against Item 80003 = 30000.|

The explanation for the following fields against Reservation Entry 43 is as follows.

|Field|Description|  
|---------------------------------|---------------------------------------|  
|**Reservation Status**|Surplus as Item 80003 is set up with order tracking but no demand exists.|  
|**Location Code**|In-transit location OWN LOG is the location on which the item exists.|  
|**Source Type**|Item Ledger Entry Table 32.|  
|**Source Ref. No.**|The open Item Ledger Entry number 322.|

#### Example 2

The next example illustrates what happens when a component is transferred between locations, but at the same time is tracked between a demand need and available supply. The components transfer from location RED to BLUE, which is to be consumed on a released production order. The component uses Order Tracking, Order Planning, and Item Tracking.

The example highlights the detected flow in Table 337 in relation to the fields **Reservation Status**, **Location Code**, **Source Type**, **Source ID**, **Source Ref. No.**, and type of **Binding**.

1. In the **Manufacturing Setup** page, set field **Components at Location** set to RED.
2. Create a new Item Component. Set the following fields:
  - **Base Unit of Measure**: PCS
  - Any default posting groups
  - **Replenishment System**: Purchase
  - **Manufacturing Policy**: Make-to-Stock
  - **Order Tracking Policy**: Tracking Only
  - **Item Tracking Code**: LOTALL
3. Using the Item Journal, increase inventory for Item Component against location RED to 100 units. Set the following Lot numbers:
  - Lot number Lot A, Quantity 30
  - Lot number Lot B, Quantity 70
4. Create a new item Produced. Set the following fields:
  - **Base Unit of Measure**: PCS
  - Any default posting groups
  - **Replenishment System**: Production
  - **Manufacturing Policy**: Make-to-Stock
  - **Order Tracking Policy**: Tracking Only
5. Create **Production BOM** with 1 quantity per of the Item Component.
6. Assign the Production BOM against Item Produced.
7. Create a sales order. Set the following fields:
  - **Item**: Produced
  - **Location**: BLUE
  - **Quantity**: 100
8. On the **Actions** tab of the sales order, in the **Plan** group, choose **Planning** to create a linked released production order against the sales order.
9. Open the released production order/component need and notice that the location is set as RED.
The reason is that the **Components at Location** is RED on the **Manufacturing Setup** card.
The Item Produced gets the output against location BLUE.

The status information in Table 337 is shown in the following illustration.

##### Reservation entries with numbers 55 and 56

For the component need for Lot A and Lot B, respectively, order tracking links are created from the demand in Table 5407, Prod. Order Component, to the supply in Table 32, Item Ledger Entry. The **Reservation Status** field contains **Tracking** for all four entries to indicate that these dynamic order tracking links between supply and demand.

The demand in Table 5407, Prod. Order Component is linked to the Source ID of the released production order 101006. The supply in Table 32, Item Ledger Entry, is linked to Source Ref. No. being the Item Ledger Entry numbers 325 and 326 at which the units exist.

> [!NOTE]  
> The **Lot No.** field is empty on the demand lines because the lot numbers aren't specified on the component lines of the released production order.

##### Reservation Entry with number 57

From the sales demand in Table 37, Sales Line, an order tracking link is created to the supply in Table 5406, Prod. Order Line. The **Reservation Status** field contains **Reservation**, and the **Binding** field contains **Order-to-Order**. The released production order was generated specifically for the sales order and must remain linked, unlike order tracking links with reservation status of **Tracking**, which are created and changed dynamically.

> [!NOTE]  
> The **Binding** field can also contain *Order-to-Order* when using Make-to-Order as Manufacturing Policy and/or Order as Reordering Policy.

10. At this point in the scenario, the 100 units of the component are transferred from RED location to BLUE location by using a transfer order.

Select Lot A and Lot B for the shipment.

Post the total outstanding quantity as Shipped ONLY.

> [!NOTE]  
> Components can be consumed at location RED, but for the example to illustrate the flow of reservation entries, the units are transferred manually to location BLUE.

The status information in Table 337 is shown in the following illustration.

##### Reservation Entries with number 55 and 56

Order tracking entries for the two lots of the component reflecting demand in Table 5407 are changed from a reservation status of Tracking to Surplus. The reason is that the supplies that they were linked to before, in Table 32, were used by the shipment of the transfer order. Genuine surplus reflects excess supply or demand that remains untracked. It's an indication of an imbalance in the order network, which generates an action message by the planning engine unless resolves dynamically.

##### Reservation Entry Numbers 59 to 63

Because the two lots of the component posted on the transfer order as shipped but not received, all related positive order tracking entries are of reservation type **Surplus**. This type indicates that they aren't allocated to any demands. For each lot number, one entry relates to Table 5741, Transfer Line, and one entry relates to the item ledger entry at the in-transit location where the items now exist.

Table 5741, **Transfer Line**, is the Source Type. **Source ID** is the Transfer Order Document Number 1012 and **Source Ref. No.** is 20000 = 10000 + 10000 as detailed in Example 1. The location is set as BLUE for the transfer-to location code.

The remaining two entries with **Reservation Status** Surplus have Table 32, **Item Ledger Entry**, as Source Type and **Source Ref. No.** 328 and 330, including their lot numbers located in the In-transit location OUT LOG.

11. Post the outstanding transfer order as Received.

The status information in Table 337 is shown in the following illustration.

The order tracking entries are now similar to the first point in the scenario, before the transfer order was posted as shipped only, except entries for the component are now of reservation status **Surplus** instead of **Tracking**. This is because the component need is still at RED location, reflecting that the **Location Code** field on the production order component line contains RED as set up in the **Components at Location** setup field.

The supply that was allocated to this demand before was transferred to the BLUE location and now can't be fully tracked unless the component need on the production order line is changed to the BLUE location. This is recorded in the last two reservation entries with the lot numbers populated, **Source Type** field being Table 32 and **Source Ref. No.** field being Item ledger entries 333 and 334.

12. On the component list assigned to the released production order, change the location to BLUE for the component.

12. Open the **Consumption Journal** and run the **Calc. Consumption** batch job.
Assign Lot A Quantity 30 and Lot B Quantity 70.

Close the Item tracking form.

The status information in Table 337 is shown in the following illustration.

##### Reservation Entries with numbers 68 and 69

Because the component need changed to the BLUE location, and the supply is available as item ledger entries at the BLUE location, all order tracking entries for the two lot numbers are fully tracked, which is indicated by the reservation status of Tracking. The lot numbers aren't populated on the **Lot No.** field against the demand on Table 5406, **Prod. Order Line**, because we didn't specify lot numbers for the component on the released production order.

##### Reservation Entries with numbers 70 and 71

Entries with reservation status Prospect are generated in Table 337. The reason is that both lot numbers are assigned against the component on the consumption journal, but the journal wasn't posted.

### Planning calculated

When you use planning features, that is, requisition worksheets, planning worksheets, or order planning, reservation entries on Reservation Entry Table 337 might be modified or added depending on the planning suggestion. Example 3 uses the **Reordering Policy** of **Order** and a **Manufacturing Policy** of **Make-to Order** for a produced item. The component uses the **Reordering Policy** of **Fixed Reorder Quantity**.

#### Example 3

1. In the **Manufacturing Setup** card, **Component at Location** is RED from the previous example.
2. Create new Parent Item 70061. Set the following fields:
  - **Base Unit of Measure**: PCS
  - Any default posting groups
  - **Replenishment System**: Prod. Order
  - **Manufacturing Policy**: Make-to-Order
  - **Reordering Policy**: Order
  - **Reserve Policy**: Optional
  - **Order Tracking**: None
3. Create new Component Item 70062. Set the following fields:
  - **Base Unit of Measure**: PCS
  - Any default posting groups
  - **Replenishment System**: Purchase
  - **Reordering Policy**: Fixed Reorder Quantity
  - **Reserve Policy**: Optional
  - **Order Tracking Policy**: None
  - **Safety Stock Quantity**: 10
  - **Reorder Point**: 25
  - **Reorder Quantity**: 50
4. Create a new Production BOM and specify Component Item 70062 with quantity per 1.
Assign the Production BOM to the Parent Item 70061.
5. Create a sales order. Set the following fields:
  - **Item**: Fixed Reorder Quantity
  - **Location**: RED
  - **Quantity**: 40
  - **Shipment Date**: 2/15/2026
6. Open the **Planning Worksheets** page, and run the **Calculate Regenerative Plan** batch job.
  - **MPS/MRP**: enabled
  - **Starting Date**: 01/23/2026
  - **Ending Date**: 03/01/2026
  - Filter on items 70061 and 70062
  - No Forecast

The following planning suggestions are given.

The first planning suggestion is to create a new planned production order to supply the outstanding demand of the sales order for quantity 40 of the Parent Item 70061. Review order tracking and [!INCLUDE[prod_short](includes/prod_short.md)] shows the outstanding sales order. Order tracking is activated because the planning engine generates it.

The second line is to bring the Inventory above Reorder Point (25). So taking into account Reorder Quantity (50), the planning logic suggests a quantity of 50 units. The third line is to bring inventory to the safety stock level (10).

The fourth line is to replenish inventory when the sales order is shipped. The inventory is 20, which is below the reorder point. As a result, the planning engine proposes to purchase 50 more components taking into account reorder quantity. This amount is untracked quantity, so on Reservation Entry Table 337 it has the reservation status **Surplus**.

The status information in Table 337 is shown in the following illustration.

The **Reservation Status** field is Reservation and an Order-to-Order Binding is created. The reason is that the Item Manufacturing Policy is Make-to-Order and the Reordering Policy is set as Order. If one of the two is set to Order, the reservation status is **Reservation** instead of **Tracking** and **Binding** is set to **Order-to-Order**.

The demand of 40 units against the field **Source ID** is the sales order number 1005 and the Source Type is *Sales Line* Table 37. The reservation entry is aligned with the planning suggestion, Source Ref. No. 10000, Source ID is PLANNING, and Source Type is Requisition Line Table 246. So there's a balance between the demand from the sales order and its supply suggested by the planning engine.

##### Reservation Entry numbers 73 and 74

Running the **Calculate Plan** batch job generates the next four entries with a reservation status **Tracking** due to the setting of the reordering policy **Fixed Reorder Quantity** for the component. The planning suggestions replenish the required supply for component Item 70062, Source Ref. No. 20000 and 30000, with Source ID set to **PLANNING** and the **Source Type** from Requisition Line Table 246. The component need is created to fulfill the demand against the Parent Item 70061 for total Quantity (Base) 40. As a result of this demand, the field **Source Prod. Order Line** is 10000, with Source Type the *Component Need* Table 99000829.

The reservation status isn't Surplus, as order tracking exists between the demand of Parent Item 70061 and the supply of Component Item 70062.

##### Reservation Entry numbers 75 and 76

The last two entries have a reservation status **Surplus** because they're untracked quantities generated on the planning worksheet related to reordering parameters **Reorder Point** and **Reorder Quantity**.

## Related information  

[Design Details: Item Tracking Design](design-details-item-tracking-design.md)  
[Design Details: Balancing Demand and Supply](design-details-balancing-demand-and-supply.md)  
[Design Details: Reservation, Order Tracking, and Action Messaging](design-details-reservation-order-tracking-and-action-messaging.md)   
[Design Details: Supply Planning](design-details-supply-planning.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
