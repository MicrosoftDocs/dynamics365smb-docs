# Combining Orders on a Whse. Shipment
The warehouse shipment document supports the ability to combine multiple source documents, such as sales orders, onto a single warehouse document for operating as a batch. When the warehouse shipment is posted, this will update all of the included source document lines. This allows for greater efficiency, as both the warehouse shipment and the warehouse pick document will combine orders into one warehouse operation.

## Scenario
The Logistics team has been informed that multiple sales orders have been created for a single customer. These documents must be released to be handled, combined on a single warehouse shipment, then posted and registered.

## Steps
### Prepare the Sales Document
When Sales is ready to hand the sales order document to the Logistics team, they must release the sales orders for these next steps.

1. Release the Sales Order **105002** 
	1. Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders** and choose the related link.
	2. Locate order 105002 and select it.
	3. Choose the **Release action**. 
2. Repeat this process for sales orders **105003**, **105004**, and **105005**.

### Create the Warehouse Shipment
In this scenario, the Logistics team is creating a warehouse shipment for multiple outgoing sales order so that they will create the warehouse shipment and then select the sales orders wanted.

1. Create the warehouse shipment
	1. Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Shipments** and choose the related link.
	2. Choose the **New** action
	3. On the warehouse shipment page, press Enter to have a warehouse shipment number automatically selected.
	4. Enter the **Location Code** as **YELLOW**.
2. Select the source document
	1. Choose the **Get Source Documents...** action
	2. Using multiple selection mode, select Sales Orders 105002, 105003, 105004, and 105005 from the list and choose the **OK** button.
	3. The lines will contain a new entry for each sales order line.

### Create the Warehouse Pick
To make items available to be shipped (and update the **Qty. to Ship** on the lines), the items must be put onto a warehouse pick, then that pick must be registered.

1. Create the warehouse pick from the warehouse shipment
	1. On the warehouse shipment page, choose the **Create Pick** action.
	2. Confirm any of the pick settings needed, then choose the **OK** button.
	3. You will receive a confirmation message with the pick number. The pick will not automatically open.
2. Open the warehouse pick
	1. Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Picks** and choose the related link.
	2. Locate the warehouse pick you just created and open it.
	3. Update the **Qty. to Handle** as needed for any lines or choose the **Autofill Qty. to Handle** action.
	4. Choose the **Register Pick** action.
	5. The warehouse pick will close and be removed if all the quantities are handled.

### Post the Warehouse Shipment
After the warehouse pick is registered, the warehouse shipment will be updated with the **Qty. to Ship** populated.
	
1. Update the document:
	1. On the warehouse shipment page, review the **Lines** section and update the **Qty. to Ship** if you need to ship less. Alternatively, if the warehouse shipment is being shipped in its entirety, you may choose the **Autofill Qty. to Ship** action.
2. Choose the **Post** action.
3. Confirm the **Ship** option.

## Results

- a posted warehouse pick will be created    
- a posted warehouse shipment will be created    
- four posted sales shipments (for each sales order) will be created    
- the sales orders will have the **Quantity Shipped** updated for the lines shipped    
- the item **Inventory**  will be decreased by the chosen quantities

## See Also
[Ship Items](../../../warehouse-how-ship-items.md)
[View the Availability of Items](../../../inventory-how-availability-overview.md)