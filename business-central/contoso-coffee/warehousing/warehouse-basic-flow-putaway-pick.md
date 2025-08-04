---
title: Receiving, Puting-away, Picking and Shipping in Basic Warehouse Configuration
description: In Business Central, the inbound and outbound processes can be performed in different ways depending on the warehouse complexity level.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords:
ms.search.form: 
ms.date: 02/23/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Walkthrough of inbound and outbound flow in Basic Warehouse Configurations

This walkthrough demonstrates how to complete inbound and outbound flows in the Basic: Order-by-Order configuration. For more information, see [Overview of different configuration options](../../design-details-warehouse-management.md#overview-of-different-configuration-options).

## Prerequisites  
To complete this walkthrough, you need to make yourself a warehouse employee at *SILVER* location by following these steps:  
1. Choose the ![Lightbulb that opens the Tell Me feature 1.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Employees**, and then choose the related link.  
2. Choose the **User ID** field, and select your own user account on the **Users** page.  
3. In the **Location Code** field, enter *SILVER*.  

## Inbound flow: Receiving and Putting Away in Basic Warehouse Configurations

In [!INCLUDE[prod_short](../../includes/prod_short.md)], the inbound processes for receiving and putting away can be performed in four ways using different functionalities depending on the warehouse complexity level.  

|Method|Inbound process|Bins|Receipts|Put-aways|Complexity level (See [Design Details: Warehouse Setup](../../design-details-warehouse-setup.md))|  
|------------|---------------------|----------|--------------|----------------|--------------------------------------------------------------------------------------------------------------------|  
|A|Post receipt and put-away from the order line|X|||2|  
|B|Post receipt and put-away from an inventory put-away document|||X|3|  
|C|Post receipt and put-away from a warehouse receipt document||X||4/5/6|  
|D|Post receipt from a warehouse receipt document and post put-away from a warehouse put-away document||X|X|4/5/6|  

For more information, see [Design Details: Inbound Warehouse Flow](../../design-details-inbound-warehouse-flow.md).  

The following walkthrough demonstrates method B in the previous table.  

### Scenario  
Alicia, the purchasing agent, creates a purchase order for various roasted beans. When the delivery arrives at the warehouse, John, the warehouse worker, puts the items away in suited bins. When John posts the put-away, the items are posted as received into inventory and available for sale or other demand.  

### Steps
1. Set up the **Location Card** page to define the company's inbound warehouse flows.  

    1.  Choose the ![Lightbulb that opens the Tell Me feature 2.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Locations**, and then choose the related link.  
    2.  Open the *SILVER* location card.  
    3.  Select the **Require Put-away** check box.  

2. Define a default bin for the item to control where it is put-away

    1.  Choose the **Bins** action in the **Location Card**
    2.  Select the first row, for bin *S-1-01*, and then choose the **Contents** action.  
    3.  Choose the **New** action.  
    4.  Select the **Fixed** and the **Default** fields.  
    5.  In the **Item No.** field, enter *WRB-1000*.  

3. Create the Purchase Order, which is the most common type of inbound source document.  

    1.  Choose the ![Lightbulb that opens the Tell Me feature 3.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders**, and then choose the related link.  
    2.  Choose the **New** action.  
    3.  Create a purchase order for vendor 10000 with the following purchase order lines. Use the personalization tools if the **Bin Code** field isn't visible. For more information, see [Personalize Your Workspace](../../ui-personalization-user.md). 

    |Item|Location code|Bin Code|Quantity|  
    |----------|----------|---------|--------------|  
    |WRB-1000|SILVER|S-1-01|20|  
    |WRB-1001|SILVER||30|

    The bin code in the first is filled accordingly to setup. The bin code for the second item is empty as it doesn't have default values. Keep it this way.  

    4.  Choose the **Release** action to notify the warehouse that the purchase order is ready for warehouse handling when the delivery arrives.  

4. Create **Inventory Put-away** to receive and put the delivered items away  

    1. Choose the ![Lightbulb that opens the Tell Me feature 4.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Inventory Put-aways**, and then choose the related link.  
    2. Choose the **New** action. 
    3. Select *SILVER* in the **Location Code** field.
    4. Select the **Source Document** field, and then select **Purchase Order**.  
    5. Select the **Source No.** field, select the line for the purchase from vendor 10000, and then choose the **OK** button to fill the put-away lines according to the selected source document.

        Alternatively, choose the **Get Source Document** action, and then select the purchase order.  

5. Modify the inventory put-away based on actual placing of items and post document

    When putting items to bins, John noticed default bin already contains some items, so he decided to use another bin. John also places other items to the next bins, as received quantity don't fit the capacity.

    1. In the first line change **Bin Code** from *S-1-01*, that was copied from the purchase order, to *S-1-02*. 
    2.  Enter 20 in the **Qty. to Handle** field on the inventory put-away line with item WRB-1000.  
    3. In the second line, enter 20 into the **Qty to Handle** field and choose **Split Line** action. A new line appears, which is a copy of the original line, except that the **Qty. to Handle** field contains the quantity that you removed from the original line. 
    4. Fill in bins codes for item WRB-1001:

    |Item|Bin code|Quantity|  
    |----------|-------------------|--------------|  
    |WRB-1001|S-1-03|20|  
    |WRB-1001|S-1-04|10|

    5.  Choose the **Post** action, select the **Receive** action, and then choose the **OK** button.  

### Results 
 - the roasted beans are now registered as put away in specified bins
 - the **Posted Invt. Put-Away** is  created
 - the **Posted Purchase Receipt** is created
 - the purchase order has the **Quantity Received** updated for the lines received
 - the item **Inventory** is increased by the chosen quantity
    

## Outbound flow: Picking and Shipping in Basic Warehouse Configurations

In [!INCLUDE[prod_short](../../includes/prod_short.md)], the outbound processes for picking and shipping can be performed in four ways using different functionalities depending on the warehouse complexity level.  

|Method|Inbound process|Bins|Picks|Shipments|Complexity level (See [Design Details: Warehouse Setup](../../design-details-warehouse-setup.md))|  
|------------|---------------------|----------|-----------|---------------|--------------------------------------------------------------------------------------------------------------------|  
|A|Post pick and shipment from the order line|X|||2|  
|B|Post pick and shipment from an inventory pick document||X||3|  
|C|Post pick and shipment from a warehouse shipment document|||X|4/5/6|  
|D|Post pick from a warehouse pick document and post shipment from a warehouse shipment document||X|X|4/5/6|  

For more information, see [Design Details: Outbound Warehouse Flow](../../design-details-outbound-warehouse-flow.md).  

The following walkthrough demonstrates method B in the previous table.

### Scenario  
Susan, the order processor, creates a sales order for various roasted beans and passes it to warehouse. John, the warehouse worker must make sure that the shipment is prepared and delivered to the customer. John manages all involved tasks on the **Inventory Pick** page, which automatically points to the bins where roasted beans are stored.

### Steps
This is a continuation of [Inbound flow: Receiving and Putting Away in Basic Warehouse Configurations](#inbound-flow-receiving-and-putting-away-in-basic-warehouse-configurations).

1. Set up the **Location Card** page to define the company's inbound warehouse flows.  

    1.  Choose the ![Lightbulb that opens the Tell Me feature 5.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Locations**, and then choose the related link.  
    2.  Open the *SILVER* location card.  
    3.  Select the **Require Pick** check box.  

2. Create the Sales Order, which is the most common type of outbound source document.  

    1. Choose the ![Lightbulb that opens the Tell Me feature 6.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, and then choose the related link.  
    2. Choose the **New** action.  
    3. Create a sales order for customer 10000 with the following sales order line.  

    |Item|Location Code|Quantity|  
    |----|-------------|--------|  
    |WRB-1000|SILVER|20|  
    |WRB-1001|SILVER|30|  

    The bin codes are populated automatically with default bins.

    4. Choose the **Create Inventory Put-away/Pick** action.
    5. Select the **Create Invt. Pick** check box.  
    6. Choose the **OK** button. A new inventory pick will be created.

3. Pick and ship items

    1. Choose the ![Lightbulb that opens the Tell Me feature 7.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Inventory Picks**, and then choose the related link.  
    2. Select the inventory pick for the sales to customer 10000
    
    The created inventory pick ignored bin defined for the item *WRB-1000*, as it doesn't contain inventory and used another bin. The second lines, with item *WRB-1001* was automatically split to pick from several bins.
    
4. Choose the **Autofill Qty. to Handle** action.  

5. Choose the **Post** action, select **Ship**, and then choose the **OK** button.  

### Results
 - the roasted beans are now registered as picked from specified bins
 - the **Posted Invt. Pick** is created
 - the **Posted Sales Shipment** is created
 - the sales order has the **Quantity Shipped** updated for the lines shipped
 - the item **Inventory** is decreased by the chosen quantity


## Related information
[Put-Away Items with Inventory Put-Aways](../../warehouse-how-to-put-items-away-with-inventory-put-aways.md) 
[Set Up Basic Warehouses with Operations Areas](../../warehouse-how-to-set-up-basic-warehouses-with-operations-areas.md) 
[Design Details: Inbound Warehouse Flow](../../design-details-inbound-warehouse-flow.md) 
[Pick Items with Inventory Picks](../../warehouse-how-to-pick-items-with-inventory-picks.md) 
[Design Details: Outbound Warehouse Flow](../../design-details-outbound-warehouse-flow.md) 
[View the Availability of Items](../../inventory-how-availability-overview.md) 
