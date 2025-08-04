---
title: Count and adjust inventory
description: Describes how to count physical inventory and use inventory documents to adjust on-hand inventory.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: adjustment, status, negative, positive, increase, decrease, inventory
ms.search.forms: 5895, 6561, 6562, 6563, 6564, 6565, 6566, 5892, 5891, 5879, 5880, 5893, 5897, 5882, 5881, 5899, 5875, 5878, 5877, 5876, 5896, 6567, 6568, 6569, 6570, 6571, 6572, 5883, 5886, 884, 5898, 5885, 5890, 5888, 5889, 5887, 5894, 6774, 6775, 6776, 6780, 6781, 6782, 6783
ms.date: 04/19/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Count and adjust inventory using documents

You can take a physical inventory of your items by using physical inventory order and physical inventory recording documents. The **Physical Inventory Order** page is used to organize the complete inventory counting project, for example one per location. Use the **Phys. Inventory Recording** page capture and communicate the actual count of items. You can create multiple recordings for one order, for example, to distribute groups of items to different employees.

You can print the **Physical Invt. Recording** report from each recording, and it contains empty quantity fields where you can enter the counted inventory. When you're done counting and the quantities are entered on the **Phys. Inventory Recording** page, choose the **Finish** action. This action transfers the quantities to the related lines on the **Physical Inventory Order** page. [!INCLUDE [prod_short](includes/prod_short.md)]ensures that you can't record an item count twice.  

> [!NOTE]
> Using documents to perform a physical inventory count provides more control and supports distributing the counting to multiple employees. You can also use journals to perform the task, such as the **Phys. Inventory Journals** and **Whse. Phys. Inventory Journals** pages. To learn more, go to [Count, Adjust, and Reclassify Inventory Using Journals](inventory-how-count-adjust-reclassify.md). This article describes how to use documents to do a physical inventory count.
>
> If you're using zones in your warehouse, you can't use physical inventory orders. Instead, use the **Whse. Phys. Inventory Journal** page to count your warehouse entries before you synchronize them with item ledger entries.

Counting inventory by using documents consists of the following overall steps:

1. Create a physical inventory order with expected item quantities prefilled.
2. Generate one or more physical inventory recordings from the order.
3. Enter the counted item quantities on the recordings, as captured on print-outs, for example, and set it to **Finished**.
4. Complete and post the physical inventory order.

## To create a physical inventory order

A physical inventory order is a complete document that consists of a physical inventory order header and order lines. The information on a physical inventory header describes how to take the physical inventory. The order lines contain the information about the items and their locations.

