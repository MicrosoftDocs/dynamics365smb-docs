---
    title: How to Perform a Physical Inventory | Microsoft Docs
    description: You must take a physical inventory, that is, count the actual items on hand, to check if the quantity registered is the same as the physical quantity in stock at the end of a fiscal year, if not more often. If there are differences, you must post them to the item accounts before you do the inventory valuation.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# How to: Perform a Physical Inventory
You must take a physical inventory, that is, count the actual items on hand, to check if the quantity registered is the same as the physical quantity in stock at the end of a fiscal year, if not more often. If there are differences, you must post them to the item accounts before you do the inventory valuation.  
  
> [!IMPORTANT]  
>  This topic describes how to perform a physical inventory in a non-directed warehouse setup. For information on how to perform it in a warehouse setup with directed put-away and pick, see [How to: Perform Warehouse Physical Inventories](../how-to-perform-warehouse-physical-inventories.md).  
  
 Apart from the physical counting task, the complete process involves the following three tasks:  
  
-   Calculate the expected inventory.  
  
-   Print the report to be used when counting.  
  
-   Enter and post the actual counted inventory.  
  
### To calculate the expected inventory  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Phys. Inventory Journal**, and then choose the related link.  
  
2.  On the **Actions** tab, in the **Functions** group, choose **Calculate Inventory**.  
  
3.  In the **Calculate Inventory** window, on the **Options** FastTab, specify the conditions to use to create the journal lines, such as whether to include items that have zero recorded inventory.  
  
4.  Set filters if you only want to calculate inventory for certain items, bins, locations, or dimensions.  
  
5.  Choose the **OK** button.  
  
> [!NOTE]  
>  The item entries are processed according to the information that you specified, and lines are created in the physical inventory journal. Notice that the **Qty. (Phys. Inventory)** field is automatically filled in with the same quantity as the **Qty. (Calculated)** field. With this feature, it is not necessary for you to enter the counted inventory on hand for items that are the same as the calculated quantity. However, if the quantity counted differs from what is entered in the **Qty. (Calculated)** field, you must overwrite it with the quantity actually counted.  
  
### To print the report used when counting  
  
1.  In the  **Phys. Inventory Journal** window containing the calculated expected inventory, on the **Actions** tab, in the **General** group, choose **Print**.  
  
2.  In the **Phys. Inventory List** window, on the **Options** FastTab, specify if the report should show the calculated quantity and if the report should list inventory items by serial/lot numbers.  
  
     For more information, see Phys. Inventory Journal.  
  
3.  On the **Item Journal Batch** FastTab, set filters if you only want to print the report for certain items, bins, locations, or dimensions.  
  
4.  Choose the **Print** button.  
  
 Employees can now proceed to count inventory and record any discrepancies on the printed report.  
  
### To enter and post the actual counted inventory  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Phys. Inventory Journal**, and then choose the related link.  
  
2.  On each line where the actual inventory on hand, as determined by the physical count, differs from the calculated quantity, enter the actual inventory on hand in the **Qty. (Phys. Inventory)** field.  
  
     The related fields are updated accordingly.  
  
    > [!NOTE]  
    >  If the physical count reveals differences that are caused by items posted with incorrect location codes, do not enter the differences in the physical inventory journal. Instead, use the reclassification journal or a transfer order to redirect the items to the correct locations. For more information, see Item Reclass. Journal or [How to: Create Transfer Orders](../how-to-create-transfer-orders.md).  
  
3.  To adjust the calculated quantities to the actual counted quantities, on the **Actions** tab, in the **Posting** group, choose **Post**.  
  
     Both item ledger entries and physical inventory ledger entries are created. Open the item card to view the resulting physical inventory ledger entries.  
  
4.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Items**, and then choose the related link.  
  
5.  Open the item card in question, and then, on the **Navigate** tab, in the **Item** group, choose **Phys. Inventory ledger Entries**.  
  
## See Also  
 Phys. Inventory Journal   
 [How to: Perform Warehouse Physical Inventories](../how-to-perform-warehouse-physical-inventories.md)   
 [Design Details: Integration with Inventory](../../design-details-integration-with-inventory.md)