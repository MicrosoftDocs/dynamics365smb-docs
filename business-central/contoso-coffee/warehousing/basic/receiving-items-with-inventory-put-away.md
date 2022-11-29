# Receiving Items with Inventory Put-Away

When using a Location that has **Require Put Away** enabled, the Logistics team can perform per-order operations using Inventory Put-Away.

## Scenario
Using **Purchase Order 107000**, the Logistics team will receive goods from the document created by the Purchasing team.

## Steps

## Prepare the Purchase Document
When Purchasing is ready to hand the **Purchase Order** Document to the Logistics team, they must **Release** the Purchase order for these next steps.
1. Release the Purchase  Order **107000**
    1. Using the {**search**} icon, enter **Purchase Orders** and choose the related link.
    2. Locate Order 107000 and select it.
    3. Choose the **Release** action.

> [!NOTE]
> The Purchaser can create the Inventory Put-Away document directly at this point by choosing the **Create Inventory Pick/Put-Away** and enabling the **Inventory Put-Away** option.

### Create the Inventory Document
When the Logistics team wants to prepare for the incoming goods, they will create an Inventory Put-Away and bring the Purchase Order Lines onto the Put-Away Document:

1. Create the Inventory Put-Away
    1. Using the {search} icon, enter **Inventory Put-Aways** and choose the related link.
    2. Choose the **New** action.
    3. On the Inventory Put-Away page, press Enter to have an Inventory Put-Away number automatically selected.
    4. Change the **Location Code** to the **SILVER** location.
			
 2. Select the Source Document
    1. Choose the **Get Source Document** action.
    2. Select **Purchase Order 107000** from the list and choose the **OK** button.
    3. The Source and Vendor fields in the General header will update to the Purchase Order information.  Additionally, the Lines from the Purchase Order (in this case, just one) will be added to the Inventory Put-Away.

The document is now ready for handling.

### Posting the Inventory Document
When the Logistics team is ready to receive the items, the Inventory Put-Away should be updated and then Posted.

1. Update the Document
    1. On the **Inventory Put-Away** page, review the **Lines** section and update the **Qty. to Handle**.  Alternatively, if the order is being received in its entirety, you may choose the **Autofill Qty. to Handle** action.
	2. Review or set the **Bin Code** for each line.
			
2. Choose the **Post** action.

## Results 
After the Put-Away has been posted, the following will be true:

 - A **Posted Invt. Put-Away** will be created
 - A **Purchase Receipt Receipt** will be created
 - The Purchase Order will have the **Quantity Received** updated for the lines received
 - The Item **Inventory** will be increased by the chosen quantity

## See Also
[Put-Away Items with Inventory Put-Aways](https://learn.microsoft.com/en-us/dynamics365/business-central/warehouse-how-to-put-items-away-with-inventory-put-aways)
[Receive Items](https://learn.microsoft.com/en-us/dynamics365/business-central/warehouse-how-receive-items)