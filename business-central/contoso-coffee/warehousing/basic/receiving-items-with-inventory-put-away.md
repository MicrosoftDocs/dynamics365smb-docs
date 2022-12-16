# Receiving Items with Inventory Put-Away
When using a location that has **Require Put Away** enabled, the Logistics team can perform per-order operations using inventory put-away.

## Scenario
Using **Purchase Order 107000**, the Logistics team will receive goods from the document created by the Purchasing team.

## Steps

## Prepare the Purchase Document
When Purchasing is ready to hand the **Purchase Order** document to the Logistics team, they must **Release** the purchase order for these next steps.
1. Release the purchase order **107000**
    1. Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders** and choose the related link.
    2. Locate order 107000 and select it.
    3. Choose the **Release** action.

> [!NOTE]
> The purchaser can create the inventory put-away document directly at this point by choosing the **Create Inventory Pick/Put-Away** and enabling the **Inventory Put-Away** option.

### Create the Inventory Document
When the Logistics team wants to prepare for the incoming goods, they will create an inventory put-away and bring the purchase order lines onto the put-away document:

1. Create the inventory put-away
    1. Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Inventory Put-Aways** and choose the related link.
    2. Choose the **New** action.
    3. On the inventory put-away page, press Enter to have an inventory put-away number automatically selected.
    4. Change the **Location Code** to the **SILVER** location.
			
 2. Select the source document
    1. Choose the **Get Source Document** action.
    2. Select **Purchase Order 107000** from the list and choose the **OK** button.
    3. The source and vendor fields in the General header will update to the purchase order information.  Additionally, the lines from the purchase order (in this case, just one) will be added to the inventory put-away.

The document is now ready for handling.

### Posting the Inventory Document
When the Logistics team is ready to receive the items, the inventory put-away should be updated and then Posted.

1. Update the document
    1. On the **Inventory Put-Away** page, review the **Lines** section and update the **Qty. to Handle**.  Alternatively, if the order is being received in its entirety, you may choose the **Autofill Qty. to Handle** action.
	2. Review or set the **Bin Code** for each line.	
2. Choose the **Post** action.

## Results 
 - a **Posted Invt. Put-Away** will be created
 - a **Purchase Receipt Receipt** will be created
 - the purchase order will have the **Quantity Received** updated for the lines received
 - the item **Inventory** will be increased by the chosen quantity

## See Also
[Put-Away Items with Inventory Put-Aways](../../../warehouse-how-to-put-items-away-with-inventory-put-aways.md)
[Receive Items](../../../warehouse-how-receive-items.md)
[Walkthrough: Receiving and Putting Away in Basic Warehouse Configurations](../../../walkthrough-receiving-and-putting-away-in-basic-warehousing.md)