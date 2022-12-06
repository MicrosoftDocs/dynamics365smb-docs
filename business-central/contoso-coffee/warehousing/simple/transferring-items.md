# Transferring Items
When moving goods from one Location to another, this is done by Shipping the items from one Location, then Receiving the items in the destination Location. In the time between the Shipment and the Reception, the items are stored in an “In-Transit Location.” For more general information, see the Transfer Inventory Between Locations topic.

## Scenario
The Logistics team has been directed to transfer items from the YELLOW location to WHITE location. Logistics will create and Post a Transfer Order.

> [!NOTE]
> To follow this scenario, you must have completed either scenario “Receiving Items with Inventory Put Away” or “Adjusting Items into or out of Inventory” to have Stock to ship.

## Steps
### Create the Transfer Order
The Transfer Order document outlines which Locations are involved, as well as which Items are being transferred. The Logistics team will create the Transfer Order, then select which items to transfer.

1. Create the Transfer Order
	1 Using the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Transfer Orders** and choose the related link.
	2. Choose the **New** action.
	3. Enter the **Transfer-From Code** as **YELLOW**.
	4. Enter the **Transfer-To Code** as **WHITE**.
	5. Enter the **In-Transit Code** as **OWN. LOG.**. 
2. Enter the Items as Lines
	1. On a new line, enter **WRB-1000** as the **Item No.**. 
	2. Enter the **Quantity** as **10**.

### Release the Transfer Order
When the Logistics team is ready to ship the Items, the Transfer Order should be Released for handling.

1. Release the Transfer Order
	1. Using the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Transfer Orders** and choose the related link.
	2. Locate the Transfer Order created in the previous step
	3. *Optional*: Update the **Qty. to Ship** or **Shipment Date** fields as necessary
	4. Choose the **Release** action. 

> [!NOTE]
> The Logistics team can create the Warehouse Shipment document directly at this point by choosing the **Create Whse. Shipment** action.

### Create the Warehouse Shipment
In this scenario, the Logistics team is creating a Warehouse Shipment for a single outgoing Sales Order so that they will create the Warehouse Shipment, then select the Sales Order wanted.

1. Create the Warehouse Shipment
	1. Using the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Shipments** and choose the related link.
	2. Choose the **New** action
	3. On the Warehouse Shipment page, press Enter to have a Warehouse Shipment number automatically selected.
	4. Enter the **Location Code** as **YELLOW**.
2.  Select the Source Document
	1. Choose the **Get Source Documents…** action
	2. Select the Outbound Transfer you created from the list and choose the **OK** button.
	3. The Lines will contain a new entry for each Transfer Order Line.

### Create the Warehouse Pick
To make Items available to be shipped (and update the Qty. to Ship on the Lines), the Items must be put onto a Warehouse Pick, then that Pick must be Registered.

1. Create the Warehouse Pick from the Warehouse Shipment
	1. On the Warehouse Shipment page, choose the **Create Pick** action.
	2. Confirm any of the Pick settings needed, then choose the **OK** button.
	3. You will receive a confirmation message with the Pick number. The Pick will not automatically open.
2. Open the Warehouse Pick
	1. Using the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Picks** and choose the related link.
	2. Locate the **Warehouse Pick** you just created and open it.
	3. Update the **Qty. To Handle** as needed or choose the **Autofill Qty. to Handle** action.
	4. Choose the **Register Pick** action.
	5. The Warehouse Pick will close and be removed if all the quantities are handled.

### Post the Warehouse Shipment
After the Warehouse Pick is registered, the Warehouse Shipment will be updated with the **Qty. to Ship** populated.

1. Update the Document
	1. On the Warehouse Shipment page, review the **Lines** section and update the **Qty. to Ship** if you need to ship less. Alternatively, if the Warehouse Shipment is being shipped in its entirety, you may choose the **Autofill Qty. to Ship** action.
2. Choose the **Post** action.

## Results

- A Posted Warehouse Pick will be created    
- A Posted Warehouse Shipment will be created    
- The Transfer Order line will reflect the **Quantity Shipped** updated for the lines shipped    
- The Item **Inventory**  will be the same, as no quantity has left the company. To see the Items in transit separately from the items in stock, use the **Item Availability by Location** action on the Item Card.

## See also