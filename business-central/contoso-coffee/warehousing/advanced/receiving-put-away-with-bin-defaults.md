# Receiving & Put-Away with Bin Defaults

Assigning default bins to your items can make the process of shipping, receiving, and moving your items much easier. When a default bin is assigned to an item, this bin is suggested every time you initiate a transaction for this item.

## Scenario 
The Logistics team has a new item WRB-1001 they’re planning for in the Warehouse.  They will set up the default bin for the item, then receive the first purchase order for it.

## Steps

### Assign the Default Bin

1. Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do")  icon, enter **Items** and choose the related link.
2. Locate the **WRB-1001** item and open the item card.
3. Choose the **Bin Content** action.
4. Enter a new bin content:

    | Location Code | WHITE |
    |--|--|
    | Bin Code | W-02-0003 |
    | Default | Enabled |
    | Unit of measure Code | PCS |

### Prepare the Purchase Documents 
When Purchasing is ready to hand the **Purchase Order** documents to the Logistics team, they must **Release** the purchase orders for these next steps.

1. Release the purchase order **107006**
    1. Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders** and choose the related link.
    2. Locate order 107006 and select it.
    3. Choose the **Release** action.
2. Repeat this process for purchase order **107007**.

### Create the Warehouse Receipt
In this scenario, the Logistics team is creating a warehouse receipt for multiple incoming purchase orders, so they will create the warehouse Receipt, then select the purchase orders wanted.

1. Create the warehouse receipt
    1. Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Receipts** and choose the related link.
    2. Choose the **New** action
    3. On the warehouse receipt page, press Enter to have a warehouse receipt number automatically selected.
    4. Enter the **Location Code** as **WHITE**.
1. Select the source document
    1. Choose the **Get Source Documents...** action
    2. Using multiple selection mode, select purchase orders 107006 and 107007 from the list and choose the **OK** button.
    3. The lines will contain a new entry for each purchase order line.
    4. The bin code for the lines will be the receiving bin, as configured on the location card, which will be **W08-0001**

### Post the Warehouse Receipt
When the Logistics team has received the items, the warehouse receipt should be updated (with **Qty. to Receive**) and Posted.

1. Update the document
	1. On the warehouse receipt page, review the **Lines** section and update the **Qty. to Receive** for each line. Alternatively, if the warehouse receipt is being received in its entirety, you may choose **Autofill Qty. to Receive** action.
2. Choose the **Post** action.
3. Confirm the **Receive** option.

### Register the Warehouse Put-Away
Once the Logistics team has processed the incoming items however necessary, they need to make the items available by putting them away.

> [!NOTE]
> When the warehouse receipt is posted, the put-away is created automatically. However, if the put-away was deleted or not created automatically due to system configuration, you can **Create Put-Away** on the **Posted Whse. Receipt** page for the receipt involved.

3. Register the warehouse put-away
    1. Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Put-Away** and choose the related link.
    2. Locate the warehouse put-away document created from your warehouse receipt and open it
    3. On the **Warehouse Put-Away** page, review the **Lines** section and update the **Qty. to Handle** for each line. Alternatively, if the order is being received in its entirety, you may choose the **Autofill Qty. to Handle** action.
    4. The **Take** lines will be set to the receiving bin, W-08-0001. The **Place** lines will be set to the default bin configured, **W-04-0001**.
    5. Choose the **Register** action.

## Results
- a posted warehouse receipt will be created
- a posted warehouse put-away will be created
- a posted purchase receipt will be created for each purchase order selected
- each selected purchase order will have the **Quantity Received** updated for the lines received
- the item **Inventory** will be increased by the total quantity of all lines received
- the item will be placed in the default bin set, which will be visible via the **Bin Contents** from the item card

## See Also
