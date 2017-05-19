---
title: "How to: Perform Cycle Counting"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "cycle counting, without directed pick and put-away"
  - "inventory, counting"
  - "counting, calculating periods"
  - "physical inventory, cycle counting"
  - "directed put-away and pick, posting counted quantities"
  - "cycle counting, with directed pick and put-away"
ms.assetid: e19afc9a-6abd-4493-8c1c-d5c1b48e10d5
caps.latest.revision: 10
ms.author: "sgroespe"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-nz"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# How to: Perform Cycle Counting
Although you count all items in inventory at least once a year, you may have decided to count some items more often, perhaps because they are more valuable, or because they are very fast movers and a large part of your business.  
  
 Before you begin cycle counting, you must set up and assign physical inventory counting periods. For more information, see [How to: Set Up Physical Inventory Counting Periods](../WarehouseActivities/how-to-set-up-physical-inventory-counting-periods.md).  
  
 You can perform the cycle counting in either of the following ways depending on your warehouse setup:  
  
-   If your location is not using directed put\-away and pick, you use the **Phys. Inventory Journal** window in the **Inventory** menu, and the procedure is much the same as when you conduct a physical inventory without cycle counting.  
  
-   If your location is using directed put\-away and pick, you first use the **Whse. Phys. Invt. Journal** window, and then you use the **Item Journal** window to run the **Calculate Whse. Adjustment** function.  
  
### To perform cycle counting without directed put\-away and pick  
  
1.  In the **Search** box, enter **\($ N\_392 Phys. Inventory Journal $\)**, and choose the related link.  
  
2.  On the **Actions** tab, in the **Functions** group, choose **Calculate Counting Period**. The **Phys. Invt. Item Selection** window opens, which contains the items for which counting periods have been established that need to be counted, according to their counting periods.  
  
    > [!NOTE]  
    >  You can also keep track of stockkeeping units using cycle counting.  
  
3.  Select the items that warehouse employees have time to count on this work date. On another date, you can calculate counting periods again, and the items that you do not select now will be included in that calculation.  
  
4.  Choose the **OK** button, and the selected lines now appear in the **Phys. Inventory Journal** window.  
  
5.  In the **Search** box, enter **\($ R\_722 Phys. Inventory List $\)**, and choose the related link.  
  
6.  Open the report request page and print the report, and count all the items in the warehouse with the item numbers on the report lines.  
  
7.  Enter the quantities counted in the **Qty. \(Phys. Inventory\)** field.  
  
8.  Post the results of the physical inventory. The program creates item ledger entries for the items where adjustment is necessary and physical inventory ledger entries for all the items for which you have performed the cycle count. If you are using bins, the program also creates warehouse entries for the items for which an adjustment is necessary.  
  
### To perform cycle counting with directed put\-away and pick  
  
1.  In the **Search** box, enter **\($ N\_7326 Whse. Phys. Invt. Journal $\)**, and choose the related link.  
  
2.  On the **Actions** tab, in the **Functions** group, choose **Counting Period**. The **Phys. Invt. Item Selection** window opens, containing the items or stockkeeping units for which counting periods have been established that need to be counted according to their counting periods.  
  
3.  Select the items or stockkeeping units that you want to count and choose the **OK** button.  
  
4.  The program has created lines for each bin that contains the items in the journal.  
  
    > [!NOTE]  
    >  You must count the item in all the bins that contain the particular item. If you delete some of the bin lines that the program has retrieved for counting in the **Whse. Phys. Inventory** window, then you will not be counting all the items in the warehouse. If you later post such incomplete results in the Phys. Inventory Journal, the amounts posted will be incorrect.  
  
5.  Print the ![Shortcut icon](../BusinessFunctionality/OnlineMaps/media/shortcutcoldicon.gif "shortcutColdIcon")**[\($ R\_7307 Whse. Phys. Inventory List $\)](DynamicsNAV:////runreport?report=7307)** report without filtering out some of the lines.  
  
6.  Count the items and note the quantities on the report.  
  
7.  Enter the quantities that were counted in the **Qty. \(Phys. Inventory\)** field on each line.  
  
8.  On the **Actions** tab, in the **Registering** group, choose **Register** to complete the warehouse physical inventory.  
  
 When you have counted the item or stockkeeping unit in all the bins that contain it, you are ready to post the results in the item ledger and the physical inventory ledger.  
  
### To post the results with directed put\-away and pick  
  
1.  In the **Search** box, enter **Item Journal**, and choose the related link.  
  
2.  On the **Actions** tab, in the **Functions** group, choose **Calculate Whse. Adjustment**.  
  
3.  Select the same items that you counted in the cycle counting physical inventory you just performed, and any other items that require adjustment, and then choose the **OK** button.  
  
     The **Inventory Journal** window opens and lines are created for these items. Note that the net quantities that you just counted and registered bin by bin are now ready to be consolidated and synchronized as item ledger entries.  
  
4.  Post the journal without changing any quantities.  
  
 The quantities in the item ledger \(item entries\) and the quantities in the warehouse \(warehouse entries\) are now once again the same for these items, and the program has updated the last counting date of the item or stockkeeping unit.  
  
 For the items\/stockkeeping units that you have just counted, you must now calculate the next counting period on each item\/stockkeeping unit card.  
  
### To calculate the next counting period  
  
1.  In the **Search** box, enter **Items**.  
  
2.  Select the item card of each item for which you performed a cycle count.  
  
3.  On each card, on the **Actions** tab, in the **Functions** group, choose **Calculate Counting Period**.  
  
 The new counting period is calculated and the date of the counting period is updated in the **Last Counting Period Update** field on the **Warehouse** FastTab of the item card.  
  
> [!NOTE]  
>  If you update the item cards on the same day that you post the physical inventory, then this field contains the last counting date, corresponding to the value in the **Last Phys. Invt. Date** field. If you calculate the counting period later on, this field contains the date of the counting period update.  
  
 When you have done this, the lines for these items in the **Phys. Invt. Item Selection** window will not be brought up until the work date is within the next cycle counting period, as indicated on the item\/stockkeeping unit card.  
  
## See Also  
 [How to: Perform a Physical Inventory](../DesignAndEngineering/how-to-perform-a-physical-inventory.md)   
 [How to: Set Up Physical Inventory Counting Periods](../WarehouseActivities/how-to-set-up-physical-inventory-counting-periods.md)   
 [Count, Adjust, and Reclassify Inventory](../WarehouseActivities/count-adjust-and-reclassify-inventory.md)   
 [Design Details: Integration with Inventory](../ApplicationDesign/design-details-integration-with-inventory.md)