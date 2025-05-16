---
title: Reservation Entry table - Features that update the Reservation Entry table
description: Learn how to troubleshoot data inconsistency issues in the Reservation Entry table.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords:
ms.date: 06/26/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Reservation Entry table - Introduction

This technical whitepaper provides guidance to help you understand and troubleshoot data inconsistency issues in the *Reservation Entry* table (Table 337) in [!INCLUDE[prod_short](includes/prod_short.md)]. The first part introduces the features that generate or modify data in this table. It also covers several fields in the *Reservation Entry* table that are worth pointing out with these features. The second part demonstrates through examples how entries in the *Reservation Entry* table are generated, deleted, or modified when transfer orders are processed or planning features are executed.

The *Reservation Entry* table handles and stores reservation, item tracking, and order tracking information.

When handling item tracking with partial posting, the table works with the *Tracking Specification* table (Table 336). Data entered in the **Item Tracking Lines** page by the user is created in a temporary version of Table 336 and is committed to Table 337 and the tracking specification table when the page is closed.

In general terms, the data generated in the *Reservation Entry* table depends on which features you use and which parameters you selected on the item card. These include:

- Order Tracking policy
- Reservation policy
- Planning features executed
- Reordering and manufacturing policy
- Planning parameters on the item or stock-keeping unit card
- Item Tracking Code

## Features that update the Reservation Entry table

### Order Tracking policy

If the **Order Tracking Policy** field on an item is set to None, [!INCLUDE[prod_short](includes/prod_short.md)] will never create reservation entries in the *Reservation Entry* table, unless the Net Change Plan or Regenerative Plan, Reservation, or Item Tracking is executed. Additionally, without order tracking enabled, you can have reservation entries when using the Manufacturing-to-Order or Assembly-to-Order policies.

You can consider setting the **Order Tracking Policy** to None if you won't require tracking on the fly a demand against a supply or vice versa. The tracking of supply against demand is handled by the order tracking functionality or the planning engine. We don't recommend that you use order tracking together with planning functionality.

When you set the **Order Tracking Policy** field to Tracking Only, [!INCLUDE[prod_short](includes/prod_short.md)] will always create entries in table 337 whenever an order is created for the item, but the **Reservation Status** in table 337 isn't always strictly set to Tracking. Consider the following scenario:

> [!NOTE]  
> The work date is set as 01/23/2014 (MM/DD/YYYY) for all examples. 
  
1. Create an item with **Order Tracking Policy** field set to Tracking Only.  
1. Create a purchase order. [!INCLUDE[prod_short](includes/prod_short.md)] will create a reservation entry with the **Reservation Status** of Surplus, since the purchase order isn't yet allocated to a demand.
1. Create a sales order. [!INCLUDE[prod_short](includes/prod_short.md)] will now create another reservation entry with a **Reservation Status** of Tracking.

The **Reservation Status** created in step 2 will be updated to Tracking; this is handled by [!INCLUDE[prod_short](includes/prod_short.md)] automatically. This concept is called Dynamic Tracking.
By setting the **Order Tracking Policy** field on the item to Tracking Only, an end user can make use of the order tracking feature to get an overview of which supply the demand is allocated to and vice versa.

> [!NOTE]  
> Tracking functionality does not replace planning functionality, which considers all items, demands, and supplies together to provide the optimal planning proposals to optimize customer service levels and balance inventory levels.

### Reservation policy

A reservation consists of a pair of records in the *Reservation Entry* table with a **Reservation Status** of Reservation, which shares the same entry number. One record has the Positive field enabled and points to the supply. The other record has the **Positive** field not enabled and points to the demand. The fields **Source Type**, **Source Ref. No.**, and **Source ID** highlight the reservation link between the demand and supply.

The information in the **Source Type** field is the table the reservation **Entry No.** field is related to. For example, if it's a demand (negative) entry, then it could be the *Sales Order* table (Table 37) or the *Planning Component* (Table 99000829).

The **Source ID** field contains the ID of the document in the table referenced by the Source Type.

