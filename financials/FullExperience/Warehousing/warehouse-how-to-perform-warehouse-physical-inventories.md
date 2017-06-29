---
    title: Insert topic title| Microsoft Docs
    description: Insert description
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
# How to: Perform Warehouse Physical Inventories
At least once in every fiscal year, you must take a physical inventory to see if the quantity registered is the same as the physical quantity in stock. If there are differences, you must post them to the item accounts before you do an inventory valuation. You also post your results to the physical inventory ledger, to record that you have counted a particular item on a particular date.  
  
 If you are not using directed put-away and pick for a location, you perform a physical inventory using the Phys. Inventory Journal. For more information, see [How to: Perform a Physical Inventory](../how-to-perform-a-physical-inventory.md). If you are using directed put-away and pick, you use the Whse. Phys. Inventory Journal, and later on, the Phys. Inventory Journal. This process is described here. In warehouses with bins, the counting is performed and registered bin by bin.  
  
### To perform a warehouse physical inventory  
  
1.  In the **Search** box, enter **Item Journal**, and choose the related link.  
  
2.  On the **Actions** tab, in the **Functions** group, choose **Calculate Whse. Adjustment**.  
  
3.  Fill in the batch job request window with the numbers of the items you want to count and with your location. Choose the **OK** button, and post the adjustments if any. If you do not do this before you perform the warehouse physical inventory, the results you post to the physical inventory journal and item ledger in the second part of the process will be the physical inventory results combined with other warehouse adjustments for the items that were counted.  
  
4.  In the **Search** box, enter **Whse. Phys. Invt. Journal**, and choose the related link.  
  
5.  In the journal, on the **Actions** tab, in the **Functions** group, choose **Calculate Inventory**. The **Whse. Calculate Inventory** batch job request window opens.  
  
6.  Set the filters to limit the items that will be counted in the journal, and then choose the **OK** button. The program creates a line for each bin that fulfills the filter requirements. You can at this point still delete some of the lines, but if you want to post the results as a physical inventory, you must count the item in all the bins that contain it.  
  
     If you only have time to count the item in some bins and not others, you can discover discrepancies, register them, and later post them in the item journal using the **Calculate Whse. Adjustment** function.  
  
7.  In the **Search** box, enter **Whse. Phys. Inventory List**, and choose the related link.  
  
8.  Open the ![Shortcut icon](../media/shortcutcoldicon.gif "shortcutColdIcon") report request page and print the lists on which you want employees to record the quantity of items that they count in each bin.  
  
9. When the counting is done, enter the counted quantities in the **Qty. \(Phys. Inventory\)** field in the warehouse physical inventory journal.  
  
    > [!NOTE]  
    >  In the warehouse physical inventory journal, **Qty. \(Calculated\)** field is filled in automatically on the basis of warehouse bin records and copies these quantities are copied to the **Qty. \(Physical\)** field on each line. If the quantity counted by the warehouse employee differs from what the program has entered in the Qty. \(Physical\) field, you must enter the quantity actually counted.  
  
10. When you have entered all the counted quantities, register the journal. On the **Actions** tab, in the Registering group, choose **Register**.  
  
     When you register the journal, the program creates two warehouse entries in the warehouse register for every line that was counted and registered:  
  
    -   If the calculated and the physical quantities differ, a negative or positive quantity is registered for the bin, and a balancing quantity is posted to the adjustment bin of the location.  
  
    -   If the quantity calculated is equal to the physical quantity, the program registers an entry of 0 for both the bin and the adjustment bin. The entries are the record that on the registering date, a warehouse physical inventory was performed, and there was no discrepancy in inventory for the item.  
  
 When you register the warehouse physical inventory, you are not posting to the item ledger, the physical inventory ledger, or the value ledger, but the records are there for immediate reconciliation whenever necessary. If you like to keep precise records of what is happening in the warehouse, however, and you counted all of the bins where the items were registered, you should immediately post the warehouse results as an inventory physical inventory. For more information, see [How to: Perform a Physical Inventory](../how-to-perform-a-physical-inventory.md).  
  
### To post warehouse results as a physical inventory  
  
1.  In the **Search** box, enter **Phys. Inventory Journal**, and choose the related link.  
  
2.  On the **Actions** tab, in the **Functions** group, choose **Calculate Inventory**.  
  
3.  Select the same items that you counted in the warehouse physical inventory, and choose the **OK** button.  
  
4.  The lines are created in the **Phys. Inventory Journal** window for these items. Note that the **Qty. \(Phys. Inventory\)** field is filled with the sum of the quantities you counted and registered for the item bin by bin in the Whse. Phys. Invt. Journal, and  the **Quantity** field has been calculated.  
  
5.  Post the journal without changing any quantities.  
  
 The quantities in the item ledger \(item entries\) and the quantities in the warehouse \(warehouse entries\) are now once again the same for these items, and a full physical inventory has been performed for the item.  
  
> [!NOTE]  
>  Only an employee with permissions in the Inventory area can update the item ledger and physical inventory ledger with the results of the warehouse physical inventory.  
  
## See Also  
 [How to: Perform a Physical Inventory](../how-to-perform-a-physical-inventory.md)   
 [How to: Set Up Physical Inventory Counting Periods](../how-to-set-up-physical-inventory-counting-periods.md)   
 [Count, Adjust, and Reclassify Inventory](../count-adjust-and-reclassify-inventory.md)   
 [Design Details: Integration with Inventory](../design-details-integration-with-inventory.md)