# Shipping Items with Inventory Picks
When using a location that has **Require Pick** enabled, the Logistics team can perform per-order operations using inventory pick.

## Scenario
Using **Sales Order 105000**, the Logistics team will ship goods from the document created by the Sales team.

> [!NOTE]
> To follow this scenario, you must have completed either scenario "Receiving Items with Inventory Put Away" or "Adjusting Items into or out of Inventory" to have inventory to ship.

## Steps

### Prepare the Sales Document 
When Sales is ready to hand the **Sales Order** document to the Logistics team, they must release the sales order for these next steps.
	
1. Release the Sales Order **105000**
    1. Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter sales orders and choose the related link.
    2. Locate order 105000 and select it.
    3. Choose the **Release** action.

> [!NOTE]
> The Salesperson can create the inventory pick document directly at this point by choosing the **Create Inventory Pick/Put-Away** and enabling the **Inventory Pick** option.

### Create the Inventory Document
When the Logistics team wants to prepare to send the outgoing goods, they will create an inventory pick and bring the sales order lines onto the pick document:

1. Create the inventory pick
    1. Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter inventory pick and choose the related link.
    2. Choose the **New** action
    3. On the inventory pick page, press Enter to have an inventory pick number automatically selected
    4. Change the **Location** Code to the **SILVER** location.
2. Select the source document
    1. Choose the **Get Source Document** action.
    2. Select **Sales Order 105000** from the list and choose the OK button.
    3. The source and customer fields in the General header will update to the sales order information. Additionally, the lines from the sales order (in this case, just one) will be added to the inventory pick.

The document is now ready for handling.

### Posting the Inventory Document
When the Logistics team is ready to ship the items, the inventory pick should be updated and then posted.

1. Update the document
	1. On the **Inventory Pick** page, review the **Lines** section and update the **Qty. to Handle**. Alternatively, if the order is being shipped in its entirety, you may choose the **Autofill Qty. to Handle** action.
	2. Review or set the **Bin Code** for each line.
2. Choose the **Post** action
3. Confirm the **Ship** option.

## Results
After the pick has been posted, the following will be true:

 - a **Posted Invt. Pick** will be created
 - a **Posted Sales Shipment** will be created
 - the sales order will have the **Quantity Shipped** updated for the lines shipped
 - the item **Inventory**  will be decreased by the chosen quantity

## See Also
[Pick Items with Inventory Picks](../../../warehouse-how-to-pick-items-with-inventory-picks.md)
[Ship Items](../../../warehouse-how-ship-items.md)
[View the Availability of Items](../../../inventory-how-availability-overview.md)