The **Source Ref. No.** field contains a reference number for the line, to which the reservation **Entry No.** is related to. If the entry is related to a sale or purchase line, a journal line, or a requisition line, information in this field is copied from the **Line No.** field. If it's related to an entry in the *Item Ledger Entry* table (Table 32), information in this field is copied from the **Entry No.** field of the *Item Ledger Entry* table.

When you use the reservation policy option Always in combination with order tracking, both are normally in sync. However, when the reservation is removed or the receipt date of supply is moved forward past the demand due date, the order tracking will be removed. You can also encounter an error message, in which [!INCLUDE[prod_short](includes/prod_short.md)] asks what to do with existing reservations. This scenario is illustrated in the following example:

1. Create a new item called COMP. Set the following fields:
  - **Replenishment System**: Purchase
  - **Order Tracking Policy**: Tracking Only
  - **Reserve**: Always
2. Create a second item called FG. Set the following fields:
  - **Replenishment System**: Prod. Order
  - **Order Tracking Policy**: Tracking Only
  - **Reserve**: Always
3. Create a second item called FG. Set the following fields:
  - **Item**: COMP
  - **Quantity Per**: 1
4. Certify the Production BOM No. BOM FG and assign against Item FG.
5. Create a purchase order. Set the following fields:
  - **Item**: COMP
  - **Quantity**: 10
  - **Location Code**: BLUE
  - **Expected Receipt Date**: 01/24/2014
6. Create a sales order. Set the following fields:
  - **Shipment Date**: 02/14/2014
  - **Location Code**: BLUE
  - **Item**: COMP
  - **Quantity**: 10

> [!NOTE]  
> Automatic reservation has been executed between the purchase and sales order. Additionally, order tracking has been created between the purchase and sales orders.

7. Create a manual released production order. Set the following fields:
  - **Item**: 02/14/2014
  - **Quantity**: 10
  - **Location**: BLUE
  - **Due Date**: 02/01/2014
8. On the **Home** tab, in the Process group, choose **Refresh Production Order**.
9. Open the components list and look up Item COMP.

> [!NOTE]  
> No reservation or order tracking is created by [!INCLUDE[prod_short](includes/prod_short.md)]. The reason is that a reservation already exists against the sales order created in Step 6.

Suppose, due to business reasons, the item is needed more urgently on the released production order created in Step 7. So next, in the following steps we cancel the reservation from the sales order that was created in Step 6 and notice how order tracking is handled.

10. Look up the sales order for Item COMP from Step 6 and cancel the reservation.
11. Open the purchase order from Step 5 and notice that order tracking is now created between the purchase order and the component needed from the released production order.
12. Recreate the reservation between the component needed from the released production order and the supply from the purchase order in Step 5.

> [!NOTE]  
> The reservation is not re-created, which needs to be done manually.

13. Change the **Expected Receipt Date** field on the purchase order header at Step 5 from 01/24/2014 to 02/05/2014.

[!INCLUDE[prod_short](includes/prod_short.md)] will display the following warning message:

   Reservations exist for this Order. These reservations are canceled if a data conflict is caused by this change. Do you want to continue?

14. Choose Yes. Look up the reservation and order tracking entries from the purchase order.

> [!NOTE]  
> The existing reservation is canceled and needs to be recreated manually. The order, however, is dynamic and has been recreated by [!INCLUDE[prod_short](includes/prod_short.md)] to exist between the purchase order and the sales order. The reason is the demand for the released production order (02/01/2014) is before the expected receipt date of the supply.

This concludes the demonstration of the interaction between using automatic reservations and order tracking. The examples also show what happens when you modify due dates and the error message that is triggered when there's a reservation conflict.

### Planning calculated

Planning done using order planning, the requisition worksheet, or the planning worksheet will generate entries in the *Reservation Entry* table with the **Reservation Status** field set to Tracking, Reservation, or Surplus. There should always be a matching pair with the same Entry No. of positive and negative value in the **Quantity (Base)** field when the status is Tracking or Reservation. The **Source Type** field will be the demand type, that is, table 37 for the negative quantity and a planning table, for example, table 246, for the positive quantity. The **Source ID** field will be PLANNING.

