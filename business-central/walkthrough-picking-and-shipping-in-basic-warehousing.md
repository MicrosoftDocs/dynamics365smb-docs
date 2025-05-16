---
title: Picking and Shipping in Basic Warehouse Configurations
description: This article describes various levels of complexity in picking and shipping processes.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 02/27/2023
ms.custom: bap-template
ms.search.form: 7335, 7337, 7339, 7340, 7341, 7362, 9008
ms.service: dynamics-365-business-central
---
# Walkthrough: Picking and Shipping in Basic Warehouse Configurations

In [!INCLUDE[prod_short](includes/prod_short.md)], you pick and ship items using one of four methods, as described in the following table.

|Method|Outbound Process|Require Pick|Require Shipment|Complexity Level (Learn more at [Warehouse Management Overview](design-details-warehouse-management.md))|  
|------|----------------|-----|---------|-------------------------------------------------------------------------------------|  
|A|Post the pick and shipment from the order line|||No dedicated warehouse activity.|  
|B|Post the pick and shipment from an inventory pick document|Turned on||Basic: Order-by-order.|  
|C|Post the pick and shipment from a warehouse shipment document||Turned on|Basic: Consolidated receive/ship posting for multiple orders.|  
|D|Post the pick from a warehouse pick document, and post the shipment from a warehouse shipment document|Turned on|Turned on|Advanced|  

Learn more at [Outbount Warehouse Flow](design-details-outbound-warehouse-flow.md).

The following walkthrough demonstrates method B in the previous table.  

## About This Walkthrough

In basic warehouse configurations where your location is set up to require pick processing but not ship processing, you use the **Inventory Pick** page to record and post pick and ship information for your outbound source documents. The outbound source document can be a sales order, purchase return order, outbound transfer order, or a production order with component need.  

This walkthrough demonstrates the following tasks:  

- Setting up SOUTH location for inventory picks.  
- Creating a sales order for customer 10000 for 30 Amsterdam Lamps.  
- Releasing the sales order for warehouse handling.  
- Creating an inventory pick based on a released source document.  
- Registering the warehouse movement from the warehouse and at the same time posting the sales shipment for the source sales order.  

## Roles

This walkthrough demonstrates tasks that are performed by the following user roles:  

- Warehouse Manager  
- Order Processor  
- Warehouse Worker  

<!-- ## Prerequisites

To complete this walkthrough, you will need:  

- For [!INCLUDE[prod_short](includes/prod_short.md)] online, a company based on the **Advanced Evaluation - Complete Sample Data** option in a sandbox environment. For [!INCLUDE[prod_short](includes/prod_short.md)] on-premises, CRONUS installed.
 -->

## Story

Ellen, the warehouse manager at CRONUS, sets up SOUTH warehouse for basic pick handling where warehouse workers process outbound orders individually. Susan, the order processor, creates a sales order for 30 units of item 1928-S to be shipped to customer 10000 from the SOUTH Warehouse. John, the warehouse worker must make sure that the shipment is prepared and delivered to the customer. John manages all involved tasks on the **Inventory Pick** page, which automatically points to the bins where 1928-S is stored.

[!INCLUDE[set_up_location.md](includes/set_up_location.md)]

### Setting Up the Bin Codes

Once you have the location set up, you must add two bins.

#### To setup the bin codes

1. Select the **Bins** action.
2. Create two bins, with the codes *S-01-0001* and *S-01-0002*.

### Making Yourself a Warehouse Employee at Location SOUTH

In order to use this functionality, you must add yourself to the location as a warehouse worker. 

#### To make yourself a warehouse employee

  1. Choose the ![Lightbulb that opens the Tell Me feature first.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Employees**, and then choose the related link.  
  2. Choose the **User ID** field, and select your own user account on the **Warehouse Employees** page.
  3. In the **Location Code** field, choose SOUTH.  
  4. Select the **Default** field, and then select the **Yes** button.  

### Making Item 1928-S Available

To make item 1928-S available at the SOUTH location follow these steps:  

  1. Choose the ![Lightbulb that opens the Tell Me feature second.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Item Journals**, and then choose the related link.  
  2. Open the default journal, and then create two item journal lines with the following information about the work date (January 23).  

        |Entry Type|Item Number|Location Code|Bin Code|Quantity|  
        |----------------|-----------------|-------------------|--------------|--------------|  
        |Positive Adjmt.|1928-S|SOUTH|S-01-0001|20|  
        |Positive Adjmt.|1928-S|SOUTH|S-01-0002|20|  

        By default, the **Bin Code** field on the sales lines are hidden, so you must display it. To do this you need to personalize the page. For more information, see [To start personalizing a page through the Personalizing banner](ui-personalization-user.md#start-personalizing-by-using-the-personalization-mode).

  3. Choose **Actions**, then **Posting**, and then choose **Post**.  
  4. Select the **Yes** button.  

## Creating the Sales Order

Sales orders are the most common type of outbound source document.  

### To create the sales order

1. Choose the ![Lightbulb that opens the Tell Me feature third.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, and then choose the related link.  
2. Choose the **New** action.  
3. Create a sales order for customer 10000 on the work date (January 23) with the following sales order line.  

    |Item|Location Code|Quantity|  
    |----|-------------|--------|  
    |1928-S|SOUTH|30|  

     Proceed to notify the warehouse that the sales order is ready for warehouse handling.  

4. Choose the **Release** action.  

    John proceeds to pick and ship the sold items.  

## Picking and Shipping Items

On the **Inventory Pick** page, you can manage all outbound warehouse activities for a specific source document, such as a sales order. [!INCLUDE[tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]  

### To pick and ship items

1. Choose the ![Lightbulb that opens the Tell Me feature fourth.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Inventory Picks**, and then choose the related link.  
2. Choose the **New** action.  

    Make sure that the **No.** field on the **General** FastTab is filled in.
3. Select the **Source Document** field, and then select **Sales Order**.  
4. Select the **Source No.** field, select the line for the sale to customer 10000, and then choose the **OK** button.  

    Alternatively, choose the **Get Source Document** action, and then select the sales order.  
5. Choose the **Autofill Qty. to Handle** action.  

    Alternatively, in the **Qty. to Handle** field, enter 10 and 20 respectively on the two inventory pick lines.  
6. Choose the **Post** action, select **Ship**, and then choose the **OK** button.  

    The 30 Amsterdam Lamps are now registered as picked from bins S-01-0001 and S-01-0002, and a negative item ledger entry is created reflecting the posted sales shipment.  

## Related information

[Pick Items with Inventory Picks](warehouse-how-to-pick-items-with-inventory-picks.md)  
[Pick Items for Warehouse Shipment](warehouse-how-to-pick-items-for-warehouse-shipment.md)  
[Set Up Basic Warehouses with Operations Areas](warehouse-how-to-set-up-basic-warehouses-with-operations-areas.md)  
[Pick for Production or Assembly](warehouse-how-to-pick-for-production.md)  
[Move Items Ad Hoc in Basic Warehouse Configurations](warehouse-how-to-move-items-ad-hoc-in-basic-warehousing.md)  
[Design Details: Outbound Warehouse Flow](design-details-outbound-warehouse-flow.md)  
[Business Process Walkthroughs](walkthrough-business-process-walkthroughs.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
