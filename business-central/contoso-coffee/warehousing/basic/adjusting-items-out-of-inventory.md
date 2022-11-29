# Adjusting Items into or out of Inventory
When Items need to be added or removed from Inventory, this requires an Item Journal to be created and posted.  This will raise or lower the Inventory for the given Item, Location, and Bin.

## Scenario
The Logistics team has been told to add 20 bags of coffee to the Inventory. They will create a Positive Adjustment through the Item Journal.

## Steps 
1. Using the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter Item Journal and choose the related link.
2. On a new line, fill in the fields as described in the following table:

    |Field| Value |
    |--|--|
    | Entry Type | Positive  Adjmt. |
    | Item No.| WRB-1000 |
    | Location Code | SILVER |
    | Bin Code | S-01-0001 |
    | Quantity | 20 |
        
3. Choose the **Post** action and Confirm.

> [!NOTE]
> You will have to personalize the Item Journal to show the **Bin Code** field.

## Results
 - The Item **Inventory**  will be increased by the chosen quantity, which will also be clear in the **Item Availability by Location** and **Bin Contents** actions from the Item Card.

## See Also