In the case of non-allocated supply or demand, [!INCLUDE[prod_short](includes/prod_short.md)] will set the **Reservation Status** field to Surplus. For example, you can have a reservation status of Surplus when the existing inventory is below the safety stock quantity or demand is linked to the forecast.

The *Untracked Planning Element* table (Table 99000855) holds information about untracked quantities displayed when the user does a lookup from the order tracking page to see untracked quantities or chooses a Warning Icon in the planning worksheet. The table contains entries that account for an untracked surplus quantity in the order tracking network.

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

In the *Reservation Entry* table, as on the Purchase, Transfer and Production orders, there's a **Planning Flexibility** field. This option field defines if the supply represented by these supply orders is considered by the planning system when calculating Action Messages. If the field contains the option Unlimited, then the planning system includes the line when calculating Action Messages. If the field contains the option None, then the line is firm and unchangeable, and the planning system doesn't include the line when calculating Action Messages. The feature is managed in the *Reservation Entry* table by the field with the same name.

### Reordering and manufacturing policy

If a planning feature is executed for an item set with the Reordering Policy set to Order, [!INCLUDE[prod_short](includes/prod_short.md)] will create entries in the *Reservation Entry* table with the reservation status of type Reservation instead of Tracking.

The **Source Type** and **Source ID** fields will have the equivalent treatment of other reordering policies. However, in the **Binding** field in the *Reservation Entry* table, [!INCLUDE[prod_short](includes/prod_short.md)] will enter Order-to-Order.

The **Binding** field is filled in to control supply orders that are bound to specific demand, for example, production orders that are created directly from a sales order. The field displays Order-to-Order when the entry is tied specifically to a demand or a supply (Automatic Reservation). The demand can be related to sales or component needs.

### Item tracking and prospect reservation entry

The Prospect reservation status can be created by [!INCLUDE[prod_short](includes/prod_short.md)] in the *Reservation Entry* table when you aren't using any order network entities, that is, Order Tracking. For example, on a consumption journal line you assign Item tracking to the component. However, if the item is already order tracked, [!INCLUDE[prod_short](includes/prod_short.md)] might create more Prospect reservation entries. This is demonstrated in EXAMPLE 2 related to transfer orders in the second part of this document.

When you view or modify the **Item tracking lines** page, the collective contents of the *Tracking Specification* table (Table 336) and *Reservation Entry* table are presented in a temporary version of Table 336. This ensures that historic and active item tracking data is accessed as one.

Reservations fall into two categories: Nonspecific reservations, where lot and serial numbers aren't specified at the time of reservation, and Specific reservations, where you reserve specific lot or serial numbers from inventory.

On a Nonspecific reservation, the **Lot No.** or **Serial No.** field is blank in the **Entry No.** of Table 337 pointing at the demand (for instance, the sale). Because of the structure of the reservation logic in [!INCLUDE[prod_short](includes/prod_short.md)], when you place a Nonspecific reservation on an item-tracked item in inventory, [!INCLUDE[prod_short](includes/prod_short.md)] must nevertheless select specific item ledger entries to reserve against.

Since the item ledger entries carry the item tracking information, the reservation indirectly reserves specific lot or serial numbers, even though the user didn't intend this. However, with Late Binding, [!INCLUDE[prod_short](includes/prod_short.md)] still reserves against specific entries, but then uses a reshuffling mechanism in [!INCLUDE[prod_short](includes/prod_short.md)] when posting.

For further information, review the [!INCLUDE[prod_short](includes/prod_short.md)] Technical Whitepapers listed in the Additional Resources at the end of this document.

### Source Subtype, Suppressed Action Msg., Action Message Adjustment, and Disallow Cancellation fields

The **Source Subtype**, **Suppressed Action Msg.**, **Action Message Adjustment**, and **Disallow Cancellation** fields in the *Reservation Entry* table are described in this section. Scenarios are provided to demonstrate the use of the **Suppressed Action Msg.**, **Action Message Adjustment** and **Disallow Cancellation** fields. The **Action Message Adjustment** field is used for the order tracking policy feature Tracking and Action Message. The **Disallow Cancellation** field is used for the Assembly-to-Order feature in [!INCLUDE[prod_short](includes/prod_short.md)] 2013.

