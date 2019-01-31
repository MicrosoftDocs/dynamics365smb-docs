---
title: Count Inventory With Document-Based Functionality| Microsoft Docs
description: Describes how to perform physical counting using the Physical Order Inventory and Physical Inventory Recording pages.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: adjustment, negative, positive, increase, decrease
ms.date: 01/31/2019
ms.author: sgroespe

---
# Count Inventory Using Documents
You can take a physical inventory of your items using the physical inventory order and the physical inventory recording documents. The **Physical Inventory Order** page is used to organize the complete inventory counting project, for example one per location. The **Physical Inventory Recording** page is used by to perform the actual counting of items. You can create multiple recordings for one order, for example to distribute groups of items to different employees. The **Physical Inventory Recording** report is printed from each recording and contains empty quantity fields for entering the counted inventory. When a user is done counting, and the quantities are entered on the **Physical Inventory Recoding** page, they choose the **Finish** action. This transfers the quantities to the related lines on the **Physical Inventory Order** page. Functionality ensures that no item count can be recorded twice.      

> [!NOTE]
> This procedure describes how to perform a physical inventory using documents, a method that provides more control and supports distributing the counting to multiple employees. You can also perform the task by using journals, the **Phys. Inventory Journals** and **Whse. Phys. Inventory Journals** pages. For more information, see [Count, Adjust, and Reclassify Inventory Using Journals](inventory-how-count-adjust-reclassify.md).<br /><br />
> Note that if you have locations set up with bins, you must use the **Whse. Phys. Inventory Journal** page to count your warehouse entries before synchronizing them with item ledger entries.

Counting your inventory by using documents consist of the following overall steps:
1. Create a physical inventory order with expected item quantities prefilled.
2. Generate one or more physical inventory recordings from the order.
3. Enter the counted item quantities on the recordings, as captured on print-outs, for example, and set it to **Finished**.
4. Complete and post the physical inventory order.

## To create a physical inventory order
A physical inventory order is a complete document that consists of a physical inventory order header and some physical inventory order lines. The information on a physical inventory header describes how to take the physical inventory. The physical inventory order lines contain the information about the items and their locations. To create the physical inventory order lines, you typically use the **Calculate Lines** function to reflect the current inventory as lines on the order. Alternatively, you can use the **Copy Document** function to fill the lines with the content of another open or posted physical inventory order.