To create the physical inventory order lines, you typically use the **Calculate Lines** action to add the current inventory as lines on the order. You can also use the **Copy from Document** action to fill in the lines with the content of another open or posted physical inventory order. The following procedure only describes how to use the **Calculate Lines** action.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Physical Inventory Orders**, and then choose the related link.
2. Choose the **New** action.
3. Fill in the required fields on the **General** FastTab. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. On the **Actions** tab, in the **Functions** group, choose **Other**, and then choose **Calculate Lines**.
5. Select options as necessary.
6. Set filters, for example, to only include a subset of items to count with the first recording.

    > [!TIP]
    > To plan for multiple employees to count the inventory, set different filters each time you use the **Calculate Lines** action to fill in the order with the subset of inventory items that a user will record. Then, as you generate multiple physical inventory recordings for multiple employees, you minimize the risk of counting items twice. To learn more, go to [To create a physical inventory recording](#to-create-a-physical-inventory-recording).

7. Choose the **OK** button.

A line for each item that exists on the chosen location and per the set filters and options is added to the order. For items that are set up for item tracking, the **Use Item Tracking** checkbox is selected and information about the expected quantity of serial and lot numbers is available by choosing **Lines**, and then **Item Tracking Lines**. To learn more, go to [Handle item tracking when counting inventory](#handle-item-tracking-when-counting-inventory).

You can now create one or more recordings, which are instructions to the employees who do the counting.  

> [!NOTE]
> If you use package-specific tracking, you can also use documents to count and adjust inventory with package numbers. To start using this feature, you must turn on **Feature Update: Enable use of package tracking in physical inventory orders** on the **Feature Management** page. Existing physical inventory orders are updated, however, [!INCLUDE [prod_short](includes/prod_short.md)] can't populate the **Package No.** field. You must recreate these lines using the **Calculate Lines** action on the **Physical Inventory Order** page.
>
> You can enter the package number for items where package tracking is needed on the **Phys. Inventory Recording Lines** page. Choose **Finish** to finalize recording.
>
> After you choose **Finish** on the **Physical Inventory Order** page, [!INCLUDE [prod_short](includes/prod_short.md)] calculates differences with respect to the package and other item tracking details, and makes positive or negative adjustments.

## To create a physical inventory recording

For each physical inventory order, you can create one or more physical inventory recording documents on which employees enter the counted quantities. Employees can enter quantities either manually, or with a scanning device.

By default, a recording is created for all the lines on the related physical inventory order. To avoid that two employees count the same items if you distribute counting, gradually fill in the physical inventory order by setting filters on the **Calculate Lines** batch job. Then create the physical inventory recording with the **Only Lines Not in Recordings** checkbox selected. This setting ensures that each new recording contains different items than those on other recordings.

For manual counting, you can print the **Phys. Invt. Recording** report, which has an empty column where warehouse employees can write the counted quantities. When counting is complete, you enter the recorded quantities on the related lines on the **Phys. Inventory Recording** page. Lastly, you transfer the recorded quantities to the related physical inventory order by setting the status to **Finished**.

1. On a **Physical Inventory Order** page that contains lines for the items to be counted in one recording, you need to choose the **Make New Recording** action.
1. On the **Actions** tab, in the **Functions** group, choose **Other**, and then choose **Make New Recording**.
1. Select options and set filters as necessary.
1. Choose the **OK** button.
1. For every set of items to be counted, load them on the related physical inventory order and repeat steps 1 through 3 with the **Only Lines Not in Recordings** checkbox selected.
1. On the **Related** tab, choose **Order**, and then choose the **Recordings** action to open the **Phys. Inventory Recording List** page.
1. Open the relevant recording.
1. On the **General** FastTab, fill in the fields as necessary.
1. For items that use item tracking, create an additional line for each lot number or serial number code by choosing the **Functions** action, and then the **Copy Line** action. To learn more, go to [Handle item tracking when counting inventory](#handle-item-tracking-when-counting-inventory).  
1. Choose the **Print** action to prepare the physical document that employees can use to note the quantities they count.

## To finish a physical inventory recording

After employees count the quantities, record the quantities in [!INCLUDE [prod_short](includes/prod_short.md)].

1. From the **Phys. Inventory Recording List** page, select the physical inventory recording that you want to finish, and then choose the **Edit** action.
2. On the **Lines** FastTab, fill the actual counted quantity in the **Quantity** field for each line.
3. For items with serial or lot numbers (the **Use Item Tracking** checkbox is selected), enter the counted quantities on the lines for the item's serial and lot numbers respectively. To learn more, go to [Handle item tracking when counting inventory](#handle-item-tracking-when-counting-inventory).
4. Select the **Recorded** checkbox on each line.
5. When you have entered all data for a physical inventory recording, choose the **Finish** action. Note that all lines must have the **Recorded** checkbox selected.

    > [!NOTE]
    > When you finish a physical inventory recording, each line is transferred to the line on the related physical inventory order that matches it exactly. To match, the values in the **Item No.**, **Variant Code**, **Location Code**, and **Bin Code** fields must be the same on the recording and the order lines.>
    > 
    > If a matching physical inventory order line doesn't exist, and if the **Allow Recording Without Order** checkbox is selected, a new line is added and the **Recorded Without Order** checkbox on the related physical inventory order line is selected. Otherwise, an error message displays and the process is canceled.>
    > If more than one physical inventory recording lines match a physical inventory order line, then a message displays and the process is canceled. If, for some reason, two identical physical inventory lines end up on the physical inventory order, you can use a action to resolve it. To learn more, go to [To find duplicate physical inventory order lines](#to-find-duplicate-physical-inventory-order-lines).

## To complete a physical inventory order

After you finish a physical inventory recording, the **Qty. Recorder (Base)** field on the related physical inventory order is updated with the counted (recorded) values, and the **On Recording Lines** checkbox is selected. If a counted quantity differs from the expected quantity, the **Pos Qty. (Base)** and **Neg Qty. (Base)** fields show the difference.

To access the expected quantities and any recorded differences for items with item tracking, choose the **Lines** action, and then choose **Item Tracking Lines** to select various views for the serial and lot numbers in the physical inventory count.

You can also choose the **Phys. Inventory Order Diff.** action to view any differences between the expected quantity and the counted quantity.

### To find duplicate physical inventory order lines

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Physical Inventory Orders**, and then choose the related link.
2. Open the physical inventory order to view duplicate lines for.
1. On the **Related** tab, choose **Other**, and then choose **Show Duplicate Lines**.

Duplicate physical inventory order lines display so that you can delete them and keep only one line with a unique set of values in the **Item No.**, **Variant Code**, **Location Code**, and **Bin Code** fields.

### To post a physical inventory order

After you complete a physical inventory order and change its status to **Finished**, you can post it. You can only set the status of a physical inventory order to **Finished** under the following conditions:

- All related physical inventory recordings have a status of **Finished**.
- Each physical inventory order line is counted by at least one inventory recording line.
- The **In Recording Lines** and the **Qty. Exp. Calculated** checkboxes are selected for all physical inventory order lines.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Physical Inventory Orders**, and then choose the related link.
2. Select the physical inventory order that you want to complete, and then choose the **Edit** action.

    On the **Physical Inventory Order** page, the quantity recorded shows in the **Qty. Recorded (Base)** field.
3. Choose the **Finish** action.

    The value in the **Status** field is **Finished**. You can now only change the order by choosing the **Reopen** action.
4. To post the order, choose the **Post** action, and then choose the **OK** button.

    The item ledger entries are updated along with any related item tracking entries.

    [!INCLUDE [preview-posting-inventory](includes/preview-posting-inventory.md)]

### To view posted physical inventory orders

After posting, the physical inventory order is deleted and you can view and evaluate the document as a posted physical inventory order. The posted order includes its physical inventory recordings and any comments made.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Posted Phys. Invt. Orders**, and then choose the related link.
2. On the **Posted Phys. Invt. Orders** page, select the posted inventory order to view, and then choose the **View** action.
3. On the **Related** tab, choose **Order**, and then choose the **Recordings** action to view a list of related physical inventory recordings.  

## Handle item tracking when counting inventory

Item tracking relates to the serial or lot numbers that are assigned to items. When you count an item that's stored in inventory as, for example, 10 different lot numbers, employee must be able to record which and how many units of each lot number are on inventory. To learn more, go to [Work with Serial and Lot Numbers](inventory-how-work-item-tracking.md).

The **Use Item Tracking** checkbox on physical inventory order lines is automatically selected if an item tracking code is set up for the item. You can select or clear the checkbox manually.

### Example - Prepare a physical inventory recording for an item-tracked item

Consider a physical inventory for Item A, which is stored in inventory as ten different serial numbers.

1. On the recording line for the item, select the **Use Item Tracking** checkbox.
2. Choose the **Serial No.** field, select the first serial number that exists in inventory for the item, and then choose the **OK** button.

    Copy the line for the first item-tracked item to insert additional lines that correspond to the number of serial numbers that are stored in inventory.

3. Choose the **Functions** action, and then choose **Copy Line**.
4. On the **Copy Phys. Invt. Rec. Line** page, enter **9** in the **No. of Copies** field, and then choose the **OK** button.
5. On the first line, in the **Serial No.** field, select the next serial number for the item.
6. Repeat step 5 for the remaining eight serial numbers. Be sure you don't select the same number twice.
7. Choose the **Print** action to prepare the print-out that employees use to write down the counted items and serial/lot numbers.

Notice that the **Phys. Invt. Recording** report contains ten lines for Item A, one for each serial number.

### Example - Record and post counted lot number differences

A lot-tracked item is stored in inventory with the "LOT" number series.

**Expected Inventory**:

|Lot No.|Quantity|
|-|-|
|LOT1001|80|
|LOT1003|30|
|LOT1006|10|
|Total|120|

**Recorded Quantities**:

|Lot No.|Quantity|
|-|-|
|LOT1001|80|
|LOT0002|12|
|LOT1003|20|
|LOT1006|10|
|Total|112|

**Quantities to Post**:

|Lot No.|Expected Quantity|Recorded Quantity|Quantity to Post|
|-|-|-|-|
|LOT1001|80|80|0|
|LOT1002|0|12|+12|
|LOT1003|30|20|-10|
|LOT1006|10|0|-10|
|Total|120|112|-8|

On the **Physical Inventory Order** page, the **Neg. Qty. (Base)** field contains **8**. For the order line, the **Phys. Invt. Item Track. List** page shows the positive or negative quantities for each lot number.

## Inventory documents

The following types of documents are useful for managing your warehouse:

* Use **inventory receipts** to register positive adjustments of items based on the quality, quantity, and cost.
* Use **inventory shipments** to write off missing or damaged goods.

You can print these documents at any stage, release, and reopen them, and assign common values such as dimensions in the header. To reprint the documents after they're posted, use the **Posted Inventory Receipt** and **Posted Inventory Shipment** pages.

> [!NOTE]
> Before you can use these documents, you must specify a number series to create their identifiers. To learn more, go to [To set up numbering for inventory documents](#to-set-up-numbering-for-inventory-documents).

### To set up numbering for inventory documents

The following procedure shows how to set up numbering for inventory documents.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Inventory Setup**, and then choose the related link.
2. On the **Numbering** FastTab, specify in the following fields the series of numbers for documents:

   - **Invt. Receipt Nos.**  
   - **Posted Invt. Receipt Nos.**  
   - **Invt. Shipment Nos.**  
   - **Posted Invt. Shipment Nos.**  

### To create and post an inventory document

The following procedure shows how to create, print, and post an inventory receipt. The steps are similar for inventory shipments.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Inventory Receipts**, and then choose the related link.  
2. In the header of the **Invt. Receipt** page, choose the location in the **Location Code** field, and then fill in the remaining fields as necessary.
3. On the **Lines** FastTab, in the **Item** field, choose the inventory item. In the **Quantity** field, enter the number of items to add.
4. To print an **Inventory Receipt** report from the **Invt. Receipt** page, choose the **Print** action.

The following functions are available on the **Invt. Receipt** page:

- Choose the **Release** or **Reopen** actions to set the status for the next processing stage.  
- Choose the **Post** action to post the inventory receipt, or choose **Post and Print** to post the receipt and print the test report.  

    [!INCLUDE [preview-posting-inventory](includes/preview-posting-inventory.md)]

## Printing inventory documents

You can specify the reports that must be printed at different stages by choosing one of the following options in the **Usage** field the **Report Selection - Inventory** page:

* Inventory Receipt
* Inventory Shipment
* Posted Inventory Receipt
* Posted Inventory Shipment

> [!NOTE]
> The available reports might vary based on the localization for your country/region. The base application doesn't include any layouts.

## Related information

[Count, Adjust, and Reclassify Inventory Using Journals](inventory-how-count-adjust-reclassify.md)    
[Work with Serial and Lot Numbers](inventory-how-work-item-tracking.md)    
[Inventory](inventory-manage-inventory.md)    
[Warehouse Management Overview](design-details-warehouse-management.md)    
[Sales](sales-manage-sales.md)    
[Purchasing](purchasing-manage-purchasing.md)    
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
