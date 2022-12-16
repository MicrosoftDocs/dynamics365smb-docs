# Receiving & Put-Away with Breakbulk
The unit of measure of system allows for receiving in a large unit of measure and shipping in a smaller unit of measure with the ability to "breakbulk" the larger unit of measure on demand.

## Scenario
The Logistics team will receive in 1 **BAG**, which contains 176 **PCS**, of Item **WRB-1001**. A sales order needs to be shipped that requires 20 PCS, so the BAG will be converted as part of the picking process into PCS.

## Steps

### Prepare the Purchase Documents
When purchasing is ready to hand the **Purchase Order** documents to the Logistics team, they must **Release** the purchase orders for these next steps.

1.  Release the purchase order **107008**
2.  Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders** and choose the related link.
3.  Locate order 107008 and select it.
4.  Choose the **Release** action.

### Create the Warehouse Receipt
In this scenario, the Logistics team is creating a warehouse receipt for a single incoming purchase order, so they will create the warehouse receipt, then select the purchase order wanted.

1. Create the warehouse receipt
    1. Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Receipts** and choose the related link.
    2. Choose the **New** action
    3. On the warehouse receipt page, press Enter to have a warehouse receipt number automatically selected.
    4. Enter the **Location Code** as **WHITE**
2. Select the source document
    1. Choose the **Get Source Documents...** action
    2. Using multiple selection mode, select purchase orders 107008 and choose the **OK** button.
    3. The lines will contain a new entry for the purchase order Line.
    4. The bin code for the lines will be the receiving bin, as configured on the location card, which will be **W-08-0001**

### Post the Warehouse Receipt
When the Logistics team has received the items, the warehouse receipt should be updated (with **Qty. to Receive**) and posted.

1. Update the document
	1. On the warehouse receipt page, review the **Lines** section and update the **Qty. to Receive** for the line. Alternatively, if the warehouse receipt is being received in its entirety, you may choose the **Autofill Qty. to Receive** action.
2. Choose the **Post** action.
3. Confirm the **Receive** option.

### Register the Warehouse Put-Away
Once the Logistics team has processed the incoming items however necessary, they need to make the items available for by putting them away.

> [!NOTE]
> When the warehouse receipt is posted, the put-away is created automatically. However, if the put-away was deleted or not created automatically due to system configuration, you can **Create Put-Away** on the **Posted Whse. Receipt** page for the receipt involved.
 
1. Register the warehouse put-away
    1. Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Put-Away** and choose the related link.
    2. Locate the warehouse put-away document created from your warehouse receipt and open it
    3. On the **Warehouse Put-Away** page, review the **Lines** section and update the **Qty. to Handle** for each line. Alternatively, if the order is being received in its entirety, you may choose the **Autofill Qty. to Handle** action.
    4. The **Take** lines will be set to the receiving bin, W-08-0001 . The **Place** lines will be set to the bin **W-04-0001**.
    5. Choose the **Register** action.

A review of the bin contents from the item card for WRB-1001 will show that there is an entry for 1 **BAG** (176 quantity base, PCS) in bin **W-04-0001**.

### Prepare the Sales Document
When sales is ready to hand the **Sales Order** document to the Logistics team, they must **Release** the sales order for the next steps.

1. Release the sales order 105006
    1. Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders** and choose the related link.
    2. Locate order 105006 and select it.
    3. Choose the **Release** action
2. Repeat this process for sales order 105006.

### Create the Warehouse Shipment
In this scenario, the Logistics team is creating a warehouse shipment for a single outgoing sales order, so they will create the warehouse shipment, then select the sales order wanted.

1. Create the warehouse shipment
    1. Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Shipments** and choose the related link.
    2. Choose the **New** action
    3. On the warehouse shipment page, press Enter to have a warehouse shipment number automatically selected.
    4. Enter the **Location Code** as **WHITE**
2. Select the source document
    1. Choose the **Get Source Documents...** action
    2. Select sales order 105006 from the list and choose the **OK** button
    3. The lines will contain a new entry for the sales order Line.

### Create the Warehouse Pick
To make items available to be shipped (and update the **Qty. to Ship** on the Lines), the items must be put onto a warehouse pick, then that pick must be registered.

1. Create the warehouse pick from the warehouse shipment
    1. On the warehouse shipment page, choose the **Create Pick** action.
    2. Confirm any of the pick settings needed then choose the **OK** button.
    3. You will receive a confirmation message with the pick number. The pick will not automatically open.
2. Open the warehouse pick
    1. Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Picks** and choose the related link.
    2. Locate the Pick you just created and open it.

At this stage, the breakbulk functionality is revealed. There will be 4 pick lines:

- A line to Take the 1 BAG out of stock, from bin W-04-0001
- A line to Place the 176 PCS back into stock, in bin W-04-0001
- A line to Take the 20 PCS out of bin W-04-0001
- A line to Place the 20 PCS into the shipping bin, W-09-0001

Complete the warehouse pick in the usual way:
1. Update the **Qty. to Handle** as needed for any lines or choose the **Autofill Qty. to Handle** action.
2. Choose the **Register Pick** action.

The warehouse pick will close and be removed if all the quantities are handled.

#### Post the Warehouse Shipment
After the warehouse pick is registered, the warehouse shipment will be updated with the **Qty. to Ship** populated.

1. Update the document
	1. On the warehouse shipment page, review the **Lines** section and update the **Qty. to Ship** if you need to ship less. Alternatively, if the warehouse shipment is being shipped in its entirety, you may choose the **Autofill Qty. to Ship** action
2. Choose the **Post** action.
3. Confirm the **Ship** option.

## Results 
- a posted warehouse receipt will be created    
- a posted warehouse put-away will be created   
- a posted purchase receipt will be created for the purchase order selected    
- the selected purchase order will have the **Quantity Received** updated for the line received
- a posted warehouse pick will be created
- a posted warehouse shipment will be created  
- the selected sales order will have the **Quantity Shipped** updated for the line shipped    
- the item **Inventory**  will be increased by the quantity of the lines received, minus the quantity of the line shipped.    
- the item will be placed in the **Default Bin** set, which will be visible via the **Bin Contents**
- the bin contents will reflect the **PCS** value of the remaining portion (156) of the received BAG (Depending on the scenarios run, the quantity in the bin content may be greater than 156)

## See Also
[Receive Items](../../../warehouse-how-receive-items.md)
[Enable Automatic Breaking Bulk with Directed Put-away and Pick](../../../warehouse-enable-automatic-breaking-bulk-with-directed-put-away-and-pick.md)
[Walkthrough: Receiving and Putting Away in Advanced Warehouse Configurations](../../../walkthrough-receiving-and-putting-away-in-advanced-warehousing.md)
[Design Details: Inbound Warehouse Flow](../../../design-details-inbound-warehouse-flow.md)
[View the Availability of Items](../../../inventory-how-availability-overview.md)