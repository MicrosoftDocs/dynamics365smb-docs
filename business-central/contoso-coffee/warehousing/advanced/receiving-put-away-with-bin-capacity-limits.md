# Receiving & Put-Away with Bin Capacity Limits
A Logistics team can configuration capacities on bins, in volume, weight, or quantities. During the put away process, this will ensure that the items do not exceed the known limits of the bins selected for storing the inventory.

## Scenario
In this scenario, the bin W-02-0001 in the WHITE location has been configured with a volume and weight limit of 15000. A purchase order was set up to receive a Pallet, which will be more than the capacity of the bin.

## Steps

### Prepare the Purchase documentsa
When Purchasing is ready to hand the **Purchase Order** documents to the Logistics team, they must **Release** the purchase orders for these next steps.

1. Release the purchase order
    1. Release the purchase order **107010**
    2. Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders** and choose the related link.
    3. Locate order 107010 and select it.
    4. Choose the **Release** action.

### Create the Warehouse Receipt
In this scenario, the Logistics team is creating a warehouse receipt for multiple incoming purchase orders, so they will create the warehouse receipt, then select the purchase orders wanted.

1. Create the warehouse receipt
    1. Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Receipts** and choose the related link.
    2. Choose the **New** action
    3. On the warehouse receipt page, press Enter to have a warehouse receipt number automatically selected.
    4. Enter the **Location Code** as **WHITE**
2. Select the source document
    1. Choose the **Get Source Documents...** action
    2. Using multiple selection mode, select purchase order 107010 and choose the **OK** button.
    3. The Lines will contain a new entry for each purchase order line.
    4. The bin code for the lines will be the receiving bin, as configured on the location card, which will be **W-08-0001**

### Post the Warehouse Receipt
When the Logistics team has received the items, the warehouse receipt should be updated (with **Qty. to Receive**) and posted.
1. Update the document
	1. On the warehouse receipt page, review the **Lines** section and update the **Qty. to Receive** for each line. Alternatively, if the warehouse receipt is being received in its entirety, you may choose the **Autofill Qty. to Receive** action.
2. Choose the **Post** action.

### Register the Warehouse Put-Away
Once the Logistics team has processed the incoming items however necessary, they need to make the items available by putting them away.

> [!NOTE]
> When the warehouse receipt is posted, the put-away is created automatically. However, if the put-away was deleted or not created automatically due to system configuration, you can create **Put-Away** on the **Posted Whse. Receipt** page for the receipt involved.

1. Register the warehouse put-away
    1. Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Put-Away** and choose the related link.
    2. Locate the warehouse put-away document created from your Warehouse Receipt and open it
    3. On the **Warehouse Put-Away** page, review the **Lines** section

At this stage, the bin capacity logic is revealed. the warehouse put-away lines will have at least 3 lines:
   - A Take line to move the PALLET quantities from the receiving bin (W-08-0001)
   - A Place line that will move a partial quantity into the default bin (W-04-0001)
   - A Place line that will move the remaining quantity, but no bin will have been selected

This is because the default bin cannot contain the full receipt quantity. If you try to set line #3 to have the default bin of W-04-0001, you will receive a warning that this will exceed the bin capacity.

> [!NOTE]
>  Bin capacity checks are controlled the **Bin Capacity Policy** on the **Location Card**. In our scenario, bin W-04-0001 is configured to **Prohibit More Than Max. Cap.** so it will not be possible to register the pick using Bin W-04-0001 for all the lines.

2. Complete the pick registration:
   1. Update Line #3 to use bin **W-04-0003**.
   2. Update the **Qty. to Handle** for each line. Alternatively, if the order is being received in its entirety, you may chcoose the **Autofill Qty. to Handle** action.
   3. Choose the **Register** action.

## Results
- a posted warehouse receipt will be created   
- a posted warehouse put-away will be created   
- a posted purchase receipt will be created for the purchase order selected
- each selected purchase order will have the **Quantity Received** updated for the line received    
- the item **Inventory** will be increased by the total quantity of all lines received    
- the **Bin Contents** for the item will reflect the new **PALLET** lines in the bins selected

## See Also


