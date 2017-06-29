---
title: "How to: Restructure Warehouses"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "bins, changing codes on records"
  - "warehouse management, setting up"
  - "restructuring warehouses"
  - "warehouse management, restructuring"
  - "bins, deleting"
  - "bins, renaming"
ms.assetid: b349049f-01d9-4e0c-8fac-e8f255febfd0
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
# How to: Restructure Warehouses
You may want to restructure your warehouse with new bin codes and new bin characteristics.  
  
 You will not undertake this kind of activity very often, but situations can occur where a reclassification is necessary to achieve or maintain a more efficient operation. For example:  
  
1.  You might want to switch to bin codes that support the use of automatic data capture, for example, with hand\-held devices.  
  
2.  The warehouse may have purchased a new rack system that gives new possibilities in item storage.  
  
3.  The company may have altered its item assortment and moved the warehouse to a new physical location to accommodate this change.  
  
 If your warehouse is set up to use bins but not directed put\-away and pick, restructure your warehouse by creating the new bins that you want to use in the future.  
  
### To restructure a basic warehouse that uses bins only  
  
1.  In the **Search** box, enter **Locations**, and then choose the related link.  
  
2.  On the **Warehouse** FastTab, set the **Default Bin Selection** field to **Last\-Used Bin**.  
  
3.  Move all the contents of your current bins to the new bins that you have just created.  
  
    1.  In the **Search** box, enter **Item Reclassification Journal**, and then choose the related link.  
  
    2.  Select a journal line, and then, on the **Actions** tab, in the **Functions** group, choose **Get Bin Content**.  
  
    3.  On the **Bin Content** FastTab, set filters in the **Location Code**, **Bin Code**, and **Item No.** fields to specify the content that you want to move.  
  
    4.  Choose the **OK** button to fill a journal line.  
  
    5.  In the **New Bin Code** field, select the bin to which the items should be moved.  
  
    6.  Repeat steps b through e for all bin content that you want to move.  
  
    7.  On the **Actions** tab, in the **Posting** group, choose **Post**.  
  
 You have now emptied the bins where the items used to be. The default bins for your items have now been changed to the new bins.  
  
### To restructure an advanced warehouse that uses directed put\-away and pick  
  
1.  Create the new bins that you want to use in the future. For more information, see [How to: Create Bins in the Bin Creation Worksheet](../WarehouseActivities/how-to-create-bins-in-the-bin-creation-worksheet.md).  
  
2.  Move all the contents of your current bins to the new bins that you just created.  
  
    1.  In the **Search** box, enter **Warehouse Reclassification Journal**, and then choose the related link.  
  
    2.  For the bins where no real movement of items is involved, create a line for each of your current bins in the **Warehouse Reclassification Journal** with the old bin code, **From Bin Code**, and the new bin code, **To Bin Code**.  
  
    3.  If some of the movements involve actual physical movements that you want employees to perform, use **Movement Worksheets** to prepare movement instructions instead of using the warehouse reclassification journal. For more information, see [How to: Move Items in Advanced Warehousing](../WarehouseActivities/how-to-move-items-in-advanced-warehousing.md).  
  
3.  When the old bins are emptied, reclassify them as **QC** type bins to ensure that they are not included in item flows.  
  
    1.  In the **Search** box, enter **Locations**, and then choose the related link.  
  
    2.  Select the line with the location, and then, on the **Navigate** tab, choose **Bins**.  
  
    3.  In the **Bins** window, in the **Bin Type Code** field, enter **QC** for each of the old bins that you emptied in step 3 in the previous procedure.  
  
 You have now removed the bins from the warehouse flow, and reclassified them as QC bins. QC bins have none of the activity fields in the **Bin Types** window selected and are therefore not considered by the item flow. For more information, see [How to: Set Up Bin Types](../WarehouseActivities/how-to-set-up-bin-types.md).  
  
### To delete a bin  
  
1.  In the **Search** box, enter **Locations**, and then choose the related link.  
  
2.  Select the location where you want to delete bins. On the **Navigate** tab, in the **Location** group, choose **Bins.**  
  
3.  Select the lines for the bins that you want to delete.  
  
4.  On the **Home** tab, in the **Manage** group, choose **Delete**.  
  
     If you choose the **Yes** button, the bin is deleted for use in the future, but the bin code in all warehouse entries remains the same.  
  
 If you want to rename a bin so that all records associated with the bin are also renamed, including bin contents, warehouse activity lines, registered warehouse activity lines, warehouse worksheet lines, warehouse receipt lines, posted warehouse receipt lines, warehouse shipment lines, posted warehouse shipment lines, and warehouse entries, you can do so in the **Bins** window.  
  
### To rename a bin and change the bin code in all records  
  
1.  In the **Search** box, enter **Locations**, and then choose the related link.  
  
2.  Select the location where you want to rename a bin or change the bin code, and on the **Navigate** tab, in the **Location** group, choose **Bins.**  
  
3.  Select the bin that you want to change and enter a new bin code in the **Code** field.  
  
4.  Choose the **Yes** button.  
  
> [!NOTE]  
>  If you choose **Yes** and there are many entries concerning this bin, for example, because you have not deleted warehouse documents for some time, it may take some time to rename all the records. Therefore, if you use this method, consider running the batch job **Delete Registered Whse. Documents** before you start the renaming process. Also note that the only documents that are deleted in this batch job are put\-aways, picks, and movements.  
>   
>  If you are renaming a receiving bin or a shipping bin, all the posted receipts or shipments that refer to the bin in question are renamed.  
  
## See Also  
 [How to: Set Up Locations to Use Bins](../WarehouseActivities/how-to-set-up-locations-to-use-bins.md)   
 [How to: Set Up Warehouses for Directed Put\-away and Pick](../WarehouseActivities/how-to-set-up-warehouses-for-directed-put-away-and-pick.md)   
 [How to: Set Up Warehouse Management](../WarehouseActivities/how-to-set-up-warehouse-management.md)   
 Bin Content   
 [How to: Set Up Bin Contents](../WarehouseActivities/how-to-set-up-bin-contents.md)   
 [How to: Delete Registered Warehouse Documents](../WarehouseActivities/how-to-delete-registered-warehouse-documents.md)   
 [Design Details: Warehouse Management](../ApplicationDesign/design-details-warehouse-management.md)   
 [Configure Warehouse Processes](../WarehouseActivities/configure-warehouse-processes.md)