# Transferring Items
When moving goods from one location to another, this is done by shipping the items from one Location, then receiving the items in the destination Location. In the time between the shipment and the reception, the items are stored in an *In-Transit Location*. 

## Scenario
The Logistics team has been directed to transfer items from the **SILVER** location to **YELLOW** location. Logistics will create and post a transfer order.

> [!NOTE]
> To follow this scenario, you must have completed either scenario "Receiving Items with Inventory Put Away" or "Adjusting Items into or out of Inventory" to have inventory to ship.

## Steps

### Create the Transfer Order
The transfer order document outlines which locations are involved, as well as which items are being transferred. The Logistics team will create the transfer order, then select which items and quantities to transfer.

1. Create the transfer order
	1. Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Transfer Orders** and choose the related link.
	2. Choose the **New** action.
	3. Enter the **Transfer-From Code** as **SILVER**.
	4. Enter the **Transfer-To Code** as **YELLOW**.
	5. Enter the **In-Transit Code** as **OWN. LOG**.
2. Enter the items as lines
	1. On a new line, enter **WRB-1000** as the **Item No.**.
	1. Enter the **Quantity** as **10**.

### Release the Transfer Order
When the Logistics team is ready to ship the items, the transfer order should be released for handling.
 
1. Release the transfer order
    1. Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter transfer orders and choose the related link.
    2. Locate the transfer order created in the previous step
    3. Optional: Update the **Qty. to Ship** or **Shipment Date** fields as necessary
    4. Choose the **Release** action.

> [!NOTE]
> The Logistics team can create the inventory put-away document directly at this point by choosing the **Create Inventory Pick/Put-Away** action and enabling the **Inventory Pick** option.

### Create the Inventory Document
When the Logistics team wants to prepare to send the outgoing goods, they will create an inventory pick and bring the transfer order lines onto the pick document:

1. Create the inventory pick
	1. Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Inventory Pick** and choose the related link
	2. Choose the **New** action.
	3. On the inventory pick page, press Enter to have an inventory pick number automatically selected.
	4. Change the **Location Code** to the **SILVER** location
2. Select the source document
	1. Choose the **Get Source Document** action.
	2. Select the transfer order created above from the list and choose the **OK** button. The **Source Document** will describe the document as an **Outbound Transfer**.
	3. The source and location fields in the General header will update to the transfer order information. Additionally, the lines from the transfer order (in this case, just one) will be added to the inventory pick.

### Posting the Inventory Document
When the Logistics team is ready to ship the items, the inventory pick should be updated and then posted.
1. Update the document
   1. On the **Inventory Pick** page, review the **Lines** section and update the **Qty. to Handle**. Alternatively, if the order is being shipped in its entirety, you may choose the **Autofill Qty. to Handle** action.
   2. Review or set the **Bin Code** for each line
2. Post the document
   1. Choose the **Post** action
   2. Confirm you want to post the **Invt. Pick and Outbound Transfer**.

## Results
- a **Posted Invt. Pick** will be created
- a **Posted Transfer Shipment** will be created    
- the transfer order line will reflect the **Quantity Shipped** updated for the lines shipped
- the item **Inventory**  will be the same, as no quantity has left the company. To see the items in transit separately from the items in stock, use the **Item Availability by Location** action on the item card

## See Also
[Transfer Inventory Between Locations](../../../inventory-how-transfer-between-locations.md)
[Move Items Ad Hoc in Basic Warehouse Configurations](../../../warehouse-how-to-move-items-ad-hoc-in-basic-warehousing.md)
[View the Availability of Items](../../../inventory-how-availability-overview.md)