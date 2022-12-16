# Transferring Items
When moving goods from one location to another, this is done by shipping the items from one location, then receiving the items in the destination Location. In the time between the shipment and the reception, the items are stored in an *In-Transit Location*. 

## Scenario
The Logistics team has been directed to transfer items from the YELLOW location to WHITE location. Logistics will create and post a transfer order.

> [!NOTE]
> To follow this scenario, you must have completed either scenario "Receiving Items with Inventory Put Away" or "Adjusting Items into or out of Inventory" to have inventory to ship.

## Steps
### Create the Transfer Order
The transfer order document outlines which locations are involved, as well as which items are being transferred. The Logistics team will create the transfer order, then select which items to transfer.

1. Create the transfer order
	1 Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Transfer Orders** and choose the related link.
	2. Choose the **New** action.
	3. Enter the **Transfer-From Code** as **YELLOW**.
	4. Enter the **Transfer-To Code** as **WHITE**.
	5. Enter the **In-Transit Code** as **OWN. LOG.**. 
2. Enter the items as lines
	1. On a new line, enter **WRB-1000** as the **Item No.**. 
	2. Enter the **Quantity** as **10**.

### Release the Transfer Order
When the Logistics team is ready to ship the items, the transfer order should be released for handling.

1. Release the transfer order
	1. Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Transfer Orders** and choose the related link.
	2. Locate the transfer order created in the previous step
	3. *Optional*: Update the **Qty. to Ship** or **Shipment Date** fields as necessary
	4. Choose the **Release** action. 

> [!NOTE]
> The Logistics team can create the warehouse shipment document directly at this point by choosing the **Create Whse. Shipment** action.

### Create the Warehouse Shipment
In this scenario, the Logistics team is creating a warehouse shipment for a single outgoing sales order so that they will create the warehouse shipment, then select the sales order wanted.

1. Create the warehouse shipment
	1. Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Shipments** and choose the related link.
	2. Choose the **New** action
	3. On the warehouse shipment page, press Enter to have a warehouse shipment number automatically selected.
	4. Enter the **Location Code** as **YELLOW**.
2.  Select the source document
	1. Choose the **Get Source Documents...** action
	2. Select the outbound transfer you created from the list and choose the **OK** button.
	3. The lines will contain a new entry for each transfer order line.

### Create the Warehouse Pick
To make items available to be shipped (and update the **Qty. to Ship** on the lines), the items must be put onto a warehouse pick, then that pick must be registered.

1. Create the warehouse pick from the warehouse shipment
	1. On the warehouse shipment page, choose the **Create Pick** action.
	2. Confirm any of the pick settings needed, then choose the **OK** button.
	3. You will receive a confirmation message with the pick number. The pick will not automatically open.
2. Open the warehouse pick
	1. Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Picks** and choose the related link.
	2. Locate the **Warehouse Pick** you just created and open it.
	3. Update the **Qty. To Handle** as needed or choose the **Autofill Qty. to Handle** action.
	4. Choose the **Register Pick** action.
	5. The warehouse pick will close and be removed if all the quantities are handled.

### Post the Warehouse Shipment
After the warehouse pick is registered, the warehouse shipment will be updated with the **Qty. to Ship** populated.

1. Update the document
	1. On the warehouse shipment page, review the **Lines** section and update the **Qty. to Ship** if you need to ship less. Alternatively, if the warehouse shipment is being shipped in its entirety, you may choose the **Autofill Qty. to Ship** action.
2. Choose the **Post** action.

## Results
- a posted warehouse pick will be created    
- a posted warehouse shipment will be created    
- the transfer order line will reflect the **Quantity Shipped** updated for the lines shipped    
- the item **Inventory**  will be the same, as no quantity has left the company. To see the items in transit separately from the items in stock, use the **Item Availability by Location** action on the item card

## See also
[Transfer Inventory Between Locations](../../../inventory-how-transfer-between-locations.md)
[Move Items Ad Hoc in Basic Warehouse Configurations](../../../warehouse-how-to-move-items-ad-hoc-in-basic-warehousing.md)
[View the Availability of Items](../../../inventory-how-availability-overview.md)