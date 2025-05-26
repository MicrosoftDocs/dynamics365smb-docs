---
title: Receiving, putting-away, moving, picking and shipping in advanced warehouse configuration
description: Inbound and outbound processes can be performed in different ways depending on the warehouse complexity level.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords:
ms.search.form: 
ms.date: 12/07/2023
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Walkthrough of inbound and outbound flow in advanced warehouse Configuration

This walkthrough demonstrates how to complete inbound and outbound flows in the Advanced: Directed Put-away and Pick configuration. For more information, see [Overview of different configuration options](../../design-details-warehouse-management.md#overview-of-different-configuration-options).

## Prerequisites  
To complete this walkthrough, you need to make yourself a warehouse employee at *WHITE* location by following these steps:  
1. Choose the ![Lightbulb that opens the Tell Me feature 1.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Employees**, and then choose the related link.  
2. Choose the **User ID** field, and select your own user account on the **Users** page.  
3. In the **Location Code** field, enter WHITE.  
4. Enable the **Default** toggle.


## Scenario  
Ellen, the warehouse manager utilizes cross-dock and bin replenishment functionality to speed up receiving and shipping time.  

## Steps

1. Create Warehouse Shipment.  

    1. Choose the ![Lightbulb that opens the Tell Me feature 2.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, and then choose the related link.  
    2. Select order for customer 10000 for the WHITE location. External Order No is *W-1*.
    3. Choose the **Create Warehouse Shipment** action to create warehouse shipment for selected sales order.
    4. Choose the **Release** action to notify the warehouse that the sales shipment is ready for warehouse handling.  

2. Define bins for the item to control where it's put-away 

    1.  Choose the ![Lightbulb that opens the Tell Me feature 3.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.  
    2.  Select the *WRB-1000* and then choose the **Bin Contents** action.  
    3.  Choose the **New** action. Add two lines.
    
    |Item|Location code|Bin Code|Fixed|Unit of Measure|
    |----------|----------|---------|---|------|  
    |WRB-1000|WHITE|W-05-0001|Yes|BAG|  
    |WRB-1000|WHITE|W-05-0002|Yes|BAG|

3. Create Warehouse Receipt.  

    1. Choose the ![Lightbulb that opens the Tell Me feature 4.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders**, and then choose the related link.  
    2. Select order from vendor 10000 for the WHITE location. Vendor Order No is *W-2*. Use the personalization tools if the **Vendor Order No.** field isn't visible. For more information, see [Personalize Your Workspace](../../ui-personalization-user.md).
	3. Choose the **Create Warehouse Receipt** action to create warehouse receipt for selected purchase order.


4. Check if there are outgoing orders that need received items and post receipt
    1. Choose the **Calculate Cross-Dock** action. This populates a column **Qty. to Cross-Dock**.
    2. Enter 0 into the **Qty. to Cross Dock** field in the line with item *WRB-1000* as you don't plan to repack in the receiving area.
    3. Choose the **Post Receipt** action.

5. Register the Warehouse Put-Away
    1. Using the ![Lightbulb that opens the Tell Me feature 5.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Put-Away** and choose the related link.
    2. Locate the warehouse put-away document created from your Warehouse Receipt and open it
    3. On the **Warehouse Put-Away** page, review the **Lines** section

    At this stage, the bin capacity logic is revealed. the warehouse put-away lines have three lines for item *WRB-1000*:
    - A Take line to move the received quantities from the receiving bin (W-08-0001)
    - A Place line that moves a one BAG into the one of configured fixed bins (W-05-0001)
    - A Place line that moves another BAG into another fixed bins (W-05-0002). This is because single fixed bin can't contain the full receipt quantity.

    Because this put-away contains cross-dock lines, you see three  lines for item *WRB-1001*:
    -  A Take line to move the received quantities from the receiving bin (W-08-0001)
    -  A Place line for the 2 into the cross-dock bin
    -  A Place line for the remaining quantity in storage bin

    4. Choose the **Register Put-away** action.


6. Define a pick bins for the item to control where it's picked from 

    1.  Choose the ![Lightbulb that opens the Tell Me feature 6.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Locations**, and then choose the related link.  
    2.  Open the *WHITE* location card.  
    3.  Choose the **Bins** action in the **Location Card**
    4.  Select the bin *W-02-0001*, and then choose the **Contents** action.  
    5.  Choose the **New** action.  
    6.  Enable the **Fixed** toggle.  
    7.  In the **Item No.** field, enter *WRB-1000*. 
    8.  In the **Min Qty.** field, enter *2*. 
    9.  In the **Max Qty** field, enter *10*. 

    Use the personalization tools if the **Min Qty.** and **Max Qty.** fields aren't visible. For more information, see [Personalize Your Workspace](../../ui-personalization-user.md). 

7. Reorganize warehouse by moving items from bulk storage area to picking area, to optimize picking time.

    1. Choose the ![Lightbulb that opens the Tell Me feature 7.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Movement Worksheets** and choose the related link
    2. Choose the **Calculate Bin Replenishment** action. 

    The warehouse worksheet with proposal on moving item *WRB-1000* from bulk storage to pick area is created.

    3. Choose the **Create Movement** action and confirm to create the document.
    4.  Choose the ![Lightbulb that opens the Tell Me feature 8.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Movements** and choose the related link
    5.  Open the warehouse movement you created, review the **Lines** section

     At this stage, the break-bulk functionality is revealed. There will be four lines:
    - A line to Take the one BAG out bulk storage bin
    - A line to Place the 48 PCS back into stock in the same bin. 
    - A line to Take the 10 PCS out bulk storage bin
    - A line to Place the 10 PCS into the picking bin

    6.  Choose the **Register Movement** action.

8. Create warehouse picks

    1. Choose the ![Lightbulb that opens the Tell Me feature 9.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Pick Worksheets** and choose the related link
    2. Choose the **Get Warehouse Documents** action, select the line for the sales order for customer 10000, and then choose the **OK** button to fill the worksheet lines according to the selected document.

    3. Inspect the **Qty. on Cross-Dock Bin** field. 

    4. Choose the **Create Pick** action.
    5. Confirm any of the pick settings needed, for example, enable **Per From Zone** toggle. Choose the **OK** button.
    
    You receive a confirmation message with the pick numbers. There are two picks as some items are located in the cross-dock zone, close to shipping area, and it would make sense to process them separately.

9.  Register the warehouse picks
    1. Choose the ![Lightbulb that opens the Tell Me feature 10.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Picks** and choose the related link.
    2. Locate the picks you created and open it.
    3. Choose the **Register Pick** action.
    4. Repeat for the second pick

10. Post the Warehouse Shipment
    
    1. Choose the ![Lightbulb that opens the Tell Me feature 11.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Shipment** and choose the related link.
	2. On the warehouse shipment page, review the **Lines** section. After the warehouse pick is registered, the warehouse shipment will be updated with the **Qty. to Ship** populated.
    3. Choose the **Post Shipment** action.
    4. Confirm the **Ship** option.


## Results
- the **Posted Warehouse Receipt** is created
- the **Registered Warehouse Put-away** is created    
- the **Posted Purchase Receipt** is created    
- the **Purchase Order** has the **Quantity Received** updated for the lines received
- the **Registered Warehouse Movement** is created
- the **Registered Warehouse Pick** is created
- the **Posted Warehouse Shipment** is created
- the **Posted Sales Shipment** is created
- the **Sales Order** has the **Quantity Shipped** updated for the lines shipped
- the item **Inventory** is increased by any remainder not shipped out



## Related information
[Receive Items](../../warehouse-how-receive-items.md) 
[Design Details: Inbound Warehouse Flow](../../design-details-inbound-warehouse-flow.md) 
[Ship Items](../../warehouse-how-ship-items.md) 
[Pick Items for Warehouse Shipment](../../warehouse-how-to-pick-items-for-warehouse-shipment.md) 
[Design Details: Outbound Warehouse Flow](../../design-details-outbound-warehouse-flow.md) 
[View the Availability of Items](../../inventory-how-availability-overview.md) 
