---
title: Receiving and Putting Away in Advanced Warehousing
description: The inbound processes for receiving and putting away can be performed in four ways using different functionalities depending on the warehouse complexity level.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords:
ms.date: 06/24/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Walkthrough: Receiving and Putting Away in Advanced Warehouse Configurations

<!-- [!INCLUDE[complete_sample_data](includes/complete_sample_data.md)]   -->

In [!INCLUDE[prod_short](includes/prod_short.md)], receiving and putting away occurs using one of four methods, as described in the following table.

|Method|Inbound Process|Require Receipts|Require Put-aways|Complexity Level (Learn more at [Warehouse Management Overview](design-details-warehouse-management.md))|  
|------------|---------------------|--------------|----------------|------------|  
|A|Post receipt and put-away from the order line|||No dedicated warehouse activity.|  
|B|Post receipt and put-away from an inventory put-away document||Turned on|Basic: Order-by-order.|  
|C|Post receipt and put-away from a warehouse receipt document|Turned on||Basic: Consolidated receive/ship posting for multiple orders.|  
|D|Post receipt from a warehouse receipt document and post put-away from a warehouse put-away document|Turned on|Turned on|Advanced|  

Learn more at [Inbound Warehouse Flow](design-details-inbound-warehouse-flow.md).

The following walkthrough demonstrates method D in the previous table.  

## About This Walkthrough

In advanced warehouse configurations where your location is set up to require receiving processing in addition to put-away processing, you use the **Warehouse Receipt** page to record and post the receipt of items on multiple inbound orders. When the warehouse receipt is posted, one or more warehouse put-away documents are created to instruct warehouse workers to take the received items and place them in designated places according to bin setup or in other bins. The specific placement of the items is recorded when the warehouse put-away is registered. The inbound source document can be a purchase order, sales return order, inbound transfer order, or assembly or production order with output that is ready to be put away. If the receipt is created from an inbound order, more than one inbound source document can be retrieved for the receipt. By using this method you can register many items arriving from different inbound orders with one receipt.  

This walkthrough demonstrates the following tasks:  

-   Setting up WHITE location for receiving and putting away.  
-   Creating and releasing two purchase orders for full warehouse handling.  
-   Creating and posting a warehouse receipt document for multiple purchase order lines from specific vendors.  
-   Registering a warehouse put-away for the received items.  

## Roles

This walkthrough demonstrates tasks that are performed by the following user roles:  

-   Warehouse Manager  
-   Purchasing Agent  
-   Receiving Staff  
-   Warehouse Worker  

## Prerequisites

To complete this walkthrough, you will need:  

-   CRONUS installed.  
-   To make yourself a warehouse employee at WHITE location by following these steps:  

1.  Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Employees**, and then choose the related link.  
2.  Choose the **User ID** field, and select your own user account on the **Users** page.  
3.  In the **Location Code** field, enter WHITE.  
4.  Select the **Default** field.  

## Story

Ellen, the warehouse manager at CRONUS, creates two purchase orders for accessory items from vendors 10000 and 20000 to be delivered to WHITE warehouse. When the deliveries arrive at the warehouse, Sammy, who is responsible for receiving items from vendors 10000 and 20000, uses a filter to create receipt lines for purchase orders arriving from the two vendors. Sammy posts the items as received into inventory in one warehouse receipt and makes the items available for sale or other demand. John, the warehouse worker, takes the items from the receiving bin and puts them away. John puts all units away in their default bins, except 40 out of 100 received hinges are put away in the assembly department by splitting the put-away line. When John registers the put-away, the bin contents are updated and the items are made available for picking from the warehouse.  

## Reviewing the WHITE Location Setup

The setup of the **Location Card** page defines the company's warehouse flows.  

### To review the location setup  

1.  Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Locations**, and then choose the related link.  
2.  Open the WHITE location card.  
3.  Note on the **Warehouse** FastTab that the **Directed Put-away and Pick** check box is selected.  

    This means that the location is set up for the highest complexity level, reflected by the fact that all warehouse handling check boxes on the FastTab are selected.  

4.  Note on the **Bins** FastTab that bins are specified in the **Receipt Bin Code** and the **Shipment Bin Code** fields.  

This means that when you create a warehouse receipt, this bin code is copied to the header of the warehouse receipt document by default and to the lines of the resulting warehouse put-aways.  

## Creating the Purchase Orders

Purchase orders are the most common type of inbound source document.  

### To create the purchase orders  

