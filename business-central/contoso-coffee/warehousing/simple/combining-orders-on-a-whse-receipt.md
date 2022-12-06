# Combining Orders on a Whse. Receipt
The Warehouse Receipt document also supports the ability to combine multiple source documents, such as Purchase Orders, onto a single warehouse document for operating as a batch.  When the Warehouse Receipt is posted, this will update all of the included source document lines. This allows for greater efficiency, as both the Warehouse Receipt and the Warehouse Put-Away document will combine orders into one Warehouse operation.

## Scenario
The Logistics team has been informed that multiple Purchase Orders have been created from a single vendor. These documents must be Released to be handled, combined on a single Warehouse Receipt, then Posted and Registered.

## Steps 
### Prepare the Purchase Documents
When Purchasing is ready to hand the **Purchase Order** Documents to the Logistics team, they must **Release** the Purchase Orders for these next steps.

1. Release the Purchase  Order **107001**
	1. Using the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders** and choose the related link.
	2. Locate Order 107001 and select it.
	3. Choose the **Release** action
2. Repeat this process for Purchase Orders **107002**, **107003**, **107004**, and **107005**.

### Create the Warehouse Receipt
In this scenario, the Logistics team is creating a Warehouse Receipt for multiple incoming Purchase Orders so that they will create the Warehouse Receipt, then select the Purchase Orders wanted.

1. Create the Warehouse Receipt
	1. Using the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter Warehouse Receipts and choose the related link.
	2. Choose the **New** action
	3. On the Warehouse Receipt page, press Enter to have a Warehouse Receipt number automatically selected
	4. Enter the **Location Code** as **YELLOW**.
2. Select the Source Document
	1. Choose the **Get Source Documents…** action
	2. Using multiple selection mode, select Purchase Orders 107002, 107003, 107004, and 107005  from the list and choose the **OK** button.
	3. The Lines will contain a new entry for each Purchase Order Line.
### Post the Warehouse Receipt
When the Logistics team has received the Items, the Warehouse Receipt should be updated (with **Qty. to Receive**) and Posted.

1. Update the Document 
	2. On the Warehouse Receipt page, review the **Lines** section and update the **Qty. to Handle** for each line. Alternatively, if the Warehouse Receipt is being received in its entirety, you may choose the **Autofill Qty. to Receive** action.
2. Choose the **Post** action.
### Register the Warehouse Put-Away
Once the Logistics team has processed the incoming Items, however necessary, they need to make the Items available for putting them away.

> [!NOTE]
> When the Warehouse Receipt is posted, the Put-Away is created automatically. However, if the Put-Away was deleted or not created automatically due to system configuration, you can **Create Put-Away** on the **Posted Whse. Receipt** page for the receipt involved.

1. Register the Warehouse Put-Away
	1. Using the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Put-Away** and choose the related link.
	2. Locate the Warehouse Put-Away document created from your Warehouse Receipt and open it
	3. On the **Warehouse Put-Away** page, review the **Lines** section and update the **Qty. to Handle** for each line. Alternatively, if the order is being received in its entirety, you may choose the **Autofill Qty. to Handle** action.
	4. Choose the **Register** action.
## Results
-   A Posted Warehouse Receipt will be created    
-   A Posted Warehouse Put-Away will be created   
-   A Posted Purchase Receipt will be created for each Purchase Order selected    
-   Each selected Purchase Order will have the **Quantity Received** updated for the lines received
-   The Item **Inventory**  will be increased by the total quantity of all lines received

## See Also