#### Source Subtype

The **Source Subtype** field indicates which Source Subtype the reservation entry is related to. If the entry is related to a purchase or sales line, the field is copied from the **Document Type** field on the line. If it is related to a journal line, the field is copied from the **Entry Type** field on the journal line.

#### Suppressed Action Msg.

The **Suppressed Action Msg.** field records when an existing supply has already been partially processed, for example, when a purchase order has already been partially received or a production order has consumptions posted against it.

When Planning is executed, [!INCLUDE[prod_short](includes/prod_short.md)] marks this field and sets the **Reservation Entry Status** field to **Surplus**. The following example serves as an illustration:

1. Open Item 80001. Set the following fields:
  - **Reordering Policy**: Lot-for-Lot
  - **Reserve**: Optional
  - **Order Tracking Policy**: None
2. Create a sales order. Set the following fields:
  - **Item**: 80001
  - **Location**: Blank/None
  - **Quantity**: 10
  - **Shipment Date**: 2/15/2014
3. Open the **Requisition Worksheets** and run the **Calculate Plan** batch job for Item 80001.
  - **Starting Date**: 01/23/2014
  - **Ending Date**: 03/01/2014
4. A planning suggestion is given to replenish the quantity of 10 with a new purchase order and **Due Date** 02/15/2014.
5. On the **Actions** tab, in the Functions group, choose **Carry Out Action** Message to create a purchase order with **Expected Receipt Date** 02/15/2014.
6. Open the purchase order from Step 5 and set **Qty. to Receive** to 2 and post only Receipt.
7. Open the sales order from Step 2 and change **Shipment Date** to 02/10/2014.
8. Open the **Requisition Worksheets** and run **Calculate Plan** for Item 80001
  - **Starting Date**: 01/23/2014
  - **Ending Date**: 03/01/2014
9. A planning suggestion is given to replenish quantity of 8 with a new purchase order and **Due Date** 02/10/2014.

The status information in Table 337 is shown in the following illustration.

Entry No. 28 in Table 337 has reservation status Tracking to match the existing inventory recorded on Item Ledger Entry 318 for 2 units and the outstanding demand in the Sales Order Table 37. The subsequent Entry No. 29 also has reservation status Tracking and links the remaining quantity of 8 units between the demand in Sales Order Table 37 and the suggested supply in the Requisition Line Table 246.

Entry No. 30 is the existing purchase order is partially received with quantity 2. As a result, the **Reservation Status** field is Surplus, and [!INCLUDE[prod_short](includes/prod_short.md)] sets the **Quantity (Base)** field to *8* (remaining balance) and the **Suppressed Action Msg.** field is enabled.

#### Action Message Adjustment

The **Action Message Adjustment** field displays the change in the supply side of the order tracking that results when you accept the related action messages. A value appears here only when the facilities for both order tracking and action messages are active (Order Tracking policy set to Tracking & Action Msg.). The value is calculated based on the data in the *Action Message Entry* table (Table 99000849). The following example serves as an illustration:
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
7. Open the **Planning Worksheets** page and on the **Home** tab, in the **Process** group, choose **Get Action Messages**. [!INCLUDE[prod_short](includes/prod_short.md)] will suggest increasing the Purchase Order quantity from 100 to 105.

#### Disallow Cancellation

The **Disallow Cancellation** field indicates that the reservation entry represents the link between a sales order line and an assembly order. You can't delete this reservation because it's required to maintain the synchronization that occurs when an item is assembled to order. The following example serves as an illustration:

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
4. Open an Item Journal and increase the inventory of Assemble COMP to quantity 10 against location BLUE and post the journal line.
5. Create a sales order. Set the following fields:
  - **Item**: Assemble FG
  - **Location**: BLUE
  - **Quantity**: 1
The status information in Table 337 is shown in the following illustration.

