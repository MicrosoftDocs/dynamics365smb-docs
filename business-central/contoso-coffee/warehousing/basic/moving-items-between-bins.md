# Moving Items Between Bins
When using Basic Logistics, from time to time, it is necessary to move Items from one Bin to another. This can be completed using either Internal Movements or Item Reclassifications.

## Scenario
Using the Internal Movement, the Logistics Team will move Items from one Bin to another.  To generate the logistics document, a Source Document is required, which is the **Internal Movement**.

> [!NOTE]
> To follow this scenario, you must have completed either scenario “Receiving Items with Inventory Put Away” or “Adjusting Items into or out of Inventory” to have Stock to ship.

## Steps

### Create the Internal Movement
The Internal Movement specifies which destination **Location Code** and **To Bin Code**, along with what date. The Lines on this document specifies which Items, quantities, and source Bins.

1. Create the Internal Movement
	1. Using the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Internal Movement** and choose the related link.
	2. Choose the **New** action
	3. On the Internal Movement page, press Enter to have a Movement number automatically selected.
	4. Ensure the **Location Code** is set to **SILVER**.
	5. Enter the **To Bin Code** as **S-01-0002**.
	6. On the Lines FastTab, choose the **Item No.** field to open the **Bin Contents List** page, and then select the item to move based on its availability in bins.  Select the **WRB-1000** item in Bin **S-01-0001**.  When you have selected the item, the **From Bin Code**and **To-Bin Code** will populate
	7. Enter the **Quantity** as **10**.

### Create the Inventory Movement
Unlike other logistics documents, the **Inventory Movement** cannot be created directly, then use Get Source Documents.

The Logistics Team must create the Inventory Movement document directly from the **Internal Movement** by choosing the **Create Inventory Movement** action.

1. Locate the Internal Movement
	1. Using the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Internal Movement** and choose the related link.
	2. Open the Internal Movement created in the previous step.
	3. Choose the **Create Inventory Movement** action
	4. Confirm you wish to create the movement

This will create a new **Inventory Movement**.

### Register the Inventory Movement
1. Locate the Inventory  Movement
	1. Using the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Inventory Movement** and choose the related link.
	2. Open the Inventory Movement created in the previous step. You will note this document does not have a **Source Document**, and each like on the Internal movement was turned into a pair of lines, one of Action Type **Take** and one of Action Type of **Place**.
	3. Enter the **Qty. to Handle** of the items you wish to move or choose the **Autofill Qty. to Handle** action
	4. Choose the **Register Invt. Movement** action
	5. Confirm you want to Register the document.

> [!NOTE]
> Because this is a logistics operation that does not have any direct financial impact, this is called Register rather than Post.

## See Also
