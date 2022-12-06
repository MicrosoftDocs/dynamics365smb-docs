# Combining Orders on a Whse. Shipment

The Warehouse Shipment document also supports the ability to combine multiple source documents, such as Sales Orders, onto a single warehouse document for operating as a batch. When the Warehouse Shipment is posted, this will update all of the included source document lines. This allows for greater efficiency, as both the Warehouse Shipment and the Warehouse Pick document will combine orders into one Warehouse operation.

## Scenario
The Logistics team has been informed that multiple Sales Orders have been created for a single customer. These documents must be Released to be handled, combined on a single Warehouse Shipment, then Posted and Registered.

## Steps
### Prepare the Sales Document
When Sales is ready to hand the Sales  Order Document to the Logistics team, they must Release the Sales Orders for these next steps.

1. Release the Sales Order --. 
	1. Using the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders** and choose the related link.
	2. Locate Order -- and select it.
	3. Choose the **Release action**. 
2. Repeat this process for Sales Orders--.

### Create the Warehouse Shipment
In this scenario, the Logistics team is creating a Warehouse Shipment for multiple outgoing Sales Order so that they will create the Warehouse Shipment and then select the Sales Orders wanted.

1. Create the Warehouse Shipment
	1. Using the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Shipments** and choose the related link.
	2. Choose the **New** action
	3. On the Warehouse Shipment page, press Enter to have a Warehouse Shipment number automatically selected.
	4. Enter the **Location Code** as **YELLOW**.
2. Select the Source Document
	1. Choose the **Get Source Documents…** action
	2. Using multiple selection mode, select Sales Orders __, __, __, and __from the list and choose the **OK** button.
	3. The Lines will contain a new entry for each Sales Order Line.
### Create the Warehouse Pick
To make Items available to be shipped (and update the Qty. to Ship on the Lines), the Items must be put onto a Warehouse Pick, then that Pick must be Registered.

1. Create the Warehouse Pick from the Warehouse Shipment
	1. On the Warehouse Shipment page, choose the **Create Pick** action.
	2. Confirm any of the Pick settings needed, then choose the **OK** button.
	3. You will receive a confirmation message with the Pick number. The Pick will not automatically open.
2. Open the Warehouse Pick
	1. Using the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Picks** and choose the related link.
	2. Locate the Pick you just created and open it.
	3. Update the **Qty. to Handle** as needed for any lines or choose the **Autofill Qty. to Handle** action.
	4. Choose the **Register Pick** action.
	5. The Warehouse Pick will close and be removed if all the quantities are handled.
### Post the Warehouse Shipment
After the Warehouse Pick is registered, the Warehouse Shipment will be updated with the **Qty. to Ship** populated.
	
1. Update the document:
	1. On the Warehouse Shipment page, review the **Lines** section and update the **Qty. to Ship** if you need to ship less. Alternatively, if the Warehouse Shipment is being shipped in its entirety, you may choose the **Autofill Qty. to Ship** action.
2. Choose the **Post** action.

## Results

- A Posted Warehouse Pick will be created    
- A Posted Warehouse Shipment will be created    
- Four Posted Sales Shipments (for each Sales Order) will be created    
- The Sales Orders will have the **Quantity Shipped** updated for the lines shipped    
- The Item **Inventory**  will be decreased by the chosen quantities

## See Also