---
title: Count, adjust, and reclassify inventory
description: Learn how to do physical counting and make adjustments and reclassifications.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.date: 06/10/2025
ms.custom: bap-template
---
# Count, adjust, and reclassify inventory using journals

To ensure that your quantities are correct, physically count all of the items in your inventory. Some businesses do an annual physical count, and others count all or only some items more often. After you count items, use journals to post the actual quantities to the general ledger. For example, when you valuate inventory at the end of a period.

To count some items more often than others, perhaps because of their value, use cycle counts. For cycle counts, assign special counting periods to the items. Learn more at [To do cycle counting](inventory-how-count-adjust-reclassify.md#to-do-cycle-counting).

To adjust quantities after a physical count or other purposes, use an item journal to change the inventory ledger entries without posting transactions. You can also adjust the quantity for a single item on an item card.

To change attributes on item ledger entries, use an item reclassification journal. Typical attributes to reclassify include dimensions and sales campaign codes. You can also use reclassification journals for transfers by reclassifying bin and location codes. Special steps apply when you want to reclassify serial or lot numbers and their expiration dates. Learn more at [Work with Serial and Lot Numbers](inventory-how-work-item-tracking.md).

> [!NOTE]
> In multi-step processes, items are registered in bins as warehouse entries, not as item ledger entries. Therefore, you do counting, adjusting, and reclassifying in warehouse journals that support bins. Then you synchronize the new or changed warehouse entries with their related item ledger entries to reflect the changes in inventory quantities and values.

[!INCLUDE [edit-in-excel](includes/edit-in-excel.md)]

## To count physical inventory

To check whether the quantity registered is the same as the physical quantity in stock, count your physical inventory. That is, count the actual items on hand. Typically, counts happen at the end of a fiscal year, but some businesses count items more often. If there are differences, post the actual quantities to the item accounts before you do inventory valuation.

> [!NOTE]
> This procedure describes how to do a physical inventory using a journal on the **Phys. Inventory Journal** page. You can use documents on the **Physical Inventory Order** and **Physical Inventory Recording** pages. These documents offer more control and support for distributing the counting work to multiple employees. Learn more at [Count Inventory Using Documents](inventory-how-count-inventory-with-documents.md).
>
> Note that you can't use the document-based functionality to count items in bins or warehouse entries.

The counting process also involves the following tasks:

- Calculate the expected inventory.
- Print the report you want to use for the count.
- Enter and post the actual quantities.

Depending on your warehouse setup, count physical inventory in one of the following ways. Learn more at [Setting Up Warehouse Management](warehouse-setup-warehouse.md).  

- If your location doesn't use directed put-away and pick, use the **Phys. Inventory Journal** page. The procedure is similar to physical inventory without cycle counting.  
- If your location uses directed put-away and picks, use the **Warehouse Physical Inventory Journal** page. Then use the **Item Journals** page to run the **Calculate Warehouse Adjustment** action. <!--We should say what to do on each of these pages.-->

### To calculate expected inventory in basic warehouse configurations

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Physical Inventory Journals**, and then choose the related link.
2. Choose the **Calculate Inventory** action from **Prepare**.
3. On the **Calculate Inventory** page, specify the conditions to use to create the journal lines, such as whether to include items that have zero recorded inventory.
4. Set filters if you only want to calculate inventory for certain items, bins, locations, or dimensions.
5. Choose the **OK** button.

> [!NOTE]  
> Item entries are processed according to the information that you specified, and lines are created in the physical inventory journal. Notice that the **Qty. (Phys. Inventory)** field has the same quantity as the **Qty. (Calculated)** field. You don't need to enter the counted quantity for items where these values match. However, if the quantity counted differs, enter the quantity that was counted.

### To print the report to be used when counting

1. On the **Physical Inventory Journals** page containing the calculated expected inventory, Choose the **Print** action from **Home**.
2. On the **Physical Inventory List** page, specify whether the report will show the calculated quantity and inventory items by serial and lot numbers.
3. Set filters if you only want to print the report for certain items, bins, locations, or dimensions.
4. Choose **Print**.

Warehouse employees can now count inventory and record any differences on the printed report.

> [!NOTE]
> It can take several days before printed reports come back for final processing and posting. When you specify and post actual counted inventory, the system adjusts inventory to reflect the difference between the expected and the actual counted inventory. You must keep the originally calculated journal lines and not recalculate the expected inventory, because the expected inventory may change and lead to incorrect inventory levels. If you need to issue multiple reports, such as for different locations or group of items, you must create and keep separate journal batches.

### To enter and post the actual counted inventory in basic warehouse configurations

1. On each line on the **Physical Inventory Journals** page where the actual inventory on hand, as determined by the physical count, differs from the calculated quantity, enter the actual inventory on hand in the **Qty. (Phys. Inventory)** field.
  
  > [!NOTE]  
  > If the physical count reveals differences caused by items posted with incorrect locations, don't enter the differences in the physical inventory journal. Instead, use a reclassification journal or a transfer order to redirect the items to the correct locations. 

2. To adjust the calculated quantities to the actual counted quantities, choose the **Post** action from **Home**.

    Posting creates item ledger entries and physical inventory ledger entries. Open the Item Card page for the item to find its physical inventory ledger entries.

3. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.
4. To verify the count, open the **Item Card** page for the item, and choose the **Phys. Inventory Ledger Entries** action from **Item**

### To calculate the expected inventory in advanced warehouse configurations

Synchronize item ledger and warehouse data before you count physical inventory. Otherwise, what you post to the physical inventory journal and item ledger is the physical inventory results combined with other warehouse adjustments for the items. Learn more at [Synchronize quantities in the item ledger and warehouse](inventory-how-count-adjust-reclassify.md#to-synchronize-the-adjusted-warehouse-entries-with-the-related-item-ledger-entries).

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Physical Inventory Journal**, and choose the related link.  
2. Choose the **Calculate Inventory** action to open the **Whse. Calculate Inventory** page.  
3. Set the filters to specify the items to count in the journal, and then choose **OK**.

   [!INCLUDE [prod_short](includes/prod_short.md)] creates a line for each bin that meets the filter requirements. You can delete lines, but if you want to post the results as a physical inventory, count the item in all the bins that contain it.  

   If you only count an item in some bins but not others, you can enter differences and post them in the **Item Journal** page later by using the **Calculate Warehouse Adjustment** action.  

### To enter and post the actual counted inventory in advanced warehouse configurations

1. On the **Warehouse Physical Inventory Journal** page, enter the actual quantities in the **Qty. (Phys. Inventory)** field.  

    > [!NOTE]  
    > The **Qty. (Calculated)** field is filled in based on bin records. This quantity is copied to the **Qty. (Physical)** field on each line. If the quantities in these fields don't match, enter the actual quantity.  

2. After you enter all actual quantities, choose the **Register** action.  

    When you register the journal, [!INCLUDE [prod_short](includes/prod_short.md)] creates two warehouse entries in the warehouse register for every line that was counted and registered:  

    - If the calculated and the actual quantities differ, a negative or positive quantity is registered for the bin, and a balancing quantity is posted to the location's adjustment bin.  
    - If the calculated quantity equals the physical quantity, [!INCLUDE [prod_short](includes/prod_short.md)] registers **0** for both the bin and the adjustment bin.

When you register physical inventory, you don't post to the item, physical inventory, or the value ledgers. However, the records are available for reconciliation when needed. To keep quantities accurate, after you count items in all bins, post the results.<!--physical inventory journal--> Learn more at [Synchronize quantities in the item ledger and warehouse](inventory-how-count-adjust-reclassify.md#to-synchronize-the-adjusted-warehouse-entries-with-the-related-item-ledger-entries).

## To do cycle counting

You can count items as often as you'd like. For example, because they're more valuable or top sellers. Specify the counting frequency by assigning special counting periods to the items.

Depending on your warehouse setup, you can do cycle counting in the following ways. Learn more at [Setting Up Warehouse Management](warehouse-setup-warehouse.md).  

- If your location doesn't use directed put-away and picks, use the **Physical Inventory Journal** page. The steps are similar to counting physical inventory without cycle counting.  
- If your location uses directed put-away and picks, use the **Warehouse Physical Inventory Journal** page. Then use the **Item Journals** page to run the **Calculate Warehouse Adjustment** action.  

### To set up counting periods

Counting physical inventory is typically a recurring task, for example monthly, quarterly, or annually. You can set up the inventory counting periods you need and assign one to each item. Afterward, use the **Calculate Counting Period** action on the **Physical Inventory Journal** page to automatically create lines for the items.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Physical Inventory Counting Periods**, and then choose the related link.  
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

### To assign a counting period to an item

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.  
2. Select the item to which you want to assign a counting period.  
3. In the **Phys Invt Counting Period Code** field, select the counting period.  

> [!NOTE]
> If you're changing the counting period, a message displays information about the results of the change. Choose **Yes** to change the code and calculate the first counting period for the item. The next time you choose to calculate a counting period in the physical inventory journal, the item appears as a line on the **Phys. Invt. Item Selection** page. You can then count the item periodically.

### To start a count based on counting periods in basic warehouse configurations

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Physical Inventory Journal**, and then choose the related link.
2. Choose the **Calculate Counting Period** action.

    The **Phys. Invt. Item Selection** page shows items that need to be counted according to their counting periods.
3. Count the physical inventory. Learn more at [To count physical inventory](inventory-how-count-adjust-reclassify.md#to-count-physical-inventory).

### To start a count based on counting periods in advanced warehouse configurations

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Physical Inventory Journal**, and choose the related link.  
2. Choose the **Calculate Counting Period** action.

    The **Phys. Invt. Item Selection** page show items need to be counted according to their counting periods.
3. Count the physical inventory. Learn more at [To count physical inventory](inventory-how-count-adjust-reclassify.md#to-count-physical-inventory).  

   > [!NOTE]  
   > Count the item in all bins that contain it. If you delete bin lines that were retrieved for counting on the **Whse. Phys. Inventory** page, the count will be incorrect when you post it in a physical inventory journal.  

## To adjust the quantity of one item

After you do a physical count of an item, use the **Adjust Inventory** action to record the actual inventory quantity.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.
2. Select the item for which you want to adjust inventory, and then choose the **Adjust Inventory** action.
3. In the **New Inventory** field for the location, enter the result of the count.
4. Choose the **OK** button.

The item’s inventory is adjusted. The new quantity is shown in the **Quantity on Hand** field on the **Item Card** page.

You can also use the **Adjust Inventory** action as an easy way to add purchased items to inventory if you don't use purchase invoices or orders to record your purchases. Learn more at [Record Purchases](purchasing-how-record-purchases.md).

> [!NOTE]  
> After you adjust inventory, update its current value. Learn more at [Revalue Inventory](inventory-how-revalue-inventory.md).

### To adjust the quantities of multiple items in basic warehouse configurations

On the **Item Journals** page, you can post item transactions directly to adjust inventory for purchases, sales, and positive or negative changes without using documents.

If you often use the item journal to post the same or similar journal lines, for example, for material consumption, the **Standard Item Journal** page can make this recurring work easier. Learn more at [Work with Standard Journals](ui-work-general-journals.md#work-with-standard-journals).

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Item Journals**, and then choose the related link.
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Choose the **Post** action to adjust the quantities.

### To adjust bin quantities in advanced warehouse configurations

If your location uses directed put-away and picks, use the **Warehouse Item Journal** page to post unplanned positive and negative quantity changes. For example, for items posted as missing that show up unexpectedly, or losses due to breakage.  

Warehouse item journals give you more levels of adjustment to make your quantities more precise. The warehouse knows how many items are on hand and where they're stored, but each adjustment isn't posted to the item ledger. Credits or debits are made to the real bin with the quantity adjustment. A balancing entry is made in an adjustment bin. The adjustment bin is a virtual bin with no real items. You specify the virtual bin in the **Invt. Adjustment Bin Code** field on **Location Card** pages.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Item Journal**, and then choose the related link.  
2. Fill in the header information.  
3. In the **Item No.** field on the line, choose the item.  
4. Enter the bin in which you're putting the extra items or where items are missing.  
5. In the **Quantity** field, if you find extra items, enter a positive quantity. If items are missing, enter a negative quantity.  
6. Choose the **Register** action.

## To synchronize the adjusted warehouse entries with the related item ledger entries

Post the adjustment bin records in the item ledger for the defined periods. Some companies post daily adjustments to the item ledger, while others reconcile less often.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Item Journal**, and then choose the related link.  
2. Fill in the fields on each journal line.  
3. Choose the **Calculate Warehouse Adjustment** action, and then add filters on the **Calculate Warehouse Adjustment** page. Adjustments are calculated only for the entries in the adjustment bin that meet the filter requirements.  
4. On the **Options** FastTab, fill in the **Document No.** field with a number. The number displays on the item journal lines.
5. Choose **OK**. The positive and negative adjustments are totaled for each item, and lines are created in the item journal.  
6. Post the journal lines to enter the quantity differences in the item ledger. The quantities in the bins and the item ledger now match.  

## Related information

[CountInventory Using Documents](inventory-how-count-inventory-with-documents.md)  
[Inventory](inventory-manage-inventory.md)  
[Warehouse Management Overview](design-details-warehouse-management.md)  
[Sales](sales-manage-sales.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