The following procedure only describes how to use the **Calculate Lines** function.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Physical Inventory Orders**, and then choose the related link.
2. Choose the **New** action.
3. Fill in the required fields on the **General** FastTab. [!INCLUDE [tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Choose the **Calculate Lines** action.
5. Select options as necessary.
6. Set filters, for example, to only include a subset of items to be counted with the first recording.

    > [!TIP]
    > To plan for multiple employees to count the inventory, it is advisable to set different filters each time you use the **Calculate Lines** action and in between creating each physical inventory recording. For more information, see the "To create a physical inventory recording" section.

6.  Choose the **OK** button.

A line for each item that exists on the chosen location and per the set filters and options is inserted on the order. You can now proceed to create one or more recordings, which are instructions to the employees who perform the actual counting.  

## To create a physical inventory recording
For each physical inventory order, you can create one or more physical inventory recording documents on which you enter the counted quantities, either manually or through an integrated scanning device.

By default, a recording is created for all the lines on the related physical inventory order. To avoid that two employees count the same items in case of distributed counting, it is advisable to gradually fill the physical inventory order by setting filters on the **Calculate Lines** batch job (see the "To create a physical inventory order" section) and then create the physical inventory recording while selecting the **Only Lines Not in Recordings** check box. This settings makes sure that each new recording that you create only contains different items than the ones on other recordings.

In case of manual counting, you can print a list, the **Phys. Inventory Recording** report, which has an empty column in which employees write the counted quantities. You then enter the values on the related lines on the **Phys. Inventory Recording** page. Lastly, you transfer the counted quantities to the related physical inventory order by setting the status to **Finished**.

1. On a **Physical Inventory Order** page that contains lines for the items to be counted in one recording, choose the **Make New Recording** action.
2. Select options and set filters as necessary.
3. Choose the **OK** button.
4. For every set of items to be counted, load them on the related physical inventory order and repeat steps 1 through 3 with the **Only Lines Not in Recordings** check box selected.

    A physical inventory recording document is created.
5. Choose the **Recordings** action to see it on the **Phys. Inventory Recording List** page.
6. Choose the **Print** action to prepare the physical documents that employees will use to write down the counted quantities.

## To complete a physical Inventory recording
When employees have counted and written down the inventory quantities, you must prepare to record them in the system.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Physical Inventory Recordings**, and then choose the related link.
2. Select the physical inventory recording that you want to complete, and then choose the **Edit** action.
3. On the **General** FastTab, fill in the fields as necessary.
4. On the **Lines** FastTab, fill the actual counted quantity in the **Quantity** field for each line.
5. For items with serial or not numbers, select the **Use Item Tracking** check box, to enable that the counted quantities are entered in the **Serial No.** and **Lot No.** fields respectively.
6. Select the **Recorded** check box for each line.
7. When you have entered all data for a physical inventory recording, choose the **Finish** action. Note that all lines must have the **Recorded** checkbox selected.

The physical inventory recording lines are transferred to the related physical inventory order.

> [!NOTE]
> When you finish a physical inventory recording, each line is transferred to the line on the related physical inventory order that matches it exactly. To match, the values in the **Item No.**, **Variant Code**, **Location Code**, and **Bin Code** fields must be the same on the recording and the order lines.<br /><br />

> If no matching physical inventory order line exists, and if the **Allow Recording Without Order** checkbox is selected, then a new line is inserted automatically and the **Recorded Without Order** checkbox on the related physical inventory order line is selected. Otherwise, an error message is displayed and the process is canceled.<br /><br />

> If more than one physical inventory recording lines match a physical inventory order line, then a message is displayed and the process is canceled. If, for some reason, two identical physical inventory lines end up on the physical inventory order, you can use a function to resolve it. For more information, see the "To find duplicate physical inventory order lines" section.

## To find duplicate physical inventory order lines
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Physical Inventory Orders**, and then choose the related link.
2. Open the physical inventory order that you want to view to duplicate lines for.
3. Choose the **Show Duplicate Lines** action.

Any duplicate physical inventory order lines are displayed, so that you can delete them and keep only one line with a unique set of values in the **Item No.**, **Variant Code**, **Location Code**, and **Bin Code** fields.

## To post a physical inventory order
After completing a physical inventory order and changing its status to **Finished**, you can post it. You can set the status of a physical inventory order to **Finished** if the following are true:

- All related physical inventory recordings have a status of **Finished**.
- Each physical inventory order line has been counted by at least one inventory recording line.
- The **In Recording Lines** and the **Qty. Exp. Calculated** check boxes have been selected for all of the physical inventory order lines.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Physical Inventory Orders**, and then choose the related link.
2. Select the physical inventory order that you want to complete, and then choose the **Edit** action.

    On the **Physical Inventory Order** page, you can view the quantity recorded after taking physical inventory in the **Qty. Recorded (Base)** field.
4. Choose the **Finish** action.

The value in the Status field is changed to **Finished**, and you can now only change the order by first choosing the **Reopen** action.
5. To post the order, choose the **Post** action, and then choose the **OK** button.

## To view posted physical inventory orders
After posting, the physical inventory order will be deleted and you can view and evaluate the document as a posted physical inventory order including its physical inventory recordings and any comments made.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Posted Phys. Invt. Orders**, and then choose the related link.
2. In the **Posted Phys. Invt. Orders** window, select the posted inventory order that you want to view, and then choose the **View** action.
3. To view a list of related physical inventory recordings, choose the **Recordings** action.

You can also choose the **Phys. Inventory Order Diff.** action  to view any differences between the expected quantity and the quantity actually counted (recorded).

## See Also
[Count, Adjust, and Reclassify Inventory Using Journals](inventory-how-count-adjust-reclassify.md)  
[Inventory](inventory-manage-inventory.md)
[Warehouse Management](warehouse-manage-warehouse.md)    
[Sales](sales-manage-sales.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
