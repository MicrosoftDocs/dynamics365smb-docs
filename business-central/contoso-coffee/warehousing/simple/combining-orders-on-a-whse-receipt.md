# Combining Orders on a Whse. Receipt
The warehouse receipt document also supports the ability to combine multiple source documents, such as purchase orders, onto a single warehouse document for operating as a batch.  When the warehouse receipt is posted, this will update all of the included source document lines. This allows for greater efficiency, as both the warehouse receipt and the warehouse put-away document will combine orders into one warehouse operation.

## Scenario
The Logistics team has been informed that multiple purchase orders have been created from a single vendor. These documents must be released to be handled, combined on a single warehouse receipt, then posted and registered.

## Steps 
### Prepare the Purchase Documents
When Purchasing is ready to hand the **Purchase Order** documents to the Logistics team, they must **Release** the purchase orders for these next steps.

1. Release the **Purchase Order 107002**
	1. Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders** and choose the related link.
	2. Locate order 107002 and select it.
	3. Choose the **Release** action
2. Repeat this process for Purchase Orders **107003**, **107004**, and **107005**.

### Create the Warehouse Receipt
In this scenario, the Logistics team is creating a warehouse receipt for multiple incoming purchase orders so that they will create the warehouse receipt, then select the purchase orders wanted.

1. Create the warehouse receipt
	1. Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter warehouse receipts and choose the related link.
	2. Choose the **New** action
	3. On the warehouse receipt page, press Enter to have a warehouse receipt number automatically selected
	4. Enter the **Location Code** as **YELLOW**.
2. Select the source document
	1. Choose the **Get Source Documents...** action
	2. Using multiple selection mode, select Purchase Orders 107002, 107003, 107004, and 107005 from the list and choose the **OK** button.
	3. The lines will contain a new entry for each purchase order line.
### Post the Warehouse Receipt
When the Logistics team has received the items, the warehouse receipt should be updated (with **Qty. to Receive**) and posted.

1. Update the document 
	2. On the warehouse receipt page, review the **Lines** section and update the **Qty. to Receive** for each line. Alternatively, if the warehouse receipt is being received in its entirety, you may choose the **Autofill Qty. to Receive** action.
2. Choose the **Post** action.
3. Confirm the **Receive** option.

### Register the Warehouse Put-Away
Once the Logistics team has processed the incoming items, they need to make the items available for putting them away.

> [!NOTE]
> When the warehouse receipt is posted, the put-away is created automatically. However, if the put-away was deleted or not created automatically due to system configuration, you can **Create Put-Away** on the **Posted Whse. Receipt** page for the receipt involved.

1. Register the warehouse put-away
	1. Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Put-Away** and choose the related link.
	2. Locate the warehouse put-away document created from your warehouse receipt and open it
	3. On the **Warehouse Put-Away** page, review the **Lines** section and update the **Qty. to Handle** for each line. Alternatively, if the order is being received in its entirety, you may choose the **Autofill Qty. to Handle** action.
	4. Choose the **Register** action.
## Results
-   a posted warehouse receipt will be created    
-   a posted warehouse put-away will be created   
-   a posted purchase receipt will be created for each purchase order selected    
-   each selected purchase order will have the **Quantity Received** updated for the lines received
-   the item **Inventory**  will be increased by the total quantity of all lines received

## See Also
[Receive Items](../../../warehouse-how-receive-items.md)
[View the Availability of Items](../../../inventory-how-availability-overview.md)