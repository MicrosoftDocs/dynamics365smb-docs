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
ms.date: 01/23/2019
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

> [!NOTE]
> When you finish the current physical inventory recording, every physical inventory recording line is assigned to one line of the related physical inventory order. The physical inventory order lines are assigned with the same values in the **Item No.**, **Variant Code**, **Location Code**, and **Bin Code** fields as the physical inventory recording line has.<br /><br />

> If no such physical inventory order line exists, and if the **Allow Recording Without Order** checkbox is selected, then a new line is inserted automatically and the **Recorded Without Order** checkbox on the related physical inventory order line is selected. Otherwise, an error message is displayed and the process is canceled. Also, if there are more than one such physical inventory order lines, an error message is displayed and the process is canceled.

## To finish a physical inventory order
After completing the physical inventory recordings and the physical inventory order, you can post the physical inventory order. The information is transferred to the physical inventory journal. After this transfer, the physical inventory order will be available as a posted physical inventory order for future retrieval.

## To view posted physical inventory documents  
After posting the physical inventory order will be deleted and you can view and evaluate the document as posted physical inventory order.  

When posting the physical inventory orders also physical inventory recording headers and physical inventory recording lines and physical inventory comment lines will be transferred to posted documents.  

The posted inventory documents offer you the possibility to get a complete overview about the whole process of physical inventory. You cannot change the data of posted physical inventory order headers and posted physical inventory order lines because the documents have been already posted.  

If you have used also item tracking lines to register serial nos. and lot nos. the program will save the expected item tracking lines, the recorded item tracking lines and the posted item tracking ledger entries.  

It is possible to use the posted physical inventory order to create new physical inventory orders using the copy function.  

You can use Navigate to view the inventory ledger entries and other related ledger entries for a posted physical inventory order.  

## See Also
[Inventory](inventory-manage-inventory.md)
[Warehouse Management](warehouse-manage-warehouse.md)    
[Sales](sales-manage-sales.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
