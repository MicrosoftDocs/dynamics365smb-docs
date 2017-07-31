---
title: Count, Adjust, and Reclassify Inventory| Microsoft Docs
description: Describes how to perform physical counting, make negative or positive adjustments, and how to change information, such as location or lot number, on item ledger entries or warehouse entries.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: adjustment, negative, positive, increase, decrease
ms.date: 06/02/2017
ms.author: sgroespe

---
# How to: Count, Adjust, and Reclassify Inventory
At least once every fiscal year you must take a physical inventory, that is, count all the items on inventory, to see if the quantity registered in the database is the same as the actual physical quantity in the warehouses. When the actual physical quantity is known, it must be posted to the general ledger as a part of period-end valuation of inventory.

Although you count all items in inventory at least once a year, you may have decided to count some items more often, perhaps because they are more valuable, or because they are very fast movers and a large part of your business. For this purpose, you can assign special counting periods to those items. For more information, see the "To perform cycle counting" section.

If you need to adjust recorded inventory quantities, in connection with counting or for other purposes, you can use an item journal to change the inventory ledger entries directly without posting business transactions. Alternatively, you can adjust for a single item on the item card.

If you need to change attributes on item ledger entries as well as the quantities, you can use the item reclassification journal. Typical attributes to reclassify include serial/lot numbers, expiration dates, and dimensions.

## To perform a physical inventory
You must take a physical inventory, that is, count the actual items on hand, to check if the quantity registered is the same as the physical quantity in stock at the end of a fiscal year, if not more often. If there are differences, you must post them to the item accounts before you do the inventory valuation.

Apart from the physical counting task, the complete process involves the following three tasks:

- Calculate the expected inventory.
- Print the report to be used when counting.
- Enter and post the actual counted inventory.

### To calculate the expected inventory
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Phys. Inventory Journals**, and then choose the related link.
2. Choose the **Calculate Inventory** action.
3. In the **Calculate Inventory** window, specify the conditions to use to create the journal lines, such as whether to include items that have zero recorded inventory.
4. Set filters if you only want to calculate inventory for certain items, bins, locations, or dimensions.
5. Choose the **OK** button.

> [!NOTE]  
>   The item entries are processed according to the information that you specified, and lines are created in the physical inventory journal. Notice that the **Qty. (Phys. Inventory)** field is automatically filled in with the same quantity as the **Qty. (Calculated)** field. With this feature, it is not necessary for you to enter the counted inventory on hand for items that are the same as the calculated quantity. However, if the quantity counted differs from what is entered in the **Qty. (Calculated)** field, you must overwrite it with the quantity actually counted.

### To print the report used when counting
1. In the **Phys. Inventory Journal** window containing the calculated expected inventory, Choose the **Print** action.
2. In the **Phys. Inventory List** window, specify if the report should show the calculated quantity and if the report should list inventory items by serial/lot numbers.
3. Set filters if you only want to print the report for certain items, bins, locations, or dimensions.
4. Choose the **Print** button.

Employees can now proceed to count inventory and record any discrepancies on the printed report.

### To enter and post the actual counted inventory
1. On each line in the **Phys. Inventory Journal** window where the actual inventory on hand, as determined by the physical count, differs from the calculated quantity, enter the actual inventory on hand in the **Qty. (Phys. Inventory)** field.

    The related fields are updated accordingly.

    > [!NOTE]  
>   If the physical count reveals differences that are caused by items posted with incorrect location codes, do not enter the differences in the physical inventory journal. Instead, use the reclassification journal or a transfer order to redirect the items to the correct locations. For more information, see Item Reclass. Journal or How to: Create Transfer Orders.

2. To adjust the calculated quantities to the actual counted quantities, choose the **Post** action.

    Both item ledger entries and physical inventory ledger entries are created. Open the item card to view the resulting physical inventory ledger entries.

3. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Items**, and then choose the related link.
4. To verify the inventory counting, open the item card in question, and then, choose the **Phys. Inventory ledger Entries** action.

# To perform cycle counting
Although you count all items in inventory at least once a year, you may have decided to count some items more often, perhaps because they are more valuable, or because they are very fast movers and a large part of your business. For this purpose, you can assign special counting periods to those items.

> [!NOTE]  
>   If your location is set up for directed put-away and pick, then you first use the **Whse. Phys. Invt. Journal** window, and then you use the **Calculate Whse. Adjustment** function in the **Item Journal** window.

## To set up counting periods
A physical inventory is typically taken at some recurring interval, for example monthly, quarterly, or annually. You can set up whatever inventory counting periods necessary.

You set up the inventory counting periods that you want to use and then assign one to each item. When you perform a physical inventory and use the **Calculate Counting Period** in the physical inventory journal, lines for the items are created automatically.

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Phys. Invt. Counting Periods**, and then choose the related link.  
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## To assign a counting period to an item  
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Items**, and then choose the related link.  
2. Select the item to which you want to assign a counting period.  
3. In the **Phys Invt Counting Period Code** field, select the appropriate counting period.  
4. Choose the **Yes** button to change the code and calculate the first counting period for the item. The next time you choose to calculate a counting period in the physical inventory journal, the item appears as a line in the **Phys. Invt. Item Selection** window. You can then begin to count the item on a periodic basis.

## To initiate a count based on counting periods
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Phys. Inventory Journal**, and then choose the related link.
2. Choose the **Calculate Counting Period** action.

    The **Phys. Invt. Item Selection** window opens showing the items that have counting periods assigned and need to be counted according to their counting periods.
3. Perform the physical inventory. For more information, see the "To perform a physical inventory" section.

## To adjust the inventory of one item
After you have made a physical count of an item in your inventory area, you can use the **Adjust Inventory** function to record the actual inventory quantity.

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Items**, and then choose the related link.
2. Select the item for which you want to adjust inventory, and then choose the **Adjust Inventory** action.
3. In the **New Inventory** field, enter the inventory quantity that you want to record for the item.
4. Choose the **OK** button.

The item’s inventory is now adjusted. The new quantity is shown in the **Current Inventory** field in the **Adjust Inventory** window and in the **Inventory** field in the **Item Card** window.

You can also use the **Adjust Inventory** function as a simple way to place purchased items on inventory if you do not use purchase invoices or orders to record your purchases. For more information, [How to: Record Purchases](purchasing-how-record-purchases.md).

> [!NOTE]  
>   After you have adjusted inventory, you must update it with the current, calculated value. For more information, see [How to: Revalue Inventory](inventory-how-revalue-inventory.md).

## To adjust the inventory quantity of one or more items
In the **Item Journal** window, you can post item transaction directly to adjust inventory in connection with purchases, sales, and positive or negative adjustments without using documents.

If you often use the item journal to post the same or similar journal lines, for example, in connection with material consumption, you can use the **Standard Item Journal** window to make this recurring work easier. For more information, see the "Standard Journals" section in [Working with General Journals](ui-work-general-journals.md).

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Item Journals**, and then choose the related link.
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Choose the **Post** action to make the inventory adjustments.

> [!NOTE]  
>   After you have adjusted inventory, you must update it with the current, calculated value. For more information, see [How to: Revalue Inventory](inventory-how-revalue-inventory.md).

## To reclassify an item's lot number
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Item Reclass. Journals**, and then choose the related link.
2. In the **Item Reclass. Journal** window, fill in the fields as necessary.
3. To In the **Lot No.** field, enter the items current lot number.
4. In the **New Lot No.** field, enter the item's new lot number.
5. Choose the **Post** action.

## See Also
[Inventory](inventory-manage-inventory.md)  
[Sales](sales-manage-sales.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