1.  Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders**, and then choose the related link.  
2.  Choose the **New** action.  
3.  Create a purchase order for vendor 10000 on the work date (January 23) with the following purchase order lines.  

    |Item|Location code|Quantity|  
    |----------|-------------------|--------------|  
    |70200|WHITE|100 PCS|  
    |70201|WHITE|50 PCS|  

    Proceed to notify the warehouse that the purchase order is ready for warehouse handling when the delivery arrives.  

4.  Choose the **Release** action. The status changes from Open to Released.

    Proceed to create the second purchase order.  

5.  Choose the **New** action.  
6.  Create a purchase order for vendor 20000 on the work date (January 23) with the following purchase order lines.  

    |Item|Location code|Quantity|  
    |----------|-------------------|--------------|  
    |70100|WHITE|10 CAN|  
    |70101|WHITE|12 CAN|  

    Choose the **Release** action. The status changes from Open to Released.

    The deliveries of items from vendors 10000 and 20000 have arrived at WHITE warehouse, and Sammy starts to process the purchase receipts.  

## Receiving the Items

On the **Warehouse Receipt** page, you can manage multiple inbound orders for source documents, such as a purchase order.  

### To receive the items  
1.  Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Receipts**, and then choose the related link.  
2.  Choose the **New** action.  
3.  In the **Location Code** field, enter WHITE.  
4.  Select **Actions** then **Functions** then choose the **Use Filters to Get Src. Docs.** action.  
5.  In the **Code** field, enter **ACCESSORY**.  
6.  In the **Description** field, enter **Vendors 10000 and 20000**.  
7.  Choose the **Modify** action.  
8.  On the **Purchase** FastTab, in the **Buy-from Vendor No. Filter** field, enter **10000&#124;20000**.  
9. Choose the **Run** action. The warehouse receipt is filled with four lines representing purchase order lines for the specified vendors. The **Qty. to Receive** field is filled because you did not select the **Do not Fill Qty. to Handle** check box on the **Filters to Get Source Docs.** page.  
10. Optionally, if you want to use a filter as described earlier in this section, choose the **Get Source Document** action, and then select purchase orders from the vendors in question.  
11. Choose **Posting** then the **Post Receipt** action, and then choose the **Yes** button.  

    Positive item ledger entries are created reflecting the posted purchase receipts of accessories from vendors 10000 and 20000, and the items are ready to be put away in the warehouse from the receiving bin.  

## Putting the Items Away

On the **Warehouse Put-away** page, you can manage put-aways for a specific warehouse receipt document covering multiple source documents. Like all warehouse activity documents, each item on the warehouse put-away is represented by a Take line and a Place line. In the following procedure, the bin code on the Take lines is the default receiving bin at WHITE location, W-08-0001.  


### To put the items away  
1.  Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Put-Aways**, and then choose the related link.  
2.  Select the only warehouse put-away document in the list, and then choose the **Edit** action.  

    The warehouse put-away document opens with a total of eight Take or Place lines for the four purchase order lines.

    The warehouse worker is told that 40 hinges are needed in the assembly department, and proceeds to split the single Place line to specify a second Place line for bin W-02-0001 in the assembly department where the warehouse worker places that part of the received hinges.  

3.  Select the second line on the **Warehouse Put-away** page, the Place line for item 70200.  
4.  In the **Qty. to Handle** field, change the value from 100 to 60.  
5.  On the **Lines** FastTab, choose **Functions**, and then choose **Split Line**. A new line is inserted for item 70200 with 40 in **Qty. to Handle** field.  
6.  In the **Bin Code** field, enter W-02-0001. The **Zone Code** field is automatically filled.  

    By default, the **Zone Code** field on the sales lines are hidden, so you must display it. To do this you need to personalize the page. For more information, see [To start personalizing a page through the Personalizing banner](ui-personalization-user.md#start-personalizing-by-using-the-personalization-mode).

    Proceed to register the put-away.  

7.  Choose the **Register Put-Away** action, and then choose the **Yes** button.  

    The received accessories are now put-away in the items' default bins, and 40 hinges are placed in the assembly department. The received items are now available for picking to internal demand, such as assembly orders, or to external demand, such as sales shipments.  

## Related information  
 [Put Items Away with Warehouse Put-aways](warehouse-how-to-put-items-away-with-warehouse-put-aways.md)   
 [Move Items in advanced warehouse configurations](warehouse-how-to-move-items-in-advanced-warehousing.md)   
 [Design Details: Inbound Warehouse Flow](design-details-inbound-warehouse-flow.md)   
 <!-- [Walkthrough: Receiving and Putting Away in Basic Warehouse Configurations](walkthrough-receiving-and-putting-away-in-basic-warehousing.md)    -->
 [Business Process Walkthroughs](walkthrough-business-process-walkthroughs.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
