# Transferring Items
When moving goods from one Location to another, this is done by Shipping the items from one Location, then Receiving the items in the destination Location. In the time between the Shipment and the Reception, the items are stored in an “In-Transit Location.” For more general information, see the Transfer Inventory Between Locations topic.

## Scenario
The Logistics team has been directed to transfer items from the **SILVER** location to **YELLOW** location. Logistics will create and Post a Transfer Order.

> [!NOTE]
> To follow this scenario, you must have completed either scenario “Receiving Items with Inventory Put Away” or “Adjusting Items into or out of Inventory” to have Stock to ship.

## Steps

### Create the Transfer Order
The Transfer Order document outlines which Locations are involved, as well as which Items are being transferred. The Logistics team will create the Transfer Order, then select which items to transfer.

1. Create the Transfer Order
	1. Using the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Transfer Orders** and choose the related link.
	2. Choose the **New** action.
	3. Enter the **Transfer-From Code** as **SILVER**.
	4. Enter the **Transfer-To Code** as **YELLOW**.
	5. Enter the **In-Transit Code** as **OWN. LOG**.
2. Enter the Items as Lines
	1. On a new line, enter **WRB-1000** as the **Item No.**.
	1. Enter the **Quantity** as **10**.

### Release the Transfer Order
When the Logistics team is ready to ship the Items, the Transfer Order should be Released for handling.
 
1. Release the Transfer Order
    1. Using the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter Transfer Orders and choose the related link.
    2. Locate the Transfer Order created in the previous step
    3. Optional: Update the **Qty. to Ship** or **Shipment Date** fields as necessary
    4. Choose the **Release** action.

> [!NOTE]
> The Logistics team can create the Inventory Put-Away document directly at this point by choosing the **Create Inventory Pick/Put-Away** action and enabling the **Inventory Pick** option.

### Create the Inventory Document
When the Logistics team wants to prepare to send the outgoing goods, they will create an Inventory Pick and bring the Transfer Order Lines onto the Pick Document:

1. Create the Inventory Pick
	1. Using the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Inventory Pick** and choose the related link
	2. Choose the **New** action.
	3. On the Inventory Pick page, press Enter to have an Inventory Pick number automatically selected.
	4. Change the **Location Code** to the **SILVER** location
2. Select the Source Document
	1. Choose the **Get Source Document** action.
	2. Select the Transfer Order created above from the list and choose the **OK** button. The **Source Document** will describe the document as an **Outbound Transfer**.
	3. The Source and Location fields in the General header will update to the Transfer Order information. Additionally, the Lines from the Transfer Order (in this case, just one) will be added to the Inventory Pick.

### Posting the Inventory Document
When the Logistics team is ready to ship the items, the Inventory Pick should be updated and then Posted.
1. Update the Document
   1. On the **Inventory Pick** page, review the **Lines** section and update the **Qty. to Handle**. Alternatively, if the order is being shipped in its entirety, you may choose the **Autofill Qty. to Handle** action.
   2. Review or set the **Bin Code** for each line
2. Post the Document
   1. Choose the **Post** action
   2. Confirm you want to post the **Invt. Pick and Outbound Transfer**.

## Results
- A **Posted Invt. Pick** will be created
- A **Posted Transfer Shipment** will be created    
- The Transfer Order line will reflect the **Quantity Shipped** updated for the lines shipped
- The Item **Inventory**  will be the same, as no quantity has left the company. To see the Items in transit separately from the items in stock, use the **Item Availability by Location** action on the Item Card.

## See Also