---
title: Walkthrough - Receive and put away in basic warehouse configurations
description: Learn about the different ways to handle inbound processes for receiving and putting away.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.date: 02/27/2023
ms.custom: bap-template
ms.service: dynamics-365-business-central
---
# Walkthrough: Receiving and Putting Away in Basic Warehouse Configurations

In [!INCLUDE[prod_short](includes/prod_short.md)], you receive items and put them away using one of four methods, as described in the following table.

|Method|Inbound Process|Require Receipts|Require Put-aways|Complexity Level (Learn more at [Warehouse Management Overview](design-details-warehouse-management.md))|  
|------------|---------------------|--------------|----------------|------------|  
|A|Post receipt and put-away from the order line|||No dedicated warehouse activity.|  
|B|Post receipt and put-away from an inventory put-away document||Turned on|Basic: Order-by-order.|  
|C|Post receipt and put-away from a warehouse receipt document|Turned on||Basic: Consolidated receive/ship posting for multiple orders.|  
|D|Post receipt from a warehouse receipt document and post put-away from a warehouse put-away document|Turned on|Turned on|Advanced|  

Learn more at [Inbound Warehouse Flow](design-details-inbound-warehouse-flow.md).

The following walkthrough demonstrates method B in the previous table.  

## About this walkthrough  

In basic warehouse configurations where your location is set up to require put-away processing but not receive processing, use the **Inventory Put-away** page to record and post put-away and receipt information for your inbound source documents. The following documents are inbound source documents:

* Purchase order
* Sales return order
* Inbound transfer order
* Production order with output that's ready to be put away

> [!NOTE]
> Even though the settings are called **Require Pick** and **Require Put-away**, you can still post receipts and shipments directly from the source business documents at locations where you select these checkboxes.  

This walkthrough demonstrates the following tasks:  

* Set up SILVER location for inventory put aways.  
* Set up SILVER location for bin handling.  
* Define a default bin for item LS-81. (LS-75 is already set up in CRONUS.)  
* Create a purchase order for vendor 10000 for 40 loudspeakers.  
* Verify that the put-away bins are preset by setup.  
* Release the purchase order for warehouse handling.  
* Create an inventory put-away based on a released source document.  
* Verify that the put-away bins are inherited from the purchase order.  
* Register the warehouse movement into the warehouse and post the purchase receipt for the source purchase order.  

> [!NOTE]
> [!INCLUDE [locations-cronus](includes/locations-cronus.md)]

## Roles  

The following user roles perform the tasks that this walkthrough demonstrates:  

* Warehouse Manager  
* Purchasing Agent  
* Warehouse Worker  

## Prerequisites  

To complete this walkthrough, you'll need:  

* CRONUS International Ltd. data  
* To be a warehouse employee at SILVER location. To set yourself up, follow these steps:  

    1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Employees**, and then choose the related link.  
    2. Choose the **User ID** field, and select your user account on the **Users** page.  
    3. In the **Location Code** field, choose **SILVER**.  
    4. Select the **Default** checkbox.  

## Story  

Ellen, the warehouse manager at CRONUS International Ltd., creates a purchase order for 10 units of item LS-75 and 30 units of item LS-81 from vendor 10000 to be delivered to SILVER Warehouse. When the delivery arrives at the warehouse, John, the warehouse worker, puts the items away in the default bins defined for the items. When John posts the put-away, the items are posted as received into inventory and available for sale or other demand.  

## Setting up the location  

Settings on the **Location Card** page define the company's warehouse flows.  

### To set up the location  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Locations**, and then choose the related link.  
2. Open the SILVER location card.  
3. Turn on the **Require Put-away** toggle.  

    Set up a default bin for the two item numbers to control where they're put away.  

4. Choose the **Bins** action.  
5. Select the first row, for bin **S-01-0001**, and then choose the **Contents** action.  

    Notice on the **Bin Content** page that item **LS-75** is already set up as content in bin S-01-0001.  

6. Choose the **New** action.  
7. Select the **Fixed** and the **Default** fields.  
8. In the **Item No.** field, enter **LS-81**.  

## Create the purchase order  

Purchase orders are the most common type of inbound source document.  

### To create the purchase order  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders**, and then choose the related link.  
2. Choose the **New** action.  
3. Create a purchase order for vendor 10000 on the work date (January 23) with the following purchase order lines.  

    |Item|Location code|Bin code|Quantity|  
    |----------|-------------------|--------------|--------------|  
    |LS_75|SILVER|S-01-0001|10|  
    |LS-81|SILVER|S-01-0001|30|  

    > [!NOTE]  
    > The bin code is entered automatically according to the setup you created in the [Setting up the location](#setting-up-the-location) section.  

    Next, notify the warehouse that the purchase order is ready for warehouse handling when the delivery arrives.  

4. Choose the **Release** action.  

    The delivery of loudspeakers from vendor 10000 has arrived at SILVER warehouse, and John proceeds to put them away.  

## Receive and put the items away  

Use the **Inventory Put-away** page to manage all inbound warehouse activities for a specific source document, such as a purchase order.  

### To receive and put the items away  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Inventory Put-aways**, and then choose the related link.  
2. Choose the **New** action.  
3. Select the **Source Document** field, and then select **Purchase Order**.  
4. Select the **Source No.** field, select the line for the purchase from vendor 10000, and then choose the **OK** button.  

    Alternatively, choose the **Get Source Document** action, and then select the purchase order.  

5. Choose the **Autofill Qty. to Handle** action.  

    Alternatively, in the **Qty. to Handle** field, enter 10 and 30 respectively on the two inventory put-away lines.  

6. Choose the **Post** action, select the **Receive** action, and then choose the **OK** button.  

    The 40 loudspeakers are now registered as put away in bin S-01-0001, and a positive item ledger entry is created reflecting the posted purchase receipt.  

## Related information  

[Put Items Away with Inventory Put-aways](warehouse-how-to-put-items-away-with-inventory-put-aways.md)  
[Set Up Basic Warehouses with Operations Areas](warehouse-how-to-set-up-basic-warehouses-with-operations-areas.md)  
[Pick for Production or Assembly](warehouse-how-to-pick-for-production.md)  
[Move Items Ad Hoc in Basic Warehouse Configurations](warehouse-how-to-move-items-ad-hoc-in-basic-warehousing.md)  
[Design Details: Inbound Warehouse Flow](design-details-inbound-warehouse-flow.md)  
[Business Process Walkthroughs](walkthrough-business-process-walkthroughs.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
