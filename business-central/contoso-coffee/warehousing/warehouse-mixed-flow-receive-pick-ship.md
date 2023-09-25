---
title: Receiving, Puting-away, Picking and Shipping in Mixed Warehouse Configuration
description: In Business Central, the inbound and outbound processes can be performed in different ways depending on the warehouse complexity level. 
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.search.form: 
ms.date: 04/01/2021
ms.author: bholtorf
---

# Walkthrough of inbound and outbound flow in mixed Warehouse Configurations

This walkthrough demonstrates how to complete inbound and outbound flows in mixed configuration, where for inbound flow warehouse is configured as Basic: Order-by-Order and for outbound flow Advanced configuration is used. For more information, see [Overview of different configuration options](../../design-details-warehouse-management.md#overview-of-different-configuration-options).

## Prerequisites  
To complete this walkthrough, you need to make yourself a warehouse employee at *YELLOW* location by following these steps:  
1. Choose the ![Lightbulb that opens the Tell Me feature 1.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Employees**, and then choose the related link.  
2. Choose the **User ID** field, and select your own user account on the **Users** page.  
3. In the **Location Code** field, enter *YELLOW*.  

## Inbound flow: Receiving and Putting Away in Basic Warehouse Configurations

In [!INCLUDE[prod_short](../../includes/prod_short.md)], the inbound processes for receiving and putting away can be performed in four ways using different functionalities depending on the warehouse complexity level.  

|Method|Inbound process|Bins|Receipts|Put-aways|Complexity level (See [Design Details: Warehouse Setup](../../design-details-warehouse-setup.md))|  
|------------|---------------------|----------|--------------|----------------|--------------------------------------------------------------------------------------------------------------------|  
|A|Post receipt and put-away from the order line|X|||2|  
|B|Post receipt and put-away from an inventory put-away document|||X|3|  
|C|Post receipt and put-away from a warehouse receipt document||X||4/5/6|  
|D|Post receipt from a warehouse receipt document and post put-away from a warehouse put-away document||X|X|4/5/6|  

For more information, see [Design Details: Inbound Warehouse Flow](../../design-details-inbound-warehouse-flow.md).  

The following walkthrough demonstrates method C in the previous table.  

### Scenario  
Alicia, the purchasing agent, creates purchase orders for various roasted beans as demand appears. When combined delivery arrives at the warehouse, John, the warehouse worker, receives and puts the items away. When John posts the receipt, the items are posted as received into inventory and available for sale or other demand.  

### Steps
1. Set up the **Location Card** page to define the company's inbound warehouse flows.  

    1.  Choose the ![Lightbulb that opens the Tell Me feature 2.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Locations**, and then choose the related link.  
    2.  Open the *YELLOW* location card.  
    3.  Disable the **Require Put-away** toggle.  

2. Release Purchase Orders to warehouse.  

    1. Choose the ![Lightbulb that opens the Tell Me feature 3.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders**, and then choose the related link.  
    2. Select orders from vendor 10000 for the YELLOW location. Vendor Orders No are *Y-1* and *Y-2*. Use the personalization tools if the **Vendor Order No.** field isn't visible. For more information, see [Personalize Your Workspace](../../ui-personalization-user.md).
    3. Choose the **Release** action to notify the warehouse that the selected purchase orders are ready for warehouse handling when the delivery arrives.  

3. Create the Warehouse Receipt to receive and put the delivered items away
	1. Choose the ![Lightbulb that opens the Tell Me feature 4.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Receipts** and choose the related link.
	2. Choose the **New** action
	3. On the warehouse receipt page, press Enter to have a warehouse receipt number automatically selected
	4. Enter the **Location Code** as *YELLOW*.
	5. Choose the **Get Source Documents...** action
	6. Select previously released purchase orders from vendor 10000 and choose the **OK** button.
	    The lines will contain a new entry for each purchase order line.

4. Adjust quantity to receipt based on received quantity and post document
    1. Select line with item *WRB-1000*.
    2. Select *OVERRCPT10* in the **Over-Receipt Code** field and change value in the **Quantity to Receive** field from *100* to *110*.
    3. Select line with item *WRB-1001* and 
    4. In the second line,  change value in the **Quantity to Receive** field from *200* to *190*.
    5. Choose the **Post Receipt** action.

### Results 
 - the roasted beans are now registered as put away
 - the **Posted Warehouse Receipt** is created
 - the **Posted Purchase Receipt** is created
 - the purchase order has the **Quantity Received** updated for the lines received
 - the item **Inventory** is increased by the chosen quantity
    

## Outbound flow: Picking and Shipping in Advanced Warehouse Configurations

In [!INCLUDE[prod_short](../../includes/prod_short.md)], the outbound processes for picking and shipping can be performed in four ways using different functionalities depending on the warehouse complexity level.  

|Method|Inbound process|Bins|Picks|Shipments|Complexity level (See [Design Details: Warehouse Setup](../../design-details-warehouse-setup.md))|  
|------------|---------------------|----------|-----------|---------------|--------------------------------------------------------------------------------------------------------------------|  
|A|Post pick and shipment from the order line|X|||2|  
|B|Post pick and shipment from an inventory pick document||X||3|  
|C|Post pick and shipment from a warehouse shipment document|||X|4/5/6|  
|D|Post pick from a warehouse pick document and post shipment from a warehouse shipment document||X|X|4/5/6|  

For more information, see [Design Details: Outbound Warehouse Flow](../../design-details-outbound-warehouse-flow.md).  

The following walkthrough demonstrates method D in the previous table.

### Scenario  
Susan, the order processor, creates sales orders for various roasted beans and passes it to warehouse. As all of orders are coming from the same customer, Ellen, the warehouse manager decides to ship them together. John, the warehouse worker must make sure that the shipment is prepared and delivered to the customer.

### Steps
This is a continuation of [Inbound flow: Receiving and Putting Away in Basic Warehouse Configurations](#inbound-flow-receiving-and-putting-away-in-basic-warehouse-configurations).

1. Release Sales Orders to warehouse.  

    1. Choose the ![Lightbulb that opens the Tell Me feature 5.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, and then choose the related link.  
    2. Select orders for customer 10000 for the YELLOW location. External Orders No are *Y-3*, *Y-4*, and *Y-5*.
    3. Choose the **Release** action to notify the warehouse that the selected sales orders are ready for warehouse handling.  

2. To ship items  
    1. Choose the ![Lightbulb that opens the Tell Me feature 6.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Shipments**, and then choose the related link.  
    2. Choose the **New** action.  
    3. In the **Location Code** field, enter *YELLOW*.  
    4. Choose the **Use Filters to Get Src. Docs.** action.  
    5. In the **Code** field, enter **CUST10000**.  
    6. In the **Description** field, enter **Customer 10000**.  
    7. Choose the **Modify** action.  
    8. On the **Sales** FastTab, in the **Sell-to Customer No. Filter** field, enter *10000*.  
    9. Choose the **Run** action. 
    
    The warehouse shipment is filled with four lines representing sales order lines for the specified customer. The **Qty. to Ship** field is empty, as items needs to be picked first.

3. Create the Warehouse Pick from the warehouse shipment
    1. On the warehouse shipment page, choose the **Create Pick** action.
	2. Confirm any of the pick settings needed, for example, select *Item* in the **Sorting Method for Activity Line** field to group same items together. Choose the **OK** button.
	3. You'll receive a confirmation message with the pick number. 

4. Open the warehouse pick
	1. Using the ![Lightbulb that opens the Tell Me feature 7.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Picks** and choose the related link.
	2. Locate the pick you created and open it.
	3. Update the **Qty. to Handle** if necessary.
	4. Choose the **Register Pick** action.
	5. The warehouse pick will close and be removed if all the quantities are handled.

5. Post the Warehouse Shipment
   1. Choose the ![Lightbulb that opens the Tell Me feature 8.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Shipments**, and then choose the related link.  
   2. Locate the shipment you created earlier and open it.
    Notice that **Qty. to Ship** populated.
    3. You can update **Posting Date**, **External Document No.**, **Shipping Agent Code**, **Shipping Method** if needed. Non-empty values will be propagated to source documents.
    4. Choose the **Post Shipment** action.
    5. Confirm the **Ship** option.

### Results
 - the roasted beans are now registered as picked 
 - the **Registered Warehouse Pick** is created
 - the **Posted Warehouse Shipment** is created
 - the three **Posted Sales Shipment** are created
 - the sales order has the **Quantity Shipped** updated for the lines shipped
 - the item **Inventory** is decreased by the chosen quantity


## See Also
[Receive Items](../../warehouse-how-receive-items.md)
[Set Up Basic Warehouses with Operations Areas](../../warehouse-how-to-set-up-basic-warehouses-with-operations-areas.md)
[Design Details: Inbound Warehouse Flow](../../design-details-inbound-warehouse-flow.md)
[Ship Items](../../warehouse-how-ship-items.md)
[Pick Items for Warehouse Shipment](../../warehouse-how-to-pick-items-for-warehouse-shipment.md)
[Design Details: Outbound Warehouse Flow](../../design-details-outbound-warehouse-flow.md)
[View the Availability of Items](../../inventory-how-availability-overview.md)
