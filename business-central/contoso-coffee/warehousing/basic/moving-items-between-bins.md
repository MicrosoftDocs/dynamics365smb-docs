# Moving Items Between Bins
When using basic logistics, from time to time, it is necessary to move items from one Bin to another. This can be completed using either internal movements or item reclassifications.

## Scenario
Using the internal movement, the Logistics team will move items from one bin to another.  To generate the logistics document, a source document is required, which is the **Internal Movement**.

> [!NOTE]
> To follow this scenario, you must have completed either scenario "Receiving Items with Inventory Put Away" or "Adjusting Items into or out of Inventory" to have stock to ship.

## Steps

### Create the Internal Movement
The internal movement specifies which destination **Location Code** and **To Bin Code**, along with what date. The lines on this document specifies which items, quantities, and source bins.

1. Create the internal movement
	1. Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Internal Movement** and choose the related link.
	2. Choose the **New** action
	3. On the internal movement page, press Enter to have a movement number automatically selected.
	4. Ensure the **Location Code** is set to **SILVER**.
	5. Enter the **To Bin Code** as **S-01-0002**.
	6. On the lines fasttab, choose the **Item No.** field to open the **Bin Contents List** page, and then select the item to move based on its availability in bins.  Select the **WRB-1000** item in bin **S-01-0001**.  When you have selected the item, the **From Bin Code**and **To-Bin Code** will populate
	7. Enter the **Quantity** as **10**.

### Create the Inventory Movement
Unlike other logistics documents, the **Inventory Movement** cannot be created directly.

The Logistics Team must create the inventory movement document directly from the **Internal Movement** by choosing the **Create Inventory Movement** action.

1. Locate the internal movement
	1. Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Internal Movement** and choose the related link.
	2. Open the internal movement created in the previous step.
	3. Choose the **Create Inventory Movement** action
	4. Confirm you wish to create the movement

This will create a new **Inventory Movement**.

### Register the Inventory Movement
1. Locate the inventory movement
	1. Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Inventory Movement** and choose the related link.
	2. Open the inventory movement created in the previous step. You will note this document does not have a **Source Document**, and each like on the internal movement was turned into a pair of lines, one of action type **Take** and one of action type of **Place**.
	3. Enter the **Qty. to Handle** of the items you wish to move or choose the **Autofill Qty. to Handle** action
	4. Choose the **Register Invt. Movement** action
	5. Confirm you want to **Register** the document.

> [!NOTE]
> Because this is a logistics operation that does not have any direct financial impact, this is called register rather than post.

## See Also
