# Adding Users as Warehouse Employees
Warehouse operations allow Users to be configured to access specific locations.  This is managed through the **Warehouse Employees**.

For each Location a User should have access to, they must have a record in the Warehouse Employee table for the Location.

## Set up User for a Location

1. Using the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Employee** and choose the related link.
2. Choose the **New** action
3. For each scenario Location (**SILVER**, **YELLOW** and **WHITE**), for each User that will run through the Scenarios, create a record.  For example, for a user named ADMIN, you would add:

    |User ID|Location|Default|
    |:--|:--|:--|
    |ADMIN|SILVER|Enabled|
    |ADMIN|YELLOW|Disabled|
    |ADMIN|WHITE|Disabled|

## See Also

[Set Up Warehouse Employees](../../warehouse-how-to-set-up-warehouse-employees.md)