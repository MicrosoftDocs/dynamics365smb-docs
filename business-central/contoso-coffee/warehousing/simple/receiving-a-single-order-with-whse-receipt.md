# Receiving a Single Order with Whse. Receipt
The process of Receiving a single Purchase Order using the Warehousing module is similar to  the Inventory Put-Away process:

- Release the Purchase Order to indicate the document is ready for handling
- Create the Warehouse Receipt from the Purchase Order directly
- Create the Warehouse Receipt, then use the Get Source Documents functionality to pick up the Purchase Order

## Scenario 
Use Purchase Order **107001**; the Logistics team will receive the items expected by creating a Warehouse Receipt and adding the Item from the Purchase Order.

## Steps 
### Prepare the Purchase Document
When Purchasing is ready to hand the **Purchase Order** Document to the Logistics team, they must **Release** the Purchase Order for these next steps.

1. Release the Purchase  Order **107001**
		a. Using the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders** and choose the related link.
		b. Locate Order **107001** and select it.
		c. Choose the **Release** action.
		
> [!NOTE]
> The Purchaser can create the Warehouse Receipt document directly at this point by choosing the **Create Warehouse Receipt** action.

### Create the Warehouse Receipt
In this scenario, the Logistics team is creating a Warehouse Receipt for a single incoming Purchase Order so that they will create the Warehouse Receipt and then select the Purchase Order wanted.

1. Create the Warehouse Receipt
		1. Using the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Receipts** and choose the related link.
		2. Choose the **New** action
		3. On the Warehouse Receipt page, press Enter to have a Warehouse Receipt number automatically selected.
		4. Enter the **Location Code** as **YELLOW**
2. Select the Source Document
		1. Choose the **Get Source Documents…** action
		2. Select Purchase Order 107001 from the list and choose the **OK** button.
		3. The Lines will contain a new entry for each Purchase Order Line.
### Post the Warehouse Receipt
When the Logistics team has received the Items, the Warehouse Receipt should be updated (with **Qty. to Receive**) and Posted.

1. Update the Document
   1. On the Warehouse Receipt page, review the **Lines** section and update the **Qty. to Receive**. Alternatively, if the Warehouse Receipt is being received in its entirety, you may choose the **Autofill Qty. to Receive** action.
2. Choose the **Post** action.

### Register the Warehouse Put-Away
Once the Logistics team has processed the incoming Items, however necessary, they need to make the Items available for putting them away.

Note: When the Warehouse Receipt is posted, the Put-Away is created automatically. However, if the Put-Away was deleted or not created automatically due to system configuration, you can **Create Put-Away** on the **Posted Whse. Receipt** page for the receipt involved.

1. Register the Warehouse Put-Away
		1. Using the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Put-Away** and choose the related link.
		2. Locate the Warehouse Put-Away document created from your Warehouse Receipt and open it.
		3. On the **Warehouse Put-Away** page, review the **Lines** section and update the **Qty. to Handle**. Alternatively, if the order is being received in its entirety, you may choose the **Autofill Qty. to Handle** action.
		4. Choose the **Register** action.
## Results 
-   A Posted Warehouse Receipt will be created
-   A Posted Warehouse Put-Away will be created    
-   A Posted Purchase Receipt will be created    
-   The Purchase Order will have the **Quantity Received** updated for the lines received
-   The Item **Inventory**  will be increased by the chosen quantity

## See Also