---
title: 'Contoso Coffee: Mixed Warehouse Flow Walkthrough'
description: Practice receiving Contoso Coffee items with warehouse receipts, then picking and shipping combined sales orders in a mixed warehouse configuration.
author: brentholtorf
ms.topic: how-to
ai-usage: ai-assisted
ms.date: 11/12/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Contoso Coffee: Mixed warehouse flow walkthrough

This walkthrough demonstrates how to complete inbound and outbound flows in a mixed configuration, with warehouse receipts for inbound flow and warehouse picks and shipments for outbound flow. Learn more in [Overview of different configuration options](../../design-details-warehouse-management.md#overview-of-different-configuration-options).

## Prerequisites  

Generate the warehouse demo data as described in [Set up Contoso Coffee warehousing data](contoso-coffee-warehousing-intro.md#set-up-contoso-coffee-warehousing-data). This walkthrough uses the default **YELLOW** location, vendor **20000**, customer **10000**, and items **WRB-1000** and **WRB-1001**, with quantities in **PCS**.

To complete this walkthrough, you need to make yourself a warehouse employee at the *YELLOW* location. To do that, follow these steps:  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Warehouse Employees**, and then choose the related link.
1. In the **User ID** field, choose your user account.
1. In the **Location Code** field, enter **YELLOW**.

## Inbound flow: Receiving and putting away with warehouse receipts

In [!INCLUDE[prod_short](../../includes/prod_short.md)], the inbound processes for receiving and putting away can be done in four ways using different functionalities depending on the warehouse complexity level.  

|Method|Inbound process|Bins|Receipts|Put-aways|Complexity level (See [Design Details: Warehouse Setup](../../design-details-warehouse-setup.md))|  
|------------|---------------------|----------|--------------|----------------|--------------------------------------------------------------------------------------------------------------------|  
|A|Post receipt and put-away from the order line|X|||2|  
|B|Post receipt and put-away from an inventory put-away document|||X|3|  
|C|Post receipt and put-away from a warehouse receipt document||X||4/5/6|  
|D|Post receipt from a warehouse receipt document and post put-away from a warehouse put-away document||X|X|4/5/6|  

Learn more in [Design Details: Inbound Warehouse Flow](../../design-details-inbound-warehouse-flow.md).

The following walkthrough demonstrates method C in the previous table.  

### Scenario

Alicia, the purchasing agent, creates purchase orders for various roasted beans as demand appears. When combined delivery arrives at the warehouse, John, the warehouse worker, receives the items and puts them away. When John posts the receipt, the items are posted as received into inventory and are available for sale or other demand.  

### Steps

1. Set up the **Location Card** page to define the company's inbound warehouse flows.  

    1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Locations**, and then choose the related link.
    1. Open the **YELLOW** location.
    1. Turn off the **Require Put-away** toggle.

1. Release purchase orders to the warehouse.

    1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Purchase Orders**, and then choose the related link.
    1. Select orders from vendor 20000 for the YELLOW location. The vendor order numbers are *Y-1* and *Y-2*. Use the personalization tools if the **Vendor Order No.** field isn't visible. Learn more in [Personalize Your Workspace](../../ui-personalization-user.md).
    1. Choose the **Release** action to notify the warehouse that the selected purchase orders are ready for warehouse handling when the delivery arrives.

1. Create the warehouse receipt to receive the delivered items and put them away.

    1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Warehouse Receipts**, and then choose the related link.
    1. Choose the **New** action.
    1. On the warehouse receipt page, press Enter to have a warehouse receipt number automatically selected.
    1. Enter the **Location Code** as **YELLOW**.
    1. Choose the **Get Source Documents...** action.
    1. Select released purchase orders from vendor 20000, and choose the **OK** button.
	    
        The lines have a new entry for each purchase order line.

1. Adjust the quantity to receive based on the received quantity and then post the document.

    1. Select the line with item **WRB-1000**.
    1. In the **Over-Receipt Code** field, choose **OVERRCPT10**, and then change the value in the **Quantity to Receive** field from **100** to **110**.
    1. Select line with item **WRB-1001**.
    1. On the second line, change the value in the **Quantity to Receive** field from **100** to **90**.
    1. Choose the **Post Receipt** action.

### Results

- The roasted beans are now registered as put away.
- The **Posted Warehouse Receipt** is created.
- The **Posted Purchase Receipt** is created.
- The purchase order has the **Quantity Received** updated for the lines received.
- The item **Inventory** is increased by the chosen quantity.

## Outbound flow: Picking and shipping in advanced warehouse configurations

In [!INCLUDE[prod_short](../../includes/prod_short.md)], the outbound processes for picking and shipping can be done in four ways using different functionalities depending on the warehouse complexity level.  

|Method|Outbound process|Bins|Picks|Shipments|Complexity level (See [Design Details: Warehouse Setup](../../design-details-warehouse-setup.md))|
|------------|---------------------|----------|-----------|---------------|--------------------------------------------------------------------------------------------------------------------|  
|A|Post pick and shipment from the order line|X|||2|  
|B|Post pick and shipment from an inventory pick document||X||3|  
|C|Post pick and shipment from a warehouse shipment document|||X|4/5/6|  
|D|Post pick from a warehouse pick document and post shipment from a warehouse shipment document||X|X|4/5/6|  

Learn more in [Design Details: Outbound Warehouse Flow](../../design-details-outbound-warehouse-flow.md).

The following walkthrough demonstrates method D in the previous table.

### Scenario

Susan, the order processor, creates sales orders for various roasted beans and releases the orders to the warehouse. Because the orders are for the same customer, Ellen, the warehouse manager decides to ship them together. John, the warehouse worker, must make sure that the shipment is prepared and delivered to the customer.

### Steps

These steps are a continuation of [Inbound flow: Receiving and putting away with warehouse receipts](#inbound-flow-receiving-and-putting-away-with-warehouse-receipts).

1. Release sales orders to the warehouse.  

    1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Sales Orders**, and then choose the related link.
    1. Select orders for customer **10000** for the **YELLOW** location. The **External Document No.** values are **Y-3**, **Y-4**, and **Y-5**.
    1. Choose the **Release** action to notify the warehouse that the selected sales orders are ready.

1. Ship the items.

    1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Warehouse Shipments**, and then choose the related link.
    1. Choose the **New** action.
    1. In the **Location Code** field, enter **YELLOW**.
    1. Choose the **Use Filters to Get Src. Docs.** action.
    1. In the **Code** field, enter **CUST10000**.
    1. In the **Description** field, enter **Customer 10000**.
    1. Choose the **Modify** action.
    1. On the **Sales** FastTab, in the **Sell-to Customer No. Filter** field, enter **10000**.
    1. Choose the **Run** action.

    The warehouse shipment has four lines that represent sales order lines for the customer. The **Qty. to Ship** field is empty because warehouse workers need to pick the items.

1. Create the warehouse pick from the warehouse shipment.

    1. On the **Warehouse Shipment** page, choose the **Create Pick** action.
    1. Confirm any of the pick settings needed, for example, select **Item** in the **Sorting Method for Activity Line** field to group same items together. Choose the **OK** button.

    A confirmation message displays the pick number.

1. Open the warehouse pick.

    1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Warehouse Picks**, and then choose the related link.
    1. Find the pick you created and open it.
    1. Update the **Qty. to Handle** field, if needed.
    1. Choose the **Register Pick** action.
    1. The warehouse pick closes and is removed if all the quantities are handled.

1. Post the warehouse shipment.

   1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Warehouse Shipments**, and then choose the related link.
   1. Find the shipment you created earlier and open it. Notice that the **Qty. to Ship** field is filled in.
   1. Optionally, you can update the **Posting Date**, **External Document No.**, **Shipping Agent Code**, **Shipping Method** fields. The values transfer to the source documents.
   1. Choose the **Post Shipment** action.
   1. Confirm the **Ship** option.

### Results

- The roasted beans are registered as picked.
- A registered warehouse pick is created.
- A posted warehouse shipment is created.
- Three posted sales shipments are created.
- The **Quantity Shipped** field on the sales order is updated for the lines shipped.
- The inventory for the item decreased by the chosen quantity.

## Related information

[Receive Items](../../warehouse-how-receive-items.md)  
[Set Up Basic Warehouses with Operations Areas](../../warehouse-how-to-set-up-basic-warehouses-with-operations-areas.md)  
[Design Details: Inbound Warehouse Flow](../../design-details-inbound-warehouse-flow.md)  
[Ship Items](../../warehouse-how-ship-items.md)  
[Pick Items for Warehouse Shipment](../../warehouse-how-to-pick-items-for-warehouse-shipment.md)  
[Design Details: Outbound Warehouse Flow](../../design-details-outbound-warehouse-flow.md)  
[View the Availability of Items](../../inventory-how-availability-overview.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
