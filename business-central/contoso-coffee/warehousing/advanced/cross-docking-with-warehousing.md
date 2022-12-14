# Cross-Docking with Warehousing
when using directed pick and put-away, sometimes items are being received that could be immediately prepared for an outgoing shipment. Being able to move items directly from the receiving bin to the shipping bin without going to storage bins is the cross-dock functionality.

## Scenario
The Logistics team has items that are due to be shipped out at the same time they are receiving them. During the receipt Process, the Logistics team will calculate if any quantity should be redirected to the shipping process.

## Steps

#### Prepare the Purchase Documents
When Purchasing is ready to hand the **Purchase Order** documents to the Logistics team, they must **Release** the purchase orders for these next steps.

1.  Release the Purchase Order **107011**
2.  Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders** and choose the related link.
3.  Locate order 107011 and select it.
4.  Choose the **Release** action.

### Prepare the Sales Document
When Sales is ready to hand the **Sales Order** Document to the Logistics team, they must **Release** the sales orders for these next steps.

1.  Release the Sales Order **105008**
    1.  Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders** and choose the related link.
    2.  Locate order 105008 and select it.
    3.  Choose the **Release** action.

### Create the Warehouse Receipt
In this scenario, the Logistics team is creating a warehouse receipt for a single incoming purchase order, so they will create the warehouse receipt, then select the purchase order wanted.

1.  Create the warehouse receipt
    1. Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Receipts** and choose the related link.
    2. Choose the **New** action
    3. On the Warehouse Receipt page, press Enter to have a warehouse receipt number automatically selected.
    4. Enter the **Location Code** as **WHITE**
2.  Select the Source Document
    1. Choose the **Get Source Documents...** action
    2. Select purchase order 1070011 and choose the **OK** button.
    3. The lines will contain a new entry for the purchase order line.
    4. The bin code for the line will be the receiving bin, as configured on the location card, which will be **W-08-0001**

### Calculate Cross-Dock Opportunities on the Warehouse Receipt
On the warehouse receipt, the system will look for any cross-dock opportunities if the location is configured for it.  This does not happen automatically, so the Logistics team must check.

1. Choose the **Calculate Cross-Dock** action

This will populate a column on the line, **Qty. to Cross-Dock** with **20**, as of the 100 being received, 20 are possible to go out on a shipment.

### Post the Warehouse Receipt
When the Logistics team has received the items, the warehouse receipt should be updated (with **Qty. to Receive**) and posted.

1. Update the document
	1. On the Warehouse Receipt page, review the **Lines** section and update the **Qty. to Receive** for the line. Alternatively, if the warehouse receipt is being received in its entirety, you may choose the **Autofill Qty. to Receive** action.
2.  Choose the **Post** action.
3.  Confirm the **Receive** option.

### Register the Warehouse Put-Away
Once the Logistics team has processed the incoming items however necessary, they need to make the items available by putting them away.

> [!NOTE]
>  When the warehouse receipt is posted, the put-away is created automatically. However, if the put-away was deleted or not created automatically due to system configuration, you can **Create Put-Away** on the **Posted Whse. Receipt** page for the receipt involved.

Because this put-away will contain cross-dock lines, you’ll see 3 lines on the document:
1.  A Take line for the 100 in Bin W-08-0001, the receiving bin
2.  A Place line for the 20 into Bin W-14-0001, the cross-dock bin
3.  A Place line for the 80 into Bin W-04-0001, a storage bin

1.  Register the warehouse put-away
    1.  Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Put-Away** and choose the related link.
    2.  Locate the warehouse put-away document created from your warehouse receipt and open it
    3.  On the **Warehouse Put-Away** page, review the Lines section and update the **Qty. to Handle** for each line. Alternatively, if the order is being received in its entirety, you may choose the **Autofill Qty. to Handle** action.
    4.  Choose the **Register** action.

### Create the Warehouse Shipment
In this scenario, the Logistics team is creating a warehouse shipment for multiple outgoing sales ordera, so they will create the warehouse shipment, then select the sales orders wanted.

1.  Create the warehouse shipment
    1.  Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter warehouse shipments and choose the related link.
    2.  Choose the **New** action
    3.  On the warehouse shipment page, press **Enter** to have a warehouse shipment number automatically selected.
    4.  Enter the **Location Code** as **WHITE**
2.  Select the source document
    1.  Choose the **Get Source Documents...** action
    2.  Select sales order 105008 from the list and choose the **OK** button.
    3.  The lines will contain a new entry for the sales order line.

### Create the Warehouse Pick
To make items available to be shipped (and update the qty. to ship on the lines), the items must be put onto a warehouse pick, then that pick must be registered.

1.  Create the warehouse pick from the warehouse shipment
    1.  On the warehouse shipment page, choose the **Create Pick** action.
    2.  Confirm any of the pick settings needed then choose the **OK** button.
    3.  You will receive a confirmation message with the pick number. the pick will not automatically open.
2.  Open the warehouse pick
    1.  Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Picks** and choose the related link.
    2.  Locate the pick you just created and open it.
    
At this stage, the cross-dock functionality is revealed again. There will be 2 pick lines:
- A line to Take the 20 out of Bin W-14-0001, the cross-dock bin
- A line to Place the 20 into Bin W-09-0001, the shipping bin
    
Complete the warehouse pick in the usual way:
1.  Update the **Qty. to Handle** as needed for any lines or choose the **Autofill Qty. to Handle** action.
2.  Choose the **Register Pick** action.

The warehouse pick will close and be removed if all the quantities are handled.

### Post the Warehouse Shipment
After the warehouse pick is registered, the warehouse shipment will be updated with the **Qty. to Ship** populated.
1.  Update the document
	1. On the warehouse shipment page, review the **Lines** section and update the **Qty. to Ship** if you need to ship less. Alternatively, if the warehouse shipment is being shipped in its entirety, you may choose the **Autofill Qty. to Ship** action.
2.  Choose the **Post** action.

## Results

## See Also