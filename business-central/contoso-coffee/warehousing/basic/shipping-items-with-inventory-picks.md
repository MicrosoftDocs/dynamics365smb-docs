# Shipping Items with Inventory Picks
When using a Location that has **Require Pick** enabled, the Logistics team can perform per-order operations using Inventory Pick.

## Scenario
Using **Sales Order 105000**, the Logistics team will ship goods from the document created by the Sales team.

> [!NOTE]
> To follow this scenario, you must have completed either scenario “Receiving Items with Inventory Put Away” or “Adjusting Items into or out of Inventory” to have Stock to ship.

## Steps

### Prepare the Sales Document 
When Sales is ready to hand the **Sales Order** Document to the Logistics team, they must Release the Sales Order for these next steps.
	
1. Release the Sales Order **105000**
    1. Using the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter Sales Orders and choose the related link.
    2. Locate Order 105000 and select it.
    3. Choose the **Release** action.

> [!NOTE]
> The Salesperson can create the Inventory Pick document directly at this point by choosing the **Create Inventory Pick/Put-Away** and enabling the **Inventory Pick** option.

### Create the Inventory Document
When the Logistics team wants to prepare to send the outgoing goods, they will create an Inventory Pick and bring the Sales Order Lines onto the Pick Document:

1. Create the Inventory Pick
    1. Using the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter Inventory Pick and choose the related link.
    2. Choose the **New** action
    3. On the Inventory Pick page, press Enter to have an Inventory Pick number automatically selected
    4. Change the **Location** Code to the **SILVER** location.
2. Select the Source Document
    1. Choose the **Get Source Document** action.
    2. Select **Sales Order 105000** from the list and choose the OK button.
    3. The Source and Customer fields in the General header will update to the Sales Order information. Additionally, the Lines from the Sales Order (in this case, just one) will be added to the Inventory Pick.

The document is now ready for handling.

### Posting the Inventory Document
When the Logistics team is ready to ship the items, the Inventory Pick should be updated and then Posted.

1. Update the Document
	1. On the **Inventory Pick** page, review the **Lines** section and update the **Qty.** to **Handle**. Alternatively, if the order is being shipped in its entirety, you may choose the **Autofill Qty. to Handle** action.
	2. Review or set the **Bin Code** for each line.
2. Choose the **Post** action
	1. Choose the **Ship** option.

## Results
After the Pick has been posted, the following will be true:

 - A **Posted Invt. Pick** will be created
 - A **Posted Sales Shipment** will be created
 - The Sales Order will have the **Quantity Shipped** updated for the lines shipped
 - The Item **Inventory**  will be decreased by the chosen quantity

## See Also
