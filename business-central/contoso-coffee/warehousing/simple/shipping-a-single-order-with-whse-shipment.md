# Shipping a Single Order with Whse. Shipment
The process of Shipping a single Sales Order using the Warehousing module is similar to the Inventory Pick process:

1. Release the Sales Order to indicate the document is ready for handling
2. Either:
   1. Create the Warehouse Shipment from the Sales Order directly
   2. Create the Warehouse Shipment, then use the Get Source Documents
   functionality to pick up the Sales Order

## Scenario 
Use Sales Order __; the Logistics team will ship the items by creating a Warehouse Shipment and adding the Item from the Sales Order.

## Steps
### Prepare the Sales Document
When Sales is ready to hand the **Sales  Order** Document to the Logistics team, they must **Release** the Sales Order for these next steps.

1. Release the Sales Order __.
	1. Using the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders** and choose the related link.
	2. Locate order (--) and select it.
	3. Choose the **release** action.

> [!NOTE]
>  The Salesperson can create the Warehouse Shipment document directly at this point by choosing the **Create Warehouse Shipment** action.
> 
### Create the Warehouse Shipment
In this scenario, the Logistics team is creating a Warehouse Shipment for a single outgoing Sales Order so that they will create the Warehouse Shipment, then select the Sales Order wanted.

1. Create the Warehouse Shipment
	1. Using the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Shipments** and choose the related link.
	2. Choose the **New** action.
	3. On the Warehouse Shipment page, press Enter to have a Warehouse Shipment number automatically selected.
	4. Enter the **Location Code** as **YELLOW**.
2. Select the Source Document
	1. Choose the **Get Source Documents**… action
	2. Select Sales Order __ from the list and choose the **OK** button.
	3. The Lines will contain a new entry for each Sales Order Line.
### Create the Warehouse Pick
To make Items available to be shipped (and update the Qty. to Ship on the Lines), the Items must be put onto a Warehouse Pick, then that Pick must be Registered.

1. Create the Warehouse Pick from the Warehouse Shipment:
	1. On the Warehouse Shipment page, choose the **Create Pick** action.
	2. Confirm any of the Pick settings needed, then choose the **OK** button.
	3. You will receive a confirmation message with the Pick number. The Pick will not automatically open.
2. Open the Warehouse Pick
	1. Using the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Picks** and choose the related link.
	2. Locate the Pick you just created and open it.
	3. Update the **Qty. to Handle** as needed or choose the **Autofill Qty. to Handle** action.
	4. Choose the **Register Pick** action.
	5. The Warehouse Pick will close and be removed if all the quantities are handled.
### Post the Warehouse Shipment
After the Warehouse Pick is registered, the Warehouse Shipment will be updated with the **Qty. to Ship** populated.

1. Update the Document
	1. On the Warehouse Shipment page, review the Lines section and update the **Qty. to Ship** if you need to ship less. Alternatively, if the Warehouse Shipment is being shipped in its entirety, you may choose the **Autofill Qty.** to Ship action.
2. Choose the **Post** action.

## Results

- A Posted Warehouse Pick will be created    
- A Posted Warehouse Shipment will be created    
- A Posted Sales Shipment will be created    
- The Sales Order will have the **Quantity Shipped** updated for the lines shipped    
- The Item **Inventory** will be decreased by the chosen quantity
	
## See Also