Entry No. 82 has Reservation Status Surplus as 9 units of the Assemble Comp on inventory and has no demand. Entry No. 84 is tracking reservation entries between the demand on the *Assembly Line* Table 901 and its supply on item ledger entry 346.

Entry No. 86 has Binding Order-to-Order with Reservation Status Reservation. Additionally, the **Disallow Cancellation** field is enabled as the assembly policy is set as Assemble to Order for item Assembly FG. Finally, the **Planning Flexibility** field is set to None, as [!INCLUDE[prod_short](includes/prod_short.md)] doesn't permit the planning logic to delete the reservation.

#### Quantity available to pick and reservations

The **Reserved Pick & Ship Qty.** field in Table 337 exists in versions prior to [!INCLUDE[prod_short](includes/prod_short.md)] 2013 controls item availability within a managed warehouse. In any installation of [!INCLUDE[prod_short](includes/prod_short.md)] warehouse management, item quantities exist both as warehouse entries and as item ledger entries. These two entry types contain different information about where items exist and whether they're available. Warehouse entries define an item’s availability by bin and bin type, which is called bin content. Item ledger entries define an item’s availability by its reservation to outbound documents. Special functionality exists in the picking algorithm to calculate the quantity that is available to pick when bin content is coupled with reservations. The picking algorithm subtracts quantities that are reserved for other outbound documents, quantities on existing pick documents, and quantities that are picked but not yet shipped or consumed. The result is displayed in the **Available Qty. to Pick** field in the **Pick Worksheet** page, where the field is calculated dynamically. The value is also calculated when a user creates warehouse picks directly from outbound documents such as sales orders, production consumption, or outbound transfers.

*Quantity available to pick = quantity in pick bins - quantity on picks and movements – (reserved quantity in pick bins + reserved quantity on picks and movements).*

The following example illustrates how the value in the quantity available to pick is calculated in [!INCLUDE[prod_short](includes/prod_short.md)]:

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
Reserved Quantity is automatically set to 100 due to the Reserve policy being set to Always.
10. Release the first sales order from Step 8 and create a warehouse shipment.
11. Release the warehouse shipment and on the **Actions** tab, choose **Create Pick**.
The following error message is displayed:
  *Nothing to Handle.*
The reason is that the available quantity to pick is zero. This is calculated as follows:
   Quantity on Inventory = 110
   Quantity available to pick = 100

> [!NOTE]  
> Quantity on put-away or on receive bin is not available to pick.
   
   Total reserved against sales orders is 110
   Quantity available to pick = 100 – 110 = zero.

When the warehouse put-away is registered in Step 7, that enables the creation of the warehouse pick in Step 11. In versions prior to [!INCLUDE[prod_short](includes/prod_short.md)] 2013, the Reserved **Pick & Ship Qty.** field in Table 337 is populated against the reservation for quantity 10.

The following illustration is taken from [!INCLUDE[prod_short](includes/prod_short.md)] 2009 R2.

## Illustrations using transfer orders and planning

### Transfer orders

When using transfer orders and the item is shipped but not fully received, in the *Reservation Entry* table you get a reservation status Surplus. The location code will be the Transfer-to Location.

The **Source Ref. No.** field is calculated by the last Line Entry Number + Line Entry Number of the Item on the posted Transfer Shipment.

When order tracking is activated and there's no demand (sales order or consumption), [!INCLUDE[prod_short](includes/prod_short.md)] creates two entries in Table 337 with reservation status Surplus. One is against the *Transfer Line* Table 5741 and the other is against the Item Ledger Entry Table 32.

This is demonstrated in the first example.

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

The next example illustrates what happens when a component is transferred between locations, but at the same time is tracked between a demand need and available supply. The components will be transferred from location RED to BLUE, which is to be consumed on a released production order. The component uses Order Tracking, Order Planning, and Item Tracking.

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
The Item Produced will get the output against location BLUE.

The status information in Table 337 is shown in the following illustration.

##### Reservation Entries with numbers 55 and 56

