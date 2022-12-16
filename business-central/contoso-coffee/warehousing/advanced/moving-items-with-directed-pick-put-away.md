# Moving Items with Directed Pick & Put Away
To move items from one bin to another in a location using directed pick and put-away, a movement worksheet is used to plan and create the movement document.

## Scenaio
The Logistics team needs to relocate 2 PCS of item WRB-1001 from one bin to another.

> [!IMPORTANT]
> To complete this scenario, you must first complete the **Adjusting Items with Directed Pick & Put Away** scenario.

## Steps

### Create the Movement Worksheet

1.  Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Movement Worksheets** and choose the related link
2.  Choose the **Edit Worksheet** action
    1.  Enter following information:
   
    | Item No. | WRB-1001 |
    |--|--|
    | From Bin Code | W-04-0001 |
    | To Bin Code | W-04-0003 |
    | Quantity | 2 |
    2.  Choose the **Create Movement** action and confirm to create the document.
    
A warehouse movement will be created, and the warehouse journal line will be removed.

### Post the Movement
1.  Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Movements** and choose the related link
2.  Open the warehouse movement you just created
3.  Update the document
	1.  On the warehouse movement page, review the **Lines** section and update the **Qty. to Handle** if you need to move less. You may also choose the **Autofill Qty. to Handle** action.
4.  Choose the **Register Movement** action.

## Results
- A **Registered Warehouse Movement** will be added to the registered warehouse movement list
- The item will still have the same **Inventory** level as the start, with the **Bin Contents** showing the 2 PCS in the **W-04-0003** bin.

## See also
[Design Details: Warehouse Management](../../../design-details-warehouse-management.md)
[Design Details: Internal Warehouse Flows](../../../design-details-internal-warehouse-flows.md)
[Move Items in Advanced Warehouse Configurations](../../../warehouse-how-to-move-items-in-advanced-warehousing.md)
[View the Availability of Items](../../../inventory-how-availability-overview.md)