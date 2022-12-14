# Shipping & Picking

The process of shipping a single sales order using the warehousing module with **Direct Pick and Put-Away** enabled uses the warehouse pick functionality
1.  Release the sales order to indicate the document is ready for handling
2.  Either:
	- Create the warehouse shipment from the sales order directly
	- Create the warehouse shipment, then use the *Get Source Documents* functionality to select the sales order
3.  Creating the warehouse pick document    
4.  Registering the warehouse pick    
5.  Posting the warehouse shipment

## Scenario
Using sales order 105007, the Logistics team will ship the items by creating a warehouse shipment and adding the item from the sales order. They will create and register a warehouse pick, then post the shipment

## Steps

### Prepare the Sales Document
When Sales is ready to hand the **Sales Order** document to the Logistics team, they must **Release** the sales order for these next steps.
1. Release the sales order 105007
    1.  Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders** and choose the related link.
    2.  Locate order 105007 and select it.
    3.  Choose the **Release** action.

> [!NOTE]
> The Salesperson can create the warehouse shipment document directly at this point by choosing the **Create Warehouse Shipment** action.

### Create the Warehouse Shipment
In this scenario, the Logistics team is creating a warehouse shipment for a single outgoing sales order, so they will create the warehouse shipment, then select the sales order wanted.

1.  Create the warehouse shipment
    1.  Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Shipments** and choose the related link.
    2.  Choose the **New** action
    3.  On the warehouse shipment page, press Enter to have a warehouse shipment number automatically selected.
    4.  Enter the **Location Code** as **WHITE**
2. Select the source document
    1.  Choose the **Get Source Documents...** action
    2.  Select sales order 105007 from the list and choose the **OK** button.
    3.  The lines will contain a new entry for each sales order line.

### Create the Warehouse Pick
To make items available to be shipped (and update the **Qty. to Ship** on the lines), the items must be put onto a warehouse pick, then that pick must be registered.

1.  Create the warehouse pick from the Warehouse Shipment
    1.  On the warehouse shipment page, choose the **Create Pick** action.
    2.  Confirm any of the pick settings needed then choose the **OK** button.
    3.  You will receive a confirmation message with the pick number. The pick will not automatically open.
2.  Open the warehouse pick
    1.  Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Picks** and choose the related link.
    2.  Locate the pick you just created and open it.
    3.  Update the **Qty. to Handle** as needed or choose the **Autofill Qty. to Handle** action.
    4.  Choose the **Register Pick** action.
    5.  The warehouse pick will close and be removed if all the quantities are handled.

### Post the Warehouse Shipment
After the warehouse pick is registered, the warehouse shipment will be updated with the **Qty. to Ship** populated.
1. Update the document
   1. On the warehouse shipment page, review the **Lines** section and update the **Qty. to Ship** if you need to ship less. Alternatively, if the warehouse shipment is being shipped in its entirety, you may choose the **Autofill Qty. to Ship** action.
2.  Choose the **Post** action.
3.  Confirm the **Ship** option.

## Results
- a posted warehouse pick will be created
- a posted warehouse shipment will be created
- a posted sales shipment will be created
- the sales order will have the **Quantity Shipped** updated for the lines shipped
- the item **Inventory** will be decreased by the chosen quantity

## See also