For the component need for Lot A and Lot B, respectively, order tracking links are created from the demand in Table 5407, Prod. Order Component, to the supply in Table 32, Item Ledger Entry. The **Reservation Status** field contains Tracking for all four entries to indicate that these dynamic order tracking links between supply and demand.

The demand in Table 5407, Prod. Order Component is linked to the Source ID of the released production order 101006. The supply in Table 32, Item Ledger Entry, is linked to Source Ref. No. being the Item Ledger Entry numbers 325 and 326 at which the units exist.

> [!NOTE]  
> The **Lot No.** field is empty on the demand lines because the lot numbers are not specified on the component lines of the released production order.

##### Reservation Entry with number 57

From the sales demand in Table 37, Sales Line, an order tracking link is created to the supply in Table 5406, Prod. Order Line. The **Reservation Status** field contains Reservation, and the **Binding** field contains Order-to-Order. This is because the released production order was generated specifically for the sales order and must remain linked, unlike order tracking links with reservation status of Tracking, which are created and changed dynamically.

> [!NOTE]  
> The **Binding** field can also contain *Order-to-Order* when using Make-to-Order as Manufacturing Policy and/or Order as Reordering Policy.

10. At this point in the scenario, the 100 units of the component are transferred from RED location to BLUE location by using a transfer order.

Select Lot A and Lot B for the shipment.

Post the total outstanding quantity as Shipped ONLY.

> [!NOTE]  
> Components can be consumed at location RED, but for the example to illustrate the flow of reservation entries, the units are transferred manually to location BLUE.

The status information in Table 337 is shown in the following illustration.

##### Reservation Entries with number 55 and 56

Order tracking entries for the two lots of the component reflecting demand in Table 5407 are changed from a reservation status of Tracking to Surplus. The reason is that the supplies that they were linked to before, in Table 32, have been used by the shipment of the transfer order. Genuine surplus, as in this case, reflects excess supply or demand that remains untracked. It's an indication of an imbalance in the order network, which will generate an action message by the planning system unless it's resolved dynamically.

##### Reservation Entry Numbers 59 to 63

Because the two lots of the component are posted on the transfer order as shipped but not received, all related positive order tracking entries are of reservation type Surplus, indicating that they aren't allocated to any demands. For each lot number, one entry relates to Table 5741, Transfer Line, and one entry relates to the item ledger entry at the in-transit location where the items now exist.

Table 5741, **Transfer Line**, is the Source Type. **Source ID** is the Transfer Order Document Number 1012 and **Source Ref. No.** is 20000 = 10000 + 10000 as detailed in Example 1. The location is set as BLUE for the transfer-to location code.

The remaining two entries with **Reservation Status** Surplus have Table 32, **Item Ledger Entry**, as Source Type and **Source Ref. No.** 328 and 330, including their lot numbers located at present in the In-transit location OUT LOG.

11. Post the outstanding transfer order as Received.

The status information in Table 337 is shown in the following illustration.

The order tracking entries are now similar to the first point in the scenario, before the transfer order was posted as shipped only, except entries for the component are now of reservation status Surplus instead of Tracking. This is because the component need is still at RED location, reflecting that the **Location Code** field on the production order component line contains RED as set up in the **Components at Location** setup field.

The supply that was allocated to this demand before had been transferred to the BLUE location and can't now be fully tracked unless the component need on the production order line is changed to the BLUE location. This is recorded in the last two reservation entries with the lot numbers populated, **Source Type** field being Table 32 and **Source Ref. No.** field being Item ledger entries 333 and 334.

12. On the component list assigned to the released production order, change the location to BLUE for the component.

12. Open the **Consumption Journal** and run the **Calc. Consumption** batch job.
Assign Lot A Quantity 30 and Lot B Quantity 70.

Close the Item tracking form.

The status information in Table 337 is shown in the following illustration.

##### Reservation Entries with numbers 68 and 69

Since the component need has been changed to BLUE location, and the supply is available as item ledger entries at the BLUE location, all order tracking entries for the two lot numbers are now fully tracked, indicated by the reservation status of Tracking. The lot numbers aren't populated on the **Lot No.** field against the demand on Table 5406, **Prod. Order Line**, as we did not specify lot numbers for the component on the released production order.

