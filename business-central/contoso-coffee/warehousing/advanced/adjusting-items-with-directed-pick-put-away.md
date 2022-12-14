# Adjusting Items with Directed Pick & Put Away
when items need to be added or removed from inventory using directed pick and put-away, this requires both a warehouse item journal and an item journal to be created and posted. this will raise or lower the inventory for the given item, location, and bin.

## Scenaio
The Logistics team has been told to add 100 PCS to the inventory. They will create a positive adjustment through the warehouse item journal, then complete the process through the item journal.

## Steps

### Create the Warehouse Item Journal
This process will register the change in quantity to the Warehouse.

1.  Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Item Journals** and choose the related link
2.  Choose the **Edit Journal** action
    a.  Enter **WRB-1001** as the **Item No.**.  
    b.  Enter **W-04-0001** as the Bin Code
    c.  Enter **100** as the Quantity
3.  Choose the **Register** action and confirm registration

### Create the Item Journal
This process will complete the adjustment transaction, completing the quantity change and Posting the costs/value.

> [!NOTE]
> If you have also run the Contoso Manufacturing Demo setup, or added the demo data via other means, the item journal in the next process may have existing lines. They should be posted (via the **Post** action) before continuing.

1.  Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Item Journals** and choose the related link
2.  Choose the **Edit Journal** action
3.  Choose the **Calculate Warehouse Adjustment...** action
4.  In the **Calculate Warehouse Adjustment** dialog, enter the **Document No.** as **ADJUST1**
	-  This will create a new line in the item journal from the warehouse entry with the following settings:

    | Entry Type | Positive Adjustment |
    |--|--|
    | Document No. | ADJUST1 |
    | Item No. | WRB-1001 |
    | Location Code | WHITE |
    | Quantity | 100 |

5. Choose the **Post** action

## Results

## See also
