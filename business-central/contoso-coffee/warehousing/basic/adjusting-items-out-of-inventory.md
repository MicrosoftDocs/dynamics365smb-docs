# Adjusting Items into or out of Inventory
When items need to be added or removed from inventory, this requires an item journal to be created and posted.  This will raise or lower the inventory for the given item, location, and bin.

## Scenario
The Logistics team has been told to add 20 bags of coffee to the inventory. They will create a positive adjustment through the item journal.

## Steps 
1. Using the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter item journal and choose the related link.
2. On a new line, fill in the fields as described in the following table:

    |Field| Value |
    |--|--|
    | Entry Type | Positive  Adjmt. |
    | Item No.| WRB-1000 |
    | Location Code | SILVER |
    | Bin Code | S-01-0001 |
    | Quantity | 20 |
        
3. Choose the **Post** action and confirm.

> [!NOTE]
> You will have to personalize the item journal to show the **Bin Code** field.

## Results
 - The item **Inventory** will be increased by the chosen quantity, which will also be clear in the **Item Availability by Location** and **Bin Contents** actions from the item card

## See Also
[Count, Adjust, and Reclassify Inventory Using Journals]: (../../../inventory-how-count-adjust-reclassify.md)