##### Reservation Entries with numbers 70 and 71

Entries with reservation status Prospect are generated in Table 337. The reason is that both lot numbers are assigned against the component on the consumption journal, but the journal hasn't been posted.

This completes the section on how order tracking entries in the **Reservation Entry** table are generated, modified, and deleted when using multiple features in combination with transfer orders.

### Planning calculated

When using planning features, that is, the **Requisition Worksheet**, **Planning Worksheet**, or **Order Planning**, then reservation entries on **Reservation Entry** Table 337 might be modified or added depending on the planning suggestion given by the logic in [!INCLUDE[prod_short](includes/prod_short.md)]. Example 3 will use **Reordering Policy** Order with **Manufacturing Policy** Make-to Order for a produced Item. The component will use **Reordering Policy** Fixed Reorder Quantity.

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
  - **Shipment Date**: 2/15/2014
6. Open the **Planning Worksheets** page, and run the **Calculate Regenerative Plan** batch job.
  - **MPS/MRP**: enabled
  - **Starting Date**: 01/23/2014
  - **Ending Date**: 03/01/2014
  - Filter on items 70061 and 70062
  - No Forecast

The following planning suggestions are given.

The first planning suggestion is to create a new planned production order to supply the outstanding demand of the sales order for quantity 40 of the Parent Item 70061. Review order tracking and [!INCLUDE[prod_short](includes/prod_short.md)] will show the outstanding sales order. Order tracking is activated as it is generated by the planning engine.

The second line is to bring the Inventory above Reorder Point (25). So taking into account Reorder Quantity (50), a quantity of 50 units is suggested by the planning logic. The third line is to bring the Inventory to Safety Stock Level (10).

The fourth line is to replenish inventory when the sales order is shipped. At that time, the Inventory is 20 and so below Reorder Point. As a result, the planning engine proposes to purchase 50 additional components taking into account Reorder Quantity. This is Untracked Quantity, so on the *Reservation Entry* Table 337 this will be marked with reservation status Surplus.

The status information in Table 337 is shown in the following illustration.

The **Reservation Status** field is Reservation and an Order-to-Order Binding is created. The reason is that the Item Manufacturing Policy is Make-to-Order and the Reordering Policy is set as Order. If one of the two is set to Order, then the reservation status will be Reservation instead of Tracking and Binding is set to Order-to-Order.

The demand of 40 units against the field **Source ID** is the sales order number 1005 and the Source Type is *Sales Line* Table 37. The reservation entry is aligned with the planning suggestion, Source Ref. No. 10000, Source ID is PLANNING, and Source Type is *Requisition Line* Table 246. So there's a balance between the demand from the sales order and its supply suggested by the planning engine.

##### Reservation Entry numbers 73 and 74

By running the Calculate Plan batch job, the next four entries are generated with a reservation status Tracking due to the setting of the reordering policy Fixed Reorder Quantity for the component. The required supply for component Item 70062 is replenished by the planning suggestions given, Source Ref. No. 20000 and 30000, with Source ID set to PLANNING and Source Type from *Requisition Line* Table 246. The component need is created to fulfill the demand against the Parent Item 70061 for total Quantity (Base) 40. As a result of this demand, the field **Source Prod. Order Line** is 10000, with Source Type the *Component Need* Table 99000829.

The reservation status isn't Surplus, as order tracking exists between the demand of Parent Item 70061 and the supply of Component Item 70062.

##### Reservation Entry numbers 75 and 76

The last two entries have a reservation status Surplus, as these are Untracked Quantities generated on the planning worksheet related to reordering parameters Reorder Point and Reorder Quantity.

## Related information  
[Design Details: Item Tracking Design](design-details-item-tracking-design.md)  
[Design Details: Balancing Demand and Supply](design-details-balancing-demand-and-supply.md)  
[Design Details: Reservation, Order Tracking, and Action Messaging](design-details-reservation-order-tracking-and-action-messaging.md)   
[Design Details: Supply Planning](design-details-supply-planning.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
