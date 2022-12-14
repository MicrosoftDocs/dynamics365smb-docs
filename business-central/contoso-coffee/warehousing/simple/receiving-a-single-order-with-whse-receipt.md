# Receiving a Single Order with Whse. Receipt
The process of receiving a single purchase order using the Warehousing module is similar to the inventory put-away process:

- Release the purchase order to indicate the document is ready for handling
- Create the warehouse receipt from the purchase order directly
- Create the warehouse receipt, then use the get source documents functionality to pick up the purchase order

## Scenario 
Use Purchase Order **107001**; the Logistics team will receive the items expected by creating a warehouse receipt and adding the item from the purchase order.

## Steps 
### Prepare the Purchase Document
When Purchasing is ready to hand the **Purchase Order** document to the Logistics team, they must **Release** the purchase order for these next steps.

1. Release the purchase order
	1. Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders** and choose the related link.
	2. Locate order **107001** and select it.
	3. Choose the **Release** action.
		
> [!NOTE]
> The Purchaser can create the warehouse receipt document directly at this point by choosing the **Create Warehouse Receipt** action.

### Create the Warehouse Receipt
In this scenario, the Logistics team is creating a warehouse receipt for a single incoming purchase order so that they will create the warehouse receipt and then select the purchase order wanted.

1. Create the warehouse receipt
   1. Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Receipts** and choose the related link.
   2. Choose the **New** action
   3. On the warehouse receipt page, press Enter to have a warehouse receipt number automatically selected.
   4. Enter the **Location Code** as **YELLOW**
2. Select the source document
   1. Choose the **Get Source Documents...** action
   2. Select purchase order 107001 from the list and choose the **OK** button.
   3. The lines will contain a new entry for each purchase order line.

### Post the Warehouse Receipt
When the Logistics team has received the items, the warehouse receipt should be updated (with **Qty. to Receive**) and posted.

1. Update the document
   1. On the warehouse receipt page, review the **Lines** section and update the **Qty. to Receive**. Alternatively, if the warehouse receipt is being received in its entirety, you may choose the **Autofill Qty. to Receive** action.
2. Choose the **Post** action.

### Register the Warehouse Put-Away
Once the Logistics team has processed the incoming items, however necessary, they need to make the items available for putting them away.

> [!NOTE]
> When the warehouse receipt is posted, the put-away is created automatically. However, if the put-away was deleted or not created automatically due to system configuration, you can **Create Put-Away** on the **Posted Whse. Receipt** page for the receipt involved.

1. Register the warehouse put-away
   1. Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Put-Away** and choose the related link.
   2. Locate the warehouse put-away document created from your warehouse receipt and open it.
   3. On the **Warehouse Put-Away** page, review the **Lines** section and update the **Qty. to Handle**. Alternatively, if the order is being received in its entirety, you may choose the **Autofill Qty. to Handle** action.
   4. Choose the **Register** action.
   
## Results 
- a posted warehouse receipt will be created
- a posted warehouse put-away will be created    
- a posted purchase receipt will be created    
- the purchase order will have the **Quantity Received** updated for the lines received
- the item **Inventory**  will be increased by the chosen quantity

## See Also